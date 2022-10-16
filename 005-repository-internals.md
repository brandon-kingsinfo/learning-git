# local git repository is contained in the .git folder

# to remove the local repo, remove the .git folder

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ ls -al
total 9
drwxr-xr-x 1 brandonh 197121 0 Oct 16 13:10 ./
drwxr-xr-x 1 brandonh 197121 0 Oct 16 15:33 ../
drwxr-xr-x 1 brandonh 197121 0 Oct 16 15:44 .git/
-rw-r--r-- 1 brandonh 197121 43 Oct 16 13:10 README.md

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ rm -rf .git

# here we are no longer in the master branch

# because the repo has been deleted

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo

# to initialize an existing project folder

$ git init .
Initialized empty Git repository in D:/git-demo/.git/

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)
README.md

nothing added to commit but untracked files present (use "git add" to track)

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)

# create second-file.md

# we can stage all files in the current directory

$ git status
On branch master

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)
README.md
second-file.md

nothing added to commit but untracked files present (use "git add" to track)

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git add .

# now we have 2 files waiting to be commited

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master

No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: README.md
new file: second-file.md

# when commiting changes, if you don't provide -m switch, # git will lauch default editor to edit the message

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git commit
[master (root-commit) 300a3a0] this commit includes 2 files README.md, second-file.md
2 files changed, 34 insertions(+)
create mode 100644 README.md
create mode 100644 second-file.md
