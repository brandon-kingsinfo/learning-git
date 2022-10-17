# prepare for first commit
### create README.md
```bash
brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ ls
README.md
```
### this shows we have untracked files, README.md
```bash
brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)
README.md

nothing added to commit but untracked files present (use "git add" to track)
```
### add README.md to "staging area"
```bash
brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git add README.md

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git status
On branch master

No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: README.md
```
### first commit
```bash
brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ git commit -m "first file in the repo"
[master (root-commit) f90c3bb] first file in the repo
1 file changed, 1 insertion(+)
create mode 100644 README.md
```