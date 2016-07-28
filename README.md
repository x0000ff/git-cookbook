# Git Cookbook

<p align="center">
 <img src="/assets/git-logo.png" alt="Git logo">
</p>

My Git Cookbook with notes during my learning.

# Commit

## 1. Rename the last commit message

Sometimes I want to edit the last local commit message:

```
git commit --amend
```

Configured editor will appear. After editing save and close it. The commit's message will be updated

Or to re write the whole commit message in one line:

```
git commit --amend -m "New commit message"
```

## 2. Add a file to the last local commit

```
git add file-name
git commit --amend
```

# Branches

## 1. Rename your local branch.

If you are on the branch you want to rename:

```
git branch -m new-name
```

If you are on a different branch:

```
git branch -m old-name new-name
```

## 2. Delete remote branch.

```
git push origin :old-name
```

## 3. Delete the old-name remote branch and push the new-name local branch.

```
git push origin :old-name new-name
```

## 4. Reset the upstream branch for the new-name local branch.

Switch to the branch and then:

```
git push origin -u new-name
```

## 5. Push branch to remote by force

It's useful after local rebase a branch which was pushed to remote

```
git push -f origin branch-name
```

## 6. List of local branches

```
git branch
```

## 7. List of all branches

```
git branch --all
```

or

```
git branch -a
```