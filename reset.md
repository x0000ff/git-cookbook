# Make ~~America~~ Our Project Great Again!

There 3 main components of a Git repository

![](/assets/main-components.png)
> https://wac-cdn.atlassian.com/dam/jcr:0c5257d5-ff01-4014-af12-faf2aec53cc3/01.svg?cdnVersion=fk

* `--soft`
The staged snapshot and working directory are not altered in any way.

* `--mixed`
The staged snapshot is updated to match the specified commit, but the working directory is not affected. This is the default option.

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

---

# Further reading


- `$ git help reset`

- [Reset, Checkout, and Revert](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting)

- [Reset Demystified](https://git-scm.com/blog/2011/07/11/reset.html)

