# Add files to staging

Let's create a file

```
$ echo "111" > ./1.txt
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

As you can see appeared new object `58c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c`

- What is this?

  It is a blob with contents of `1.txt`

- What is `58c9bd...`?

  It's a **sha1** hash of `blob⎵<blob size>\0<content>`
  ```
  $ git hash-object 1.txt
58c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c
  ```
  
> **Important**
As you can see hash doesn't depend of time, OS, localization and so on. It means that if you create file with the same content on other machine you will have the same hash.

## But if we add another file with the same content?

```
$ mkdir files
$ echo "111" > files/2.txt
$ tree .
.
├── 1.txt
└── files
    └── 2.txt

1 directory, 2 files
```

```
$ git add .
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   1.txt
	new file:   files/2.txt
```

So, what do we have in the **objects**?

```
$ tree .git/objects
.git/objects
├── 58
│   └── c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c
├── info
└── pack

3 directories, 1 file
```

**Nothing changed!** 

**Git** just **can't** create any object because new object will have the same hash and content.



