### Managing branches

#### Creating a new branch locally

```
git checkout -b <branch-name>
```
With this command, you create a new branch in your local repository, and switch to it by updating the index and the files in the working tree.

#### Pushing the new branch remotely

When you are done with your work, commit the changes, and push them to your remote repository.

```
git add -A
git commit -m "commit message"
git push -u origin <branch-name>
```

#### Deleting a branch locally

```
git branch -d <branch-name>
```

#### Deleting a branch remotely

```
git push origin --delete <branch-name>
```
