## Human‑Readable Source and Reproducible Build

This repository provides the human‑readable source for the distributed minified assets used by the WordPress plugin.

- Readable (human‑friendly):
  - `chat-widget.js`
  - `chat-widget.css`
- Minified (distribution):
  - `chat-widget.min.js`
  - `chat-widget.min.css`

The minified files are produced directly from the readable files using the commands below.

### Prerequisites
- Node.js LTS (with `npx` available)

### Rebuild the minified files from the readable ones

- JavaScript (minify `chat-widget.js` → `chat-widget.min.js`):
```bash
npx terser@5 chat-widget.js -c -m --ecma 2018 --comments '/^!|@preserve|@license|@cc_on/' -o chat-widget.min.js
```

- CSS (minify `chat-widget.css` → `chat-widget.min.css`):
```bash
npx csso@5 chat-widget.css -o chat-widget.min.css
```

### Optional: Generate a JS source map
```bash
npx terser@5 chat-widget.js -c -m --ecma 2018 --comments '/^!|@preserve|@license|@cc_on/' --source-map "url='chat-widget.min.js.map'" -o chat-widget.min.js
```

Notes:
- `--comments` preserves license/preserve banners if present.
- Tool versions are pinned (`@5`) for reproducible output.
