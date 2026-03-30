[[Index]]
#### Prerequisites:
1. [[Events]]
#### Steps:
1. You know the drill. Navigate to:![[Pasted image 20260314013208.png]]
2. Create a new (or edit) `.yaml` file. Please try and make it sensible. Let's say we name ours "test.yaml"
3. Basic syntax:
```yaml
# This is a comment!

this_is_a_node:
   this_is_a_property: this is a value!
```
4. Naming conventions:
```yaml
message_xx:
	faceset: MainCharacters_Faraway # the group of faces to choose from
	faceindex: 0 # which face to use
	text: IT'S PIZZA TIME! 
	# ^^the message to send
```
5. Go to an event you've made and add a Plugin Command:
`ShowMessage test.message_xx`
6. Basic formatting:
	1. `\Com[x]`
		1. Calls a Common Event with the number `x`.
		2. E.g:
			1. `\Com[2]` shakes the screen
	2. `\sinv[1]` and `\sinv[2]`
		1. Sine waves the text.
	3. `\|`
		1. Pauses for 60 frames.
	4. `\!`
		1. Wait for user input.
	5. \fr
		1. Resets the font. 
	6. **For extended YAML plugin only:**
		1. ```yaml
		   font: font_name_here
		   ```
7. In your event, create a Plugin Command:
	1. `ShowMessage YAML_FILE.message_xx`
	2. Tada!