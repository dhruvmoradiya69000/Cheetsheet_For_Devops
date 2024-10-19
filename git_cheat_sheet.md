# Git and GitHub Command Cheat Sheet

## Table of Contents
 - [Git Configuration](#git-configuration)
 - [Repository Operations](#repository-operations)
 - [Basic Git Workflow](#basic-git-workflow)
 - [Branching and Merging](#branching-and-merging)
 - [Viewing Changes and History](#viewing-changes-and-history)
 - [Undoing Changes](#undoing-changes)
 - [GitHub-Specific Commands](#github-specific-commands)
 - [Advanced Git Operations](#advanced-git-operations)
 - [Advanced Branching](#advanced-branching)
 - [Git Hooks](#git-hooks)
 - [Submodules](#submodules)
 - [Worktree](#worktree)
 - [Reflog and Recovery](#reflog-and-recovery)
 - [Advanced GitHub Features](#advanced-github-features)
 - [Git Configuration and Aliases](#git-configuration-and-aliases)

## Git Configuration

| Command | Description |
|---------|-------------|
| `git config --global user.name "<name>"` | Set your name for Git commits |
| `git config --global user.email "<email>"` | Set your email for Git commits |
| `git config --list` | View Git configuration |

## Repository Operations

| Command | Description |
|---------|-------------|
| `git init` | Initialize a new Git repository |
| `git clone <url>` | Clone a repository from a remote source |
| `git remote add <name> <url>` | Add a remote repository |
| `git remote -v` | List remote repositories |

## Basic Git Workflow

| Command | Description |
|---------|-------------|
| `git status` | Show the status of your working directory |
| `git add <file>` | Stage changes for commit |
| `git add .` | Stage all changes for commit |
| `git commit -m "<message>"` | Commit staged changes with a message |
| `git push <remote> <branch>` | Push commits to a remote repository |
| `git pull <remote> <branch>` | Fetch and merge changes from a remote repository |

## Branching and Merging

| Command | Description |
|---------|-------------|
| `git branch` | List local branches |
| `git branch <name>` | Create a new branch |
| `git checkout <branch>` | Switch to a different branch |
| `git checkout -b <name>` | Create and switch to a new branch |
| `git merge <branch>` | Merge a branch into the current branch |
| `git branch -d <branch>` | Delete a branch |

## Viewing Changes and History

| Command | Description |
|---------|-------------|
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes |
| `git log` | View commit history |
| `git log --oneline` | View commit history in a compact format |
| `git log --graph --oneline --al` | Show commit history with graph | 
| `git blame <file>` | Show who changed what and when in a file |

## Undoing Changes

| Command | Description |
|---------|-------------|
| `git restore <file>` | Discard changes in working directory |
| `git restore --staged <file>` | Unstage changes |
| `git reset HEAD~1` | Undo the last commit, keeping changes |
| `git reset --hard HEAD~1` | Undo the last commit, discarding changes |
| `git revert <commit>` | Create a new commit that undoes a previous commit |

## GitHub-Specific Commands

| Command | Description |
|---------|-------------|
| `git push -u origin <branch>` | Push a new branch to GitHub and set upstream |
| `git fetch origin` | Fetch changes from GitHub without merging |
| `git pull origin <branch>` | Fetch and merge changes from GitHub |
| `git push origin --delete <branch>` | Delete a remote branch on GitHub |

## Advanced Git Operations

| Command | Description |
|---------|-------------|
| `git stash` | Temporarily save uncommitted changes |
| `git stash pop` | Apply and remove the most recent stash |
| `git cherry-pick <commit>` | Apply a specific commit to the current branch |
| `git rebase <branch>` | Reapply commits on top of another branch |

## Advanced Branching

| Command | Description |
|---------|-------------|
| `git branch -m <old-name> <new-name>` | Rename a branch |
| `git branch --merged` | List merged branches |
| `git branch --no-merged` | List unmerged branches |
| `git push --force-with-lease` | Force push with a safety check |

## Git Hooks

| Command | Description |
|---------|-------------|
| `git hooks` | Directory containing hook scripts |
| `pre-commit` | Hook run before a commit is created |
| `post-commit` | Hook run after a commit is created |
| `pre-push` | Hook run before a push is done |

## Submodules

| Command | Description |
|---------|-------------|
| `git submodule add <url>` | Add a new submodule |
| `git submodule init` | Initialize submodules |
| `git submodule update` | Update submodules |
| `git submodule foreach <command>` | Run a command on each submodule |

## Worktree

| Command | Description |
|---------|-------------|
| `git worktree add <path> <branch>` | Create a new worktree |
| `git worktree list` | List details of each worktree |
| `git worktree remove <worktree>` | Remove a worktree |

## Reflog and Recovery

| Command | Description |
|---------|-------------|
| `git reflog` | Show a log of changes to HEAD |
| `git fsck` | Check the integrity of the Git database |
| `git gc` | Clean up unnecessary files and optimize local repository |

## Advanced GitHub Features

| Command | Description |
|---------|-------------|
| `git shortlog -sn` | Show commit count by author |
| `git describe` | Give an object a human readable name |
| `git bisect start` | Use binary search to find the commit that introduced a bug |
| `git blame -L <start>,<end> <file>` | Show what revision and author last modified each line |

## Git Configuration and Aliases

| Command | Description |
|---------|-------------|
| `git config --global alias.<alias-name> <git-command>` | Create a Git command alias |
| `git config --global core.editor <editor>` | Set default editor for Git |
| `git config --global merge.tool <tool>` | Set default merge resolution tool |
| `git config --global pull.rebase true` | Set pull to use rebase by default |

Remember to use `git help <command>` for more detailed information on any Git command!
