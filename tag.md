# Tag them all!

Tag is an object

## My first tag

### Add - Light first

```
$ git tag the-beginning
```

```
$ git cat-file -p the-beginning
tree 99339a532fb221a08fb0faf07175e5380bc0999d
parent 6347ba4da019ebb50a9bcdb6ced527adb83c78ee
author Konstantin Portnov <konstantin.portnov@mercadolibre.cl> 1500360967 -0400
committer Konstantin Portnov <konstantin.portnov@mercadolibre.cl> 1500360967 -0400

Second
```

Adding tag you can pass `<commit hash>` or `<object>`

```
$ git tag first HEAD~2
```

> `HEAD~2` second son of the HEAD of the current branch

```
$ git tag seconds develop
```

> Here `develop` is name of branch

## List

```
$ git tag
the-beginning
```

## Show

Will show the commit at which points tag

```
$ git tag show the-beginning
```

### Delete

```
$ git tag -d the-beginning
Deleted tag 'the-beginning' (was 885bb6c)
```


### Add - Annotated

```
$ git tag -a -m "My annotation" another-feature
```

# Further reading

- `$ git help tag`

- [2.6 Git Basics - Tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging)