# Git and GitHub

```{figure} ../figures/Git-logo.png
:alt: Git
:width: 200
``` 


Git is a distributed version control system created by Linus Torvalds in 2005, 
which allows developers to track changes in their code over time and 
collaborate with others seamlessly. Git offers numerous features and properties, including:

1. **Distributed systems**: Each developer has a local copy of the repository on their machine.
This allows for faster operations since most tasks are performed locally.
2. **Branching and merging**: Developers can create branches to work on specific features or fixes
without affecting the main codebase. Once the work is complete, the changes can be merged back into the main branch.
3. **Data integrity**: Every file and commit are checksummed using SHA-1 hashes, ensuring data integrity.
Commited data are very difficult to alter, providing a reliable history of changes.
4. **Distributed collaboration**: Git supports various workflows for collaborating with others on a project.
5. **Open Source and Community**: Git is free and open-source and has a large community of users and contributors.
It works cross-platform, working on all major operating systems, including Windows, macOS, and Linux.

There are several platforms that provide Git hosting services, including GitHub, GitLab, and Bitbucket.
These platforms offer additional features on top of Git, such as issue tracking, pull requests, and continuous integration.
In this workshop, we will focus on GitHub, one of the most popular Git hosting services, and explore its features and functionalities.

```{figure} ../figures/GitHub.png
:alt: GitHub
:width: 150
``` 

Github is a web-based platform that provides hosting for Git repositories and offers a wide range of features to support software development projects.
Some of the key features of GitHub include:

* **Version Control**: Keep track of changes in your code, and revert to previous versions if needed.  
* **Collaboration**: Work with others on the same project, and keep track of who did what.  
* **Code Review**: Get feedback on your code from others, and improve its quality.  
* **Issue Tracking**: Keep track of bugs, feature requests, and other tasks related to your project.  
* **Continuous Integration**: Automate testing and deployment of your code, making it easier to maintain and scale.  
* **Documentation**: Write and maintain documentation for your project, making it easier for others to understand and use it.
* **Community**: Build a community around your project, and get help from others when needed.
* **Open Source**: Share your work with others, and contribute to open source projects.
* **Portfolio**: Showcase your work to potential employers, collaborators, and users.


## Why GitHub for research?

Git is a powerful tool that offers numerous benefits to developers and teams working on software projects.
However, for research projects, Git can be equally valuable, providing several advantages:

1. **Version Control**: Keep track of changes in your research code, data, and documentation.
2. **Collaboration**: Work with others on the same project, and keep track of who did what.
3. **Reproducibility**: Ensure that your research is reproducible by tracking changes and sharing code.
4. **Documentation**: Write and maintain documentation for your research, making it easier for others to understand and use it.
5. **Backup**: Keep your research safe by storing it in a remote repository, preventing data loss.
6. **Open Science**: Share your research with others, and contribute to open science initiatives.

By using Git for your research projects, you can improve the quality, transparency, 
and reproducibility of your work, making it easier to collaborate with others and share 
your findings with the world. Or simply, keep track of your work and avoid losing it.

Having your research on GitHub is also a way you can share your code for others to use and 
reproduce your results. This is becoming more and more important in the scientific community,
and it desired by some journal and funders as it allows for more transparency and 
reproducibility in research.

## Key Concepts

```{admonition} Repository (Repo)
:class: dropdown
A repository is a storage space where a project and its files are kept. 
It contains all the project's files and the entire revision history 
of each file. Repositories can be public, allowing anyone to view and 
contribute, or private, restricting access to specific users. 
They are the central hub for all the activity in a project, 
including code, documentation, and issues.
```
   
```{admonition} Branch
:class: dropdown
A branch is a parallel version of a repository. It allows you to work 
on different versions of a project simultaneously. The main branch, 
often called "main" or "master," is considered the production-ready 
version of the project. Developers create branches to develop features, 
fix bugs, or experiment without affecting the main branch. 
Once the work on a branch is complete, it can be merged back into the main branch.
```

```{admonition} Commit
:class: dropdown
A commit is a record of changes made to the files in a repository. 
Each commit has a unique ID and contains a message describing the changes made. 
Commits allow you to track the history of changes in a project, providing a 
detailed timeline of how the project has evolved over time. 
They act as snapshots of the project at specific points, which can be reverted 
to if needed.
```

```{admonition} Pull Request (PR)
:class: dropdown
A pull request is a method of proposing changes to a repository. 
When you create a pull request, you ask the repository maintainers 
to review and merge your changes into the main branch. Pull requests 
facilitate collaboration by allowing team members to discuss and 
review code before it is merged. They provide a structured way to 
manage changes and ensure code quality.
```

```{admonition} Merge
:class: dropdown
Merging is the process of integrating changes from one branch into another. 
When a pull request is approved, the changes are merged into the main branch, 
incorporating the new code into the project. Merging ensures that updates 
and new features developed in separate branches are consolidated into the 
main codebase.
```

```{admonition} Fork
:class: dropdown
A fork is a personal copy of another user's repository. 
Forking a repository allows you to freely experiment with changes without 
affecting the original project. You can make changes in your fork, 
and if you want those changes to be incorporated into the original 
repository, you can submit a pull request.
```

```{admonition} Issue
:class: dropdown
An issue is a way to track enhancements, tasks, and bugs for a project. 
Issues can be assigned to specific users, labeled, and organized into milestones. 
They provide a clear way to manage and prioritize work, ensuring that everyone 
on the team is aware of what needs to be done and any problems that need to 
be addressed.
```

```{admonition} Clone
:class: dropdown
Cloning is the process of creating a local copy of a repository on your computer. 
Cloning allows you to work on a project locally, making changes and committing 
them before pushing them back to the remote repository on GitHub. 
It enables offline development and testing.
```

```{admonition} GitHub Actions
:class: dropdown
GitHub Actions is an automation tool integrated into GitHub that allows you 
to automate your software development workflows. With GitHub Actions, 
you can create workflows that build, test, and deploy your code whenever 
there is a change in your repository. It enables continuous integration 
and continuous deployment (CI/CD) directly from your repository.

:::{attention}
GitHub Actions will not be covered in this workshop, but it is a powerful
tool that you should explore to streamline your development process.
:::
```

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
6. **Push Changes**: Push your commits to the remote repository on GitHub. 
   This updates the repository with your changes and makes them available to others.
7. **Create a Pull Request**: Create a pull request to propose your changes 
   for review and merging. Pull requests allow team members to review your 
   changes and provide feedback before merging them.

![github flow.png](../figures/github_flow.png)

:::{attention}
You will need to install Git on your local machine to use the Git commands.
For this, you can follow the instructions provided on the [Git website](https://git-scm.com/).
:::