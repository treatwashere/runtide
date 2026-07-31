# Runtide

A free, browser-based code playground for writing and testing HTML, CSS, and JavaScript instantly — no installs, no signup, no build step.

🔗 **Live site:** [runtide.vercel.app](https://runtide.vercel.app)

## Features

| Page | Description |
|---|---|
| 🎨 **Playground** | Write HTML, CSS, and JS together with a live preview that updates as you type. |
| 📝 **HTML Viewer** | Paste HTML and see it render. Refresh for a clean slate — great for quick one-off tests. |
| 💾 **Saved HTML Viewer** | Same as the HTML Viewer, but your code is saved to `localStorage` so it's still there when you come back. |
| 💻 **Console** | A JavaScript console where variables persist between runs, just like your browser's devtools. |
| 📋 **Changelog** | Pulls releases and recent commits live from the GitHub API — always up to date, never edited by hand. |

Other niceties:

- 📱 **Responsive testing** — toggle the preview between desktop, tablet, and mobile widths.
- 🌙 **Dark / light mode** — your preference is saved and applied across every page.
- ⚡ **Zero setup** — open a page and start coding immediately.

## Tech stack

Runtide is intentionally dependency-free: plain **HTML, CSS, and vanilla JavaScript**, with no build tooling, frameworks, or backend. Preferences and saved code are persisted client-side via `localStorage`. The changelog page calls the public GitHub REST API directly from the browser.

## Project structure

```
runtide/
├── code/
│   ├── index.html               # Landing page
│   ├── playground.html          # HTML/CSS/JS playground with live preview
│   ├── html-viewer.html         # Stateless HTML viewer
│   ├── saved-html-viewer.html   # HTML viewer with persistent storage
│   ├── console.html             # Standalone JavaScript console
│   └── changelog.html           # Auto-generated changelog (GitHub API)
├── .github/workflows/static.yml # GitHub Pages deployment workflow
└── vercel.json                  # Vercel config (outputDirectory: code)
```

## Running locally

No build step required — just serve the `code/` directory statically:

```bash
git clone https://github.com/treatwashere/runtide.git
cd runtide/code
python3 -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

## Deployment

The site is deployed on **Vercel** (see [`vercel.json`](vercel.json), which points to `code/` as the output directory), with pushes to `main` deploying automatically. A GitHub Actions workflow ([`.github/workflows/static.yml`](.github/workflows/static.yml)) is also included for deploying the same static content to GitHub Pages.

## License

No license has been specified yet.
