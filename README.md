# KraX Tools

Free, private file tools that run entirely in your browser. Compress and convert images, compress/merge/split PDFs, and create or extract ZIP files. No account, no backend, no uploads.

**Live app:** [kraxtools.vercel.app](https://kraxtools.vercel.app/)

By **KraX Labs** — [YouTube channel](https://youtube.com/@kraxlabs724?si=P0RSWuxukLbhqgAY)

---

## Features

### Image tools
- **Compress** JPG / PNG / WEBP with an adjustable quality slider
- **Convert** between JPG, PNG and WEBP
- **Resize** by width/height, with optional aspect-ratio lock
- If compression would make the file bigger, the original is kept

### PDF tools
- **Compress PDF** with four levels: Low, Medium (recommended), High, Extreme
  - If the file does not shrink enough, the tool automatically tries stronger settings
  - Already-small or text-only PDFs may be kept as the original (see Limitations)
- **Merge PDFs**: add files one by one, then merge
- **Select and download pages**: load pages, tick the ones you want, download each as a separate PDF, JPG or PNG

### ZIP tools
- **Create ZIP** from any files
- **Extract ZIP** and download the files individually

---

## Project structure

```
krax-tools/
├── index.html   # page layout and UI
├── style.css    # styling
├── script.js    # all tool logic
└── README.md
```

## How to run

Just want to use it? Open the live app: https://kraxtools.vercel.app/

To run it locally:

1. Unzip the project.
2. Open `index.html` in any modern browser (Chrome, Edge, Firefox, Safari).
3. Make sure you are online, because the libraries load from a CDN.

No install or build step is needed.

## Deploy

It is a static site, so any static host works:

- **GitHub Pages**: push the folder to a repo, then Settings → Pages → select the branch
- **Vercel / Netlify / Cloudflare Pages**: drag and drop the folder (the live app is hosted on Vercel)

## Libraries used (loaded from cdnjs)

| Library | Version | Used for |
|---|---|---|
| [pdf-lib](https://pdf-lib.js.org/) | 1.17.1 | Building, merging and splitting PDFs |
| [PDF.js](https://mozilla.github.io/pdf.js/) | 3.11.174 | Rendering PDF pages |
| [JSZip](https://stuk.github.io/jszip/) | 3.10.1 | Creating and reading ZIP files |

## How PDF compression works

Each page is rendered to an image, re-encoded as JPEG at a lower resolution and quality, and rebuilt into a new PDF. This works very well for scanned or photo-heavy PDFs.

## Limitations

- **Text is not selectable** in a compressed PDF, because pages become images.
- **Text-only PDFs** (for example, exported from Word) are usually already tiny. Converting them to images can make them larger, so the original is kept.
- **Password-protected PDFs** must be unlocked first.
- Very large files may run out of browser memory, especially on phones.
- Internet is required to load the libraries.

## Privacy

Files are processed locally in your browser and are never sent to a server.

## Credits

Made by KraX Labs. Subscribe on [YouTube](https://youtube.com/@kraxlabs724?si=P0RSWuxukLbhqgAY) for more tools.
