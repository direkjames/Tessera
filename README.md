# Tessera

A calm, infinite canvas for ideas, references and plans — a free, private alternative to visual board apps.

**Features:** notes (with bold, italic, headings, lists), to-do lists, links, images, nested boards, columns, arrows between cards, undo/redo, copy/paste, colours, backup export/import, offline support, and install-as-app on Windows, Android, Mac and iPad.

## Your data stays on your device

There are no accounts and no sync. Boards are saved in the browser on the device you use. Clearing site data, uninstalling the app or using a private window erases them, so **export a backup** from the ⋯ menu (Ctrl S) regularly. Backups can be imported on any device.

## Put it on GitHub Pages

1. Create a new public repository (for example `tessera`).
2. Upload every file in this folder to the root of the repo.
3. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, then save.
4. After a minute it's live at `https://<your-username>.github.io/tessera/`.

To install it as an app, open that link in Chrome or Edge and choose **Install** (or ⋯ → *Install app* inside Tessera). On Android, use Chrome's menu → *Add to Home screen*.

## Updating

When you change files, bump `VERSION` in `sw.js` (e.g. `tessera-v2`) so installed copies pick up the new version.
