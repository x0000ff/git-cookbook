# Add files to staging

Let's create a file

```
$ echo "111" >> ./1.txt
$ ls .
1.txt
```

```
$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	1.txt

nothing added to commit but untracked files present (use "git add" to track)
```

```
$ tree .git
.git
├── HEAD
├── branches
├── config
├── description
├── hooks
│   ├── applypatch-msg.sample
│   ├── commit-msg.sample
│   ├── post-update.sample
│   ├── pre-applypatch.sample
│   ├── pre-commit.sample
│   ├── pre-push.sample
│   ├── pre-rebase.sample
│   ├── prepare-commit-msg.sample
│   └── update.sample
├── info
│   └── exclude
├── objects
│   ├── info
│   └── pack
└── refs
    ├── heads
    └── tags

9 directories, 13 files
```

As you can see nothing changed in the repo's state

And now we add the file to the staging area

 ```
 $ git add 1.txt
 ```
 
 ```
 $ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   1.txt
 ``` 
 
 ```
 $ tree .git
.git
├── HEAD
├── branches
├── config
├── description
├── hooks
│   ├── applypatch-msg.sample
│   ├── commit-msg.sample
│   ├── post-update.sample
│   ├── pre-applypatch.sample
│   ├── pre-commit.sample
│   ├── pre-push.sample
│   ├── pre-rebase.sample
│   ├── prepare-commit-msg.sample
│   └── update.sample
├── index
├── info
│   └── exclude
├── objects
│   ├── 58
│   │   └── c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c
│   ├── info
│   └── pack
└── refs
    ├── heads
    └── tags

10 directories, 15 files
```