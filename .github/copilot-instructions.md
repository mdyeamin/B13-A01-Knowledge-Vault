# Copilot / AI agent instructions — Knowledge Vault (Assignment-001)

## Purpose
Help contributors (and AI coding agents) rapidly implement the static site required by the assignment by pointing to the repository's constraints, reference assets, and exact expectations.

## Big picture (what this project is)
- A static HTML/CSS assignment (no build tooling, no JavaScript, no CSS frameworks). The README explicitly requires HTML5 and CSS3 only. 🔧
- Visual design is governed by the Figma link in `README.md` and by the section reference images in `Sections/` (e.g., `Sections/Banner.png`, `Sections/Navbar.png`). Use these as the canonical visual spec.
- Source of truth for assets: `assets/` (contains icons, `logo-navbar.png`, `logo-footer.png`, `hero-bg.png`, etc.). Always use these files when implementing UI elements.

## Key files & directories to reference
- `README.md` — assignment requirements (sections, behavior, constraints). Follow it literally (no Lorem Ipsum, 5 commits minimum, hover effects on buttons, etc.).
- `Sections/` — per-section screenshots to match layout and spacing.
- `assets/` — images and icons for the site (use filenames like `logo-navbar.png`, `hero-bg.png`, `Bookmarks.png`, `Brain.png`).
- `UI/KnowledgeVault.pdf` and `UI/Home.png` — additional references for expected final output.

## Non-negotiable constraints (do not change)
- No JavaScript. Implement interactive affordances (hover states) using CSS only.
- No external CSS frameworks (Bootstrap, Tailwind, etc.).
- No Lorem Ipsum copy. Use meaningful text per README.
- At least 5 meaningful commits in the git history before submission (README requirement).

## Implementation conventions and patterns (concrete, discoverable)
- Expect a single-page site: use `index.html` at repo root (or equivalent root file served by GitHub Pages).
- Place images from `assets/` with relative paths (e.g., `<img src="assets/logo-navbar.png" alt="Knowledge Vault logo">`).
- Use semantic HTML sections that match `Sections/` (e.g., `<header>` for navbar, `<section id="banner">` for the hero, `<section class="notes">` for the notes cards, etc.).
- CSS can be placed at `styles.css` (root or `/css/styles.css`). Keep files simple and well-commented so reviewers can verify alignment with Figma.
- Buttons must have hover effects (as required). Use :hover and visible focus styles for keyboard accessibility.

## Development & preview workflow
- Local preview: open `index.html` in browser or run a simple static server, e.g. `python -m http.server 8000` from the repo root (works cross-platform if Python is available) or use Live Server (VS Code extension) to validate responsive behavior.
- Testing: manual visual checks against `Sections/` images and Figma. Use browser devtools to check pixel alignment and breakpoints.
- Deployment: GitHub Pages (enable Pages on the repository to serve `index.html` from root or `gh-pages` branch). The README's "Live site deployed" requirement implies Pages is acceptable.

## PR / commit guidance (for automated agents)
- Create focused commits: one logical change per commit (e.g., `feat: add navbar markup and styles`, `fix: adjust banner spacing to match Figma`). Ensure at least 5 commits across the work lifecycle.
- PR description: reference the README requirements and list which Sections images the implementation targets (e.g., "Implements Navbar, Banner and Notes sections to match `Sections/Navbar.png`, `Sections/Banner.png`, `Sections/Notes Section.png`").

## Examples from this repo (explicit references)
- Use `assets/logo-navbar.png` in the header (left-aligned) and `assets/logo-footer.png` in the footer.
- Hero background: `assets/hero-bg.png` should be used as the banner background image.
- Notes cards: layout as four cards in a single row (desktop) matching `Sections/Notes Section.png`.

## What to avoid or flag
- Do not introduce JS frameworks or build systems unless explicitly asked by maintainers.
- If missing assets or ambiguous spacing/typography are encountered, open an issue rather than guessing — tag the maintainers and include a screenshot and suggestion.

## When you are unsure
- Compare visual output to `Sections/*.png` and `UI/Home.png` first; the README + Section images are the canonical spec.
- If a design detail is under-specified (e.g., exact font weights, spacing at a particular breakpoint), prefer conservative choices that match screenshots; ask for clarification via an issue or a comment on the PR.

---
If you'd like, I can (1) generate an initial `index.html` + `styles.css` scaffold using the exact assets and the README section layout, or (2) open a PR draft implementing the navbar and banner as a first checkpoint. Which do you prefer? ✅