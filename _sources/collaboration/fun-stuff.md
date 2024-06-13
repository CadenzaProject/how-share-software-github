# Making our repository more secure

Now, the fun stuff! We're going to make our repository more secure by adding a few more 
layers of protection. This is a good practice to prevent unauthorized changes to our codebase.
We won't block people to collaborate, but we will make sure that only the right content 
is being pushed to the repository.

## Protect the main branch

As was mentioned before, the main branch is the most important branch in our repository.
It should always contain the latest stable version of our codebase.
We will protect the main branch to prevent unwanted changes by requiring pull request 
reviews before merging.

1. Go to the repository settings
2. Click on "Branches" in the left sidebar
3. Under "Branch protection rules", click on "Add classic branch protection rule"
4. In the "Branch name pattern" field, type `main`
5. Check the following options:
   - "Require pull request reviews before merging"
   - "Require status checks to pass before merging"
   - "Require branches to be up-to-date before merging"
   - "Do not allow bypassing the above settings"

With these settings, you will ensure that all changes are reviewed before merging 
into the main branch.

6. For any other rule, just pressed "Add rule" and repeat the process.

## Creating Issues Templates

Issues are a great way to keep track of tasks, enhancements, and bugs for your projects.
By creating issue templates, you can ensure that the necessary information is provided 
when creating a new issue and will tell people what information do you need.

To create an issue template, in your local repository, follow these steps:

1. Create a new directory called `.github` in the root of your repository
2. Inside the `.github` directory, create a new directory called `ISSUE_TEMPLATE`
3. Inside the `ISSUE_TEMPLATE` directory, create a new file called `bug_report.md`
4. Add the following content to the `bug_report.md` file:

```markdown
---
name: Bug report
about: Create a report to help us improve
title: "[BUG]"
labels: bug
assignees: ''
---
**Describe the bug**
A clear and concise description of what the bug is.

**To Reproduce**
Please describe the steps to reproduce the behavior:

**Expected behavior**
A clear and concise description of what you expected to happen.

**Error Messages**
If applicable, please **copy and paste** the command that failed and the full traceback output that occurs.

**Additional context**
Add any other context about the problem here such as the data that is being used.
```

5. Add and commit the changes to your repository
6. Push the changes to the remote repository.

We got an error. What just happened?

![Blocked Branch.png](../figures/block-branch.png)

:::{toggle}
The error message is telling us that we can't push directly to the main branch.
This is because we have protected the main branch and we need to create a pull request
to merge our changes.

Let's do this in the next part.
:::

