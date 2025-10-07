# Markdown Preview (input.md Renderer)

## Project Overview
This project is a minimal single-page web application that loads a local `input.md`, converts it to HTML, and renders the result into the page element with the ID `#preview`. It uses:
- Marked for Markdown parsing
- DOMPurify for XSS-safe HTML sanitization

The app is fully static and can be hosted on any static web server or deployed to services like GitHub Pages, Netlify, or Vercel.

## Setup

1. Ensure the following files are in the same directory:
   - `index.html` (this web app)
   - `input.md` (the Markdown file to render)

2. Serve the directory over HTTP (required for `fetch()` to work). Examples:
   - Python 3: `python -m http.server 8080`
   - Node.js (serve): `npx serve .`
   - Bun: `bunx serve .`

3. Open your browser to:
   - Python example: http://localhost:8000
   - Or whichever URL/port your server reports

Note: Opening `index.html` directly via `file://` will typically block `fetch('input.md')` due to browser security. Always use a local server.

## Usage

- Edit `input.md` to change the content. On refresh, the page will re-fetch and render it into `#preview`.
- The document title automatically updates to the first Markdown H1 (if present).
- GitHub-Flavored Markdown (GFM) features such as tables, task lists, and fenced code blocks are supported by default.

### Files

- `index.html` — Main single-file application that fetches and renders `input.md`.
- `input.md` — The Markdown source to render (expected to exist alongside `index.html`).

## License

MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.