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
5. If there is anything that you think should be committed, you'll need to manually add it to the commit by doing (replacing the FILENAME  with the... uh, filename.):
6. `git status FILENAME`
7. Finally: `git push`