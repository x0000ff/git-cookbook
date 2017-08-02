# Make ~~America~~ Our Project Great Again!

There 3 main components of a Git repository

![](/assets/main-components.png)
> https://wac-cdn.atlassian.com/dam/jcr:0c5257d5-ff01-4014-af12-faf2aec53cc3/01.svg?cdnVersion=fk

* `--soft`
  The staged snapshot and working directory are not altered in any way.

* `--mixed`
  The staged snapshot is updated to match the specified commit, but the working directory is not affected. This is the default option.

  After `mixed` **staging is empty always**

* `--hard`
  The staged snapshot and the working directory are both updated to match the specified commit.

![](/assets/reset.png)
> https://wac-cdn.atlassian.com/dam/jcr:2528918b-5c1a-4ab5-8454-88c3a66b14d1/03.svg?cdnVersion=fk

---

Before any `reset`

![](https://git-scm.com/images/reset/ex7.png)

## `--soft`

![](https://git-scm.com/images/reset/reset-soft.png)

```
$ git reset --soft HEAD~

$ git status
On branch test
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   test
```

## `--mixed`

![](https://git-scm.com/images/reset/reset-mixed.png)

```
$ git reset --mixed HEAD~
Unstaged changes after reset:
M	test

$ git status
On branch test
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   test

no changes added to commit (use "git add" and/or "git commit -a")
```

## `--hard`

![](https://git-scm.com/images/reset/reset-hard.png)

```
$ git reset --hard HEAD~
HEAD is now at aaa3981 Add test

$ git status
On branch test
nothing to commit, working tree clean
```

What about untracked files?

**They won't be affected!**

```
$ touch a.file

$ git status
On branch test
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	a.file

nothing added to commit but untracked files present (use "git add" to track)

$ git reset --hard HEAD~
HEAD is now at aaa3981 Add test

$ git status
On branch test
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	a.file

nothing added to commit but untracked files present (use "git add" to track)
```

But files that were added to the staging will be changed to the version that has new tree or **deleted** if they don't exist in the tree.

# Recipes

... from `git help reset`

## Undo a commit and redo

```
$ git commit ...
$ git reset --soft HEAD^      (1)
$ edit                        (2)
$ git commit -a -c ORIG_HEAD  (3)
```

1. This is most often done when you remembered what you just committed is incomplete, or you misspelled your commit message, or
both. Leaves working tree as it was before "reset".

2. Make corrections to working tree files.

3. "reset" copies the old head to .git/ORIG_HEAD; redo the commit by starting with its log message. If you do not need to edit the
message further, you can give -C option instead.

See also the --amend option to git-commit(1).


## Undo a commit, making it a topic branch

```
$ git branch topic/wip     (1)
$ git reset --hard HEAD~3  (2)
$ git checkout topic/wip   (3)
```

1. You have made some commits, but realize they were premature to be in the "master" branch. You want to continue polishing them in a topic branch, so create "topic/wip" branch off of the current HEAD.

2. Rewind the master branch to get rid of those three commits.

3. Switch to "topic/wip" branch and keep working.

---

# Further reading


- `$ git help reset`

- [Reset, Checkout, and Revert](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting)

- [Reset Demystified](https://git-scm.com/blog/2011/07/11/reset.html)

