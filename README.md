****
### Create new git repo

- Method 1:
 
 - cd git_learning
 - git init

- Method 2:
 - git init git_learning

### Setup *local* user.name & user.email

```
✔ ~/Documents/git_learning [master|…2] 
16:21 $ git config --local user.name "qiaodeli"
✔ ~/Documents/git_learning [master|…2] 
16:21 $ git config --local user.email "qiaodeli111@126.com"
✔ ~/Documents/git_learning [master|…2] 
16:22 $ git config --local --list
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
user.name=qiaodeli
user.email=qiaodeli111@126.com
✔ ~/Documents/git_learning [master|…2] 
16:22 $ git config --global --list
core.excludesfile=/home/qiaodeli/.gitignore
user.name=qdsz
user.email=qdsz@cn.ibm.com
credential.http://gitlab.cm.ibm.com.username=qdsz@cn.ibm.com
credential.helper=cache --timeout=46800
push.default=current
credential.https://gitlab.event.ibm.com.username=qdsz@cn.ibm.com
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
✔ ~/Documents/git_learning [master|…2] 
``` 


