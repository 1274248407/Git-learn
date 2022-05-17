# git *reflog* ==  restore function
## sample
```bash
    $ git log --oneline
    be74987 (HEAD -> main) Rebase commit ok
    24469a3 HEAD ok
    16fae89 next ok
    366c344 ok
    1af2c04 modify in the 'cherry_picking'
    ac843a2 (Rebase) Rebase.md in Cherry_picking
    a1cdc32 ok
    9208c05 Co-authored-by: 1274248407 <1274248407@github.com>
    4a17b88 ok
    aa255dd combine two into one
    3f1960b updated push bug
    73be7f7 updated push bug
    338b3eb updated push bug

    $ git reset --hard a1cdc32 ##delete commit
    $ git reflog a1cdc32 ## restore commit

    $ git log --oneline
    a1cdc32 (HEAD -> main) ok
    9208c05 Co-authored-by: 1274248407 <1274248407@github.com>
    4a17b88 ok
    aa255dd combine two into one
    3f1960b updated push bug
    73be7f7 updated push bug
    338b3eb updated push bug
    87b6687 first commit
```
-----
restore commit to other new branch

1. 
```bash
    $ git branch Reflog a1cdc32 ## add new branch and restore the commit
    $ git log Reflog  
commit a1cdc3230c0d490cededa96bc6929ca79a4e5e5b (HEAD -> main, Reflog)
Author: 1274248407 <1274248407@github.com>
Date:   Fri May 13 19:17:46 2022 +0800

    ok
```
2. 
```bash
    $ git checkout Reflog
    $ vim branch_reflog
    $ git add branch_reflog 
    $ git commit -m "Reflog commit"
[Reflog 917c882] Reflog commit
 1 file changed, 2 insertions(+)
 create mode 100644 branch_reflog
# add new file 'branch_reflog' in the 'Reflog' branch
    $ git checkout main 
    $ git branch -D Reflog 
    $ ll branch_reflog 
ls: cannot access 'branch_reflog': No such file or directory
# delete branch 'Reflog'
    $ git branch Reflog 917c882
    $ git checkout Reflog 
    $ ll branch_reflog 
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407 52 May 16 18:50 branch_reflog*
# restore success
```
**also could use CRTL + Z is a undoing function**