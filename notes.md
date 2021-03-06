# Common

## Cleanup

`git-prune` - Prune all unreachable objects from the object database

```
git prune
```

[](https://git-scm.com/docs/git-prune "More")


# Commit

## Rename the last commit message

Sometimes I want to edit the last local commit message:

```
git commit --amend
```

Configured editor will appear. After editing save and close it. The commit's message will be updated

Or to re write the whole commit message in one line:

```
git commit --amend -m "New commit message"
```

## Add a file to the last local commit

```
git add file-name
git commit --amend
```

# Branches
  
## Change branch HEAD

```
git reset --hard HEAD~1
git reset --hard <COMMIT_HASH>
```

## Reset 

- Remove files from staged area

    ```
    git reset
    ``` 

- Reset completely to `HEAD` state 

    ```
    git reset --hard 
    ```

- Pull remote ignoring local branch

    ```
    git fetch --all
    git reset --hard origin/<branch_name>
    ```


## Checkout and track a remote

```
git checkout -b develop --track origin/develop
```

## Rename your local branch.

If you are on the branch you want to rename:

```
git branch -m new-name
```

If you are on a different branch:

```
git branch -m old-name new-name
```

## Delete remote branch.

```
git push origin :old-name
```

## Delete the old-name remote branch and push the new-name local branch.

```
git push origin :old-name new-name
```

## Reset the upstream branch for the new-name local branch.

Switch to the branch and then:

```
git push origin -u new-name
```

## Push branch to remote by force

It's useful after local rebase a branch which was pushed to remote

```
git push -f origin branch-name
```

## List of local branches

```
git branch
```

## List of all branches

```
git branch --all
```

or

```
git branch -a
```

# Fetch

## Remove untracked local branches

`-p`, `--prune` After fetching, remove any remote-tracking branches which no longer exist on the remote

```
git fetch --prune
```

# Tags

## Delete remote tag

```
git tag -d tag-name
git push origin :refs/tags/tag-name
```

## Move tag to other commit and push it to remote

```
git tag --force v1.0 <NEW-COMMIT-HASH>
git push --force --tags
```

> [Stackoverflow question](http://stackoverflow.com/a/25849917/2374209)

## Remove remote  
 
```
git tag -d release01
git push origin :refs/tags/release01
```

> [How do I remove or delete a tag from a Git repo](https://confluence.atlassian.com/bitbucket/how-do-i-remove-or-delete-a-tag-from-a-git-repo-282175551.html)

# Rebase

## Interactive Rebase

Start intercative rebase last **3** commits

```
git rebase -i HEAD~3
```
