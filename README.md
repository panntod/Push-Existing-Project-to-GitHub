# How to Push an Existing Project to GitHub
GitHub is a cloud-hosted Git management tool. Git is distributed version control, meaning the entire repository and history lives wherever you put it. People tend to use GitHub in their business or development workflow as a managed hosting solution for backups of their repositories. GitHub takes this even further by letting you connect with coworkers, friends, organizations, and more.
In this tutorial, you will learn how to take an existing project you are working on and push it so it also exists on GitHub.

## Step 1 
### Create a new GitHub Repo
[![create a new github repo](https://github.com/panntod/Push-Existing-Project-to-GitHub/blob/main/images/create-new-repository.png)
Sign in to GitHub and [create a new empty repo](https://github.com/new). You can choose to either initialize a README or not. It doesn’t really matter because we’re just going to override everything in this remote repository anyway.

## Step 2
### Initialize the Git Repo
Make sure you are in the root directory of the project you want to push to GitHub and run:
```bash
git init
```
This step creates a hidden .git directory in your project folder, which the git software recognizes and uses to store all the metadata and version history for the project.

### Add the files to the Git index
```bash
git add -A
```
The git add command is used to tell git which files to include in a commit, and the -A (or --all) argument means “include all”.

### Commit Added Files
```bash
git commit -m 'Added my project'
```
The git commit command creates a new commit with all the files that have been "added". The -m (or --message) flag sets a message to be included with the commit, which is used as a future reference to understand the commit. learn [semantic commit](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716) for easier teamwork

### Add a new remote origin
```bash
git remote add origin <Your Repository Github Url>
```
In git, a “remote” refers to a remote version of the same repository, which is typically on a server somewhere (in this case, GitHub). “origin” is the default name git gives to a remote server (you can have multiple remotes), so git remote add origin instructs git to add the URL of the default remote server for this repo.

### Push to GitHub
```bash
git push -u -f origin main
```
The -u (or --set-upstream) flag sets the remote origin as the upstream reference. This allows you to later perform git push and git pull commands without having to specify an origin since we always want GitHub in this case.
The -f (or --force) flag stands for force. This will automatically overwrite everything in the remote directory. We’re using it here to overwrite the default README that GitHub automatically initialized.

*Note: If you did not include the default README when creating the project on GitHub, the -f flag isn’t really necessary.
