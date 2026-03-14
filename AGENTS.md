# AGENTS.md

## Cursor Cloud specific instructions

This is an **al-folio** Jekyll-based academic website. Single service (no backend/DB).

### Running the dev server

```bash
bundle exec jekyll serve --watch --port=8080 --host=0.0.0.0 --livereload
```

Site at `http://localhost:8080`. The `bin/entry_point.sh` script wraps this with auto-restart on `_config.yml` changes.

### Lint

```bash
npx prettier --check .
```

Prettier with the Liquid plugin. Config in `.prettierrc`.

### Build

```bash
bundle exec jekyll build
```

### Key gotchas

- `jupyter-nbconvert` must be on PATH for notebook blog posts to render. It installs to `~/.local/bin/` via pip; ensure that dir is on PATH (`export PATH="$HOME/.local/bin:$PATH"`).
- System deps required: `ruby-full`, `build-essential`, `zlib1g-dev`, `imagemagick`, `inotify-tools`.
- `bundle install` must run with `sudo` since gems install to `/var/lib/gems/`.
- The Gemfile references `jekyll-terser` from a Git repo; network access is needed for `bundle install`.
- Sass deprecation warnings during build are expected and non-blocking.
- Prettier lint will report formatting issues (exit code 1) on some repo files; these are pre-existing.
