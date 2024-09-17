# Overview

### This section (***overview and subchapters***) was made possible by the work of [Paolo Venturi](https://github.com/paoloventuri) and [Davide Giudici](https://github.com/davide-giudici): it is strongly based on their training course about Git.

Git is a version-control system created in 2005.

It is very versatile as far as it regards *branches* and *reposoitories*, rollbacks and so on.

It is supported by many clients and IDEs, and it is used by a very active community.

## Basic concepts

* **A GIT project is an indivisible unit**
  * Git works always with the **entire source code** of the project
  * There is no checkout of a single file or directory

* **Peer to peer system**
  * Git works on a local copy of the **entire repository**
  * The network architecture is customizable (we can choose a distributed or a centralized network model)

* **Storage integrity**
  * Git stores files **in their entirety**
  * Git does not memorize the changes of a file: it creates <ins>a ***"smart" snapshot*** of the repository state at a given commit</ins>

* **Ramifications**
  * Strong orientation towards non-linear development

