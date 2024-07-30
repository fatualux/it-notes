## Installing Fedora on Termux

Termux is awesome, but it has more limitations than a whole GNU/Linux distribution running in proot.

Fedora is a stable and complete distribution, and you can install it above Termux by running the following command:

```
pkg install wget openssl-tool proot tar -y && hash -r && wget https://raw.githubusercontent.com/EXALAB/AnLinux-Resources/master/Scripts/Installer/Fedora/fedora.sh && bash fedora.sh
```

Then, run the following command:

```
echo "bash start-fedora.sh" >> ~/.bashrc
```

This way, every time you start Termux, a new session of Fedora will be started.

## Setting up Fedora on Termux

Let's install some packages:

```
dnf -y install vim wget git rustc cargo python3 npm nodejs openssl curl fzf zoxide xsel
```

Now, I need to customize my Fedora by importing my configs from a dedicated repository.

Before doing that, I want to have access to my GitLab account from my Android device via the SSH server.

Let's create a new SSH key:

```
ssh-keygen && cat ~/.ssh/id_rsa.pub
```

Then, I need to add the public key to my GitLab account.

```
ssh-add ~/.ssh/id_ed25519.pub && cat ~/.ssh/id_ed25519.pub
```

Then, from my GitLab account's profile, I can add the SSH key to my account.

Now I can clone my dotfiles' repository via SSH method:

```
git clone git@gitlab.com:fatualux/dotfiles.git
```

And replace the default configs with my customized ones.

```
cp -r dotfiles/.* . && rm -rf dotfiles
```
