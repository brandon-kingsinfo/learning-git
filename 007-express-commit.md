# modify the content of README.md

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)
$ npp README.md

brandonh@DESKTOP-H7TMT89 MINGW64 /d/git-demo (master)

# this show that a "tracked file" README.md has changes not staged

$ git status
On branch master
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: README.md

no changes added to commit (use "git add" and/or "git commit -a")

# to show what files git is tracking

$ git ls-files
README.md
second-file.md

# to stage a file and then proceed to commit in ONE step

$ git commit -a -m "update README.md using express commit"
[master fd825fb] update README.md using express commit
1 file changed, 2 insertions(+)

# now we have 2 commits

$ git log
commit fd825fb0bcd117c271312fe9dc4be19971b68e69 (HEAD -> master)
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date: Sun Oct 16 16:41:15 2022 +0800

    update README.md using express commit

commit 300a3a083cf852bbec881d43d75f80d909da0166
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date: Sun Oct 16 16:14:15 2022 +0800

    this commit includes 2 files
    README.md, second-file.md
