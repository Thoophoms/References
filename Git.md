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


# Push Your Own Project to Github

**Username:** Your GitHub username

**Token:** Your GitHub token

### 1. In the IntelliJ IDEA terminal, configure Git with your GitHub username

```
git config --global user.name "Username"
```

***Note:*** Replace Username with your GitHub username

### 2. In the IntelliJ IDEA terminal, configure Git with your GitHub email

```
git config --global user.email "thoophom.su@gmail.com" 
```
***Note:*** Replace email with your GitHub email address


### 3. Use CLI to login

***Note:*** if you don't have one, you can install it

`brew install gh`

If you already have it follow the instruction

`gh auth login`

You will see something like this, click enter

> What account do you want to log into?  [Use arrows to move, type to filter]
>
> ">" GitHub.com
>
>GitHub Enterprise Server

Then, you will see the below chose HTTP

> ? What is your preferred protocol for Git operations on this host?  [Use arrows to move, type to filter]
>
> ">" HTTPS
>
> SSH

Then, you will see the below, type Y

> Authenticate Git with your GitHub credentials? (Y/n)

Then, you will see below, select paste an authentication token

> How would you like to authenticate GitHub CLI?  [Use arrows to move, type to filter]
>
> Login with a web browser
>
> ">" Paste an authentication token

Then, it will ask you to place token you just created

> ? Paste your authentication token: 

