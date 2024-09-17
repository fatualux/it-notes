# Commit

It is a **package** containing *tree* and *blob*, and it retains the changes we do to one or more project's files.

Git calculates a hash for every commit, used for its identification (the comment we attach to the commit is not unique).



* Commits create the ***directed acyclic graph*** of our history:
    - Each commit remembers which commit came before it (a merge commit points to two previous commits)
* A commit is a snapshot of the state of your files, with some *metadata*, informations about it contents, authors and date.
*  Each commit has a ***pointer*** to the previous one/s, and that pointer makes it **unique**.

### Directed Acyclic Graph (DAG) of Commits

This chart shows a more complex DAG structure typical in Git repositories:

```mermaid
graph TD;
    A[Commit A] --> B[Commit B]
    A --> C[Commit C]
    C --> D[Commit D]
    B --> E[Commit E]
    D --> E
    D --> F[Commit F]
    F --> G[Commit G]
    E --> H[Final Commit]

        linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#0000FF,stroke-width:2px
    linkStyle 3 stroke:#00FF00,stroke-width:2px
    linkStyle 4 stroke:#0000FF,stroke-width:2px
    linkStyle 5 stroke:#0000FF,stroke-width:2px
    linkStyle 6 stroke:#0000FF,stroke-width:2px
    linkStyle 7 stroke:#FF0000,stroke-width:2px
```