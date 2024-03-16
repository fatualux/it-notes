# Git

##### Here are some notes I have been taking about my experience with Git.

### Git and Python Virtual Environments

In distros such as Arch Linux, you cannot install Python packages with *pip*; if you try to launch a command like:

```bash
python -m pip install <package>
```

The system will return an error message:

```
This environment is externally managed
╰─> To install Python packages system-wide, try 'pacman -S
    python-xyz', where xyz is the package you are trying to
    install.

    If you wish to install a non-Arch-packaged Python package,
    create a virtual environment using 'python -m venv path/to/venv'.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip.
The reason the user location is blocked by this is mentioned in the PEP:

    This may pose a critical problem for the integrity of distros, which often have package-management tools that are themselves written in Python. For example, it’s possible to unintentionally break Fedora’s dnf command with a pip install command, making it hard to recover.

    This applies both to system-wide installs (sudo pip install) as well as user home directory installs (pip install --user), since packages in either location show up on the sys.path of /usr/bin/python3.
```

I often try softwares whose backend is written in Python, and I prefer to install them in virtual environments, one for each project.
It may seem a waste of disk space, but this ensures that the library versions specified in *requirements.txt* are respected, and no conflicts arise.
Plus, you work in an isolated environment; this gives you more control over what you install, and you have some advantages, such as:
- you don't need to worry about your system's Python version
- every change you make does not break anything
- you can remove the software by simply deleting its directory

So, what I usually do is creating a virtual environment with the name of the project, then cloning the repository inside its directory.

```
virtualenv <project> && git -C <project> clone <repo>
cd <project> && mv -f <project>/{.,}* . && rm -rf <project>
source bin/activate && python3 -m python3 -m pip install --upgrade pip
pip install -r requirements.txt
```

To activate the virtual environment, just type:

```
source bin/activate
```

To deactivate the virtual environment, just type:

```
deactivate
```
### Mirroring a repository from Gitlab to GitHub

Here's a step by step guide on how to mirror a repository from GitLab to GitHub.

1. Go to your repository on GitLab, then:
- **Settings → Repository → Mirroring repositories**
- Click on **Add new**
- In the form *Git repository URL*, type your Github repo's URL, according to this logic:
``````
ssh://github.com/[your-username]/[your-repo-name].git
``````
- Click on **Detect host keys**
- In the form ***Authentication method***, select **SSH public key**
- Click on **Mirror repository**.
- By clicking the apporiate button, copy your SSH public key.

2. On Github, go to your repository.
- Click on **Settings → Deploy keys**
- Click on **Add deploy key**
- In the form *Title*, type something like "deploy key" and in the form *Key* paste your public key.
- Flag the field *Allow write access*, then click on **Add key**.

3. Go back to GitLab, and go to your repository on GitLab.
- In **Settings → Repository → Mirroring repositories**, under your mirrored repository, click the *Refresh* button.

### Publish an md-book on GitHub Pages

I have just started using [md-book](https://github.com/rust-lang/mdBook) to write documentation for my projects.

Here's a step by step guide on how to publish an md-book on GitHub Pages.

1. Create a public repository.
2. In the repository, add a **src** directory., and put all your md files there.
3. Create a simple book.toml.
4. Go to your repository on GitHub; in **Settings → Actions → General**, under the ***Workflow Permissions*** section, enable *Read & Write Permissions*, and flag *Allow GitHub Actions to create and approve pull requests*.
5. Create a mdBook workflow (mdbook.yml)
6. Set your Github Page deployment to newly created 'gh-pages' branch.

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
