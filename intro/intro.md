# Understanding the Basics of GitHub

```{figure} ../figures/GitHub.png
:alt: GitHub
:width: 150
``` 
GitHub is a platform for version control and collaboration, primarily
designed to facilitate software development. It is built on top of Git,
and provides a web-based interface that simplifies many aspects of Git's 
functionality, making it more accessible and easier to use, especially 
for those who are new to version control systems.


``````{admonition} Git
```{image} ../figures/Git-logo.png
:alt: Git
:width: 70
:align: left
``` 
\
Git is a distributed version control system created by Linus Torvalds in 2005, 
which allows developers to track changes in their code over time and 
collaborate with others seamlessly
``````

## Key Concepts

### Repository (Repo)
A repository is a storage space where a project and its files are kept. 
It contains all the project's files and the entire revision history 
of each file. Repositories can be public, allowing anyone to view and 
contribute, or private, restricting access to specific users. 
They are the central hub for all the activity in a project, 
including code, documentation, and issues.

### Branch
A branch is a parallel version of a repository. It allows you to work 
on different versions of a project simultaneously. The main branch, 
often called "main" or "master," is considered the production-ready 
version of the project. Developers create branches to develop features, 
fix bugs, or experiment without affecting the main branch. 
Once the work on a branch is complete, it can be merged back into the main branch.

### Commit
A commit is a record of changes made to the files in a repository. 
Each commit has a unique ID and contains a message describing the changes made. 
Commits allow you to track the history of changes in a project, providing a 
detailed timeline of how the project has evolved over time. 
They act as snapshots of the project at specific points, which can be reverted 
to if needed.

### Pull Request (PR)
A pull request is a method of proposing changes to a repository. 
When you create a pull request, you ask the repository maintainers 
to review and merge your changes into the main branch. Pull requests 
facilitate collaboration by allowing team members to discuss and 
review code before it is merged. They provide a structured way to 
manage changes and ensure code quality.

### Merge
Merging is the process of integrating changes from one branch into another. 
When a pull request is approved, the changes are merged into the main branch, 
incorporating the new code into the project. Merging ensures that updates 
and new features developed in separate branches are consolidated into the 
main codebase.

### Fork
A fork is a personal copy of another user's repository. 
Forking a repository allows you to freely experiment with changes without 
affecting the original project. You can make changes in your fork, 
and if you want those changes to be incorporated into the original 
repository, you can submit a pull request.

### Issue
An issue is a way to track enhancements, tasks, and bugs for a project. 
Issues can be assigned to specific users, labeled, and organized into milestones. 
They provide a clear way to manage and prioritize work, ensuring that everyone 
on the team is aware of what needs to be done and any problems that need to 
be addressed.

### Clone
Cloning is the process of creating a local copy of a repository on your computer. 
Cloning allows you to work on a project locally, making changes and committing 
them before pushing them back to the remote repository on GitHub. 
It enables offline development and testing.

### GitHub Actions
GitHub Actions is an automation tool integrated into GitHub that allows you 
to automate your software development workflows. With GitHub Actions, 
you can create workflows that build, test, and deploy your code whenever 
there is a change in your repository. It enables continuous integration 
and continuous deployment (CI/CD) directly from your repository.

:::{attention}
GitHub Actions will not be covered in this workshop, but it is a powerful
tool that you should explore to streamline your development process.
:::

## Workflow

The typical workflow in GitHub involves the following steps:

1. **Create a Repository**: Start by creating a new repository on GitHub. 
   You can initialize the repository with a README file, a .gitignore file, 
   and a license to get started quickly.
2. **Clone the Repository**: Clone the repository to your local machine 
   using Git. This creates a local copy of the repository that you can work on.
3. **Create a Branch**: Create a new branch to work on a specific feature 
   or bug fix. This keeps your changes isolated from the main branch until 
   they are ready to be merged.
4. **Make Changes**: Make changes to the files in your repository. 
   Add new files, modify existing files, or delete files as needed.
5. **Commit Changes**: Commit your changes to the branch with a descriptive 
   message. Commits create a snapshot of the project at that point in time.

:::{warning}
You will need to install Git on your local machine to use the Git commands.
For this, you can follow the instructions provided on the [Git website](https://git-scm.com/).
:::
