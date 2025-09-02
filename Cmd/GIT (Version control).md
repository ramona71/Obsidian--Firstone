# Shell commands
```bash 
// commands
ls                      - list
ls -a                   - list (along with secret files)
cd ..                   - to parent
cd~                     - to root directory
touch textfile.txt      - makes a text file
start textfile.txt      - to open it in notebook
code textfile.txt       - to open it in vs code
rm *                    - deletes files 
rm -r                   - delete directories(folders)
rm -r Web dev           - deletes specific directory
rm textfile.txt         - delete a specific file
pwd                     - prints the entire path of current folder
clear                   - cleares the terminal
```
- !!! fucking remember that you can delete any files with rm* and if ur in wrong directory all will be gone, MAKE SURE UR IN RIGHT DIRECTORYto initialize git

# git commands
```git
gin init                   - to intialize git
git status                 - to track any untracked files
git add filename           - to add the file to staging area
git add .                  - adds all files to staging area
git commit -m "Message"    - commits along with message
git log                    - to see what commits are made
git diff filename          - shows different between current and commmited version
git checkout filename      - rolls back to previous commit

git rm --cached -r .       - everthing is removed from git staging area
```
- git commit- message to keep track of what changed in that commit (make it clear in it dumbass it's really important)
- each commit has a unique hash
# Gitignore
- useful git ignore templetes   https://github.com/github/gitignore
- to prevent committing sensitive stuff (passwords, API keys, local utility files)
- DS_store files
```git
touch .gitignore               - make ignore file
start .gitignore               - open it
```
- inside .gitignore
```gitignore
filename        - this specific file will be ignored(case sensitive)
#  comment
*.txt       - all txt files will be ignored
*.log
```
# Git clone
- to get stuff from remote repository to local repo
```git
git clone 'url_of_the_clone'
```