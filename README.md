# Git_others

## 1.1. To clone a remote repository with a different name 
``git clone`` ***link*** **new name of repo**
```
kv@kvPC MINGW64 /d
$ git clone https://github.com/Veronika-Koronets/15.08.git 16.08
Cloning into '16.08'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.

kv@kvPC MINGW64 /d
$ cd 16.08
```
## 1.2. git init 

## 2. git status
``git status -s`` or ``git status --short`` 

```
kv@kvPC MINGW64 /d/16.08 (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   2.txt
        new file:   README

kv@kvPC MINGW64 /d/16.08 (main)
$ git status -s
A  2.txt
A  README

kv@kvPC MINGW64 /d/16.08 (main)
$ cat >> 2.txt
55566

kv@kvPC MINGW64 /d/16.08 (main)
$ cat 2.txt
111
334455
55566

kv@kvPC MINGW64 /d/16.08 (main)
$ git status -s
AM 2.txt
A  README
```


## 3. git diff
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git diff
warning: in the working copy of '2.txt', LF will be replaced by CRLF the next time Git touches it
diff --git a/2.txt b/2.txt
index ef3ef28..95dc1b9 100644
--- a/2.txt
+++ b/2.txt
@@ -1,2 +1,3 @@
 111
 334455
+55566
```

``git diff --staged`` or ``git diff --cached``
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git diff --staged
diff --git a/2.txt b/2.txt
new file mode 100644
index 0000000..ef3ef28
--- /dev/null
+++ b/2.txt
@@ -0,0 +1,2 @@
+111
+334455
diff --git a/README b/README
new file mode 100644
index 0000000..56266d3
--- /dev/null
+++ b/README
@@ -0,0 +1 @@
+My Project
```


## 4. 
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git commit
Aborting commit due to empty commit message.

kv@kvPC MINGW64 /d/16.08 (main)
$ git commit -v
[main cb9dd8e] commit
 1 file changed, 1 insertion(+)
```


## 5. 
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git rm --cached README
rm 'README'

kv@kvPC MINGW64 /d/16.08 (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    123
        deleted:    README

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README
```

```
kv@kvPC MINGW64 /d/16.08 (main)
$ git rm -f README
rm 'README'

kv@kvPC MINGW64 /d/16.08 (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    123
        deleted:    README
```


## 6. git mv
```
kv@kvPC MINGW64 /d/16.08 (main)
$ ls -la
total 14
drwxr-xr-x 1 kv 197121  0 Aug 19 19:18 ./
drwxr-xr-x 1 kv 197121  0 Aug 15 20:12 ../
drwxr-xr-x 1 kv 197121  0 Aug 19 19:18 .git/
-rw-r--r-- 1 kv 197121 25 Aug 19 18:44 2.txt
-rw-r--r-- 1 kv 197121  7 Aug 15 20:12 README.md

kv@kvPC MINGW64 /d/16.08 (main)
$ git mv 2.txt 4.txt

kv@kvPC MINGW64 /d/16.08 (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    123
        renamed:    2.txt -> 4.txt
        deleted:    README
```



## 7. git log
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git log
commit cb9dd8e102b5f3b5297e594d695c6d118c542a66 (HEAD -> main)
Author: Veronika-Koronets <koronec.v@mail.ru>
Date:   Sat Aug 19 18:46:00 2023 +0300

    commit

commit 2197819d515f514013ca73b09dba3bd2d01de2f1
Author: Veronika-Koronets <koronec.v@mail.ru>
Date:   Sat Aug 19 17:59:09 2023 +0300

     #

commit 9a3229513413b5e873c0b99e3018b3f7faa8488b (origin/main, origin/HEAD)
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Tue Aug 15 20:13:23 2023 +0300

    Create 123

commit 0dbadb73df68c01ee9d267de812772fa70c99737
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Tue Aug 15 20:10:42 2023 +0300

    Initial commit
(END)
```

git log -p 
```

kv@kvPC MINGW64 /d/16.08 (main)
$ git log -p -2
commit cb9dd8e102b5f3b5297e594d695c6d118c542a66 (HEAD -> main)
Author: Veronika-Koronets <koronec.v@mail.ru>
Date:   Sat Aug 19 18:46:00 2023 +0300

    commit

diff --git a/2.txt b/2.txt
index 31b46ad..7c0b0c7 100644
--- a/2.txt
+++ b/2.txt
@@ -2,3 +2,4 @@
 334455
 55566
 789
+yui

commit 2197819d515f514013ca73b09dba3bd2d01de2f1
Author: Veronika-Koronets <koronec.v@mail.ru>
Date:   Sat Aug 19 17:59:09 2023 +0300

     #

diff --git a/2.txt b/2.txt
```

git log --stat
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git log --stat
commit cb9dd8e102b5f3b5297e594d695c6d118c542a66 (HEAD -> main)
Author: Veronika-Koronets <koronec.v@mail.ru>
Date:   Sat Aug 19 18:46:00 2023 +0300

    commit

 2.txt | 1 +
 1 file changed, 1 insertion(+)

commit 2197819d515f514013ca73b09dba3bd2d01de2f1
Author: Veronika-Koronets <koronec.v@mail.ru>
Date:   Sat Aug 19 17:59:09 2023 +0300

     #

 2.txt  | 4 ++++
 README | 2 ++
 2 files changed, 6 insertions(+)

commit 9a3229513413b5e873c0b99e3018b3f7faa8488b (origin/main, origin/HEAD)
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Tue Aug 15 20:13:23 2023 +0300
```

git log --pretty
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git log --pretty
commit cb9dd8e102b5f3b5297e594d695c6d118c542a66 (HEAD -> main)
Author: Veronika-Koronets <koronec.v@mail.ru>
Date:   Sat Aug 19 18:46:00 2023 +0300

    commit

commit 2197819d515f514013ca73b09dba3bd2d01de2f1
Author: Veronika-Koronets <koronec.v@mail.ru>
Date:   Sat Aug 19 17:59:09 2023 +0300

     #

commit 9a3229513413b5e873c0b99e3018b3f7faa8488b (origin/main, origin/HEAD)
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Tue Aug 15 20:13:23 2023 +0300

    Create 123

commit 0dbadb73df68c01ee9d267de812772fa70c99737
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Tue Aug 15 20:10:42 2023 +0300

    Initial commit
```

git log --pretty=oneline
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git log --pretty=oneline
cb9dd8e102b5f3b5297e594d695c6d118c542a66 (HEAD -> main) commit
2197819d515f514013ca73b09dba3bd2d01de2f1  #
9a3229513413b5e873c0b99e3018b3f7faa8488b (origin/main, origin/HEAD) Create 123
0dbadb73df68c01ee9d267de812772fa70c99737 Initial commit
```


## 8. git remote
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git remote
origin

kv@kvPC MINGW64 /d/16.08 (main)
$ git remote -v
origin  https://github.com/Veronika-Koronets/15.08.git (fetch)
origin  https://github.com/Veronika-Koronets/15.08.git (push)
```
git remote rename
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git remote rename origin origin1
Renaming remote references: 100% (3/3), done.

kv@kvPC MINGW64 /d/16.08 (main)
$ git remote
origin1
```
git remote remove
```
kv@kvPC MINGW64 /d/16.08 (main)
$ git remote remove origin1

kv@kvPC MINGW64 /d/16.08 (main)
$ git remote
```
