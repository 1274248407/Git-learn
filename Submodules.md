# Submodules
## sample (add into directory)
```bash
    $ mkdir Test_submodule
    $ cd Test_submodule/
    $ git submodule add git@github.com:1274248407/GCC-and-GDB-.git
# add new files
    $ cd GCC-and-GDB-/
    $ ll
    total 60
drwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407  4096 May 17 18:15 ./
drwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407  4096 May 17 18:15 ../
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407    55 May 17 18:15 .git*
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407 19384 May 17 18:15 Learn_GDB*
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407   208 May 17 18:15 Learn_GDB.c*
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407    15 May 17 18:15 README.md*
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407 16704 May 17 18:15 a.out*
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407   128 May 17 18:15 hello_world.c*
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407 16704 May 17 18:15 hello_world.o*
-rwxrwxrwx 1 ubuntu1274248407 ubuntu1274248407   709 May 17 18:15 hello_world.s*
# but the three party code not part of that version control system
    $ git status 
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

```
------
## check the configure file (Don't mess the configure file)
```bash
    $ cat .gitmodules 
[submodule "Test_submodule/GCC-and-GDB-"]
        path = Test_submodule/GCC-and-GDB-
        url = git@github.com:1274248407/GCC-and-GDB-.git

    $ cat .git/config
        [core]
        repositoryformatversion = 0
        filemode = false
        bare = false
        logallrefupdates = true
        ignorecase = true
[remote "origin"]
        url = git@github.com:1274248407/Git-learn.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "main"]
        remote = origin
        merge = refs/heads/main
[branch "quick-test"]
        remote = origin
        merge = refs/heads/quick-test
[branch "git_extention"]
        remote = origin
        merge = refs/heads/main
[submodule "Test_submodule/GCC-and-GDB-"]
        url = git@github.com:1274248407/GCC-and-GDB-.git
        active = true
```
----------
## update submodule from origin URL/SSH or other URL/SSH
```bash
# from origin URL/SSH
    $ git submodule update --init --recursive
# from other URL/SSH
    $ git clone --recursive-submodule URL/SSH
```
