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

`git add -u` Only add the Updated files to stage area

### Rename a git managed file

```
✔ ~/Documents/git_learning [master|…2] 
16:49 $ mv git_learning_master.zip git_learning.zip
✔ ~/Documents/git_learning [master|✚ 1…3] 
16:50 $ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  deleted:    git_learning_master.zip

  git_learning.zip

no changes added to commit (use "git add" and/or "git commit -a")
✔ ~/Documents/git_learning [master|✚ 1…3] 
16:50 $ git add git_learning.zip 
git_learning_master.zip  Playing_with_git.pdf
git_learning.zip         .README.md.swp
✔ ~/Documents/git_learning [master|✚ 1…3] 
16:50 $ git add git_learning.zip 
✔ ~/Documents/git_learning [master|●1✚ 1…2] 
16:51 $ git rm git_learning_master.zip 
rm 'git_learning_master.zip'
✔ ~/Documents/git_learning [master|●1…2] 
16:52 $ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  renamed:    git_learning_master.zip -> git_learning.zip

Untracked files:
  (use "git add <file>..." to include in what will be committed)

  .README.md.swp
  Playing_with_git.pdf

✔ ~/Documents/git_learning [master|●1…2] 
16:52 $ git reset --hard
HEAD is now at 3266409 initial update for git_learning_master.zip
✔ ~/Documents/git_learning [master|…2] 
16:53 $ ll
total 3092
-rw-rw-r--. 1 qiaodeli qiaodeli   22859 Dec 26 16:53 git_learning_master.zip
drwx------. 2 qiaodeli qiaodeli    4096 Nov 27 16:47 images
-rw-r--r--. 1 qiaodeli qiaodeli    1391 Dec 26 16:42 index.html
drwx------. 2 qiaodeli qiaodeli    4096 Nov 27 16:47 js
-rw-rw-r--. 1 qiaodeli qiaodeli 3114005 Dec 26 16:31 Playing_with_git.pdf
-rw-rw-r--. 1 qiaodeli qiaodeli    1221 Dec 26 16:29 README.md
drwx------. 2 qiaodeli qiaodeli    4096 Nov 27 16:47 styles
✔ ~/Documents/git_learning [master|…2] 
16:53 $ git mv git_learning_master.zip git_learning.zip
✔ ~/Documents/git_learning [master|●1…2] 
16:53 $ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  renamed:    git_learning_master.zip -> git_learning.zip

Untracked files:
  (use "git add <file>..." to include in what will be committed)

  .README.md.swp
  Playing_with_git.pdf

✔ ~/Documents/git_learning [master|●1…2] 
16:54 $ ll
total 3092
-rw-rw-r--. 1 qiaodeli qiaodeli   22859 Dec 26 16:53 git_learning.zip
drwx------. 2 qiaodeli qiaodeli    4096 Nov 27 16:47 images
-rw-r--r--. 1 qiaodeli qiaodeli    1391 Dec 26 16:42 index.html
drwx------. 2 qiaodeli qiaodeli    4096 Nov 27 16:47 js
-rw-rw-r--. 1 qiaodeli qiaodeli 3114005 Dec 26 16:31 Playing_with_git.pdf
-rw-rw-r--. 1 qiaodeli qiaodeli    1221 Dec 26 16:29 README.md
drwx------. 2 qiaodeli qiaodeli    4096 Nov 27 16:47 styles
✔ ~/Documents/git_learning [master|●1…2] 
16:54 $ git commit -m "rename git_learning.zip"
[master 868e356] rename git_learning.zip
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename git_learning_master.zip => git_learning.zip (100%)
✔ ~/Documents/git_learning [master|…2] 
16:54 $ git log
commit 868e3565f11987616b72b17461f1aa4a7a431a2d (HEAD -> master)
Author: qiaodeli <qiaodeli111@126.com>
Date:   Wed Dec 26 16:54:43 2018 +0800

    rename git_learning.zip
```

### git log

```
git log --oneline
git log -n4 --oneline
git log -n4 --oneline --graph
```

### gitk -- Graphic git client

### .git

.git/HEAD -> .git/refs/head/master - Tell us which branch we are working on

.git/config - Local configuration file. Equals to "git config --local --list"

```
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:07 $ cat .git/refs/heads/master 
4d582352b9f2bd9b7a375815f838f78b3bf0bf7d
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:08 $ git cat-file -t 4d582352b9f2bd9b7a375815f838f78b3bf0bf7d
commit
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:10 $ git branch -av
* master 4d58235 updated README.md
  temp   700180f modified README.md
✔ ~/Documents/git_learning [master|✚ 1…2] 
```

```
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:11 $ cat .git/refs/tags/jstag 
bc7aec68db069e5a315f2208ae0bdf32eff8c82f
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:12 $ git cat-file -t bc7aec68db069e5a315f2208ae0bdf32eff8c82f
tag
✘-129 ~/Documents/git_learning [master|✚ 1…2] 
22:13 $ git cat-file -p bc7aec68db069e5a315f2208ae0bdf32eff8c82f
object 35892b1c763ad88eb5069b271d5d10363504c74c
type commit
tag jstag
tagger qiaodeli <qiaodeli111@126.com> 1545832716 +0800

js tag
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:13 $ git log --oneline
4d58235 (HEAD -> master) updated README.md
868e356 rename git_learning.zip
3266409 initial update for git_learning_master.zip
bd19959 Add refering projects
35892b1 (tag: jstag) Add js
377fbc8 Add style.css
593f246 Add index + logo
94c8215 Add README.md
```

```
[qiaodeli@oc7724824778 b4]$ pwd
/home/qiaodeli/Documents/git_learning/.git/objects/b4
[qiaodeli@oc7724824778 b4]$ ll
total 4
-r--r--r--. 1 qiaodeli qiaodeli 218 Dec 26 17:11 0027890f7d68dcc5f260cfe54283ef812cab2b
[qiaodeli@oc7724824778 b4]$ git cat-file -t b40027890f7d68dcc5f260cfe54283ef812cab2b
tree
[qiaodeli@oc7724824778 b4]$ git cat-file -p b40027890f7d68dcc5f260cfe54283ef812cab2b
100644 blob 5359dadf629c9ef2a86d99f22c1ac967dba1b16f  README.md
100644 blob cef280599b90f3292b932e05cb5b0d15b974ee88  git_learning.zip
040000 tree 96b67e399c8496ec36cbbbcb776eb924fad7f9a7  images
100644 blob 876306b3624db161e7f4e59def735996835d08f6  index.html
040000 tree 87b3e92f70e7dfa555f141afeae28a2bc4a343b6  js
040000 tree aee37060401d19e7bd9f80b7b33920a000e96b5b  styles
[qiaodeli@oc7724824778 b4]$ git cat-file -t 5359dadf629c9ef2a86d99f22c1ac967dba1b16f
blob
[qiaodeli@oc7724824778 b4]$ git cat-file -p 5359dadf629c9ef2a86d99f22c1ac967dba1b16f
****

```


```
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:28 $ git log --oneline
4d58235 (HEAD -> master) updated README.md
868e356 rename git_learning.zip
3266409 initial update for git_learning_master.zip
bd19959 Add refering projects
35892b1 (tag: jstag) Add js
377fbc8 Add style.css
593f246 Add index + logo
94c8215 Add README.md
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:34 $ git cat-file -p 377fbc8
tree 25b87c87b925bffa465fb16e8f943385624663c0
parent 593f246e2a8101360bbe6f14ff3618b68f0da194
author qiaodeli <qiaodeli111@126.com> 1545813555 +0800
committer qiaodeli <qiaodeli111@126.com> 1545813555 +0800

Add style.css
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:34 $ git cat-file -p 25b87c87b925bffa
100644 blob f1f56a988b3b75814e93999081ef7aa4dcca4752  README.md
040000 tree 96b67e399c8496ec36cbbbcb776eb924fad7f9a7  images
100644 blob 6ad4c68d567a1a5b415dcfce2010fce1a60b245f  index.html
040000 tree aee37060401d19e7bd9f80b7b33920a000e96b5b  styles
✔ ~/Documents/git_learning [master|✚ 1…2] 
22:35 $ git cat-file -p 6ad4c68d567
<!DOCTYPE html>
<html>
<head>
    <title>Git Demo</title>
    <link rel="stylesheet" type="text/css" href="styles/style.css">
</head>
<body>
    <header>
```


### Detached HEAD

```
git checkout <commit-id>
git branch -av
git checkout master
git branch fix_css <commit-id>
```

### HEAD always point to a commit!

```
1058  git checkout fix_readme
1059  git log
1060  git diff HEAD 593f246e2a8101360bbe6f14ff3618b68f0da194
1061  git diff HEAD HEAD^1
1062  git diff HEAD HEAD^^1
1063  git diff HEAD HEAD~2
```

### Delete a branch

```
git branch -d <branch_name>
git branch -D <branch_name>
```

### Modify the last commit message

```
git commit --amend
```

### Modify any commit message

```
✔ ~/Documents/git_learning [master|…2⚑ 1] 
12:19 $ git log --oneline -n4
369091a (HEAD -> master) Updating latest note
20a5689 updating readme to include the latest log
a71b762 Uploading pdf file
78de540 Updating readme
✔ ~/Documents/git_learning [master|…2⚑ 1] 
12:19 $ git rebase -i 78de540
[detached HEAD 0280a71] Uploading the pdf file
 Date: Wed Dec 26 23:03:16 2018 +0800
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 Playing_with_git.pdf
Successfully rebased and updated refs/heads/master.
✔ ~/Documents/git_learning [master|…2⚑ 1] 
12:20 $ git log --oneline -n4
94fc302 (HEAD -> master) Updating latest note
8225415 updating readme to include the latest log
0280a71 Uploading the pdf file
78de540 Updating readme
```

### Combine commits

```

