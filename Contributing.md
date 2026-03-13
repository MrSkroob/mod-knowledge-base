[[Index]]
#### Prerequisites:
1. [Git](https://git-scm.com/install/)
2. [[Getting OMORI's Assets]]
3. Knowledge of basic git commands (if you've followed the instructions of the README.md, then you're fine.)
4. Optionally, you don't need Prerequisite #2, but when contributing to maps, you'll need to follow [[Map making without OMORI and RPGMaker MV]]. 
#### Steps:
##### Set up:
1. Use Git Bash and `cd` to wherever you want 
2. `git clone "https://github.com/MrSkroob/omori-a-c-mod/tree/main"`
	1. This will take a while.
##### (Optional) update your decrypted files:
1. Navigate to: ![[Pasted image 20260312225903.png]]
2. Copy the `www_playtest_539a4027` name and rename the cloned repository to that name.
3. Cut and paste your cloned repository into the same place as the existing `www_playtest` and make sure to **replace**.
##### Updating:
1. `git fetch`
2. `git pull`
3. `git add *`
4. `git status`
5. If there is anything that you think should be committed, you'll need to manually add it to the commit by doing (replacing the FILENAME  with the... uh, filename.). 
	1. For example, when I update this vault's repo: ![[Pasted image 20260313235210.png]]
	2. After running `git add *`:![[Pasted image 20260313235301.png]]
	3. Manually adding the files (`git add .obsidian`) should shift everything up to the "Changes to be committed:"
6. `git status FILENAME` (double check again)
7. `git commit -m "YOUR COMMIT MESSAGE HERE"`
	1. Try to be short, yet descriptive here. 
	2. If you omit the `-m` argument, it should either open up your IDE (usually VSCode) or open up...
	   **vim.**
		1. Don't panic! Here are a few commands that should get you up to speed:
			1. `i` goes into insert mode. It'll act as you expect (type as normal, backspace, etc.)
			2. When done, press `escape` on your keyboard.
			3. Type `:wq` if you're happy. Press `escape` again to cancel this command.
8. Finally: `git push`: ![[Pasted image 20260313235834.png]]