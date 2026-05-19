# WellNest Participant User Manual

This repository hosts the participant-facing WellNest user manual as a GitHub Pages site built with Jekyll and the Just the Docs theme.

## Local structure

- `docs/` contains the Jekyll site source.
- `docs/assets/images/` contains screenshots used by the manual.
- `.github/workflows/pages.yml` builds and deploys the site to GitHub Pages.

## GitHub Pages setup

After pushing this repository to GitHub:

1. Open the repository on GitHub.
2. Go to **Settings** -> **Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Push to the `main` branch, or run the workflow manually from the **Actions** tab.

The site will be published at:

```text
https://USERNAME.github.io/wellnest-participant-manual/
```

Replace `USERNAME` with the GitHub account or organization name that owns the repository.

## Local preview

If Ruby and Bundler are installed locally:

```bash
cd docs
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000/wellnest-participant-manual/`.

This uses the same `baseurl` as GitHub Pages, so image paths and internal links can be tested locally before pushing changes.

Keep the server running while editing. Jekyll will rebuild the site automatically after most file changes.
