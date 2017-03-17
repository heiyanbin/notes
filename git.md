### add:
add all updates, not including untracked file, but include repo file deleted from os
	
	git add -u
add all untracked files, also deleted files or renamed files
	
	git add -A

		
### branch:
create a branch based on a specific point:
	
	git branch new_branch SHA (or tag)
	
	
rename a branch(move a branch)
	
	git branch -m old_banch_name new_branch_name
	
delete an alreay merged branch:
	 
	git branch -d <branch_name>
	
delete an unmerged branch:
	 git branch -D <branch_name>

### remote branch:
publish a local branch to remote:

	git branch new_branch
	git push -u origin new_branch
-u is setting the tracking info(upstream), then next time don't need to specify where to push

delete a remote branch:

	git push origin : <remote_branch_name>
left part of the colon should be the local branch name, here empty, meaning deleting the remote branch

### tracking:
create local and remote branch at the same time

	git branch --track new_branch origin/new_branch

### stash:
the working directory is shared between the branches, use stash to save away the temp work in a branch and reverting the working directory.

	git stash "some description".
in low git versions, you are not allowd to switch branch unless you stash or revert the index and working directory. 
in high git version, the change in working directory or index belongs to all branches

later coming back:

	git stash apply
	
### File:
**Config file:**
1. /etc/gitconfig: 
system level, config git config --system
2. ~/.gitconfig: 
user level config, git config --global
3. .git/config: 
repository level config， git config 

**.gitignore:**
 ignore file, part of the project


### Revert uncommitted change:
1. unstage : 
	git reset HEAD file
2. revert in working directory:(checkout the file into working diretory)
	git checkout -- file (the -- is not needed if the file name does not be the same with any branch name)
	git reset --hard (revert all changes in working direcotory)	
3. revert commits
revert the last commit and move the change back to the stage

	**git reset --soft HEAD~1**
revert the last commit and discard the change

	**git reset --hard HEAD~1**
	
### git log:
	git log --stat
full diff:
	
	git log -p

other:

	git log --oneline
	git log --graph
	git log --oneline | wc -l
	git shortlog: group by contributor
	git shortlog -sn: list contributors sorted by commits desc
	
### pointer:
	HEAD^ HEAD^^ HEAD^^^(HEAD~3)
