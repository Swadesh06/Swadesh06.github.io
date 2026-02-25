# AGENTS.md

## Cursor Cloud specific instructions

This is a Jekyll-based academic portfolio site using the [al-folio](https://github.com/alshedivat/al-folio) theme. It generates a static HTML site from Markdown, Liquid templates, SCSS, and BibTeX.

### Running the dev server

```bash
sudo -E env "PATH=$PATH" bundle exec jekyll serve --port=8080 --host=0.0.0.0 --livereload --trace
```

The site is served at `http://localhost:8080` with LiveReload on port `35729`.

### Lint

```bash
npx prettier --check .
```

### Build

```bash
sudo -E env "PATH=$PATH" bundle exec jekyll build --trace
```

### Key gotchas

- `bundle exec jekyll` must run with `sudo` because gems install to `/var/lib/gems/`. Pass `env "PATH=$PATH"` to sudo so that Node.js (needed by Terser/ExecJS) and `jupyter` (needed by `jekyll-jupyter-notebook`) are found.
- ImageMagick must be installed (`convert` binary) for the `jekyll-imagemagick` plugin to generate responsive WebP images.
- `nbconvert` (Python) must be installed system-wide (`sudo pip install nbconvert --break-system-packages`) so that `jupyter` is on the sudo PATH for converting `.ipynb` files during builds.
- Sass deprecation warnings and Terser "JavaScript runtime" warnings are upstream issues in the theme's SCSS/font files and are non-blocking.
- The site's `_config.yml` has `url: https://Swadesh06.github.io` and `baseurl:` empty. No changes needed for local dev.
