# git-commands

### Change commit message based on ID
notes on common use of git commands

Change commit message of a specific commit
```
git rebase -i <commit ID - 1>
```
```
7c93068 (HEAD -> master) fourth commit
5472b0d third commit
cfef644 second commit
1b11d59 initial commit
```
For example, change third commit -> so start at second commit (exclusive `cfef644`)
```
git rebase -i cfef644
```
```
pick 5472b0d third commit
pick 7c93068 fourth commit
```
Then
```
edit 5472b0d third commit
pick 7c93068 fourth commit
```
Then it stops at third commit, start making change:
```
git commit --amend -m "Updated third commit message"
git rebase --continue
```
Back to normal

### Difference
```
git diff
git diff -- <file name>
```

### Logs
```
git log --oneline -5
```

### Remote
```
git remote -v
```

### Branch
```
# list all branches
git branch

# switch branch
git checkout <branch name>

# create new branch and switch to new branch
git checkout -b <new branch>

# pull from remote repo (origin), from remote branch (master)
git pull origin master

# merge from specific branch
git merge <target branch>    --> git merge feature (merge from feature to whatever current branch we're in)
```
