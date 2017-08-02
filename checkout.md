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

---

* [--](--.md)
* [tree-ish](tree-ish.md)