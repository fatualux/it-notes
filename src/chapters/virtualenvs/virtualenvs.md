### Python Virtual Environments

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
