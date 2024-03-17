### Publish an md-book on GitHub Pages

I have just started using [md-book](https://github.com/rust-lang/mdBook) to write documentation for my projects.

Here's a step by step guide on how to publish an md-book on GitHub Pages.

1. Create a public repository.
2. In the repository, add a **src** directory., and put all your md files there.
3. Create a simple book.toml.
4. Go to your repository on GitHub; in **Settings → Actions → General**, under the ***Workflow Permissions*** section, enable *Read & Write Permissions*, and flag *Allow GitHub Actions to create and approve pull requests*.
5. Create a mdBook workflow (mdbook.yml)
6. Set your Github Page deployment to newly created 'gh-pages' branch.
