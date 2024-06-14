# Git
### Pull, Edit, Push

**Username:** the GitHub's username you want to push the file to

**Token:** GitHub's token that you want to push the file into if not for your repository


## Clone, Edit file, and Push it back to someone repository

1. Clone the repository

`git clone https://Username:Token@github.com/Username/repository.git`

2. cd into the repository

`cd repository`

3. find the file you want to edit

`find . -name "*.m"`

4. Open file and edit the file

`nano src/myfile.m`

5. Git Add

`git add src/myfile.m`

6. Git Commit

`git commit -m "Commit comments"`

7. Git Push

'git push https://username:token@github.com/username/repository.git'

---


---

### Create git local repository

`git init`

### See the hidden file

`ls -a`

### See what file has not been track

`git status`

### add file

`git add filename`

### commit file

```
git commit -m "Message commit in present tense"
```

### see that the message I commit

`git log`

### See what difference between this file and the last file

`git diff filename`


### Get the last version of the file

`get checkout filename`


### Create the remote repository

``` get remote add <name> <url> ```

***Example***

```
git remote add origin https://github.com/Thoophoms/References.git
```

### Push

```
git push -u <remote name> <branch name>
```
***Example***

```
git push -u origin main
```

***Important:*** if this happen after git push

> To https://github.com/<Username>/References.git
> 
> ! [rejected]        main -> main (non-fast-forward)
> 
> error: failed to push some refs to 'https://github.com/<Username>/<Repository>.git'
> 
> hint: Updates were rejected because the tip of your current branch is behind 
> 
> hint: its remote counterpart. Integrate the remote changes (e.g. 
> 
> hint: 'git pull ...') before pushing again. 
> 
> hint: See the 'Note about fast-forwards' in 'git push --help' for details.

Do this:

```
git pull https://github.com/<Username>/<Repository>.git
```

Then, commit again

```
git commit -m "commit message"
```

Then, push

```
git push origin main
```
