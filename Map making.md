[[Index]]
#### Prerequisites:
1. [RPGMaker MV](https://store.steampowered.com/app/363890/RPG_Maker_MV/)
2. [[Tiled]]
3. [[Getting OMORI's Assets]]

*Don't have OMORI or RPGMaker MV? Go here:*
[[Map making without OMORI and RPGMaker MV]]
#### Steps:
1. Create shortcut to www_playtest folder.
	1. Usually under here:![[Pasted image 20260312225903.png]]
2. Open RPGMaker MV. 
3. Create a new map
	1. ![[Pasted image 20260312225950.png]]
	2. ![[Pasted image 20260312230014.png]]
	3. Leave settings as default (but choose whatever Display Name you wish), but set the `Width` and `Height` to 32. 
4. Open the directory where you want your maps to be:
	1. ![[Pasted image 20260312225903.png]]
5. Find `map00_Template_32x32.json`: 
	1. ![[Pasted image 20260312230127.png]]
6. Copy and paste map, then rename it to the same one as you've given it in RPGMaker (in this case, it's map516).
7. Open Tiled ^23b677
8. No tiles found? 
	1. ![[Pasted image 20260312230246.png]]
	2. ![[Pasted image 20260312230303.png]]
	3. Leave settings as default. Click "Browse..."
9. Navigate to:
	1. ![[Pasted image 20260312230337.png]]
	2. Then select the tileset you want
10. Make your map!
11. Don't forget collisions!
	1. ![[Pasted image 20260312230500.png]]
	2. ![[Pasted image 20260312230520.png]]
	3. Use these tiles to mark places characters shouldn't clip through.
12. Remember to save regularly!
13. When done, navigate back to RPG maker to add in objects.
14. If you want to add existing objects, find a map which contains the object you want. Then copy and paste.
15. You can figure out the coordinates by going to Tiled again and checking...
	1. ![[Pasted image 20260312230717.png]]
	2. Please ignore the name. It'll be map516.json for your case. 
	3. And then matching the coordinates to: ![[Pasted image 20260314001051.png]]

Next, take a look at:
[[Events]]