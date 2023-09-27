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
## 3. git fetch
```
kv@kvPC MINGW64 /d
$ git clone https://github.com/Veronika-Koronets/1.git
Cloning into '1'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.

kv@kvPC MINGW64 /d
$ cd 1

kv@kvPC MINGW64 /d/1 (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

kv@kvPC MINGW64 /d/1 (main)
$ git fetch
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 658 bytes | 28.00 KiB/s, done.
From https://github.com/Veronika-Koronets/1
   7f18a11..1c9d31e  main       -> origin/main

kv@kvPC MINGW64 /d/1 (main)
$ git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean

kv@kvPC MINGW64 /d/1 (main)
$ git pull
Updating 7f18a11..1c9d31e
Fast-forward
 new_file | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 new_file

kv@kvPC MINGW64 /d/1 (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

kv@kvPC MINGW64 /d/1 (main)
$ ls -la
total 22
drwxr-xr-x 1 kv 197121 0 Sep 27 21:26 ./
drwxr-xr-x 1 kv 197121 0 Sep 27 21:22 ../
drwxr-xr-x 1 kv 197121 0 Sep 27 21:26 .git/
-rw-r--r-- 1 kv 197121 3 Sep 27 21:23 README.md
-rw-r--r-- 1 kv 197121 2 Sep 27 21:26 new_file

kv@kvPC MINGW64 /d/1 (main)
$ git fetch

kv@kvPC MINGW64 /d/1 (main)
$ git fetch
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 2 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (2/2), 660 bytes | 34.00 KiB/s, done.
From https://github.com/Veronika-Koronets/1
   1c9d31e..cefbe8a  main       -> origin/main
```
## git show
```
kv@kvPC MINGW64 /d/1 (main)
$ git show
commit 1c9d31e8ab403cc07f9b06833e0e7693a4741962 (HEAD -> main)
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Wed Sep 27 21:24:35 2023 +0300

    Create new_file

diff --git a/new_file b/new_file
new file mode 100644
index 0000000..8b13789
--- /dev/null
+++ b/new_file
@@ -0,0 +1 @@
+
```
```
kv@kvPC MINGW64 /d/1 (main)
$ git show 7f18a11e674692626e30a6ac6b480fba4d47ee33
commit 7f18a11e674692626e30a6ac6b480fba4d47ee33
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Tue Sep 26 17:33:05 2023 +0300

    Initial commit

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..8b5f678
--- /dev/null
+++ b/README.md
@@ -0,0 +1 @@
+# 1
\ No newline at end of file

kv@kvPC MINGW64 /d/1 (main)
$ git show  1c9d31e8ab403cc07f9b06833e0e7693a4741962
commit 1c9d31e8ab403cc07f9b06833e0e7693a4741962 (HEAD -> main)
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Wed Sep 27 21:24:35 2023 +0300

    Create new_file

diff --git a/new_file b/new_file
new file mode 100644
index 0000000..8b13789
--- /dev/null
+++ b/new_file
@@ -0,0 +1 @@
+

kv@kvPC MINGW64 /d/1 (main)
$ git show  7f18a11..1c9d31e
commit 1c9d31e8ab403cc07f9b06833e0e7693a4741962 (HEAD -> main)
Author: Veronika <130933875+Veronika-Koronets@users.noreply.github.com>
Date:   Wed Sep 27 21:24:35 2023 +0300

    Create new_file

diff --git a/new_file b/new_file
new file mode 100644
index 0000000..8b13789
--- /dev/null
+++ b/new_file
@@ -0,0 +1 @@
+
```
## git reset
```
kv@kvPC MINGW64 /d/1 (main)
$ cat > file.txt
123

kv@kvPC MINGW64 /d/1 (main)
$ git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file.txt

nothing added to commit but untracked files present (use "git add" to track)

kv@kvPC MINGW64 /d/1 (main)
$ git add file.txt

kv@kvPC MINGW64 /d/1 (main)
$ git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   file.txt

kv@kvPC MINGW64 /d/1 (main)
$ git reset file.txt

kv@kvPC MINGW64 /d/1 (main)
$ git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file.txt

nothing added to commit but untracked files present (use "git add" to track)
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

## 5. git rm
``git rm --cached file`` - make tracked file to be untracked
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
``` git rm log/\*.log



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
