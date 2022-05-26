# Merge
## Merge conflict(same modified content on differences branch)
### on 'Rebase' branch
```bash
    $ touch test_merge_conflict
    $ vim test_merge_conflict
# modified content:
# one
# two
    $ git add .
    $ git commit -a
[Rebase 6831582] okC
1 file changed, 3 insertions(+)
create mode 100644 test_merge_conflict
```
### on 'main' branch
```bash
    $ touch test_merge_conflict
    $ vim test_merge_conflict
# modified content:
# one
# two
    $ git add .
    $ git commit -a
[main bb18974] ok
1 file changed, 2 insertions(+)
create mode 100644 test_merge_conflict
    $ git merge Rebase 
CONFLICT (add/add): Merge conflict in test_merge_conflict
Auto-merging test_merge_conflict
Automatic merge failed; fix conflicts and then commit 
the result.
# conflict
    $ git status 
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both added:      test_merge_conflict

no changes added to commit (use "git add" and/or "git commit -a")
```
--------------
## Solve Method
1. ### Abort the branch
```bash 
    $ git merge --abort
```
2. ### Modifying the conflicted file (tell the teammate)
3. ### Using 'mergetool' to modify conflicted file and save the origin file
```bash
    $ git mergetool 
Merging:
test_merge_conflict
Normal merge conflict for 'test_merge_conflict':
  {local}: created file
  {remote}: created file
Hit return to start merge resolution tool (vimdiff):
3 files to edit
# respectively modify
    $ git status 
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)
Changes to be committed:
        modified:   test_merge_conflict
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Merge.md
        test_merge_conflict.orig

```