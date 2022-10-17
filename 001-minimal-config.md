# Video 3-2. Quick Install on Windows
# minimal configuration after git installation
```bash
git config --global user.name "your name"
git config --global user.email "your@email.com"
```
### To integrate notepad++ to gitbash, add the path to notepad++.exe to your 
### environment, then create an alias in ~/.bash_profile and restart GitBash 

```bash
alias npp='notepad++ -multiInst -nosession'
```bash

### if notepad++ is not selected as the default text editor
```bash
git config --global core.editor 'notepad++ -multiInst -nosession -noPlugin'
```
### test editor configuration
3 this should launch notepad++ and open ~/.gitconfig
```bash
git config --global -e
```
### after installing p4merge
```bash
git config --global diff.tool p4merge
git config --global difftool.p4merge.path "C:/Program Files/Perforce/p4merge.exe"
git config --global difftool.prompt false
git config --global merge.tool p4merge
git config --global mergetool.p4merge.path "C:/Program Files/Perforce/p4merge.exe"
git config --global mergetool.prompt false
```