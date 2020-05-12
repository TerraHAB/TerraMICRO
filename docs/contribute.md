# Contribute
## Contact us!
Chat with the team on the [RIT SPEX Slack](https://spexsuperslack.slack.com)
in the `#alumni-hab` channel.

## Follow development
To track tasks and log progress, we've set up [a JIRA for this project](https://terrahab.atlassian.net/).

## Submit your designs
TerraMICRO is an open source project. All of the source code and documentation
is hosted on [the TerraMICRO GitHub repository](https://github.com/TerraHAB/TerraMICRO).

Submit your contributions as a pull request to this repository!

## Adding to documentation
TerraMICRO documentation is powered by [MkDocs](https://www.mkdocs.org/), the
backend that builds markdown files into a beautiful website. Whenever changes
to get pushed to `master`, MkDocs is run via GitHub Actions and serves the
result at
[terrahab.github.io/TerraMICRO/](https://terrahab.github.io/TerraMICRO/).

### Formatting
Edit the docs as Markdown files, then use `mkdocs serve` to preview them in
your browser.

In addition to all GitHub flavor markdown,
[admonitions](https://python-markdown.github.io/extensions/admonition/) and
[footnotes](https://squidfunk.github.io/mkdocs-material/extensions/footnotes/)
are also allowed. 

[Even more extensions](https://python-markdown.github.io/extensions/) are
available for MkDocs, just [add them to the `mkdocs.yml`](https://www.mkdocs.org/user-guide/configuration/#markdown_extensions)
to use them.

### Adding new pages
To add a new page to the documentation, create a new `.md` file and place it
under the `docs/` directory. Add the page as a new item in the navigation bar
by adding a new key to the `mkdocs.yml` under `nav`, where the key is how it
will show up in the navigation bar and the value is the path to the 
corresponding markdown file.
```yaml
nav:
  - My New Page Title: my_new_page.md
```
Other nested navigation bar items are generated from headings inside the file.

### Building the documentation locally

Install MkDocs to your machine or virtual environment.
```bash
pip install mkdocs
```

Then start a server on `localhost`. This builds the documentation and serves
the site locally. This server updates live when edits are made to the docs
files, so you don't need to close or restart the server when editing.
```bash
mkdocs serve
```

Alternatively, just build the site files.
```bash
mkdocs build
```

For more help and options, refer to the `mkdocs` CLI help text.
```bash
mkdocs -h
```
