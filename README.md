# github commands
My personal guide in github commands

#### SSH Keys
> ssh-keygen -t ed25519 -C kltc@gmail.com - generate ssh

> eval "$(ssh-agent -s)" - for linux to start ssh agent

> ~/.ssh/config - show if private key existed

> touch ~/.ssh/config

> notepad ~/.ssh/config

    Host *
          AddKeysToAgent yes
     
          IdentityFile ~/.ssh/id_ed25519
     
> ssh-add ~/.ssh/id_ed25519



##### Test SSH
> ssh -T git@jairo@vs-ssh.visualstudio.com - for azure

> ssh -T git@github.com - for github



#### Branching and feature branch
> git checkout main

> git checkout -b develop

> git checkout -b feature_branch - work always on feature_branch

> git checkout develop

> git merge feature_branch - merge once done

> git checkout -b release/0.1.1 - for release feature branch

> git checkout main

> git merge release/0.1.0 - for releasing and merge directly to main

> git checkout main

> git merge feature_branch - also merge to main if needed (not always allowed)




#### Fork & pull request (read access only? no problem)

#### Fetch (git fetch + git merge = git pull)
> get fetch --all - fetch all from repo e.g. origin/...

> git checkout <branch-name-from-fetch> - you can start and test out the branch code

> git checkout develop

> git merge <branch-name-from-fetch>
  
> git merge --abort - cancel merge
  
> git add . & git commit after merged


###### Pull and push existing repo
> git remote add origin https://github.com/kenLovesToCode/github-commands

> git pull origin main

> git add .

> git commit -m 'commit name'

> git branch -M master main

> git pull --allow-unrelated-histories origin main - for nonrelated histories

> git push -u origin main



#### GitFlow merge and branching
> git flow init - initialize and create branch

> git flow feature start feature_branch - create feature branch from develop branch

> git flow feature finish feature_branch - finish feature branch by checkout develop and merge it

> git flow release start 0.1.0 - checkout develop branch and create copy to release/0.1.0 branch

> git flow release finish '0.1.0' - merge release branch to main

> git flow hotfix start hotfix_branch - checkout hotfix_branch from develop branch

> git flow hotfix finish hotfix_branch - merge hotfix to main and develop then delete hotfix branch



###### Move branch to branch
> git branch -m master main
  

###### git stash (temporary branches that needs comparison from time to time | temporary commits)
#####Can also be applied on different branches, can move the commit to different branches
`git stash save 'work on add function'` - put staged for commit to stash area
   
show stashes `git stash list` //show stash@{0}

`git stash apply stash@{0}` - ready to commit | code restored
  
`git stash pop` - move to commit and drop the stash from top
  
`git stash drop 'stash@{0}'` - to remove a stash
  
`git stash clear` - remove all stashes 

`gitk --all $( git fsck --no-reflog | awk '/dangling commit/ {print $3}' )` show stash including the deleted one
and apply using `git stash apply <commit-hash>`
  
  


###### remove cached and add again
> git rm -rf --cached folderName

> git add folderName/

###### setup git for the first time
> git config --global user.name 'name'

> git config --global user.email 'email'

#### go back to specific commit hash
> git log #to list all the available commit hashes

> git checkout <the commit hash only>
  

###### to show git config `cd to-project-dir` and `cat .git/config`

###### to change remote url `git remote set-url origin copy-the-ssh-to-change-ssh-link`

###### to show difference between branches `git diff`
  
###### remove all changes not staged for commit `git checkout -- .`
  
###### delete a file `git rm Test/deleteme.txt`

###### renaming a file `git mv oldtext.txt newtext.txt`

###### readable log `git log --oneline --graph --color --all --decorate`
  
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
    
###### delete remote `git remote remove origin`
 
GIT RESET
###### go back to commit and keep files staging `git reset --soft commit_hash`
  
###### go back to commit and keep files in local and unstaged  `git reset commit_hash`
  
###### go back to commit and remove all changes `git reset --hard commit_hash`
  
###### remove all changes withing commit_hash `git clean -df`
  
GIT REFLOG
###### show all git commits including the deleted `git reflog`

###### show remote info `git remote show remote_name`

###### show commits including the deleted with UI `git reflog |  awk '{ print $1 }' | xargs gitk`
