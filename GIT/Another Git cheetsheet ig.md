# 📝 Git Cheat Sheet

## 🔧 Setup
- `git config --global user.name "[firstname lastname]"` → set user name  
- `git config --global user.email "[valid-email]"` → set user email  
- `git config --global color.ui auto` → enable colorized output  

## 📂 Setup & Init
- `git init` → initialize a new repo  
- `git clone [url]` → clone repo from URL  

## 📌 Stage & Snapshot
- `git status` → show modified/staged files  
- `git add [file]` → stage file  
- `git reset [file]` → unstage file (keep changes)  
- `git diff` → unstaged changes  
- `git diff --staged` → staged but uncommitted changes  
- `git commit -m "[msg]"` → commit staged changes  

## 🌿 Branch & Merge
- `git branch` → list branches (`*` = current)  
- `git branch [name]` → create branch  
- `git checkout [branch]` → switch branch  
- `git merge [branch]` → merge branch into current  
- `git log` → commit history  

## 🔄 Share & Update
- `git remote add [alias] [url]` → add remote alias  
- `git fetch [alias]` → fetch remote branches  
- `git merge [alias]/[branch]` → merge remote branch  
- `git push [alias] [branch]` → push commits  
- `git pull` → fetch + merge remote  

## 🛠️ Tracking Path Changes
- `git rm [file]` → delete + stage removal  
- `git mv [old] [new]` → rename/move file  
- `git log --stat -M` → show commit logs w/ moved paths  

## 📦 Temporary Commits (Stash)
- `git stash` → save changes  
- `git stash list` → list stashes  
- `git stash pop` → apply + drop latest stash  
- `git stash drop` → drop latest stash  

## ✍️ Rewrite History
- `git rebase [branch]` → reapply commits on top of branch  
- `git reset --hard [commit]` → reset to commit (dangerous)  

## 🔍 Inspect & Compare
- `git log` → history of current branch  
- `git log branchB..branchA` → commits in A not in B  
- `git log --follow [file]` → history of a file  
- `git diff branchB...branchA` → diff A vs B  
- `git show [SHA]` → show object details  

## 🚫 Ignoring Patterns
- `git config --global core.excludesfile [file]` → global ignore file  
- `.gitignore` examples:  
