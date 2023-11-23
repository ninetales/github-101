# GitHub 101

**git init**
> Initializes a new Git repository in the current directory, creating the necessary data structures and files to start version control for a project.

**git clone**
> Clones an existing Git repository, copying all files, commit history, and branches to create a duplicate on your local machine.

**git config**
> Configures your Git installation, allowing you to set user-specific settings like your name and email address. These settings are crucial for identifying the author of commits.

**git add**
> Adds changes in your working directory to the staging area, preparing them to be included in the next commit. Staging allows for selective inclusion of changes.

**git commit**
> Records the changes in the staging area as a new commit, creating a snapshot in the project's history. Each commit is uniquely identified by a hash and includes details like the author, timestamp, and a descriptive commit message.

**git diff**
> Displays the differences between the working directory and the last committed version, providing a detailed overview of changes made to files.

**git stash**
> Temporarily saves changes that are not ready to be committed. This is useful when switching branches or resolving conflicts without committing incomplete work.

**.gitignore**
> Specifies files or directories that Git should ignore, preventing them from being tracked or committed. This is valuable for excluding files generated during the development process.

**git status**
> Shows the current status of your repository, indicating which files have been modified, staged, or committed. It helps you keep track of changes in your project.

**git tag**
> Adds a tag to a specific commit, often used to mark releases or significant points in the project's history. Tags provide human-readable names to specific commits.

**git blame**
> Annotates each line in a file with commit information, revealing who made each change and when. It helps in understanding the evolution of a file.

**git checkout**
> Switches between branches or to a specific commit, allowing you to explore the project's history and work on different versions.

**git clean**
> Removes untracked files from the working directory, helping to keep the project clean by getting rid of unnecessary files.

**git revert**
> Creates a new commit that undoes the changes made in a previous commit. It's a safe way to reverse changes without altering the project's history.

**git reset**
> Unstages changes or moves the branch pointer to a different commit, providing a tool to selectively rewrite history.

**git rm**
> Removes files from both the working directory and the Git repository, indicating that they should no longer be tracked.

**git rebase**
> Rearranges or combines commits to create a more linear and cleaner project history. It's a way to manage and organize commits.

**git reflog**
> Maintains a log of reference updates, allowing you to recover lost commits or branches that may have been accidentally deleted.

**git remote**
> Lists the remote repositories connected to your local repository. It provides information about where your code is being stored remotely.

**git fetch**
> Retrieves changes from a remote repository, allowing you to review them before merging. This operation updates your local repository without automatically merging the changes.

**git push**
> Uploads your local commits to a remote repository, updating the remote branch with your latest changes.

**git pull**
> Fetches changes from a remote repository and automatically merges them into your local branch, ensuring your local version is up-to-date with the remote repository.

# General Instructions

## How to clone a repo and start working in a branch
Note: Origin is referring to the remote repository. Therefore, when you run git push origin <new-branch-name>, it pushes your new branch to the remote repository named "origin". It's essentially a shortcut for specifying the full URL of the remote repository.

1. On GitHub.com, navigate to the main page of the repository.
2. Above the list of files, click Code.
3. Copy the URL for the repository.
4. Open Terminal.
5. Change the current working directory to the location where you want the cloned directory.
6. Type git clone, and then paste the URL you copied earlier.
   
```
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
```

7. In the terminal, create a new branch to work in:

```
git checkout -b <new-branch-name>
```

8. Stage the files after making any changes

```
git add .
```

9. Commit the files with a description
```
git commit -m "Describe changes"
```

10. Push branch to Github
```
git push origin <new-branch-name>
```

Source: https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository

## If someone creates a pull request and approves a merge to main (default branch)


#### If you are the person that is merging a pull request

> Inform the other teammates that they should do a pull to their local main branch to get the latest updates.

#### If you are the person that needs to update its main branch locally

1. Checkout your main (default) branch and make a "pull" to update the local branch.
```
git checkout main
git pull origin main
```

2. After the update, change back to chosen branch:
``` 
git checkout <chosen-branch>
```

3. In the chosen branch, merge the update from the main to the chosen branch
```
git merge main
```

4. If any conflicts arrises during the merge of main to chosen branch, you might have to solve them manually and then commit the changes.

Stages all files that are currently tracked by Git for the next commit. Can be read as "git add all".
```
git add .
```

```
git commit -m "Merge branch 'main' into <current branch here>"
```

5. After these steps, push the updated branch to GitHub if needed
```
git push origin <chosen-branch>
```

