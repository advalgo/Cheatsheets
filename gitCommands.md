### Git Commands:
```bash
# log:
git log     # Shows commit history
git log --oneline   # Shows summary of commits only first line of each
git log --abbrev-commit
git log --pretty=oneline

# Setting name and email:
git config --global user.name "User Name"
git config --global user.email "user@email.com"

# config:
git config --global user.name "User Name"
git config user.name "User Name"
git config --global user.email
git config user.email
git -v      # git version
git status  # tels you status of git repository
git init    # creates a git repository in the directory it is run in

# Commit
git add .                   # Add everthing for commit
git add file.txt file2.txt  # Add file by file
git commit                  # Commit change to repository
git commit --amend          # Opens COMMIT_MESSAGE for new edit
git -a -m "Add all and commit"
git -am "Add all and commit"
git -m "git message for commit"

# Setting COMMIT_MESSAGE editor:
git config --global core.editor "code --wait" # sets VSCode as COMMIT_MESSAGE editor

# branches:
git branch  # Shows all branches with an asterisk by active branch
git branch backup   # Creates branch backup
git switch backup   # Will switch to backup if it exists
git checkout branch_name    # Check out prexisting branch
git checkout -b create-new-branch   # Equivalent to below for creating new branch then switching to it
git switch -c create-new-branch     # creates new branch and switches to it
git branch -d branch-name   # Will not allow delete until merged - The current branch cannot be branch being deleted
git branch -D branch-name   # Will delete branch without merging - The current branch cannot be branch being deleted
git branch -m new-branch-name   # renames current branch
git branch -v       # Provides more detailed information on branches (-v verbose)

# merge merging:
git branch -v           # display branches verbose
git switch branch-to-merge-to
git merge branch-name   # a fast forward merges branch-name into branch-to-merge-to

# git diff:
git diff            # Shows any changes with unstaged changes
git diff HEAD       # Shows everything that has changed since last commit. Includign file additions or removals.
git diff --staged   # shows only staged changes
git diff --cached       # Synonomous with --staged
git diff HEAD name.txt      # shows all changes for specific file since last commit this can also be used for multiple files space delimited.
git diff branchA branchB    # will show difference between branchA and branchB.
git diff branchA..branchB   # synonomous with above.
git diff commit1 commit2    # where commit1 and commit2 are actually commit hashes will return the diff between those commits.
git diff commit1..commit2   # is synonomous with above.

# Stashing:
git stash           # stashes changes allowing branch change with current branch changes without commiting
git stash save      # synonomous with git stash
git stash pop       # restores stash to branch removing it from stash
git stash apply     # Allows a stash to be applied to a different branch as well as the originating branch
git stash list      # Shows all current stash items
git stash apply stash@{0}   # Applies stash at 0 which can be seen with git stash list
git stash drop stash@{0}    # Deletes stash@{0}
git stash pop stash@{0}     # Restores stash@{0}
git stash clear             # Deletes all stashes

# Navigating history/undoing/restoring:
git checkout 733cdea        # will checkout commit 733cdea detached from HEAD use git log --oneline to see commits
git checkout HEAD~1         # will checkout branch at first commit from init
git checkout HEAD~10        # will checkout branch at the 10th commit to keep this and start working from there make a new branch
git switch -                # go back one commit on the branch
git checkout HEAD file.txt  # will revert back to HEAD at the time of file.txt creation
git restore file.txt        # will do the same thing as git checkout HEAD file.txt
git restore --source HEAD~2 file.txt    # Restores branch to what it was for file.txt two commits prior to HEAD
git restore --staged file.txt           # will remove the staged (unstage) file.txt from a commit
git reset 13b1361           # will reset branch to hash 13b1361 - this is a standard reset and simply removes commits following that hash
git reset --hard 13b1361    # will reset branch and remove any current changes a hard reset
git revert 13b1361          # will revert branch to commit 12b1361 without losing history

# gitHub
git clone https://github.com/advalgo/wpdb-power-tool.git    # Clones/Copies wpdb-power-tool

# Adding Key:
ls -al ~/.ssh
ssh-keygen -t ed25519 -C "your@email.com"
cat ~/.ssh/id_ed25519.pub   # Copy this into GitHub Key and add
ssh-add ~/.ssh/ed_25519     # Add to local keys
```

