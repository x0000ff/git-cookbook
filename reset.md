# Make ~~America~~ Our Project Great Again!

[Reset, Checkout, and Revert](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting)

There 3 main parts of the Git

![](https://wac-cdn.atlassian.com/dam/jcr:0c5257d5-ff01-4014-af12-faf2aec53cc3/01.svg?cdnVersion=fk)

* `--soft`
The staged snapshot and working directory are not altered in any way.

* `--mixed`
The staged snapshot is updated to match the specified commit, but the working directory is not affected. This is the default option.

* `--hard`
The staged snapshot and the working directory are both updated to match the specified commit.