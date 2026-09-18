## Git hidden folder

There is a hidden folder called ".git" which tells you that our project is a git repo.

If we wanted to create a git repo in a repoless project we use:

```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
# makes changes to readme.md
git add Readme.md
git status
git commit -a -m "add readme file"
```

## Cloning

We can clone 3 ways: HTTPS, SSH and Github CLI

Since we are using GitHub Codespaces we'll create a temporary dir in our workspace

```sh
mkdir /workspace/tmp
cd /workspace /tmp
```

### HTTPS

```sh
git clone https://github.com/ghosty-oss/Github-Examples.git
cd GitHub-Examples
``` 
> You'll need to generate a Personal Access Token (PAT)
https://github.com/settings/token

You'll use the token when you login

 - Give it access to Contents to Commit


## SSH

```sh
git clone git@github.com:ghosty-oss/Github-Examples.git
cd GitHub-Examples
```

We will need to create our own SSH key pair

```sh
ssh-keygen -t rsa
```

For WSL users and if you create a non default key you might need to add it

```sh
eval 'ssh-agent'
ssh-add /home/folder/directory/.ssh/github_id_rsa
```

We can test our connection here:
```sh
ssh -T git@github.com
```

## GitHub CLI

Install the CLI

eg Linux (Ubuntu)
```sh
sudo apt update
sudo apt install gh -y
```

```sh
gh auth login
gh repo clone ghosty-oss/Github-Examples
```



## Commit

When we want to commit code we can write git commit which will open up the commit edit message in the editor of choice. 

```sh
git commit
```

Set the global editor
```
git config --globl core.editor emacs
```
Make a commit and commit message without opening editor
```sh
git commit -m "add another exclamation mark"
```


## Branches

List of branches

```sh
git branch
```

Create a new branch

```sh
git branch branch-name
```

## Remote

## Stashing

## Merging

## Add

When we want to stage changes that will be included in the commit. We can use the . to add all possible files.

```
git add Readme.md
git add .
```


## Reset

Allows you to move Staged changes to be unstaged. This is usefull when you want to revert all files not to be commited. 

```
git add . 
git reset
```

> git reset will revert git add .

## Status

Shows you what files will or will not be commited. 

```
git status
```

## Gitconfig file

Is what stores your global configurations for git such as email, name, editro, etc. 

Showing contents of our .gitconfig file
```
git config --list
```

When you first install Git on a machine you are supposed to set up your name and email:

```sh
git config --global user.name "John Doe"
git config --global user.email "johndoe@example.com"
```

## Log

git log will show recent git commits to the git tree

```sh
git log
```

## Push

When we want to push a repo to our remote origin 

```
git push
```