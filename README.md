# canhe173.github.io

Source code for Can He's personal academic website.

Live site: <https://canhe173.github.io>

## Stack

- Jekyll site hosted on GitHub Pages
- Theme base: Academic Pages (derived from Minimal Mistakes)
- Ruby dependencies managed with Bundler (`Gemfile`)
- Optional JavaScript minification via npm (`package.json`)

## Main Content

| Section | English URL | Chinese URL | Source file(s) |
| --- | --- | --- | --- |
| Home/About | `/` | `/zh/` | `_pages/about.md`, `_pages/about-zh.md` |
| Bio/CV | `/cv/` | `/zh/cv/` | `_pages/cv.md`, `_pages/cv-zh.md` |
| Projects | `/project/` | `/zh/project/` | `_pages/project.md`, `_pages/project-zh.md` |
| Publications | `/publications/` | `/zh/publications/` | `_pages/publications.md`, `_pages/publications-zh.md` |

Navigation menus are configured in `_data/navigation.yml` (`main` and `main_zh`).

## Repository Map

- `_config.yml`: site metadata, author profile, plugins, and global settings
- `_config.dev.yml`: local development overrides
- `_pages/`: main pages
- `_posts/`: blog posts (template/example posts are still present)
- `images/`: images and favicon assets
- `files/`: downloadable files (PDFs, CV, etc.)
- `assets/`: CSS and JavaScript
- `markdown_generator/`: optional tools for publication markdown generation

## Local Development

### 1. Install dependencies

```bash
bundle install
```

Optional (only if you want to rebuild `assets/js/main.min.js`):

```bash
npm install
```

### 2. Run the site locally

```bash
bundle exec jekyll serve --livereload --config _config.yml,_config.dev.yml
```

Then open <http://localhost:4000>.

### 3. Build for production check

```bash
bundle exec jekyll build
```

### 4. Rebuild minified JavaScript (optional)

```bash
npm run build:js
```

## Bilingual Page Pattern

For each EN/ZH page pair:

- Set `lang: en` or `lang: zh`
- Set `alt_permalink` to the corresponding page in the other language
- Keep both entries in `_data/navigation.yml`

Language-aware navigation and the EN/ZH switch are handled in `_includes/masthead.html`.

## Publications Workflow Notes

Publications are currently maintained directly in:

- `_pages/publications.md`
- `_pages/publications-zh.md`

`markdown_generator/` includes legacy scripts/notebooks from Academic Pages if you want to generate publication markdown from TSV/BibTeX in the future.

## Deployment

Push commits to the repository's publishing branch configured in GitHub Pages. GitHub Pages then rebuilds and deploys the site automatically.

## Credits

This site is based on:

- Academic Pages: <https://academicpages.github.io>
- Minimal Mistakes: <https://mmistakes.github.io/minimal-mistakes/>

## License

MIT License (see `LICENSE`).
