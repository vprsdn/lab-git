# Commands

## Clones the repo to local

- `git clone <repo ssh>`

## Adding existing project folder to git

- Create a new repo in git.
- In the local project folder, run the following:
  - `git init -b main`
  - `git add .`
  - `git commit -m "initial commit"`
  - `git remote add origin <REMOTE_URL>`
  - `git remote -v` // verifies the repo.
  - `git push origin main`

## Lists all the branches

- `git branch`

## Fetch a remote branch to work on: Get a copy of the remote branch in the local

- `git fetch origin branch_name`

## Creates a new branch

- `git branch branch_name` - create the new branch
- `git checkout -b branch_name` - create and switch to the new branch

## Switches working space to that specified branch

- `git checkout branch_name`

## Shows the status of the current branch

- `git status`

## Reverts the local changes in this file

- `git checkout fileName.ext` - goes to the state of this file in previous commit, discarding all local changes

## Checking out to commits

- `git checkout <commit number>` - goes back to the mentioned commit
- `git checkout main` - goes back to latest commit in main

## Removes all your local changes and resets the whole project to the last commit made. This cannot be undo-ed - dangerous

- `git restore .`
- `git checkout .`

## Stashing changes

- `git stash save "stash message here"` - stashes the changes
- `git stash save --include-untracked "message here"` - stashes the changes including the untracked files
- `git stash list` - lists all the stashed changes
- `git stash show <stash number?>` - shows the files changed in the recent stash or the mentioned stash number
- `git stash show <stash number?> -p` - shows changes in the recent stash or the mentioned stash number
- `git stash apply <stash number?>` - applies the recent stash or mentioned stash number
- `git stash apply stash@{n}` - applies the mentioned stash number, different syntax
- `git stash pop <stash number?>` - applies and deletes the recent stash or mentioned stash number
- `git stash drop <stash number?>` - deletes the recent stash or mentioned stash number
- `git stash clear` - deletes all the stashes

## Staging file(s)

- `git add .` - adds all the new and modified files to staging to commit
- `git add path_to_file/file_name` - adds a specified file to the staging to commit

## Unstaging file(s)

- `git reset .` - moves all the files from staged to unstaged state. DISCARDS any existing unstaged files (at least that is what the Google Bard says, but the vscode seems to be doing something that makes sure this does not happen)
- `git restore --staged .` (SAFE) - unstages all changes in the working directory, but DOES NOT DISCARD any changes.

## Committing changes

- `git commit -m "commit message here"`

## Undo/revert a commit

- `git reset --soft HEAD~n` - commit is removed and changes are preserved locally. Puts the changes back to the staged form which can be seen with the git status command. n = 1, 2, 3, etc. it represents the number of commits to reset to. Keep it at 1
- `git reset --hard HEAD~1` - commit is removed and changes are not preserved

## Pull the latest changes from the remote branch

- `git pull origin branch_name`

## Checking differences

- `git diff` - compares changes between working code and the staged (added with git add) code
- `git diff branchOne branchTwo` - compares two branches, new syntax
- `git diff branchOne..branchTwo` - compares two branches, old syntax
- `git diff --staged` - compares staged code with the last commit in local
- `git diff commit1..commit2` - compares two commits

## Aborts the current pull that caused a merge conflict. Useful in case of conflicts when the state stays in "merging"

- `git merge --abort`

## Merge one branch into another

- `git checkout main` - checkout to the main branch
- `git merge featureA` - featureA gets merged to the main branch

## Push local changes to your remote branch

- `git push origin branch_name`

## Delete branch: Be in a different branch before deleting this branch

- `git branch -d branch_name` - small d shows errors if there are any un-pushed changes in the deleting branch and asks to push it to the upper branch first
- `git branch -D branch_name` - capital D deletes the branch forcefully even if there are any changes in it
- `git push <remote_name> --delete branch_name` - deletes the remote branch. The remote name is usually "origin"

## Reset the local branch to the specified remote branch

- `git reset --hard origin/<branch_name>`
