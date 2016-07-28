# Commit

# 1. Rename the last commit message

Sometimes I want to edit the last local commit message:

```
git commit --amend
```

Configured editor will appear. After editing save and close it. The commit's message will be updated

Or to re write the whole commit message in one line:

```
git commit --amend -m "New commit message"
```

# 2. Add a file to the last local commit

```
git add file-name
git commit --amend
```