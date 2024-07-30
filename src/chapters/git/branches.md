### Managing branches

#### Creating a new branch locally

```
git checkout -b [branch-name]
```
With this command, you create a new branch in your local repository, and switch to it by updating the index and the files in the working tree.

#### Pushing the new branch remotely

When you are done with your work, commit the changes, and push them to your remote repository.

```
git add -A
git commit -m "commit message"
git push -u origin [branch-name]
```

#### Deleting a branch locally

```
git branch -d [branch-name]
```

#### Deleting a branch remotely

```
git push origin --delete [branch-name]
```

#### Renaming a branch

```
git branch -m [old-branch-name] [new-branch-name]
```

#### Merging branches

```
git merge [branch-name]
```

Example:

If you want to merge the `master` branch into the `develop` branch, use the following command:

```
git merge master develop
```

Or:

```
git checkout master
git merge develop
git branch -d develop               # Delete the `develop` branch
git push origin --delete develop    # Delete the remote `develop` branch
```
