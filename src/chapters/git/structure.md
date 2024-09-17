# Structure

We could see ***git*** as a database, holding couples *key/value*, where:

- **Tree** (as a unix-like system directory tree)
- **Blobs** (comparable to files)
- **Commit**
- **Tags**


```mermaid
graph TD

  A[Commit 25a9001] ==o B
  B[Commit 6abe5512] ==libs==o C1
  B ==templates==o C2
  C1[libs 52d09140] ==lyrics.txt==o D1
  C2[templates 12ef5142] ==template.txt==o D2
  D1[Finding beauty in the dissonance]
  D2[This is an empty template]

  style A fill:#1f77b4,stroke:#1f77b4,stroke-width:2px
  style B fill:#ff7f0e,stroke:#ff7f0e,stroke-width:2px
  style C1 fill:#2ca02c,stroke:#2ca02c,stroke-width:2px
  style C2 fill:#2ca02c,stroke:#2ca02c,stroke-width:2px
  
  linkStyle 0 stroke:#2ca02c,stroke-width:2px
  linkStyle 1 stroke:#2ca02c,stroke-width:2px
  linkStyle 2 stroke:#2ca02c,stroke-width:2px
  linkStyle 3 stroke:#2ca02c,stroke-width:2px
  linkStyle 4 stroke:#2ca02c,stroke-width:2px
```

Here we can see how every "block" has a corresponding *label*: we refer to these labels as **tags**.

```mermaid
graph TD
    A[Working Directory]:::workingDir --o|add| B[Staging Area or Index]:::stagingArea
    B -->|commit| C[Local Repository]:::localRepo
    C -->|push| D[Remote Repository]:::remoteRepo
    D -->|pull| C
    C --> E[Branch]:::branch
    E --> F[Commit]:::commit
    
    subgraph Local Repository
        C
        E
        F
    end
    
    subgraph Remote Repository
        D
    end

    classDef workingDir fill:#f9f,stroke:#333,stroke-width:2px;
    classDef stagingArea fill:#ff9,stroke:#333,stroke-width:2px;
    classDef localRepo fill:#9f9,stroke:#333,stroke-width:2px;
    classDef remoteRepo fill:#9ff,stroke:#333,stroke-width:2px;
    classDef branch fill:#f99,stroke:#333,stroke-width:2px;
    classDef commit fill:#99f,stroke:#333,stroke-width:2px;

    linkStyle 0 stroke:#2ca02c,stroke-width:2px
    linkStyle 1 stroke:#2ca02c,stroke-width:2px
    linkStyle 2 stroke:#0000FF,stroke-width:2px
    linkStyle 3 stroke:#FF0000,stroke-width:2px
    linkStyle 4 stroke:#0000FF,stroke-width:2px
    linkStyle 5 stroke:#0000FF,stroke-width:2px
```
