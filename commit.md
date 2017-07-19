# Save it!

```
$ git init
Initialized empty Git repository in /my-repo/.git/
$ echo "111" > 1.txt
$ mkdir files
$ echo "111" > files/2.txt
$ git add .
$ git commit -m "Initial commit"
[master (root-commit) ce6496b] Initial commit
 2 files changed, 2 insertions(+)
 create mode 100644 1.txt
 create mode 100644 files/2.txt
```

And what do we have in **objects**?

```
$ tree .git
.git
├── COMMIT_EDITMSG
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
├── logs
│   ├── HEAD
│   └── refs
│       └── heads
│           └── master
├── objects
│   ├── 3c
│   │   └── 1cb3829a09a57df9ea94f7bfdf76ed123161c2
│   ├── 58
│   │   └── c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c
│   ├── 61
│   │   └── caec3709a1e6473b2f33bfc92bd9d138071e88
│   ├── ce
│   │   └── 6496b7a3dd69b1ee8e403c22b77a148bd38ec4
│   ├── info
│   └── pack
└── refs
    ├── heads
    │   └── master
    └── tags
```

# What creates `commit`

Let's checkout what was created...

We have these objects:
- `3c1cb3829a09a57df9ea94f7bfdf76ed123161c2`
- `58c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c`
- `61caec3709a1e6473b2f33bfc92bd9d138071e88`
- `ce6496b7a3dd69b1ee8e403c22b77a148bd38ec4`

## Commit - `ce6496`

- Type

```
$ git cat-file -t ce6496b7a3dd69b1ee8e403c22b77a148bd38ec4
commit
```

- Content

```
$ git cat-file -p ce6496b7a3dd69b1ee8e403c22b77a148bd38ec4
tree 3c1cb3829a09a57df9ea94f7bfdf76ed123161c2
author Konstantin Portnov <konstantin.portnov@mercadolibre.cl> 1500482225 -0400
committer Konstantin Portnov <konstantin.portnov@mercadolibre.cl> 1500482225 -0400

Initial commit
```

```
$ cat ./git/
```

## `3c1cb3` - Tree `.`

- Type

```
$ git cat-file -t ce6496b7a3dd69b1ee8e403c22b77a148bd38ec4
tree
```

- Content

```
$ git cat-file -p 3c1cb3829a09a57df9ea94f7bfdf76ed123161c2
100644 blob 58c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c	1.txt
040000 tree 61caec3709a1e6473b2f33bfc92bd9d138071e88	files
```

### `61caec` - Tree `./files`

- Type

```
$ git cat-file -t 61caec3709a1e6473b2f33bfc92bd9d138071e88
tree
```

- Content


```
$ git cat-file -p 61caec3709a1e6473b2f33bfc92bd9d138071e88
git cat-file -p 61caec3709a1e6473b2f33bfc92bd9d138071e88
100644 blob 58c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c	2.txt
```

## `58c9bd` - Blob `111`

- Type

```
$ git cat-file -t 58c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c
blob
```

- Content


```
$ git cat-file -p 58c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c
111
```

## Result

So, we have this situation:

Type | Hash
---|---
commit |`ce6496b7a3dd69b1ee8e403c22b77a148bd38ec4`
tree | `3c1cb3829a09a57df9ea94f7bfdf76ed123161c2`
tree |`61caec3709a1e6473b2f33bfc92bd9d138071e88`
blob | `58c9bdf9d017fcd178dc8c073cbfcbb7ff240d6c`

