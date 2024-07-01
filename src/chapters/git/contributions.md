### Contributions

After making many mistakes about it, I decided to note down a workflow for my contributions to git repositories.

1. Fork the repository

2. Clone your fork
```
git clone [your fork] && cd [your fork]
```
3. Configure git to pull master/main branch from the original repository
```
git remote add upstream [original repository]
```
4. Create your branch
```
git checkout -b <your branch>
```
5. Commit
```
git add -A && git commit -m "commit message"
```
6. Push
```
git push
```

7. Create a merge request or a pull request.
