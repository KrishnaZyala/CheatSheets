# Git Cheat Sheet

### Configuring User Information
```
git config --global user.name "[firstname lastname]"
# Set a name that is identifiable for credit when reviewing version history

git config --global user.email "[valid-email]"
# Set an email address that will be associated with each history marker

git config --global color.ui auto
# Set automatic command line coloring for Git for easy reviewing
```

### Initializing and Cloning Repositories
```
git init
# Initialize an existing directory as a Git repository

git clone [url]
# Retrieve an entire repository from a hosted location via URL

```

### Working with Snapshots and the Git Staging Area
```
git status
# Show modified files in the working directory, staged for your next commit

git add [file]
# Add a file as it looks now to your next commit (stage)

git reset [file]
# Unstage a file while retaining the changes in the working directory

git diff
# Show unstaged changes between your index and working directory

git diff --staged
# Show the diff of what is staged but not yet committed

git commit -m "[descriptive message]"
# Commit your staged content as a new commit snapshot
```
### Isolating Work in Branches, Changing Context, and Integrating Changes
```
git branch
# List your branches. A * will appear next to the currently active branch

git branch [branch-name]
# Create a new branch at the current commit

git checkout [branch-name]
# Switch to another branch and check it out into your working directory

git checkout -b [branch]
# Create and check out a new branch named [branch]

git merge [branch]
# Merge the specified branch’s history into the current one

git log
# Show all commits in the current branch’s history
```

### Retrieving Updates from Another Repository and Updating Local Repositories
```
git remote add [alias] [url]
# Add a git URL as an alias

git fetch [alias]
# Fetch all the branches from that Git remote

git merge [alias]/[branch]
# Merge a remote branch into your current branch to bring it up to date

git push [alias] [branch]
# Transmit local branch commits to the remote repository branch

git pull [remote]
# Fetch the specified remote’s copy of the current branch and immediately merge it into the local copy

git pull --rebase [remote]
# Fetch the remote’s copy of the current branch and rebase it into the local copy
```

### Versioning File Removes and Path Changes
```
git rm [file]
# Delete the file from the project and stage the removal for commit

git mv [existing-path] [new-path]
# Change an existing file path and stage the move

git log --stat -M
# Show all commit logs with indication of any paths that moved
```

### Temporarily Store Modified, Tracked Files in Order to Change Branches
```
git stash
# Save modified and staged changes

git stash list
# List stack-order of stashed file changes

git stash pop
# Write working from top of stash stack

git stash drop
# Discard the changes from top of stash stack
```

### Rewriting Branches, Updating Commits and Clearing History
```
git rebase [branch]
# Apply any commits of current branch ahead of specified one

git rebase -i [base]
# Interactively rebase the current branch onto [base]

git reset --hard [commit]
# Clear staging area, rewrite working tree from specified commit

git commit --amend
# Replace the last commit with the staged changes and last commit combined. Use with nothing staged to edit the last commit’s message
```

### Examining Logs, Diffs and Object Information
```
git log
# Show the commit history for the currently active branch

git log branchB..branchA
# Show the commits on branchA that are not on branchB

git log --follow [file]
# Show the commits that changed file, even across renames

git diff branchB...branchA
# Show the diff of what is in branchA that is not in branchB

git show [SHA]
# Show any object in Git in human-readable format
```

### Preventing Unintentional Staging or Committing of Files
```
git config --global core.excludesfile [file]
# System wide ignore pattern for all local repositories
# Save a file with desired patterns as .gitignore with either direct string matches or wildcard globs.
```

### Undoing Changes in the Working Directory and Staging Area
```
git revert [commit]
# Create new commit that undoes all of the changes made in [commit], then apply it to the current branch

git reset [file]
# Remove [file] from the staging area, but leave the working directory unchanged. This unstages a file without overwriting any changes.

git reset
# Reset staging area to match most recent commit, but leave the working directory unchanged.

git reset --hard
# Reset staging area and working directory to match the most recent commit and overwrites all changes in the working directory.

git reset <commit>
# Move the current branch tip backward to [commit], reset the staging area to match, but leave the working directory alone.

git reset --hard <commit>
# Same as previous, but resets both the staging area & working directory to match. Deletes uncommitted changes, and all commits after [commit].
```

### Additional Git Configuration
```
git config --global alias.[alias-name] [git-command]
# Create shortcut for a Git command. E.g. alias.glog “log --graph --oneline” will set ”git glog” equivalent to ”git log --graph --oneline.

git config --system core.editor [editor]
# Set text editor used by commands for all users on the machine. [editor] arg should be the command that launches the desired editor (e.g., vi).

git config --global --edit
# Open the global configuration file in a text editor for manual editing.

git log -[limit]
# Limit number of commits by [limit]. E.g. ”git log -5” will limit to 5 commits.

git log --oneline
# Condense each commit to a single line.

git log --stat
# Include which files were altered and the relative number of lines that were added or deleted from each of them.

git log -p
# Display the full diff of each commit.

git log --author="[pattern]"
# Search for commits by a particular author.

git log --grep="[pattern]"
# Search for commits with a commit message that matches [pattern].

git log [since]..[until]
# Show commits that occur between [since] and [until]. Args can be a commit ID, branch name, HEAD, or any other kind of revision reference.

git log -- [file]
# Only display commits that have the specified file.

git log --graph --decorate
# --graph flag draws a text-based graph of commits on the left side of commit msgs. --decorate adds names of branches or tags of commits shown.

git diff HEAD
# Show difference between working directory and last commit.

git diff --cached
# Show difference between staged changes and last commit.
```

### Rebasing Branches
```
git rebase [base]
# Rebase the current branch onto [base]. [base] can be a commit ID, branch name, a tag, or a relative reference to HEAD.

git rebase -i [base]
# Interactively rebase the current branch onto [base]. Launches editor to enter commands for how each commit will be transferred to the new base.
```

### Pulling Changes from a Remote Repository
```
git pull --rebase [remote]
# Fetch the remote’s copy of the current branch and rebase it into the local copy. Uses git rebase instead of merge to integrate the branches.
```

### Pushing Changes to a Remote Repository
```
git push [remote] [branch]
# Push the branch to [remote], along with necessary commits and objects. Creates named branch in the remote repo if it doesn’t exist.

git push [remote] --force
# Forces the git push even if it results in a non-fast-forward merge. Do not use the --force flag unless you’re absolutely sure you know what you’re doing.

git push [remote] --all
# Push all of your local branches to the specified remote.

git push [remote] --tags
# Tags aren’t automatically pushed when you push a branch or use the --all flag. The --tags flag sends all of your local tags to the remote repo.
```

### More Information, Training, and Tutorials

[GitHub Docs](https://docs.github.com/en)

[GitHub Cheat Sheet PDF ](https://education.github.com/git-cheat-sheet-education.pdf)
