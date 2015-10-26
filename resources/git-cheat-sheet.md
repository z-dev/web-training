# Git Cheat Sheet

For a comprehensive cheat sheet see [github's one]()

## Actions

###Start a new repo if it's not in git / github already

`cd <directory code is in>`
`git init`

###Add a file because you want to commit it

`git add filename`

###Add all files because you want to commit them

`git add .`

###See the status git thinks your files are currently in

`git status`

###Commit your changes

`git commit -m "Commit message goes here"`

###Push your changes to the remote

`git push origin branch-name`

###Create a new branch

`git checkout -b new-branch-name`

###Switch to another branch

`git checkout existing-branch-name`

###Get the lastest version of a particular branch from github (if other people committed stuff and pushed it)

`git pull origin branch-name` Warning `pull` also merges it the branch you're currently on. If you don't want to merge it, use `fetch`.


###See what changes you made a file

`git diff`

###See what changes you made a file (but you already 'added' it)

`git diff --cached`

###Move a file / folder

Moving is a special operation in git. As well as add and remove.

You can either do a `mv file1 file2`. But git will think you deleted file1 and created file2. So `git status` will show two changes. Instead we can do:

`git mv file1 file2`

This tells git that we're actually moving a file. It shows up as 1 change in `git status` and makes the history neater later. 

###The bail out

git clone the whole thing again into a new folder :p (I do this sometimes :p) and start from there :smile:
