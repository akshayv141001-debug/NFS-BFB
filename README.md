# Break Format Builder

Reads network break-format screenshots in the browser and writes lines such as:

    Network Format: 180-8; 60s duration @ 0:15, 0:31, 0:45, 01:15, 01:45, 02:15, 02:31, 02:45

Longer breaks come first, and center times ascend within each length. Saved formats live in the visitor's browser; export and import them as JSON. The Program file tab stamps saved formats onto lines containing `format CODE`. Works in light and dark, with an Auto / Light / Dark switch.

No server, account, API key or tracking. Screenshots never leave the browser.

## Publish on GitHub Pages

1. Put every file from this folder at the top level of a public repository (no subfolders).
2. Repository **Settings > Pages > Build and deployment**: Source **Deploy from a branch**, Branch **main**, folder **/ (root)**, then **Save**.
3. After a minute or two the site is at `https://YOUR-NAME.github.io/REPO-NAME/`.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app: page, styles and code in one file |
| `tesseract.min.js`, `worker.min.js` | OCR library (Tesseract.js 5.1.1) |
| `tesseract-core-lstm.wasm.js`, `tesseract-core-simd-lstm.wasm.js` | OCR engine |
| `eng.traineddata` | English language data |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

To change the app, edit `index.html` only. Serve it over http(s); opening it from disk will not run the OCR worker. Locally: `python3 -m http.server 8000`.
