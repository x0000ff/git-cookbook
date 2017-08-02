# What is HEAD?

`HEAD` is the snapshot of your last commit, next parent

```
$ cat .git/HEAD
ref: refs/heads/master

$ cat .git/refs/heads/master
e9a570524b63d2a2b3a7c3325acf5b89bbeb131e

$ git cat-file -p e9a570524b63d2a2b3a7c3325acf5b89bbeb131e
tree cfda3bf379e4f8dba8717dee55aab78aef7f4daf
author Scott Chacon  1301511835 -0700
committer Scott Chacon  1301511835 -0700

initial commit

$ git ls-tree -r cfda3bf379e4f8dba8717dee55aab78aef7f4daf
100644 blob a906cb2a4a904a152...   README
100644 blob 8f94139338f9404f2...   Rakefile
040000 tree 99f1a6d12cb4b6f19...   lib
```

# What is **current branch**?

It's the branch which **HEAD will point to the next** created **commit** automatically

# How Git knows **which branch is current**?

Inside `.git` folder there is a **simple text** file `HEAD`.

- Current brunch is `feature` (**points on a reference**)
```
$ cat .git/HEAD
ref: refs/heads/feature
```  

- Detached `HEAD` state, **points on commit** `51d8df...`
```
$ cat .git/HEAD
51d8dfa0322483a91adda2ef2ef4fe1319ae5a1b
```  

You can edit this file manually and it will change current branch.