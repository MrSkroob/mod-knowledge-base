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