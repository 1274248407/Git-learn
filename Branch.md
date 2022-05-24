# git branch

- [Creating new branch](#creating-new-branch)
- [Switching branch](#switching-branch)
- [Switching branch](#switching-branch)
- []
- 

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
## Pulling + pushing branches (committed different both the local and remote)
```bash
    $ git status 
On branch git_extention
Your branch and 'origin/main' have diverged,
and have 13 and 8 different commits each, respectively.
    $ git branch -v
* git_extention   035a9c7 [ahead 13, behind 8] added
```
**[ahead 13, behind 8]**
  + local: 13 commit not pushed *(ahead 13)*
  + remote 8 commit pushed *(behind 8)*

## Comparing Branch (commit different)
```bash
  $ git log origin/main 
commit e5daec068fd4cf1cb32694bc005671de16ada828 (origin/main)
Author: 1274248407 <1274248407@github.com>
Date:   Tue May 17 19:29:08 2022 +0800

    learn Submodule

commit a0407a77447545639481ead9cc0c90f85174b5f4
Author: 1274248407 <1274248407@github.com>
Date:   Tue May 17 18:36:44 2022 +0800
# Different with commit
  $ git log origin/main..main 
commit d44483df94c334f984df76667529e1c2c3d240a3 (HEAD -> main, Rebase)
Author: 1274248407 <1274248407@github.com>
Date:   Mon May 23 18:44:31 2022 +0800

    test file

commit dbfc7fa6c677fcb369ae53f2b67890fed274e6cd
Author: 1274248407 <1274248407@github.com>
Date:   Mon May 23 18:41:19 2022 +0800
```

