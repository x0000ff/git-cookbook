# What is **current branch**?

It's the branch which **HEAD will point to the next** created **commit** automatically

# How Git knows **which branch is current**?

Inside `.git` folder there is a **simple text** file `HEAD`.

Current brunch is **feature**
```
cat .git/HEAD
ref: refs/heads/feature
```  
