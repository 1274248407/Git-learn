# git branch

watch tutorial on youtube
=======
HEAD Branch == master branch ~= ROOT user on Linux (Temporary)
## Creating new branch
```bash
    $ git branch Branch_test e06547d
# add new commit on the new branch
    $ git log --oneline 
e06547d (HEAD -> main, Branch_test) 5/19/2022
```
## Switching branchs
```bash
    $ git switch Branch_test 
    $ git commit -a
    $ git log --oneline 
62f6e3d (HEAD -> Branch_test) ok
# Branch_test become HEAD branch
```
## Renaming branch
```bash
    $ git branch Rename_other_branch
    $ git branch -m Rename_other_branch Rename_branch
    $ git status 
On branch Rename_branch
```