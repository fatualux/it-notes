# Merge

This document explains the concept of fast forward and no fast forward merges in Git, as illustrated in the provided diagram.

## Explanation

### Initial State

Initially, we have two branches: `master` and `dev`.

```mermaid
graph TD;
    A[Task 1]:::task --> B[Task 2]:::task
    B --> C[Task 3]:::task
    C --> D[Final Task]:::finalTask
    C --> master[Master Branch]:::branch
    D --> dev[Development Branch]:::branch
    classDef finalTask fill:#90ee90, stroke:#000, stroke-width:2px;
    classDef branch fill:#f08080, stroke:#000, stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#2ca02c,stroke-width:2px
    linkStyle 3 stroke:#0000FF,stroke-width:2px
    linkStyle 4 stroke:#0000FF,stroke-width:2px
```

### Fast Forward Merge

When the `master` branch is merged into the `dev` branch and there are no new commits in the `master` branch, we can perform a fast forward merge. This will move the `master` branch pointer to the latest commit in the `dev` branch.

```mermaid
graph TD;
    A[Task A]:::task --> B[Task B]:::task
    B --> C[Task C]:::task
    C --> D[Final Task]:::finalTask
    D --> dev[Development Branch]:::branch
    D --> master[Master Branch]:::branch

    classDef task fill:#add8e6, stroke:#000, stroke-width:2px;
    classDef finalTask fill:#90ee90, stroke:#000, stroke-width:2px;
    classDef branch fill:#f08080, stroke:#000, stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#2ca02c,stroke-width:2px
    linkStyle 3 stroke:#0000FF,stroke-width:2px
    linkStyle 4 stroke:#0000FF,stroke-width:2px
```

### No Fast Forward Merge

If there are new commits in the `master` branch, a merge commit is created to combine the histories of the `master` and `dev` branches. This results in a no fast forward merge.

```mermaid
graph TD;
    A[Task A]:::task --> B[Task B]:::task
    B --> C[Task C]:::task
    C --> M[Merge Commit]:::merge
    C --> D[Final Task]:::finalTask
    M --> master[Master Branch]:::branch
    D --> dev[Development Branch]:::branch
    M --> D;

    classDef task fill:#add8e6, stroke:#000, stroke-width:2px;
    classDef finalTask fill:#90ee90, stroke:#000, stroke-width:2px;
    classDef merge fill:#ffcc00, stroke:#000, stroke-width:2px;
    classDef branch fill:#ff7f50, stroke:#000, stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#ff4500,stroke-width:2px
    linkStyle 3 stroke:#2ca02c,stroke-width:2px
    linkStyle 4 stroke:#0000ff,stroke-width:2px
    linkStyle 5 stroke:#0000ff,stroke-width:2px
```

## Commands

To perform a fast forward merge:

```bash
# Switch to master branch
git checkout master

# Merge dev branch into master
git merge dev
```

Optionally, you may choose to delete the feature branch after merging:

```bash
git branch -d dev               # Delete the local `develop` branch
git push origin --delete dev    # Delete the remote `develop` branch
```


To ensure no fast forward merge:

```bash
# Switch to master branch
git checkout master

# Merge dev branch into master with no fast forward option
git merge --no-ff dev
```

## Summary

- **Fast Forward Merge**: Moves the branch pointer forward without creating a new commit.
- **No Fast Forward Merge**: Combines branch histories and creates a new merge commit.