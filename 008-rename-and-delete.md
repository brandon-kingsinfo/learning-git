# adding a new file example.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ npp example.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master
Untracked files:
(use "git add <file>..." to include in what will be committed)
example.txt

nothing added to commit but untracked files present (use "git add" to track)

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git add example.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git commit -m "adding example file"
[master 1a72bb8] adding example file
1 file changed, 1 insertion(+)
create mode 100644 example.txt

# rename the file to demo.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git mv example.txt demo.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
renamed: example.txt -> demo.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git commit -m "rename example.txt"
[master 270d2fe] rename example.txt
1 file changed, 0 insertions(+), 0 deletions(-)
rename example.txt => demo.txt (100%)

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ ls
README.md demo.txt second-file.md

# to delete a file

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git rm demo.txt
rm 'demo.txt'

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
deleted: demo.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git commit -m "delete demo.txt"
[master 935e24e] delete demo.txt
1 file changed, 1 deletion(-)
delete mode 100644 demo.txt

# managing files outside of git

# (rename or delete files using gitbash command) instead of git command

# to stage all kinds of changes, use git add -A

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ touch myfile.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ ls
README.md myfile.txt second-file.md

# rename the file outside of git

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ mv second-file.md second-file.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master
Changes not staged for commit:
(use "git add/rm <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
deleted: second-file.md

Untracked files:
(use "git add <file>..." to include in what will be committed)
myfile.txt
second-file.txt

no changes added to commit (use "git add" and/or "git commit -a")

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git add -A

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
new file: myfile.txt
renamed: second-file.md -> second-file.txt

# to delete a file

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ rm myfile.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master
Changes not staged for commit:
(use "git add/rm <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
deleted: myfile.txt

no changes added to commit (use "git add" and/or "git commit -a")

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git add -u

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
deleted: myfile.txt

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git commit -m "remove myfile.txt"
[master bddaf9e] remove myfile.txt
1 file changed, 0 insertions(+), 0 deletions(-)
delete mode 100644 myfile.txt
