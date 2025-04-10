# Overview

A GitHub CLI extension that creates a pull request from a given commit.

# Install

```
gh extension install alexfu/gh-pr-from-commit
```

# Problem

- You are working on a feature branch.
- You make some commits.
- You make a commit that cleans up some code that is not strictly required but is related to your new feature to some degree.
- You make more commits.
- Push changes to origin and open pull request.

In the above scenario, that clean up commit would ideally be in a seprate pull request so that changes are minimal and focused. However, in the moment, it is too much overhead to check out a new branch, apply that work, push and open a pull request. Additionally, it would break your flow.

Often times we just end up bundling changes together because it's the path of least resistance.

This extension is aimed at reducing that friction by making it easier and less time consuming to take a commit, apply it on top of `main` and open a pull request; all with a single command.

# Usage

```
gh pr-from-commit [-i] <commit sha> [<base branch>]
```

By default, this command runs non-interactively for max efficiency...

```
$ gh pr-from-commit 6e0d35ad3c1b
🛠️ Creating temporary worktree...done.
📂 Changing directory to worktree...done.
🍒 Cherry picking commit 6e0d35ad3c1b
[alex.fu/cherry-pick-6e0d35ad3c1b f407e54] stuff
 Date: Thu Apr 10 09:38:56 2025 -0400
 1 file changed, 3 insertions(+), 1 deletion(-)
📤 Pushing changes to main...remote: 
remote: Create a pull request for 'alex.fu/cherry-pick-6e0d35ad3c1b' on GitHub by visiting:
remote:      https://github.com/alexfu/test/pull/new/alex.fu/cherry-pick-6e0d35ad3c1b
remote:
🚀 Creating pull request...
https://github.com/alexfu/test/pull/1

🧹 Cleaning up...done.
```
