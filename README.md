# github-commands
My personal guide in github commands

#### Branching and feature branch
> git checkout main

> git checkout -b develop

> git checkout -b feature_branch - work always on feature_branch

> git checkout develop

> git merge feature_branch - merge once done

> git checkout -b release/0.1.1 - for releasing feature branch

> git checkout main

> git merge release/0.1.0 - for releasing and merge directly to main

> git checkout main

> git merge feature_branch - also merge to main if needed (not always allowed)


#### Hotfix branch (For maintenance - direct to main)
> git checkout main

> git checkout -b hotfix_branch

> git checkout main

> git merge hotfix_branch

> git checkout develop

> git merge hotfix_branch

> git branch -d hotfix_branch - delete once merged




###### Pull and push existing repo
> git remote add origin https://github.com/kenLovesToCode/github-commands

> git pull origin main

> git add .

> git commit -m 'commit name'

> git branch -M master main

> git pull --allow-unrelated-histories origin main - for nonrelated histories

> git push -u origin main

###### Move branch to branch
> git branch -m master main

###### git stash for initial work `git stack save 'any name'` | `git stash list` | `git stash apply stash@{0}` to apply `git stash pop` get and delete the first stash `git stash drop stash@{0}` to drop and `git stash clear` to drop all

###### remove cached and add again
> git rm -rf --cached folderName

> git add folderName/

###### setup git for the first time
> git config --global user.name 'name'

> git config --global user.email 'email'

#### go back to specific commit hash
> git log #to list all the available commit hashes

> git checkout <the commit hash only>
  
###### show all branch remote and local `git remote -a`
  
###### create and switch branch `git branch branch_name` | `git checkout branch_name`

###### show merged branch `git branch --merged`
  
###### test output of a branch `git pull` | `git checkout commit_hash` | `git branch test`
  
###### pull and merge branch to main `git pull` | `git merge branch_name` | `git push -u origin main`
  
###### local delete merged branch `git branch -d branch_name`
  
###### remote delete branch `git push origin --delete branch_name`
  
###### delete all changes to non-added file `git checkout filename.extension`
  
###### change commit name `git commit --amend -m 'New commit name'` [danger]

###### update latest commit `git commit --amend --no-edit` [danger]
  
###### retrieve deleted commit `git reflog` | `git branch new_branch` | `git checkout main`
  
###### go back to commit without deleting commit pulled by others `git revert commit_hash`
 
GIT RESET
###### go back to commit and keep files staging `git reset --soft commit_hash`
  
###### go back to commit and keep files in local and unstaged  `git reset commit_hash`
  
###### go back to commit and remove all changes `git reset --hard commit_hash`
  
###### remove all changes withing commit_hash `git clean -df`
  
GIT REFLOG
###### show all git commits including the deleted `git reflog`

###### show remote info `git remote show remote_name`
