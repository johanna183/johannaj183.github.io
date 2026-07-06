# CLAUDE.md

Guidance for AI assistants (Claude Code and others) working in this repository.

## What this repo is

`johanna183.github.io` is a personal website served via **GitHub Pages user site**
hosting: any push to the default branch that GitHub Pages is configured to serve
(typically `main`) is published directly at `https://johannaj183.github.io/` with
no build step required.

The site is currently a minimal static scaffold and is expected to grow over time
(about/projects/contact content, possibly more pages or a blog).

## Structure

```
/
├── index.html              Home page — entry point, linked from GitHub Pages root
├── assets/
│   ├── css/style.css       All site styling (single stylesheet, CSS custom properties for theming)
│   └── images/             Static image assets (currently empty)
├── .gitignore
└── CLAUDE.md
```

There is no build tooling, package manager, or framework — pages are plain HTML
served as-is. Do not introduce a bundler, static site generator, or JS framework
unless explicitly asked; keep the site buildless and dependency-free.

## Conventions

- **Plain HTML/CSS.** No JavaScript is included unless a feature genuinely needs
  it — this site doesn't currently require any client-side scripting.
- **Single stylesheet.** All styles live in `assets/css/style.css`. Keep it that
  way unless the site grows enough to justify per-page splitting.
- **Theming via CSS custom properties.** Colors are defined as `--color-*`
  variables in `:root`, with a `prefers-color-scheme: dark` override block.
  Add new colors as variables, not hardcoded hex values, so dark mode keeps
  working.
- **Relative asset paths.** Reference assets as `assets/css/...`,
  `assets/images/...` (relative, no leading slash) so the site works correctly
  whether served from the Pages root or a preview path.
- New pages should follow `index.html`'s structure: a `.site-header`, `.site-nav`,
  `<main>` with `<section>`s, and a `.site-footer`.

## Development workflow

- **No build/install step.** Open `index.html` directly in a browser, or serve
  the directory locally (e.g. `python3 -m http.server`) to preview changes.
- **No test suite or linter** is configured. Validate changes by visually
  checking the page in a browser (and check both light and dark color scheme
  if you touch CSS).
- **Deployment is automatic**: GitHub Pages rebuilds and republishes from the
  repository's default branch on every push — there is no separate deploy
  command or CI pipeline to trigger.

## When adding features

- Keep the site static and dependency-free unless the user asks for a specific
  framework or build tool.
- Don't add analytics, tracking scripts, or third-party embeds unless
  explicitly requested.
- Placeholder content in `index.html` (About/Projects/Contact sections) is
  intentionally minimal — replace it with real content rather than expanding
  its structure speculatively.
