# How to merge an original repository into this fork

## Clone the original repository and create a new merged branch

```bash
# Clone the original repository
cd ../
git clone https://codeberg.org/ziglings/exercises.git
cd exercises

# Set the remote to your fork
git remote -v # should show origin https://codeberg.org/ziglings/exercises.git
git remote set-url origin https://github.com/s-0-a-r/ziglings-exercises.git
git remote -v # should show origin https://github.com/s-0-a-r/ziglings-exercises.git

# Create a new branch from the original branch
git switch -c original-branch

# Push the branch to your fork
git push -f origin original-branch

# Switch back to your branch
cd ../ziglings-exercises
git fetch
git switch -c merged-original-branch

# Merge the original branch into your branch
git merge origin/original-branch

# Push the merged branch to your fork
git push -u origin merged-original-branch
```

## Create a pull request

Please create a pull request from your merged branch to main.

## Merge the pull request

Please "Merge pull request" (not "Squash and merge") the pull request.
After the pull request is merged, you can delete the branch from this fork.
