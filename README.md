# Git-learn
Start date : 5/3/2022

Crash course : [Git and GitHub for Beginners - Crash Course --freeCodeCamp.org](https://www.youtube.com/watch?v=RGOj5yH7evk&t=600s&ab_channel=freeCodeCamp.org)

------------

Here are the comment I've taken the bug

+ Git push command
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
