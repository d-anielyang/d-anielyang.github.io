# Dodo Design & Build

Marketing site for Dodo, a design-and-build studio for homes and small
spaces in Vancouver, BC.

## Structure

```
dodo-site/
├── index.html        Home page
├── css/
│   └── style.css      All site styles (colors, type, layout, components)
├── assets/            Images and other static files (empty for now)
└── README.md
```

## Running locally

This is a static site — no build step, no dependencies. Two options:

- **Quickest:** open `index.html` directly in a browser.
- **Recommended:** serve it locally so relative links and fonts behave
  exactly as they will in production:
  ```
  python3 -m http.server 8000
  ```
  then visit `http://localhost:8000`.

## Editing

- **Copy and layout** live in `index.html`, in the order sections appear
  on the page (header → hero → about → services → projects → contact →
  footer).
- **All styling** lives in `css/style.css`. Colors, fonts, and spacing are
  defined once as CSS variables at the top of the file (`:root { ... }`)
  — change a value there rather than hunting for it elsewhere.
- **Fonts** (Fraunces, Work Sans, Space Mono) are loaded from Google
  Fonts via `<link>` tags in `index.html`'s `<head>`.

## Adding a new page

Create a new `.html` file at the root (or in a subfolder, e.g.
`projects/kitsilano-addition.html`) and link the same stylesheet:

```html
<link rel="stylesheet" href="css/style.css">
```

If the page lives in a subfolder, adjust the path accordingly
(`../css/style.css`).

## Notes

- No JavaScript framework or build tool — plain HTML/CSS by design, to
  keep this easy to hand off or extend later.
- If the site grows past a handful of pages, consider a static site
  generator (e.g. 11ty) to share the header/nav/footer across pages
  instead of duplicating them.
