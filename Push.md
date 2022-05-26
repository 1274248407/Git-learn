
```
> ! [rejected]        main -> main (fetch first)
> error: failed to push some refs to 'git@github.com:1274248407/Markdown_learned.git'
```

+ That only happens because your remote repository was initialized not empty, but with some files (README.md for instance) 

  That is why force pushing is a good option (in that case) 
    ```
    git push -f -u origin main 
    ```
    If you had created the repository empty, a regular push would have been enough.


## Pull Request

```bash
# 1. Fork the repository
  $ git clone git@github.com:1274248407/new-pac.git
# 2. clone to local
  $ git branch test
  $ git switch test 
# 3. add new branch
  $ vim README.md
  $ git add .
  $ git commit
# 4. what you wanna do
  $ git push --set-upstream origin test
# 5. set upstream and push to repository
# 'origin' contain the 'test'
```
