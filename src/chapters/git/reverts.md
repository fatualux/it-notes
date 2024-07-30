# Reverts

To revert to a previous commit, you must first get the commit ID. To do that, run the command `git log` and copy the commit ID that you want to revert to.

Then run the command `git revert <commit ID>` to revert the commit.

For example:

```
git log --oneline
98de210 (HEAD -> main, origin/main) Import webbrowser
885cb83 Edited README via Termux on Android
fe40696 Added function to autostart brower
5d3db85 Fixed typo
7947d96 allow other devices on the same LAN to access the app
2b0e5af Added the possibility to download overlayed images and to delete the DOWNLOAD_DIR
8f9452f changed stylesheet, added table style
b39ce41 added virtualenv support - changed names
567467a Fixed overlay_frame_on_image function
8f1994b Added requirements to README
a9dd924 Merge branch 'main' into 'main'
3ef6ebf Add working folders to .gitignore
9b1e8e7 Converted demo video to gif
```

Then run `git revert <commit ID>` to revert the commit.

```
git revert 98de210
```

To revert to a commit that has been merged into another branch, you can use the command `git revert <commit ID> --merge <branch name>`

```
git revert 98de210 --merge main
```
