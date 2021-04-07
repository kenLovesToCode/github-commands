# github-commands
My personal guide in github commands

###### Pull and push existing repo
> git remote add origin https://github.com/kenLovesToCode/github-commands

> git pull origin main

> git pull --allow-unrelated-histories origin main - for nonrelated histories

> git add .

> git commit -m 'commit name'

> git push -u origin main

###### Move branch to branch
> git branch -m master main

##### git stash for initial work
> git stack save 'any name'
> git stash list
> git stash apply stash@{0} //apply
> git stash pop // get and delete the first stash
> git stash drop stash@{0} // drop
> git stash clear // drop all

###### remove cached and add again
> git rm -rf --cached folderName
> git add folderName/
