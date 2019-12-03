# GitHub Tutorial

_by Lydia Ye_

---
## Git vs. GitHub
* **Git:** allows the user to have the power over the versions they've created throughout their ide.
* **Github:** used to collaborate with your peers, which is efficient because your edits don't intervene with the other collaborators.

---
## Initial Setup
Creating a GitHub account:
1. [Go on the GitHub website](https://github.com/)
2. Click sign up to make an account
3. Choose a username and insert your email
4. Create a password

Setting up your IDE:
* Follow the directions on this [link](https://github.com/hstatsep/ide50)
  * *Make sure to read all the instructions carefully*

> **What is an SSH key?**
An SSH key is a way to help users securely connect to their remote device. It's also an alternative way to login without having to input your username and password all the time.    
**Why do we need an SSH key?**
We need an SSH key in order to verify that the user is trying to work/interact with their remotes.

---
## Repository Setup
> **What is an repository?**
An repository is similiar to having a folder within your drive. It's a place to store all your files and your revision history (it can be public or private).

Setting up a repo in your ide (local):
1. Create a new directory that's seperate from your root directory (hint: use `mkdir <file name>`)
2. Once you've created your directory make sure to `cd` into it
3. When you're in your desired location, you can use `git init` to turn it into a repository (now you should be able to see the word "(master)" in your terminal)
4.  In order to use `git add` and `git commit` you must create changes within a file
5.  To create a file use `touch <file name>` and to open up the file use `c9 <filename`
6.  Once you've made changes in your file, you can use `git add` to put the changes onto the stage
7.  By using `git commit -m <message>` you can name the changes you added onto the stage

Using GitHub to create a repository and linking it to your ide: 
1. Firstly, make sure you're logged in on GitHub
2. Navigate for the `+` icon on the top right corner of the site
3. Click on the selection: `New repository`
4. Input the exact repository name as the one on your local ide
5. Once you've hit `Create repository` make sure that your using SSH and not HTTPS
6. On the page look for this:
```
git remote add origin git@github.com:<your github account>/<name of your repository>.git
git push -u origin master
```
7. Go back to your ide and make sure you're at your desire repository
8. Copy and paste the 2 command lines you saw after you finished creating your remote repository on Github. 

---
## Workflow & Commands
* `git status`: helps the user see which files have been edited or changed since the last commit (it will be in red) and which files are staged for the commit (it will be in green)

* `git add`: adds the current/entire directory: all files that have changes (including deleted/renamed files) to the "stage"

* `git commit -m "<message>"`: takes a snapshot of the files on the stage (creates the revision history)

* `git push`: sends any changes made in the local repo (your ide) to the remote repo (on GitHub)

---
## Rolling Back Changes
To undo your edit:
* Use `git checkout -- <filename>` in order to undo the recent changes you've made in your file

To undo your add:
* Use `git reset HEAD <filename>` to remove your changes from the stage

To undo your commit:
* Use `git reset --soft HEAD~1` or `git reset --hard HEAD~1` to undo your last commit 
  * `git reset --soft HEAD~1`: helps preserve the undone changes 
  * `git reset --hard HEAD~1`: permanently deletes the changes 

To undo your push:
* Using `git log` find the SHA or hash for the commit that you want to revert to (make sure to press q to exit out of the log) 
* In your ide type in `git revert <sha/hash>`
* To match your commits from your ide to your remote use `git reset HEAD^ --hard` and `git push origin master`
