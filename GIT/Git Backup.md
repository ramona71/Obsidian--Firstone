- google drive?
	1. online backup
	2. 2 way sync updates 
		1. update on  computer ->google drive
		2. update on drive -> computer automatic 
- git repo -> folder that's tracked by git
- local repo -> on comp 
- remote repo -> online repo
- upload to github -> push
- download from github -> pull
- we don't just push the code , but also the commit history, only one branch of commit history, so we give branch history to push
```git
git config --global credential.username "ramona71"  ->to config,before push
git remote add origin https:ramona71@//github.com/ramona71/git-one.git  
                                      ->another way to config,while adding
git push origin master --set-upstream    ->shortcut, use git push, no need for master or origin
```
# In order
```
git remote add nickname_to_localrepo url  -> to link local to remote
git remote add origin http:/bullshit

nickname_to_localrepo                     -> origin
git remote                                -> to check linked repos
git remote -v                             -> check more details

git remote remove nickname_to_localrepo(origin)  -> to remove link

git push nickname_to_localrepo branch_of_commit_we_want_topush  -> to push
git push origin master 
```

-  sometimes git askes for password when pushing, just remember it