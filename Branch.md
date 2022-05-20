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
## Switching branch
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
## Publishing branch
```bash
    $ git push -u origin new_test_branch 
Total 0 (delta 0), reused 0 (delta 0)
remote: 
remote: Create a pull request for 'new_test_branch' on GitHub by visiting:
remote:      https://github.com/1274248407/Git-learn/pull/new/new_test_branch
remote:
To github.com:1274248407/Git-learn.git
 * [new branch]      new_test_branch -> new_test_branch
Branch 'new_test_branch' set up to track remote branch 'new_test_branch' from 'origin'.
```
## Tracking branch (local branch connection remote branch)
```bash
# already pushed the 'new_test_branch' branch
    $ git branch -d new_test_branch 
Deleted branch new_test_branch (was b093c5d).
    $ git branch 
  Branch_rename
  Rebase
  Reflog
  Rename_branch
  cherry_picking
  git_extention
* main
  quick-test
# Not the 'new_test_branch' on the local
    $ git branch --track origin/new_test_branch origin/new_test_branch 
Branch 'origin/new_test_branch' set up to track remote branch 'new_test_branch' from 'origin'.
# connection 
    $ git branch 
  Branch_rename
  Rebase
  Reflog
  Rename_branch
  cherry_picking
  git_extention
* main
  origin/new_test_branch ## success
  quick-test
```
### Other method connection
```bash
    $ git checkout --track origin/new_test_branch 
M       Branch.md
Branch 'new_test_branch' set up to track remote branch 'new_test_branch' from 'origin'.
Switched to a new branch 'new_test_branch'
# directly switch
    $ git branch 
  Branch_rename
  Rebase
  Reflog
  Rename_branch
  cherry_picking
  git_extention
  main
* new_test_branch # here
  quick-test
```

