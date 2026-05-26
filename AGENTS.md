# Repository Guidelines

## Project Structure & Module Organization

This repository contains a static landing page for Clinica Medida Certa. There is no package manager, bundler, or backend in the current project.

- `index.html` contains the page markup, section structure, and CDN imports for Tailwind, GSAP, Swiper, and Lenis.
- `style.css` contains theme variables, custom component styles, responsive layout rules, and overrides that are not practical as Tailwind utilities.
- `script.js` contains animation setup, smooth scrolling, Swiper initialization, magnetic buttons, nav scroll behavior, and chatbot logic.
- `images/` stores local visual assets used by the page.
- `briefing.md` documents brand colors, audience, positioning, and communication tone.
- `CLAUDE.md` and `GEMINI.md` provide additional agent context.

## Build, Test, and Development Commands

No install or build step is required.

- Open `index.html` directly in a browser for a quick local preview.
- Use VS Code Live Server or any static server for reload-on-save development.
- Optional local server example:

```powershell
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Coding Style & Naming Conventions

Use HTML, CSS, and vanilla JavaScript. Keep indentation consistent with surrounding code, currently four spaces in `index.html` and `script.js`.

Prefer Tailwind utility classes for simple layout and spacing. Use `style.css` for reusable components, complex responsive behavior, and visual systems. Name custom classes descriptively, such as `.spec-card`, `.chat-bubble`, or `.about-reference-layout`.

Use CSS variables from `:root` for brand colors where possible, for example `--azul-clinico`, `--verde-suave`, `--bege-claro`, and `--azul-escuro`. Add descriptive `alt` text for images.

## Testing Guidelines

There is no automated test suite yet. Before submitting changes, manually verify:

- desktop and mobile layouts;
- navigation anchor links;
- chatbot open/close behavior;
- scroll animations and carousel behavior;
- image loading from `images/` or approved external URLs.

For visual changes, include before/after screenshots in the pull request.

## Commit & Pull Request Guidelines

Git history is not available in this workspace, so use simple imperative commit messages, such as `Update about section layout` or `Fix mobile contact spacing`.

Pull requests should include a short summary, affected files or sections, manual test notes, and screenshots for UI changes. Link related issues when available.

## Security & Configuration Tips

The Groq API key is currently exposed in client-side JavaScript. Do not add new secrets to `index.html`, `style.css`, or `script.js`. Move sensitive API calls behind a backend proxy before production use.
