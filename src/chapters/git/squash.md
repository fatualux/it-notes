# Squash

Squashing is a Git feature that allows you to combine multiple commits into a single commit. This is often used to create a cleaner project history before merging changes.

## What is Squash?

Squashing combines two or more consecutive commits into one, which helps to simplify the commit history and makes it easier to understand the changes made.

### How Squash Works

When you squash commits, Git will compress the selected commits into a single commit. You can do this using an interactive rebase.

```mermaid
graph TD;
    A[Commit A]:::commit --> B[Commit B]:::commit
    B --> C[Commit C]:::commit
    D[Master Branch]:::branch --> E[Commit D]:::commit
    E --> F[Commit E]:::commit

    B --> G[Start Squashing]:::action
    G --> H[Combined Commit]:::commit

    classDef commit fill:#90ee90, stroke:#000, stroke-width:2px;
    classDef branch fill:#f08080, stroke:#000, stroke-width:2px;
    classDef action fill:#ffcc00, stroke:#000, stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#2ca02c,stroke-width:2px
    linkStyle 3 stroke:#2ca02c,stroke-width:2px
    linkStyle 4 stroke:#ff4500,stroke-width:2px
```

### Example Squash

1. Assume you have the following commits in your `dev` branch:

```mermaid
graph TD;
    M[Master]:::branch --> A[Commit A]:::commit
    A --> B[Commit B]:::commit
    B --> C[Commit C]:::commit
    A --> D[Commit D]:::commit

    classDef commit fill:#90ee90, stroke:#000, stroke-width:2px;
    classDef branch fill:#f08080, stroke:#000, stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#2ca02c,stroke-width:2px
```

2. To squash the last two commits into one, initiate an interactive rebase:

```bash
# Start interactive rebase for the last 3 commits
git rebase -i HEAD~3
```

3. In the editor that opens, change the command for the last commit from `pick` to `squash` or `s`:

```plain text
pick <commit-hash-A> Commit A
pick <commit-hash-B> Commit B
squash <commit-hash-C> Commit C
```

4. After saving and exiting, Git will prompt you to edit the commit message for the new combined commit.

### Commands

To perform a squash:

```bash
# Start an interactive rebase
git rebase -i HEAD~<number-of-commits>
```

For example:

```bash
# Squash the last 3 commits
git rebase -i HEAD~3
```

### Summary

- **Squash**: Combines multiple commits into a single commit for a cleaner history.
- **Commands**: `git rebase -i HEAD~<number>`, followed by adjusting commit actions in the editor.
