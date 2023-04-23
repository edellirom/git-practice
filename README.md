### GIT Practice

--
Show commits:
``` shell
git log
```
#### Branches
Show all branches:
``` shell
git branch
```
Create new branch and switch to it 
``` shell
git checkout -b develop
```
>develop - it's a new branch that we will create

#### Deleting
To see what files in current stage branch
``` shell
git ls-files
```
Remove file from commit
``` shell
git rm filename.txt
git commit -m 'filename.txt removed'
```
Remove branch 
``` shell
git branch -D branch-to-delete
```
####Combaine commits
``` shell
# Reset to the commit by hash
git reset --soft 37db9c63a1b179bdf3ca59a7f8be4b74ac8d0fc5
# Make new one with all changes from unstaged 
git add .
git commit -m 'New commit with all changes'
```
