## `cat-file`

Git has a tool to inspect its files: `cat-file`

git-cat-file - Provide content or type and size information for repository objects

- To get object **type**
  ```
   $ git cat-file -t <HASH>
   ``` 

- To get object **content**
  ```
   $ git cat-file -p <HASH>
   ``` 

---

# Further reading

- [`cat-file` at Pro Git](https://git-scm.com/docs/git-cat-file)