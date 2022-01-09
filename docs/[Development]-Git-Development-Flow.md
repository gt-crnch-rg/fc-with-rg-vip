_Last updated: 1/9/22_

## Git development flows

Atlassian has a nice [tutorial on different workflows](https://www.atlassian.com/git/tutorials/comparing-workflows) for collaborative Git projects. Using these workflows for your own work can give you a good sense of how industry and public projects use Git to integrate new features and merge code. We recommend using either the "centralized" workflow for small, internal projects or the "forking" workflow, especially for larger, publicly available projects.

[Centralized Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows#centralized-workflow)

[Forking Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow)

## What are some high-level tips?

* Learn how to use [Github issues](https://guides.github.com/features/issues/) to communicate new features or bugfixes with your team. This also can be used to drive pull requests to integrate features from different team members.
* Make a habit of using pull requests for anything smaller than minor fixes. Starting a PR early in the feature development or bugfix process allows others to read your code, comment on it, and test it.

## What are pull requests?

When you do not possess collaborator status on a repository, you are unable to make / merge changes directly into it. You can still contribute through forking the repository on your own, making changes, and then merging changes through the usage of pull requests. Pull requests are essentially a repo-collaborator approved merging system for GitHub. 

This method is also highly recommended even when you have collaborator access, as helps to implement a standard method of modification of the master branch for all contributors. In this case, creating a forked repository is not necessary, and simply creating a separate remote branch is sufficient to perform pull requests.

## How do I create a pull request?
Once all of the changes have been committed and pushed to a remote branch, and this remote branch is ahead of master (not behind, otherwise you will need to pull from master to get updates on the branch first), you can then navigate to the GitHub repository, select the `Pull Requests` tab, and then select the remote branch to merge into master. 

It's highly recommended to start a Draft Pull Request for each future pull request that you plan to make. This allows others to easily see changes, make comments and suggests, and just generally approve changes as development is occurring, rather than all at once after all changes have been made. 

Once you have finished making changes to your local branch, it's good to sync up with the remote branch you want to merge into. That means you need to merge upstream changes into your branch and resolve any conflicts.

[Merging upstream repo into your fork](https://help.github.com/en/articles/merging-an-upstream-repository-into-your-fork)

## What do I do when I get a pull request?
Another important addition to the github workflow is how to test pull requests locally: [Github guide to locally testing PRs](https://help.github.com/en/articles/checking-out-pull-requests-locally)

The most important command to remember here is some form of `git fetch origin pull/ID/head:BRANCHNAME` where ID is the number that github assigns to the PR and BRANCHNAME is  what you would like to name the branch. After fetching the branch, you can `git checkout BRANCHNAME` and run your test suite before approving the PR. 

## Rebasing versus Merging

git rebase and git merge do very similar operations.
* [Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
* Should I rebase? Often, the answer seems to be [no](https://www.atlassian.com/git/tutorials/merging-vs-rebasing#the-golden-rule-of-rebasing), especially for publicly shared branches like master in a project. 

For more information, please check out Graham Lopez's [page on this topic](https://grahamlopez.org/git/confusion.html#merge-vs-rebase-vs-cherrypick).
