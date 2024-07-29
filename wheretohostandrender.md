# Where to Deploy are MarkDown repository to

https://joshcollinsworth.com/blog/build-static-sveltekit-markdown-blog

SvelteKit has many [adapters](https://kit.svelte.dev/docs#adapters), and comes pre-installed with one that will automatically detect and build properly for Netlify, Vercel, or Cloudflare Pages—which is both handy and impressive! But for static pre-rendering, we want `adapter-static`.

GitHub just "bundles" Jekyll support

https://squidfunk.github.io/mkdocs-material/

https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/

https://squidfunk.github.io/mkdocs-material/reference/math/

GitHub Action for MkDocs 

https://squidfunk.github.io/mkdocs-material/publishing-your-site/

https://github.com/marketplace/actions/deploy-mkdocs

https://blog.elmah.io/hosting-a-mkdocs-driven-documentation-site-on-github-pages/

https://github.com/mkdocs/mkdocs/discussions/2599

- Migrate documentation from Jekyll to [MkDocs](https://www.mkdocs.org/)
- Use [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) to make the docs more visually appealing

MkDocs is written in Python and can be installed with `pip`, doesn't need native extensions and is made for writing technical documentation. Like Jekyll, it lets us write in Markdown (which can be [extended](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/) in multiple ways) and can be deployed to GitHub pages

[Linking to internal pages](https://www.mkdocs.org/user-guide/writing-your-docs/#internal-links) is less painful than with Jekyll, and it has a great built-in search UX. It auto-generates table-of-contents for each page, which makes discovery and navigation a lot easier. Creating links to specific sections of a page is also very easy, which makes referring to our docs in Slack or GitHub issues a bit more practical.

Material for MkDocs provides a more modern look, ships with loads of advanced features and is highly customizable.

https://github.com/DependencyTrack/dependency-track/issues/1842



MkDocs uses Jinja2, a powerful templating language

1. **Documentation Structure**: MkDocs is specifically designed for creating documentation, providing a hierarchical structure that mirrors folders and files. It automatically generates a table of contents based on the file structure, simplifying navigation. Jekyll, on the other hand, gives developers more flexibility in organizing content, making it suitable for both traditional websites and documentation. Jekyll requires manual creation of navigation menus and table of contents, which can be more time-consuming for extensive documentation projects.
2. **Development Environment**: Jekyll requires Ruby and its associated dependencies to be installed, which can add a layer of complexity for developers who are not familiar with Ruby development. MkDocs, on the other hand, is built on Python and is generally easier to set up and get started with. This can make MkDocs more accessible for developers who prefer Python or want a simpler setup process.