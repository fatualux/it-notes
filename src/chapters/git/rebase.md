# Rebase

Rebasing is a powerful feature in Git that allows you to integrate changes from one branch into another. This document explains how to rebase and provides visual diagrams to illustrate the process.

## What is Rebase?

Rebasing involves moving or combining a sequence of commits to a new base commit. This results in a linear project history and can help simplify merge conflicts.

### How Rebase Works

When you rebase a branch onto another, Git replays the commits from your current branch on top of the specified branch.

```mermaid
graph TD;
    A[Commit A]:::commit --> B[Commit B]:::commit
    B --> C[Commit C]:::commit
    D[Master Branch]:::branch --> E[Commit D]:::commit
    E --> F[Commit E]:::commit

    B --> G[Rebase onto Master]:::action
    G --> F[New Commit C']:::commit

    classDef commit fill:#90ee90, stroke:#000, stroke-width:2px;
    classDef branch fill:#f08080, stroke:#000, stroke-width:2px;
    classDef action fill:#ffcc00, stroke:#000, stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#2ca02c,stroke-width:2px
    linkStyle 3 stroke:#2ca02c,stroke-width:2px
    linkStyle 4 stroke:#ff4500,stroke-width:2px
```

### Example Rebase

1. Assume you have a feature branch `dev` based on `master`. The commits look like this:

```mermaid
graph TD;
    M[Master]:::branch --> A[Commit A]:::commit
    A --> B[Commit B]:::commit
    M --> C[Commit C]:::commit

    classDef commit fill:#90ee90, stroke:#000, stroke-width:2px;
    classDef branch fill:#f08080, stroke:#000, stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#2ca02c,stroke-width:2px
```

2. If you want to rebase your `dev` branch onto `master`, after running `git rebase master`, the history would look like:

```mermaid
graph TD;
    M[Master]:::branch --> A[Commit A]:::commit
    A --> B[Commit B]:::commit
    C[Commit C]:::commit
    B --> D[New Commit C']:::commit

    classDef commit fill:#90ee90, stroke:#000, stroke-width:2px;
    classDef branch fill:#f08080, stroke:#000, stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#2ca02c,stroke-width:2px
```

### Commands

To perform a rebase:

```bash
# Start rebasing onto another branch
git rebase <branch>
```

For example:

```bash
# Rebase dev branch onto master
git rebase master
```

To continue the rebase after resolving conflicts:

```bash
git rebase --continue
```

To abort the rebase process:

```bash
git rebase --abort
```

### Handling Conflicts

During rebasing, if you encounter conflicts, you'll need to resolve them manually. Once you've fixed the conflicts, use the commands above to continue or abort the rebase.

### Summary

- **Rebase**: Moves or combines commits to a new base commit for a linear history.
- **Commands**: `git rebase <branch>`, `git rebase --continue`, `git rebase --abort`.
- **Conflict Resolution**: Similar to merging, requires manual intervention in case of conflicts.




