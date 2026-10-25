# AGENTS.md

Personal portfolio site by Germán J.E. Dieser. Static HTML/CSS + vanilla JS, no build step, no package manager.

## Files

- `index.html` — main page: about, projects, certificates carousel, educational videos, contact.
- `gamedev.html` — Unity/game-dev projects and 3D gallery.
- `games.html` — Tic-Tac-Toe test page (vanilla JS). Isolated demo; not linked from the other pages.
- `estilos.css` — the only stylesheet, shared by all pages.
- `icons/`, `images/` — static assets. `images/certificate/` feeds the carousel.

## Conventions

- **Bilingual via CSS, not JS strings**: duplicate each block with `class="lang es active"` and `class="lang en"`. `switchLang()` in each page toggles `.active`; `.lang { display: none }` lives in `estilos.css`. If you add text, add both languages, or the other language keeps stale/empty content.
- Bootstrap 5.3 comes from CDN and is the base for navbar/carousel/buttons. Custom styles go in `estilos.css`; avoid new inline `style=""` (there is legacy inline styling in `index.html`/`gamedev.html`).
- Visual language: dark animated gradient body, `Press Start 2P` for headings/brand, `Gowun Dodum` for body copy, accent `#00AFDB`, translucent black cards with blur/glow.
- Anchor navigation (`#inicio`, `#proyectos`, …) and `id` targets are shared with the CSS selectors — renaming an `id` breaks styling.
- `gamedev.html` loads `js/scripts.js`, which does not exist in the repo (404, harmless today). Don't copy that script tag into new pages.

## Working on it

- No Node/Python/PHP toolchain installed on this machine. Verify by opening the HTML directly, or serve statically and check with Chrome (installed at `C:\Program Files\Google\Chrome\Application\chrome.exe`, supports `--headless=new --screenshot`).
- Preview one page: `start index.html` (Windows). For relative assets and iframe-based responsive checks, use a static server.
- There are no tests or linters. Verification is manual: click through the flow, resize to ~360 px, and confirm both languages.
- `AGENTS.md` is the only instruction file; keep it in sync when adding a page.
