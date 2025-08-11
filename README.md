# Antalyze-Live-Chat-and-AI-Chatbot
Build: Generate minified files from human‑readable artifacts
Prerequisites: Node.js LTS. No local installs required (uses npx).
JavaScript (minify chat-widget.js → chat-widget.min.js):
Run
npx terser@5 chat-widget.js -c -m --ecma 2018 --comments '/^!|@preserve|@license|@cc_on/' -o chat-widget.min.js
CSS (minify chat-widget.css → chat-widget.min.css):
Run
npx csso@5 chat-widget.css -o chat-widget.min.css
Optional (generate a source map for JS):
Run
npx terser@5 chat-widget.js -c -m --ecma 2018 --comments '/^!|@preserve|@license|@cc_on/' \
  --source-map "url='chat-widget.min.js.map'" -o chat-widget.min.js

Notes:
The minified files above are produced directly from the readable chat-widget.js and chat-widget.css.
The --comments flag preserves any license/preserve banners if present.
Pinning tool versions (@5) ensures consistent output across environments.
Repository: Antalyze-Live-Chat-and-AI-Chatbot
Added a concise README snippet you can paste that explains exactly how to minify chat-widget.js/.css into .min.* using npx with pinned versions.
