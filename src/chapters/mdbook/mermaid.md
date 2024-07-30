### mdBook-mermaid

[mdBook-mermaid](https://github.com/badboy/mdbook-mermaid) is a preprocessor for [mdbook][] to add [mermaid.js][] support.

Mermaid.js is a JavaScript based diagramming and charting tool that renders Markdown-inspired text definitions to create and modify diagrams dynamically.

[mdbook]: https://github.com/rust-lang-nursery/mdBook
[mermaid.js]: https://mermaidjs.github.io/

#### Installation from source

```
git clone https://github.com/badboy/mdbook-mermaid.git && cd mdbook-mermaid && cargo install mdbook-mermaida
```

#### Configure your mdBook to use `mdbook-mermaid`

When adding `mdbook-mermaid` for the first time, let it add the required files and configuration:

```
mdbook-mermaid install path/to/your/book
```

This will add the following configuration to your `book.toml`:

```toml
[preprocessor.mermaid]
command = "mdbook-mermaid"

[output.html]
additional-js = ["mermaid.min.js", "mermaid-init.js"]
```
