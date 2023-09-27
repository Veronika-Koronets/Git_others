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


git diff
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

```
kv@kvPC MINGW64 /d/16.08 (main)
$ git commit
Aborting commit due to empty commit message.

kv@kvPC MINGW64 /d/16.08 (main)
$ git commit -v
[main cb9dd8e] commit
 1 file changed, 1 insertion(+)
```

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
