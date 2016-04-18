# Contributor's Guide

## Table of Contents

- [I want to help!](#i-want-to-help)
- [Contribution Guidelines](#contribution-guidelines)
- [Getting Started](#getting-started)
- [Creating Pull Requests](#creating-pull-requests)
- [Common Steps](#common-steps)
- [Next Steps](#next-steps)

## I want to help!

Follow these steps to contribute:

1.  Find an issue that needs assistance.
2.  Post a comment on the issue.

## Contribution Guidelines

1.  Fork the project
2.  Create a branch specific to the issue or feature you are working on. Push your work to that branch.
3.  Name the branch something like `fix/xxx` or `feature/xxx` where `xxx` is a short description of the changes or feature you are attempting to add. For example `fix/email-login` would be a branch where I fix something specific to email login.
4.  Squash your Commits.
6.  Submit a pull request from your branch to the `develop` branch.

## Getting Started

The easiest way to get started is to clone the repository:

```bash
# Get the latest snapshot
git clone --depth=1 https://github.com/responsive-ui-elements/bootstrap-ui-elements.git bootstrap-ui-elements

# Change directory
cd bootstrap-ui-elements

# Switch to the develop branch
git checkout develop

# Install NPM dependencies
npm install

# Install Bower dependencies
bower install
```

Run the site locally. The way nunchucks is setup, running from dist is important.

```bash

# Start the server
gulp serve:dist
```

Now navigate to your browser and open
```
http://localhost:3001
```
If the app loads, congratulations - you're all set. Otherwise, let us know by opening a GitHub issue and with your error.

## Creating Pull Requests
**What is a Pull Request?**

A pull request (PR) is a method of submitting proposed changes to Repo. You will make changes to copies of the files in a personal fork, then apply to have them accepted.

**Methods**


**Important: ALWAYS EDIT ON A BRANCH**
Take away only one thing from this document, it should be this: Never, **EVER** make edits to the `develop` branch. ALWAYS make a new branch BEFORE you edit files. This is critical, because if your PR is not accepted, your copy of develop will be forever sullied and the only way to fix it is to delete your fork and re-fork.

_**Editing via your Local Fork**_

1. Perform the maintenance step of rebasing `develop`.
2. Ensure you are on the `develop` branch using `git status`:

```bash
$ git status
On branch develop
Your branch is up-to-date with 'origin/develop'.

nothing to commit, working directory clean
```

3. If you are not on develop or your working directory is not clean, resolve any outstanding files/commits and checkout develop `git checkout develop`
4. Create a branch off of `develop` with git: `git checkout -B branch/name-here`
**Note:** Branch naming is important. Use a name like `fix/short-fix-description` or `feature/short-feature-description`.
5. Edit your file(s) locally with the editor of your choice
6. Check your `git status` to see unstaged files.
7. Add your edited files: `git add path/to/filename.ext` You can also do: `git add .` to add all unstaged files. Take care, though, because you can accidentally add files you don't want added. Review your `git status` first.
8. Commit your edits: `git commit -m "Brief Description of Commit"`
9. Squash your commits, if there are more than one.
10. Push your commits to your GitHub Fork: `git push -u origin branch/name-here`

## Common Steps
1. Once the edits have been committed, you will be prompted to create a pull request on your fork's GitHub Page.
2. All pull requests should be against the main repo, `develop` branch.
3. Submit a pull request from your branch to our `develop` branch.
3. The title (also called the subject) of your PR should be descriptive of your changes and succinctly indicates what is being fixed.
   - **Do not add the issue number in the PR title**.
   - Examples: `Add Test Cases to Bonfire Drop It` `Correct typo in Waypoint Size Your Images`
4. In the body of your PR include a more detailed summary of the changes you made and why.
   - If the PR is meant to fix an existing bug/issue, then, at the end of your PR's commit message, append the keyword `closes` and #xxxx (where xxxx is the issue number). Example: `closes #1337`.
   This tells GitHub to close the existing issue, if the PR is merged.
5. Indicate if you have tested on a local copy of the site or not.

## Next Steps

**If your PR is accepted**

Once your PR is accepted, you may delete the branch you created to submit it. This keeps your working fork clean.

You can do this with a press of a button on the GitHub PR interface. You can delete the local copy of the branch with: `git branch -D branch/to-delete-name`

**If your PR is rejected**

Don't despair! You should receive solid feedback from the Issue Moderators as to why it was rejected and what changes are needed.

Many Pull Requests, especially first Pull Requests, require correction or updating. If you have used the GitHub interface to create your PR, you will need to close your PR, create a new branch, and re-submit. This is because you cannot squash your commits via the GitHub interface.

If you have a local copy of the repo, you can make the requested changes and amend your commit with: `git commit --amend` This will update your existing commit. When you push it to your fork you will need to do a force push to overwrite your old commit: `git push --force`

Be sure to post in the PR conversation that you have made the requested changes.

**Thanks to FreeCodeCamp and their documentation for help creating this file.**
