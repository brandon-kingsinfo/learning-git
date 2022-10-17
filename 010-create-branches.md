# create and manage branches
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ ls
README.md  second-file.txt

AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working director
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ git branch
* master
```

### to create and switch to that branch
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ git checkout -b updates
Switched to a new branch 'updates'
```
### note that modification in the main branch is carried forward into the new branch
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (updates)
$ git status
On branch updates
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```
### make some changes to README.md and commit again
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (updates)
$ git add .

AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (updates)
$ git commit -m "adding updates from branch"
[updates 1d23e7b] adding updates from branch
 1 file changed, 4 insertions(+), 2 deletions(-)

AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (updates)
$ git status
On branch updates
nothing to commit, working tree clean
```
### view commit log, HEAD is on the "updates" branch
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (updates)
$ git log
commit 1d23e7b6ccdeb16f9bb1aa48bcbbd786ae0e426d (HEAD -> updates)
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date:   Mon Oct 17 10:07:57 2022 +0800

    adding updates from branch

commit bddaf9e020568df3b0e8b029b2e34d5f6f319ed8 (master)
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date:   Sun Oct 16 17:50:05 2022 +0800

    remove myfile.txt
```

### to merge changes, first switch to master
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (updates)
$ git checkout master
Switched to branch 'master'

AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ git log --all
commit 1d23e7b6ccdeb16f9bb1aa48bcbbd786ae0e426d (updates)
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date:   Mon Oct 17 10:07:57 2022 +0800

    adding updates from branch

commit bddaf9e020568df3b0e8b029b2e34d5f6f319ed8 (HEAD -> master)
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date:   Sun Oct 16 17:50:05 2022 +0800

    remove myfile.txt
```

### merge 'updates' branch into 'master' branch
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ git merge updates
Updating bddaf9e..1d23e7b
Fast-forward
 README.md | 6 ++++--
 1 file changed, 4 insertions(+), 2 deletions(-)
```

### now HEAD, updates, and master all point to the same commit ID, that's the effect of a fast-forward merge

```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ git log --all
commit 1d23e7b6ccdeb16f9bb1aa48bcbbd786ae0e426d (HEAD -> master, updates)
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date:   Mon Oct 17 10:07:57 2022 +0800

    adding updates from branch

commit bddaf9e020568df3b0e8b029b2e34d5f6f319ed8
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date:   Sun Oct 16 17:50:05 2022 +0800

    remove myfile.txt
```

### while on the master branch, we can now delete the 'updates' branch
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ git branch -d updates
Deleted branch updates (was 1d23e7b).
```

### now we no longer have 'updates' associated with the last commit ID, mnote the history didn't go away, just the label, 'updates', did 
```bash
AzureAD+黃俊卿@LAPTOP-AAPM9R32 MINGW64 /d/git-demo (master)
$ git log --all
commit 1d23e7b6ccdeb16f9bb1aa48bcbbd786ae0e426d (HEAD -> master)
Author: Brandon Huang <brandon@kingsinfo.com.tw>
Date:   Mon Oct 17 10:07:57 2022 +0800

    adding updates from branch
```
