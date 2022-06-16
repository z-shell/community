# Contributing Guidelines `WORK IN PROGRESS`

When contributing, please first discuss the change you wish to make via issue, email, or any other method with the owners of this repository before making a change.

Please note we have a [code of conduct](../.github/CODE_OF_CONDUCT.md), please follow it in all your interactions with the project.

## Knowledge Base

- [ZI Wiki](https://z-shell.pages.dev)
- [Zsh Plugin Standard](https://z-shell.pages.dev/community/zsh_plugin_standard)
- [Zsh Native Scripting Handbook](https://z-shell.pages.devcommunity/zsh_handbook)

### Need some help regarding the basics?🤔

You can refer to the following articles on the basics of Git and Github and also contact the Project Mentors,
in case you are stuck:

- [Forking a Repo](https://help.github.com/en/github/getting-started-with-github/fork-a-repo)
- [Cloning a Repo](https://help.github.com/en/desktop/contributing-to-projects/creating-an-issue-or-pull-request)
- [How to create a Pull Request](https://opensource.com/article/19/7/create-pull-request-github)
- [Getting started with Git and GitHub](https://towardsdatascience.com/getting-started-with-git-and-github-6fcd0f2d4ac6)
- [Learn GitHub from Scratch](https://lab.github.com/githubtraining/introduction-to-github)

## Submitting Contribution

Below you will find the process and workflow used to review and merge your changes.

### Step 0: Find an issue

- Take a look at the **existing issues** or create your **own** Issues!
- Wait for the Issue to be assigned to you after which you can start working on it.
- Note: Every change in this project should/must have an associated issue.

### Step 1: Fork the Project

- Fork this Repository. This will create a Local Copy of this Repository on your Github Profile.
  Keep a reference to the original project in the `upstream` remote.

```bash
git clone https://github.com/<your-username>/<repo-name>
cd <repo-name>
git remote add upstream https://github.com/z-shell/<repo-name>
```

- If you have already forked the project, update your copy before working.

```bash
git remote update
git checkout <branch-name>
git rebase upstream/<branch-name>
```

### Step 2 : Branch

Create a new branch. Use its name to identify the issue your addressing.

```bash
# It will create a new branch with name Branch_Name and switch to that branch
git checkout -b branch_name
```

### Step 3 : Work on the issue assigned

- Work on the issue(s) assigned to you.
- Add all the files/folders needed.
- After you've made changes or made your contribution to the project add changes to the branch you've just created by:

```bash
# To add all new files to branch Branch_Name
git add .

# To add only a few files to Branch_Name
git add <some files>
```

### Step 4: Commit

- To commit give a descriptive message for the convenience of reviewer by:

```bash
# This message get associated with all files you have changed
git commit -m "message"
```

- **NOTE**: A PR should have only one commit. Multiple commits should be squashed.

### Step 5: Work Remotely

- Now you are ready to your work to the remote repository.
- When your work is ready and complies with the project conventions, upload your changes to your fork:

### Step 6: Pull Request

- Go to your repository in your browser and click on compare and pull requests. Then add a title and description to your pull request that explains your contribution.

### Issues and feature requests

You've found a bug in the source code, a mistake in the documentation or maybe you'd like a new feature? Take a look at [GitHub Discussions](https://github.com/z-shell/zi/discussions) to see if it's already being discussed. You can help us by [submitting an issue on GitHub](https://github.com/z-shell/zi/issues). Before you create an issue, make sure to search the issue archive -- your issue may have already been addressed!

Please try to create bug reports that are:

- _Reproducible._ Include steps to reproduce the problem.
- _Specific._ Include as much detail as possible: which version, what environment, etc.
- _Unique._ Do not duplicate existing opened issues.
- _Scoped to a Single Bug._ One bug per report.

**Even better: Submit a pull request with a fix or new feature!**

### How to submit a Pull Request

1. Search our repository for open or closed
   [Pull Requests](https://github.com/z-shell/zi/pulls)
   that relate to your submission. You don't want to duplicate effort.
2. Fork the project
3. Create your feature branch (`git checkout -b feat/amazing_feature`)
4. Commit your changes (`git commit -m 'feat: add amazing_feature'`) Z-Shell ZI uses [conventional commits](https://www.conventionalcommits.org), so please follow the specification in your commit messages.
5. Push to the branch (`git push origin feat/amazing_feature`)
6. [Open a Pull Request](https://github.com/z-shell/zi/compare?expand=1)

#### Clean Pull Request

Contributing is also a great way to learn more about social coding on Github, new technologies and their ecosystems and how to make constructive, helpful bug reports, feature requests and the noblest of all contributions: a good, clean pull request.

- Create a personal fork of the project on Github.
- Clone the fork on your local machine. Your remote repo on Github is called the `origin`.
  - `git clone https://github.com/{YOUR-USERNAME}/zi`
- Add the original repository as a remote called `upstream`.
  - `git remote add upstream https://github.com/z-shell/zi.git`
- If you created your fork a while ago be sure to pull upstream changes into your local repository.
- Create a new branch from `next` if it exists, else from `main`.
- Implement/fix your feature, and comment on your code.
- Follow the code style of the project, including indentation.
- If there are related tests please run them.
- Write or adapt tests as needed.
- Add or change the documentation as needed.
- Squash your commits into a single commit with git's [interactive rebase](https://help.github.com/articles/interactive-rebase). Create a new branch if necessary.
- Push your branch to your fork on Github, the remote `origin`.
- From your fork open a pull request in the correct branch. Target the project's `next` branch if there is one, else go for `main`!
- Once the pull request is approved and merged you can pull the changes from `upstream` to your local repo and delete
  your extra branch(es).

> Always write your commit messages in the present tense. Your commit message should describe what the commit, when applied, does to the code – not what you did to the code. ([examples](https://www.google.com/search?q=english+"present+tense+example"))

