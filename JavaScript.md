[[Index]]
"But Skrubunger, you already know how to code in JavaScript"

Correct! I only know how the basic syntax and programming paradigms - nothing specific to JavaScript itself!

Heck, I didn't know that `this` is a clusterfuck. Apparently, in RPGMaker MV, you do:
```javascript

(function() {
	"use strict"
	this.blahblah // the "this" keyword refers to the window. 
}).call(window)
```
Window is a keyword in RPG Maker MV. 

Through that, you can access basically everything. This is how you modify and interact with the game world. Additionally, any keyword prefixed with `$` is provided by the game engine. Internally, they're initialised like this:
```javascript
window.$zero = 0
```
#### Monkey patching (examples)  (may or may not be related to the previous section)
If I wanted to create a plugin command, I do:
```javascript
// this ensures we BUILD upon the existing plugin command structure. 
const _Game_Interpreter_pluginCommand =
    Game_Interpreter.prototype.pluginCommand;
    
Game_Interpreter.prototype.PLUGIN_COMMAND = function(command, args) {
	if (command == "kill") {
		// do kill
	}
}
```
Or, alternatively:
```javascript
// create commands..
// make sure this line below is only done by one plugin.
// others can also do this, but please avoid having the same name - otherwise 
// you'll have plenty of headaches!
const PluginCommands = {};

PluginCommands.teleport = function(args) {
	// args are an array of strings, so we need to convert them to the types we need. 
    const x = Number(args[0]);
    const y = Number(args[1]);
    $gamePlayer.reserveTransfer($gameMap.mapId(), x, y);
}

// register commands...
// Similarly, please make sure only one plugin registers the "PluginCommands" 
// Record. 
const _cmd = Game_Interpreter.prototype.pluginCommand;

Game_Interpreter.prototype.pluginCommand = function(command, args) {
    _cmd.call(this, command, args);

    if (PluginCommands[command]) {
        PluginCommands[command].call(this, args);
    }
};
```
Then, in future, other plugins can:
```javascript
// Plugin B adds a new command without any potential jank of overriding certain 
// commands.
MyPluginCommands.spawnEnemy = function(args) {
    const enemyId = Number(args[0]);
    const x = Number(args[1]);
    const y = Number(args[2]);
    $gameMap.addEvent({ enemyId, x, y });
};
```
#### Monkey patching template:
```js
const _thingToPatch = ClassName.prototype.methodToPatch;

ClassName.prototype.methodToPatch = function(args) {
	_thingToPatch.call(this, args);
	
	// do own logic.
}
```
#### Shaders
Note that PIXI.js uses an extremely old version of glsl, (pre 3.0.0). Here's a glsl code snippet to give you the absolute essentials (and avoid common pitfalls).

```c
// provided by default:
// tells GPU what precision floats should be
precision mediump float;
varying vec2 vTextureCoord;
uniform sampler2D uSampler;

// must have this:
uniform mat3 mappedMatrix;

// example variable to be used:
// uniform is basically any variable that will be supplied by the CPU
uniform vec3 tint;

// main function to be called per loop:
// this runs for every pixel on your screen:
void main(void) {
	/* this is very important:
	if you do anything involving pixel manipulation, you must use
	map because with this specific version of PIXI.js, vTextureCoord acts
	weirdly on screens - please don't ask me to elaborate, it's too much trauma.
	*/
	vec3 map = vec3(vTextureCoord.xy, 1) * mappedMatrix;
	vec2 mapConversion = map.xy
	
	// get color of pixel 
	vec4 color = texture2D(uSampler, vTextureCoord);
	vec3 base = color.rgb * tint;
	
	// apply colour to screen:
	gl_FragColor = vec4(base, color.a);
}
```

this is then fed into:
```js
let uniforms = {};
uniforms.tint = {type: 'vec3', value: [0.5, 0.5, 0.5]}

// fragment contains the string of the glsl snippet that we've provided earlier. 
let filter = new PIXI.Filter(null, fragment, uniforms);


```