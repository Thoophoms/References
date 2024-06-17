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

# Push file into your own GitHub

### Cd into your directory

`cd yourDirectory`

### Make file if necessary

`touch fileName`

### If you want to edit that file in the the program

`open -a /Applications/ApplicationName .`

> ***Note: .*** is to open the whole folder/project

After done with editing

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

> To https://github.com/Username/Repository.git
> 
> ! [rejected]        main -> main (non-fast-forward)
> 
> error: failed to push some refs to 'https://github.com/Username/Repository.git'
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

---

### If there is any changes after push or create remote repository

You can edit it and save

Then, add

`git add fileName`

Then, commit

```
git commit -m "You commit message in present tense"
```

Then, push it back

`git push origin main`

___


# Working on the same project you cloned after someone made changed on their side

***Note:*** If you do git pull and this happens

```
git pull https://github.com/TheirUsername/TheirUsername.github.io.git
```

> remote: Enumerating objects: 70, done.
>
> remote: Counting objects: 100% (70/70), done.
>
> remote: Compressing objects: 100% (29/29), done.
> remote: Total 70 (delta 48), reused 60 (delta 40), pack-reused 0
>
> Unpacking objects: 100% (70/70), 17.77 KiB | 96.00 KiB/s, done.
>
> From https://github.com/theirUsername/TheirUsername.github.io
>
> * branch            HEAD       -> FETCH_HEAD
>
> * hint: You have divergent branches and need to specify how to reconcile them.
> * hint: You can do so by running one of the following commands sometime before
> * hint: your next pull:
> * hint:
> * hint:   git config pull.rebase false  # merge
> * hint:   git config pull.rebase true   # rebase
> * hint:   git config pull.ff only       # fast-forward only
> * hint:
> * hint: You can replace "git config" with "git config --global" to set a default
> * hint: preference for all repositories. You can also pass --rebase, --no-rebase,
> * hint: or --ff-only on the command line to override the configured default per
> * hint: invocation.
>
> fatal: Need to specify how to reconcile divergent branches.

The message you encountered means that your local branch and the remote branch have diverged, and Git needs to know how to reconcile the differences between them. You have three options to handle this situation:

1. Merge: This will create a merge commit that combines the changes from both branches.

2. Rebase: This will move your local commits on top of the latest commits from the remote branch.
3. Fast-forward only: This will only update your branch if it can be "fast-forwarded," meaning there are no divergent changes and the remote branch is ahead of your local branch.

To fix the issue, you need to choose one of these options. Here are the commands you can use:

I normally rebase to get the updated version of `Their GitHub`

`git config pull.rebase true`

Then, `git pull`

```
git pull https://github.com/TheirUsername/TheirUsername.github.io.git
```

***BUT*** If this happens

> error: cannot pull with rebase: You have unstaged changes.
>
> error: please commit or stash them.
>
> YourName TheirUsername.github.io % git status
>
> On branch YourBranchName
>
> Changes not staged for commit:
>
> (use "git add <file>..." to update what will be committed)
>
> (use "git restore <file>..." to discard changes in working directory)
>
> modified:   .idea/misc.xml
>
> no changes added to commit (use "git add" and/or "git commit -a")

### Do `git stach` to save what you are working on and then, `pull.rebase`, `pull` again, and make new `branch`

`git stash` is a Git command that allows you to temporarily save changes that you've made to your working directory but are not ready to commit. This is useful when you want to switch branches, pull updates, or perform other Git operations without losing your current work. When you stash changes, Git takes the uncommitted changes (both staged and unstaged) and saves them on a stack. You can then apply these changes later when you're ready.

# `git stash`

## `git config pull.rebase true`

```
git pull https://github.com/TheirUsername/TheirUsername.github.io.git
```

### `git checkout -b newBranchName`

---


### Remove all file we just add from using git add .

`git rm —cached -r  .`

### To check if all files have been removed from the staging area

`git status`

### Using `.gitignore` file to add all the file you wanted to be ignore and do not want to add them in the GitHub

If there is no `gitignore` in your project, you can create one

`touch .gitignore`

1. Open .gitignore file
2. Simply add each file in the `.gitignore` file

   ***Example:***

   	`.DS_Store`
   	`Secrets.txt`

   ***Rules:***

   	1. Comment with #: # This is a comment
   	
   	2. * to add all the file

   		***Example:***
   		
   			*.txt

---

# Branching and Merging

You can do a parallel work with the main branch and parallel branches and later on you would like to merge it together

### Check what branch you are current branch

`git branch`

### go to the new branch

`git checkout branch-name`

### Merge branch

go to the main branch (what you'd like to merge the branch into)

`git merge brach-name`

Then, the vim will be opened to have you add comments/notes, if there's nothing to be added

`:q!` - to quit the vim

Then push with -u

```
git push origin main -u
```

___

# Forking and Pull Requests

***On GitHub Website***

1. go into their repository

`fork`

2. Make some changes

3. Commit changes

4. click on `<> Code` tab
   - click on `New Pull Request`
   - click on `Create pull request`
     - Put the comment
     - click `Create pull request`

***On Owner GitHub Website***

The owner will see the pull request and will be able to compare their code and the new code we made and if they are satisfy with the modify codes, they will be able to merge it.

1. Click `Review changes`
2. Add comments
3. Click `Approve`
4. Click `Submit Review`
5. Click `Merge pull request`
6. Add comment
7. Click `Merge`

### Working on Forking and Pull Requests on terminal on IntelliJ

1. Fork the repository on GitHub
   - Go to their repository in GitHub.com and click `fork` to create your own copy
2. Clone the forked repository

```
git clone https://github.com/your-username/repository-name.git
```

3. Navigate into the cloned repository

```
cd repository-name
```

4. Add the Originally Repository as remote:

   -  This step allows you to keep your fork updated with the original repository.

```
git remote add upstream https//github.com/original-username/repository-name.git
```

5. Create a new branch for the changes

```
git checkout -b your-branch-name
```

6. Make Your Changes

7. Add and Commit your changes

`git add file-name`

```
git commit -m "Your commit message"
```

8. Push your changes to GitHub

```
git push origin your-branch-name
```

9. Create a Pull request

   - Go to your forked repository on GitHub
   - Click `Compare & pull request`
   - Add necessary comments
   - Click `submit the pull request`

___


