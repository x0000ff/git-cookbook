```
$ git help checkout


GIT-CHECKOUT(1)                    Git Manual                   GIT-CHECKOUT(1)


NAME
       git-checkout - Switch branches or restore working tree files

SYNOPSIS
       git checkout [-q] [-f] [-m] [<branch>]
       git checkout [-q] [-f] [-m] --detach [<branch>]
       git checkout [-q] [-f] [-m] [--detach] <commit>
       git checkout [-q] [-f] [-m] [[-b|-B|--orphan] <new_branch>] [<start_point>]
       git checkout [-f|--ours|--theirs|-m|--conflict=<style>] [<tree-ish>] [--] <paths>
...
       git checkout [-p|--patch] [<tree-ish>] [--] [<paths>...]
```

As you can see in the **NAME** section this command can do 2 things:

1. switch branches
2. restore working tree files

So, this command can change current **HEAD** and can change current working tree

# What is it `<tree-ish>`?

> Tree-ish" is a term that refers to any identifier (as specified in the Git revisions documentation) that ultimately leads to a (sub)directory tree"
by user456814

For example:
- branch
- tag
- commit
- ref, like HEAD~3, 

# What is it "--"?

Image that you see this command:

```
$ git checkout A B C
```

What is `A`? `B` and `C`? Are they file names or git will checkout files `B` and `C` from **branch** `A`?

[In “git checkout — files”, what does “--” mean?](https://stackoverflow.com/a/2531228/2374209)

