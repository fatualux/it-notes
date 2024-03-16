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
