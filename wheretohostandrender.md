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



https://squidfunk.github.io/mkdocs-material/publishing-your-site/#with-github-actions-material-for-mkdocs





If GitHub Actions cannot be utilized, you can manually deploy your MkDocs project to GitHub Pages by following these steps:

1. **Local Environment Setup**:
   - Ensure that you have Python and MkDocs installed on your local machine.
   - Clone your GitHub repository to your local machine if it’s not already.
2. **Build the Project**:
   - Open a terminal and navigate to your MkDocs project directory.
   - Run the command `mkdocs build`. This will generate a `site` directory containing the built website.
3. **Prepare for Deployment**:
   - Create a new branch in your repository named `gh-pages` if it doesn’t already exist.
   - Delete everything in the `gh-pages` branch, as the new build will replace it.

```
git checkout --orphan gh-pages
git rm -rf .
```



1. Move Built Files

   :

   - Move the contents of the `site` directory to the root of your repository.

```
mv site/* .
rmdir site
```



1. Commit and Push

   :

   - Commit the changes and push the `gh-pages` branch to GitHub.

```
git add .
git commit -m "Deploy MkDocs to GitHub Pages"
git push origin gh-pages
```



1. Configure GitHub Pages

   :

   - Go to the settings of your GitHub repository.
   - Navigate to the Pages section and select the `gh-pages` branch as the source.

Your MkDocs documentation should now be accessible at `https://<username>.github.io/<repository>/`. Remember to repeat steps 2-5 every time you update your documentation.



https://arturomoncadatorres.com/troubleshooting-deploying-documentation-using-mkdocs/