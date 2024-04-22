# Reset

To reset a branch to a specific commit, use the `git reset` command.

For example:

```
 git log --oneline
d2cda98 (HEAD -> testing, origin/testing) renamed utils.py
6239db6 Updated README towebapp - testing branch
1ce064e Specified where to put font files
f4d4205 Fixed generate_css function
5abf634 Testing
651dc83 (origin/main, origin/HEAD, main) Edited README
7581ce1 Added demo
74e0e66 Initial commit
```

To go back to the second commit, you run the git reset command followed by the commit ID. That is:

```
git reset 6239db6
```

If you want to undo a commit and the all the changes made after that commit, you attach the --hard flag to your git reset command.

Let's test this out by reverting back to the first commit:

```
git reset --hard d2cda98
```

**git reset** is a good option when you realize that the changes being made to a particular local branch should be undone.

**git revert** is a good option for reverting changes pushed to a remote repository.
