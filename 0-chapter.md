# 0. Chapter



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

## Tags

### 1. Delete remote tag

```
git tag -d tag-name
git push origin :refs/tags/tag-name
```

