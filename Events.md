##### Prerequisites:
1. [[Map making]]
#### Steps:
1. Open RPG Maker
2. There are two types of events you can make: Common Events & Regular Events. Both apply here with minor differences:
	1. For Common Events the way to create them is by:
	2. ![[Pasted image 20260314005233.png]]
	3. ![[Pasted image 20260314005306.png]]
3. Double click on any space. As an example, I've clicked on "Snowcone Jash": ![[Pasted image 20260314002930.png]]
4. Fill out the green section.
	1. Click the checkboxes for conditions that you want to be applied. 
	2. `Switch`:
		1. A statement that must be true: ![[Pasted image 20260314002313.png]]
		2. For example, if you chose "0002", then the flag "Picnic?" must be true for the event to occur. 
	3. `Variable` basically means (in javascript terms):
		1. `if (variable >= x) { doEvent() }`
		2. The value we're comparing to can only be a number, so the variable can't be a string. So something like "0001 PLAYER Name" won't work.
	4. `Item` is... the item needed (like Kel's pet rock). This does not include equipment.
	5. `Actor` is the party member required (so events that need Basil would need Basil filled out here.)
5. Fill out the yellow section.
	1. Most here are pretty self explanatory. However...
	2. Priority tells the event what layer it is on to be triggered (if it's activated via touch or key press)
	3. Options:
		1. `Walking` (walking animation playing when walking?)
		2. `Stepping` (walking animation playing even when standing still?)
		3. `Direction Fix` (always face the same direction?)
		4. `Through` (can walk through objects?)
6. Fill out the red section.
	1. This is basically a scripting window - controls what happens when that event occurs. You can call event methods through here, so any complex logic can be handled in an external `.js` file instead. 
	2. ...because this is mostly written for me (Skrubunger) and I understand most of this... don't expect me to tell you what this stuff does HAHAHAHAHAHAHA!!
	   That said, there's one thing I want to point out:
		1. Scripts:
			1. Scripts are basically short few lines that are javascript. That's it. Vanilla RPG Maker MV allows 12 lines at most. Any more and you should write a plugin and call that instead. 
		2. Plugin command:
			1. Syntax: `function arg0`
			2. The args will always be passed as strings.
7. Events can have multiple tabs:![[Pasted image 20260314011311.png]]
	1. The game goes through them in reverse order (3 -> 2 -> 1).
	2. It acts like a switch-case. So if page 3 has its conditions fulfilled, it'll execute page 3. If not, check page 2, etc.
	3. After executing a page, it will not check the rest of the pages.
Next, take a look at:
[[Creating Messages]]

