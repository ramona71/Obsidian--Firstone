3 - version history for code , manually 
- `git` -> powershell for version
><mark style="background: #ABF7F7A6;"> Powershell</mark> on windows for command line
- add -> helps us pick
- git tracks changes not files
-  to track the file, we need to commit 
- version = commit
> HEAD  -> which version we're currently viewing
- if u make a copy of file with git, the copy will also have git
```git
q             -> to quit, if git log --all becomes too long 
.gitignore    -> file and add the files u want to ignore inside it 
              -> need to commit this file too
//to check username and mail
git config user.name
git config user.email

// to keep alias
git config --global alias.shortcut_uwanna_keep  "actual command"

git config --global alias.s "status"    -> to use s instead of status
git config --global alias.cm "commit -m"
git config --global alias.co "checkout"
git config --global init.defaultBranch main   // to make all init ->main

rm -rf .git             -> remove git from a file/folder
```
# In order process
```git
git --version
git init                    -> initiate empty repo
git status                  -> to chech status
git log                     -> version histories / to check if git is there
git log --all               -> all version histories
git log --all --graph       -> branches
git log --oneline           -> commits without hash

git add                   -> help us pick which version we want to add
                          -> doesn't create new version (commit do)
git add .                  -> adds all in that directory
git add file/foldername    -> adds specific

git reset .                 -> un-add  (unstage commits)   
git reset file/ folder name  -> takes all out of staging area

git checkout -- config .     ->unsaves the new changes (discard changes)
git checkout -- config file/foldername

git commit                              -> creates new version
git commit -m "Version 1"               -> -m for message
git commit -m "Version 1" --amend       -> add it to the previous commit

git checkout version_hash        -> to go to a specific version
git log --all
git checkout master              -> to go to latest commit

git checkout version_hash file/foldername  -> restore a specific file from                                        previous version to current version
git checkout version_hash .       -> to restore all files

```
- if you forgot to add a file/ want a new file to be in the previous commit and not want to make another commit just do
	- this is how u edit a commit in case u mess us
	- u can edit the message too like this, incase of spelling mistakes
```git
git add .                               -> add those all files
git commit -m "Version 1" --amend       -> add it to the previous commit
```
- if u have 5 versions, and u go to 3rd one and type `git log` -> git only only 1 to 3 versions , it won't show the versions after the current versions
- so to get the hash of 5th version from 3rd version do `git log --all`
	- HEAD -> on 3rd version
```git
git checkout version_hash        -> to go to a specific version
git log --all
```
# Git Branching
-  After making 5 versions, u go back to 3rd one, think it's the best and u try to add on 3rd version, It makes a branch
	- ![[Pasted image 20250710153813.png]]
	- so unless u delete 4th and 5th versions, they still exist 
- git does not show unnamed branches
- to prevent branching but want to restore v1 to v3
	- `git checkout version_hash file/foldername  
	- `git checkout version_hash .       -> to restore all files`
	- it automatically gets added to staging area
	- just commit n u get ![[Pasted image 20250710193537.png]] instead of branching

> [!NOTE] Remember to commit after using checkout

# Vscode git
- + -> to add
	- files go from 'Changes' to 'Staged Changes'
# Email, username
- `git config --global user.email "email`
- `git config --global user.name "user_name"`
- to check if confirmed `git config --list`   or `git config --list --global`
	- or `git config user.name` 


# Images :3
![[Pasted image 20250710193848.png]]
![[Pasted image 20250710193857.png]]