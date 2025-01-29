# Git Commands
## get started
## Regular Commands

| Command | Description |
|---------|-------------|
| `git add <filename>` | Stage a file |
| `git add *` | Stage all files |
| `git add --patch` | Allows splitting of files (partially staging them) |

| Command | Description |
|---------|-------------|
| `git branch` | List all branches, with an asterisk next to the one where the HEAD is |
| `git branch <branch name>` | Create a new branch on the commit you're currently on but doesn't move the HEAD to it |
| `git branch -d <branch name>` | Delete a branch |
| `git branch --merged [branch name]` | Show all branches merged into the current branch. Optionally specify a branch without checking it out |
| `git branch --no-merge [branch name]` | Show all branches not merged into the current branch. Optionally specify a branch without checking it out. `git log --no-merges` shows unmerged commits |
| `git branch -v` | Get last commit on all branches |
| `git branch -vv` | Informs for tracking branches whether ahead or behind remote branch, or if a tracking branch at all. Helpful to call it like this: `git fetch --all; git branch -vv` |
| `git branch -m <new_branch_name>` | Changes the name of the currently checked out branch |

| Command | Description |
|---------|-------------|
| `git checkout <branch name>` | Checkout existing branch. Same as `git switch <branch name>` |
| `git checkout -b <branch name>` | Checks out a branch and creates it at the same time. Same as `git switch -c <branch name>` |
| `git checkout <tag name>` | Use this to view the files of a tagged commit. This is in detached head mode |
| `git checkout -b <branch name> origin/main` | Forces the creation based on the `origin/main` if currently in another topic branch |
| `git checkout -b <branch name> <remote_branch_name>` | Create a local branch based on (already fetched) remote one |

| Command | Description |
|---------|-------------|
| `git clean` | Used to delete untracked, unignored files |
| `git clean -n` | Shows what it would do if the `-n` option is not set |
| `git clean -n -d` | Same as previous but including directories |

| Command | Description |
|---------|-------------|
| `git commit` | Commit staged changes |
| `git commit -m "<message>"` | Allows to put the commit message on the command line instead of in a text editor |
| `git commit -a` | Commits all changes including unstaged ones. Doesn't work for untracked files; you have to add them first |
| `git commit --amend -m "<message>"` | Replace last commit with stage. If stage is empty only the commit message is changed. Don't do this to already pushed changes |
| `git commit --amend --no-edit` | Replace the last commit with stage and don't change commit message (e.g., typo fix) |

| Command | Description |
|---------|-------------|
| `git config --list --show-origin` | Show all config values and which folder they were taken from |
| `git config --global user.name "Your Name"` | Set user name |
| `git config --global user.email "your.email@example.com"` | Set email address |
| `git config --global alias.<alias name> <command to be aliased>` | Allows aliasing of common commands |

| Command | Description |
|---------|-------------|
| `git diff` | Diff of modified files |
| `git diff --check` | Informs of any whitespace errors |
| `git diff --staged` | Diff of staged files (`--cached` is a synonym) |

| Command | Description |
|---------|-------------|
| `git difftool HEAD @{u}` | Compares local branch with remote tracking branch in configured external difftool |
| `git difftool --dir-diff <left-side-commit> <right-side-commit>` | Opens one instance of beyond compare with a directory structure |

| Command | Description |
|---------|-------------|
| `git fetch origin` | Fetches all information from the originally cloned repo, but doesn't merge it |
| `git fetch --all` | Fetches from all remotes |
| `git fetch --all --recurse-submodules` | Fetches all submodule changes as well |
| `git fetch --prune` | Fetch and remove local references to already deleted remote branches |
| `git fetch --all --prune --recurse-submodules` | Additionally removes local references to remote branches that no longer exist after a merge |

| Command | Description |
|---------|-------------|
| `git init` | Set up a project from scratch |

| Command | Description |
|---------|-------------|
| `git log` | Show commit history with commit message, also shows the tag |
| `git log -p -<nr. commits>` | Shows a number of previous committed patches |
| `git log --stat -<nr. commits>` | Shows commits with stats about how many files changed, added, etc. |
| `git log --pretty=oneline` | Shows commits on one line with commit message and tag |
| `git log --pretty=short` | Like `--pretty=oneline` but with author |
| `git log --oneline` | Like `--pretty=oneline` but with shorter checksums |
| `git log --since 2.days` | Can also be changed to hours, weeks, etc. |
| `git log --pretty=format:"%C(auto)%h%d %Cblue<%an>%Creset - %ar - %s" --since 15.days --name-only` | Custom log format |
| `git log -S <string>` | Searches for commits that changed the number of occurrences of that string |
| `git log -- path cfg` | Git changes to a file or directory. Can also be used with `git status` |
| `git log --oneline --decorate --graph --all` | Show commit history with all branches |
| `git log --no-merges main..origin/main` | Show `origin/main` commits not yet merged into `main` |

| Command | Description |
|---------|-------------|
| `git merge <branch name>` | Merge the named branch to the one where the HEAD is currently |
| `git merge @{u}` | Merge in the remote tracking branch |
| `git merge origin/featureA` | Merge `featureA` branch into currently checked out branch |

| Command | Description |
|---------|-------------|
| `git mv <oldFilename> <newFilename>` | Rename a file through git |

| Command | Description |
|---------|-------------|
| `git pull` | Fetches and merges data from a tracked remote repository |
| `git pull origin <branch-name>` | pull the branch from the remote repository |

| Command | Description |
|---------|-------------|
| `git push origin main` | Pushes local `main` back to origin |
| `git push origin --tags` | Pushes all tags to the remote server |
| `git push origin <local_branch_name>` | Push local branch to a branch with the same name on the remote |
| `git push origin <local_branch_name>:<server_branch_name>` | Push local branch to remote branch with different name |
| `git push --set-upstream origin <remote_branch_name>` | Sets the remote branch as the tracking branch of the local branch |
| `git push origin --delete <remote_branch_name>` | Deletes a remote branch |

| Command | Description |
|---------|-------------|
| `git rebase <branch>` | Same final commit as git merge, but only on the current branch |
| `git rebase --onto <target branch> <intermediate branch> <3rd branch>` | Rebases a branch of a branch onto the root branch |

| Command | Description |
|---------|-------------|
| `git remote -v` | Shows remote servers including their URLs |
| `git remote show origin` | Show details of branches to be pushed and pulled |
| `git remote add <short_name> <URL>` | Add a remote repository |

| Command | Description |
|---------|-------------|
| `git reset --soft HEAD~1` | Delete the most recent local commit without destroying the non-committed work done |
| `git reset --hard HEAD~1` | Delete the most recent local commit and any non-committed work done |

| Command | Description |
|---------|-------------|
| `git restore --staged <file>` | Move a file back out of the staged to being modified again |
| `git restore <file>` | Discard changes to a modified file |

| Command | Description |
|---------|-------------|
| `git rm <filename>` | Removes a file from git and the working directory |
| `git rm --cached <filename>` | Removes a file but leaves it in the working directory |

| Command | Description |
|---------|-------------|
| `git show [tag name]` | Shows tag details including tagger and date of tagging and tag message |

| Command | Description |
|---------|-------------|
| `git stash` | Stashes modified and index files |
| `git stash list` | Lists all stashed changes |
| `git stash drop stash@{<stashIndex>}` | Removes a stash from the stash list |
| `git stash show` | Show the files in the most recent stash |
| `git stash show 0` | Show the files in the named stash |
| `git stash --keep-index` | Leave the content in the index in
