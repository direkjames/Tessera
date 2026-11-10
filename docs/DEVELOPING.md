# Developing Tessera

Tessera is one `index.html` file (HTML, CSS and JavaScript together) plus a manifest, a service worker and icons. There is no build step.

```
index.html              the whole app
sw.js                   service worker for offline use
manifest.webmanifest    install-as-app details
icon.svg, icon-*.png    app icons
docs/screenshots/       the images used in the README
```

## Put it on GitHub Pages

1. Create a new public repository (for example `tessera`).
2. Upload every file in this folder to the root of the repo.
3. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, then save.
4. After a minute it's live at `https://<your-username>.github.io/tessera/`.

To install it as an app, open that link in Chrome or Edge and choose **Install** (or ⋯ → *Install app* inside Tessera). On Android, use Chrome's menu → *Add to Home screen*.

## Try it on your computer

Service workers and IndexedDB need a web server, so serve the folder instead of opening the file:

```
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Updating

When you change files, bump `VERSION` in `sw.js` (for example `tessera-v18`) so installed copies pick up the new version.

## Services Tessera contacts

Tessera works fully offline. A few optional features reach the internet:

- **Map cards** load map tiles from OpenStreetMap (© OpenStreetMap contributors) and search places with OpenStreetMap's Nominatim service, which receives what you type in the map search. A snapshot of each map is saved on the device.
- **Google Fonts** (font cards and heading fonts) load from Google the first time.
- **Link cards** show site icons from Google's favicon service.

## Share links

**Export & share → Share link** compresses the board into the part of the URL after `#`, which is never sent to a server. The link opens inside a sandboxed frame that can't touch the viewer's own boards. Images, files and voice memos are not included (they show as placeholders), locked boards are left out, and very large boards may not fit.

## Optional sync

In **Storage & backup**, turn on automatic backup to a folder inside Google Drive, OneDrive or Dropbox, then switch **Sync** on. Do the same with the same folder on another computer. Tessera never uploads anything itself; the cloud app moves the file, and Tessera offers to load newer boards when it sees them (Chrome and Edge on computers).
