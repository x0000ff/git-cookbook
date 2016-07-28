# 0. Chapter

## Branches

### 1. Rename your local branch.

If you are on the branch you want to rename:

```
git branch -m new-name
```

If you are on a different branch:

```
git branch -m old-name new-name
```

### 2. Delete remote branch.

```
git push origin :old-name
```

### 3. Delete the old-name remote branch and push the new-name local branch.

```
git push origin :old-name new-name
```

### 4. Reset the upstream branch for the new-name local branch.

Switch to the branch and then:

```
git push origin -u new-name
```

### 5. Push branch to remote by force

It's useful after local rebase a branch which was pushed to remote

```
git push -f origin branch-name
```

## Rebase

### 1. Interactive Rebase

Start intercative rebase last **3** commits

```
git rebase -i HEAD~3
```

## Fetch

### 1. Remove untracked local branches

`-p`, `--prune` After fetching, remove any remote-tracking branches which no longer exist on the remote

```
git fetch --prune
```