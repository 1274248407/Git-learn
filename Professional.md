# Git Professional
## The perfect commit
### Upload Separately
```bash
    $ git diff Branch.md
diff --git a/Branch.md b/Branch.md
index 00dcc46..f1552bc 100644
--- a/Branch.md
+++ b/Branch.md
@@ -1,5 +1,11 @@ 
# detail omitted
@@ -95,5 +101,29 @@ and have 13 and 8 different commits each, respectively.
 **[ahead 13, behind 8]**
   + local: 13 commit not pushed *(ahead 13)*
   + remote 8 commit pushed *(behind 8)*
# add separately
    $ git add -p Branch.md 
diff --git a/Branch.md b/Branch.md
index 00dcc46..f1552bc 100644
--- a/Branch.md
+++ b/Branch.md
@@ -1,5 +1,11 @@
(1/2) Stage this hunk [y,n,q,a,d,j,J,g,/,e,?]? y
# (1/2) of difference
(2/2) Stage this hunk [y,n,q,a,d,K,g,/,e,?]? n
# (2/2) of different
    $ git status #
On branch main
Your branch is ahead of 'origin/main' by 8 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   Branch.md
## stage (1/2) this hunk
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Branch.md
## stage (2/2) this hunk
```

### The Perfect Commit Message 

Subject = concise summary of what happened 

Body = more detailed explanation:
1. What is now different than before? 
2. What's the reason for the change? 
3. Is there anything to watch out for / anything particularly remarkable? 
