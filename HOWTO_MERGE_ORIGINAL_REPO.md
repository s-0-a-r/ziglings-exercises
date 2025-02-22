# How to merge an original repository into this fork

## Clone the original repository and create a new merged branch

```bash
# Clone the original repository
cd ../
git clone https://codeberg.org/ziglings/exercises.git
cd exercises

# Set the remote to this fork
git remote -v # should show origin https://codeberg.org/ziglings/exercises.git
git remote set-url origin https://github.com/s-0-a-r/ziglings-exercises.git
git remote -v # should show origin https://github.com/s-0-a-r/ziglings-exercises.git

# Create a new branch
git switch -c original-repository

# Push the branch to this fork
git push -f origin original-repository

# Switch back to this fork
cd ../ziglings-exercises
git switch main
git fetch
git reset --hard origin/main
git switch -c merge-original-repository

# Merge the original repository into this fork
git merge origin/original-repository

# Push the merged repository to this fork
git push -u origin merge-original-repository
```

## Create a pull request

Please create a pull request from your merged branch to main.

## Merge the pull request

Please "Merge pull request" (not "Squash and merge") the pull request.
After the pull request is merged, you can delete the branch from this fork.
