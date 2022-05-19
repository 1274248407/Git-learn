# Search & Find
## Search by Date 
```bash
git log --after="2022-5-17"
git log --after="2022-5-16" --before="2022-5-18"
#      2022-5-16 < screening condition < 2022-5-18
```
## Search by Commit
```bash
$ git log --grep="modify"
```
## Search by Author
```bash
$ git log --author="chenglongwang"
$ git log --author="1274248407"
```
## Search by File (only current directory)
```bash
$ git log -- Push.md
$ git log -- README.md
```
