# EEGManySteps Website

Quarto-based website for the EEGManySteps initiative.

## Project structure

```
_quarto.yml          # Site config (navbar, theme, format)
index.qmd            # Home page (motivation, project, methodology, organisation)
news.qmd             # News items in reverse chronological order
team.qmd             # SC and AB member lists, role definitions
datasets.qmd         # Table of available MoBI datasets on OpenNeuro
join.qmd             # How to participate, role descriptions
styles.css           # Custom CSS
posters.qmd          # Conference posters and presentations
files/               # Static assets
  slides/            # Presentation slide decks
  data/              # Survey and data files
  posters/           # Conference poster PDFs and thumbnails
```

## Rules

- No Python, Jupyter, or computational notebooks. Use Chart.js (via raw HTML blocks) for any interactive charts.
- No `freeze: auto` or `requirements.txt`. The site must build with `quarto render` alone, no Python runtime.
- Always use `uv`/`uvx` for any Python scripting needs (not bare python3/pip).
- File names: lowercase, underscores, no spaces. Dates as YYYY-MM.
- All links to project files should use relative paths (e.g. `./files/slides_kickoff.pdf`), not absolute GitHub URLs.
- Links to the GitHub repo should point to `EEGManySteps/eegmanysteps.github.io` (the org repo).
- Run `typos` before committing to catch spelling errors. CI enforces this via crate-ci/typos.
- Run `quarto render` locally before pushing to verify the build.

## Deployment

- Cloudflare Pages via GitHub Actions (`.github/workflows/deploy.yml`)
- Build command: `quarto render`
- Output directory: `_site`
- Custom domain: `eegmanysteps.org`
- PR previews via Cloudflare Pages branch deploys

## Planning files

See `plan.md`, `ideas.md`, `scratch_notes.md`, `research.md` if present (all gitignored).
