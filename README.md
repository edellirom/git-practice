### GIT Practice

--
Show commits:
``` shell
git log
```
#### Branches
Show all branches:
``` shell
# Show local branches
git branch

# Show all branches, remotes tracking includes
git branch -a

git branch -r

# Show all remotes branches
git ls-remote

# Creates remotes/origin/develop branch and 'push' to it
git push origin develop

# Show tracking branches
git branch -vv

# Track feature local branch to feature remote branch
git branch --track feature origin/feature
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

#### Temp
show what heppend in the branch
``` shell
git reflog
```


### Cases
Here we try to use some cases
#### Fast-forward merge strategy
Structure description: We have two branches, master and feature
> master -> where we have folder 'master' with two files: 
> m1.txt -> commit m1
> m2.txt -> commit m2

> feature -> where we have folder 'feature' with two files:
> f1.txt -> commit f1
> f2.txt -> commit f2

``` shell
# Move to the 'master' branch
git checkout master

# Merge 'feature' branch to the 'master'
get merge feature

# Move HEAD to two commits below
git reset --hard HEAD~2

# Squash all commits from feature branch in one when merge to master -- not updating HEAD
branches> git merge --squash feature 

# Create new merge commit. Separate commit that will combine branches.
git add .
git commit -m 'merged feature and master'

# Reset previous commit. (We can use hash of necessary commit)
git reset --hard HEAD~1
```
#### Recursive merge strategy
Structure description: We have two branches, master and feature
> master -> where we have folder 'master' with two files: 
> m1.txt -> commit m1
> m2.txt -> commit m2

> feature -> where we have folder 'feature' with two files:
> f1.txt -> commit f1
> f2.txt -> commit f2

> master -> then we back to the 'master' branch and create commit with file
> m3.txt -> commit m3

```shell
# Merge made by the 'ort' strategy.
git merge feature

# To se what heppend
git log

# Back HEAD to m3 commit in our case
git reset --hard HEAD~1

# Squash all commits from feature branch in one when merge to master -- not updating HEAD
branches> git merge --squash feature 

# Create new merge commit. Separate commit that will combine branches.
git add .
git commit -m 'merged feature and master'

# Reset previous commit. (We can use hash of necessary commit)
git reset --hard HEAD~1
```

#### Rebase
Structure description: We have two branches, master and feature
> master -> where we have folder 'master' with two files: 
> m1.txt -> commit m1
> m2.txt -> commit m2

> feature -> where we have folder 'feature' with two files:
> f1.txt -> commit f1
> f2.txt -> commit f2

> master -> then we back to the 'master' branch and create commit with file
> m3.txt -> commit m3

```shell
# Switch to the 'feature' branch 
git checkout feature


```
