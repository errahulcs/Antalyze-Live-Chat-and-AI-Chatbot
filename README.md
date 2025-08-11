# Antalyze-Live-Chat-and-AI-Chatbot
## Source and Build Instructions

- The minified assets are produced directly from the human‑readable files:
  - Readable: `chat-widget.js`, `chat-widget.css`
  - Minified: `chat-widget.min.js`, `chat-widget.min.css`

### Prerequisites
- Node.js LTS (with `npx`)

### Generate minified files from the readable ones

- JavaScript (minify `chat-widget.js` → `chat-widget.min.js`)
```bash
npx terser@5 chat-widget.js -c -m --ecma 2018 --comments '/^!|@preserve|@license|@cc_on/' -o chat-widget.min.js
```

- CSS (minify `chat-widget.css` → `chat-widget.min.css`)
```bash
npx csso@5 chat-widget.css -o chat-widget.min.css
```

### Optional: Generate JS source map
```bash
npx terser@5 chat-widget.js -c -m --ecma 2018 --comments '/^!|@preserve|@license|@cc_on/' --source-map "url='chat-widget.min.js.map'" -o chat-widget.min.js
```

### Notes
- The `--comments` flag preserves license/preserve banners if present.
- Tool versions are pinned (`@5`) for reproducible output.
- Commands work on Windows PowerShell, macOS, and Linux.

### Repository
- Public source and artifacts: https://github.com/errahulcs/Antalyze-Live-Chat-and-AI-Chatbot
