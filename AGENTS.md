# Repository Guidelines

## Project Structure & Module Organization

BooksReader is a dependency-free static site deployed with GitHub Pages. The root [`index.html`](index.html) is the bookshelf landing page; [`README.md`](README.md) lists the published book sites and their scope. Each book has a self-contained, Chinese-named directory such as `控制论/`, `斯多葛/`, or `因果推断/`:

- `index.html` is the book-site overview.
- Topic pages use descriptive names such as `history.html`, `concepts.html`, `book-*.html`, and `practice.html`.
- `assets/style.css` contains the visual system shared by that book’s pages.

Keep links relative within a book directory, and update the root bookshelf when adding a new book directory. `.nojekyll` must remain at the root so GitHub Pages serves `assets/` and Chinese paths unchanged.

## Build, Test, and Development Commands

No package manager, build step, linter, or automated test suite is configured. Preview the site from the repository root:

```bash
python3 -m http.server 8000
```

Open `http://127.0.0.1:8000/`, then visit the changed root and book pages. Test relative navigation, interactive controls, responsive layouts, and browser-console errors. GitHub Pages publishes updates pushed to `main`.

## Coding Style & Naming Conventions

Use UTF-8 HTML with `lang="zh-CN"`, semantic elements where practical, and two-space indentation for markup, CSS, and inline JavaScript. Follow the existing style: CSS declarations use `property: value;`, class names are lowercase kebab-case (for example, `.nav-links` and `.book-card`), and reusable theme values belong in `:root` custom properties.

Preserve each book’s visual identity; edit its `assets/style.css` rather than copying broad style blocks between pages. Name new pages by purpose: `concepts.html`, `history.html`, or `book-<short-title>.html`.

## Commit & Pull Request Guidelines

Use concise Conventional Commit-style subjects, matching history: `feat: BOOK 05 因果推断书站上架` or `fix: correct book navigation`. Keep commits focused. Pull requests should explain the affected pages and reader-facing change, link relevant issues when available, and include screenshots for layout or interaction changes. Before requesting review, confirm all changed links work through the local server.
