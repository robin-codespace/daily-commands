# Common Git Commands

Here are the most frequently used Git commands in daily work:

## git pull
Fetches changes from a remote repository and merges them into your current branch.

## git add
Stages changes for commit. You can add specific files or use `git add .` to stage all changes.

## git stash
Temporarily saves uncommitted changes so you can switch branches or perform other operations.
Common usage:
- `git stash save "message"` - Stash changes with a description
- `git stash pop` - Apply and remove the latest stash
- `git stash list` - View all stashed changes
- `git stash drop` - Removes the most recent stash entry

## git diff
Shows differences between working directory, staging area, and committed code:
- `git diff` - Shows unstaged changes
- `git diff --staged` - Shows staged changes
- `git diff branch1 branch2` - Compare two branches

## git push
Uploads your local commits to a remote repository.
Common usage: `git push origin branch-name`

## git commit
Creates a new commit with your staged changes.
Best practices:
- Write clear commit messages
- Use `git commit -m "message"` for simple commits
- Use `git commit` for detailed commit messages

## git checkout
Switches between branches or restores working tree files.
Common usage:
- `git checkout branch-name` - Switch to an existing branch
- `git checkout -b new-branch` - Create and switch to a new branch
- `git checkout file-name` - Discard changes in working directory
