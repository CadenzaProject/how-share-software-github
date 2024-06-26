# Making Changes

## Cloning a Repository

To start working in your repository, you need to make a **local copy** of it
(a copy in your computer), which allows you to work on it offline. 
This action is called **cloning** the repository. 
The command to clone a repository with **GIT** is `git clone`. 

To clone a repository, follow these steps:

1. In you computer, open a terminal window.
2. CD to the directory where you want to clone the repository.
3. Run the following command:

```bash
git clone <repo URL>
cd <repo name>
```

The URL is the URL of the repository you want to clone.
You can get the link directly from GitHub

```{figure} ../figures/clone.png
:name: empty-repo
An empty repository
```

```{figure} ../figures/clone_2.png
:name: no-empty-repo
A repository with files.
```

`git clone` will create a directory in your computer with the same name as the repository.

![git-clone.png](../figures/git-clone.png)

:::{note}
Don't worry about the warning message in this case, it is just a message that the repository is empty.
:::

## Making changes to your repo

After cloning the repository, you can make changes to it like
adding files, modifying files, etc.

:::{admonition} README.md file
One key file on all GitHub repositories is the `README.md` file.
This file is used to describe the repository, its content, and how to use it.
It is the first file that users see when they access the repository.

The format of this file is called [**Markdown**](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax). 
Which is a lightweight markup language with plain text formatting syntax.

A good example of this is the `README.md` file of the [PyClarity repository](https://github.com/claritychallenge/clarity/blob/main/README.md).
As you can see in this file, it provides an introduction to the project, how to install it, how to use it,
and what are the current and previous challenges.

```{figure} ../figures/clarity_readme-md.png
:name: Clarity readme

PyClarity Readme for Clarity and Cadenza Projects
```

:::


## Adding files

We created our repository without a default `README.md` file.
Let's create one now.

1. In your computer, inside the repository directory, create a new file named `README.md`.
2. Open the file with your favorite text editor.
3. Add the following content:

```markdown
# VCCA 2024 - My Repo

This is the landing page for the demo repo created for VCCA 2024 workshop on sharing with GitHub.
```

4. Save the file.

![README.md](../figures/readme-md.png)

Now, you have a `README.md` file in your local copy of your repository.
To add this file to the online repository, you need to **commit** the changes.

### Committing changes

When you make changes to your repository, you need to **commit** them.  
A commit is a snapshot of the changes you made at a specific time.

To commit changes, follow these steps:

1. Open a terminal window.
2. CD to the directory of your repository.
3. Run the following command:

```bash
git add README.md
git commit -m "Add README.md file"
```

The `git add` command is used in Git, to add changes in the working directory to the staging area. 
The staging area (or index) is an intermediate area where changes are gathered before they are committed to the repository.

Usage:
* `git add <file>`: Add a specific file to the staging area. Like we did with the `README.md` file.
* `git add .`: Add all files in the working directory to the staging area (Note the ` . ` at the end).
* `git add -i`: This opens an interactive interface to select changes to be staged.

Now that the file is `staged` (in the staging area) we can commit it.

The `git commit` command is used in Git to save changes from the staging area to the repository. 
This command creates a new commit containing the changes that have been staged, 
along with a message that describes the changes.

Usage:
* `git commit -m "Descriptive commit message"`: This is the most common way to commit changes. The `-m` flag allows you to add a commit message directly from the command line.
* `git commit -a -m "Commit message"`: The `-a` flag (or `--all`) will automatically stage any tracked,  
modified files before the commit, skipping the `git add` step. However, this will not stage new (untracked) files. 


:::{admonition} Best Practices
:class: attention
* **Write Meaningful Commit Messages**: The message should short describing the changes made. This helps other collaborators understand the history of changes.
* **Commit Often**: Frequent, smaller commits are preferable over large, infrequent commits. They make it easier to track changes and find bugs.
* **Use Branches**: When working on a new feature or bug fix, create a new branch. This keeps your work organized and separated from the main codebase until it's ready to be merged.
:::

### Pushing changes

Now is time to update our online repository with the changes we made locally.
For this, we run the `git push` command. 
`git push` command is used in Git to upload local repository content to a remote repository,
by transferring the commits from your local repository to a remote one.

Usage:
* `git push`: This command is used to push commits from your local repository to a remote repository.

:::warning
Before pushing changes, make sure you have the necessary permissions to push to the repository.
:::

![Push.png](../figures/git-push.png)

## How our repository looks now

After pushing the changes, you can see the updated repository on GitHub.

![Repo.png](../figures/repo.png)


## Get information about status of your repository

To get information about the status of your repository, you can use the `git status` command.
This command shows the status of changes as untracked, modified, or staged.
It helps you understand which changes are staged for the next commit, 
which changes are not staged, and which files are not tracked by Git.

For example, I staged one change in our README.md file and then I made more modifications 
without staging them.
When I run `git status` I get the following output:


![status](../figures/status.png)

Another very useful command is `git log`. This command shows the commit logs in reverse chronological order.
This command is useful to see the history of changes in the repository.
There are many options to format the output of `git log`, you can check them in the [official documentation](https://git-scm.com/docs/git-log).
The most common are:

* **git log --oneline**: Displays a summary with each commit on a single line.
* **git log -n <number>**: Limits the log output to the specified number of commits.
* **git log --graph**: Shows a text-based graphical representation of the commit history.
* **git log --author=<name>**: Filters commits by a specific author.
* **git log --since=<date>**: Shows commits more recent than a specific date.
* **git log --until=<date>**: Shows commits older than a specific date.


## Undoing changes

Sometimes you make changes that you want to undo.
There are several ways to undo changes in Git, depending on the type of change you want to undo.

### Unstaging changes

If you have staged changes that you want to unstage, you can use the `git reset` command.
This command is used to reset the current HEAD to the specified state.

Usage:
* `git reset HEAD <file>`: Unstages the specified file, but keeps the changes in the working directory.
* `git reset HEAD`: Unstages all changes in the staging area.

### Discarding changes

If you want to discard changes in the working directory, you can use the `git checkout` command.
This command is used to update files in the working directory to match the version in the index or the specified commit.

Usage:

* `git checkout -- <file>`: Discards changes in the working directory for the specified file.
* `git checkout .`: Discards changes in the working directory for all files.

### Reverting commits

If you want to undo a commit, you can use the `git revert` command.
This command creates a new commit that undoes the changes made by a previous commit.

Usage:

* `git revert <commit>`: Reverts the changes made by the specified commit.

For more information on undoing changes in Git, you can check:
* [Git official documentation](https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things).
* [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials/undoing-changes).
