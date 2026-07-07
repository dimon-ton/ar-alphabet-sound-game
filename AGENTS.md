# Repository Guidelines

## Project Structure & Module Organization

This repository is a single-page static web game for GitHub Pages.

- `index.html` contains all HTML, CSS, and JavaScript for the AR alphabet sound game.
- `README.md` gives the short project description.
- `.nojekyll` keeps GitHub Pages from applying Jekyll processing.

There is currently no separate `src/`, `tests/`, or `assets/` directory. Keep new code close to the existing sectioned structure in `index.html` unless a feature becomes large enough to justify splitting files.

## Build, Test, and Development Commands

No package manager or build step is configured. The page loads Tailwind CSS, Google Fonts, and MediaPipe from CDNs.

- `python3 -m http.server 8000` starts a local static server.
- Open `http://localhost:8000` to test the game in a browser.
- `git status --short` checks changed files before committing.

Prefer serving the page over opening it directly from disk, because browser camera and media permissions are more predictable on `localhost`.

## Coding Style & Naming Conventions

Use the existing inline style:

- Indent HTML, CSS, and JavaScript with 4 spaces.
- Use `const` and `let`; avoid `var`.
- Name functions and variables in `camelCase`, such as `startGame`, `gameState`, and `cardsContainer`.
- Use uppercase constants for fixed configuration values, such as `MAX_SCORE` and `PINCH_THRESHOLD`.
- Keep JavaScript grouped under descriptive block comments like `GAME LOGIC & UI` and `AR / MEDIAPIPE HAND TRACKING`.

Preserve Thai and English user-facing copy where appropriate. Avoid adding new dependencies unless they are necessary for gameplay or browser compatibility.

## Testing Guidelines

There is no automated test framework yet. Manually verify changes in a modern browser:

- Splash, instruction, game, and end screens transition correctly.
- Speech synthesis plays the target letter and replay button audio.
- Mouse or touch selection works when camera access is unavailable.
- Camera permission, hand tracking, hover state, and pinch selection work on `localhost`.
- Responsive layout remains usable on desktop and mobile viewport sizes.

## Commit & Pull Request Guidelines

The git history currently uses a short imperative commit style, for example `Publish AR alphabet sound game`. Keep commits concise and action-oriented.

For pull requests, include a brief description, the user-visible behavior changed, manual test results, and screenshots or screen recordings for UI changes. Link related issues when available and call out any changes to camera, speech, or CDN-loaded dependencies.
