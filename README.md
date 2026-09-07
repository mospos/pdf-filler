# PDF Filler

Fill in and sign PDF forms in the browser — text, checkmarks, dates, whiteout,
images and signatures (drawn, typed or photographed) — then save a real,
flattened PDF.

**Everything happens in the browser.** The PDF is never uploaded: it is read
with [pdf.js](https://mozilla.github.io/pdf.js/), edited on screen, and written
back out with [pdf-lib](https://pdf-lib.js.org/). Both libraries are served from
`lib/` in this repo, so the app also works with no network at all.

## Using it

Open the hosted page, or open `index.html` from disk — both work.

- **Your Documents** on the start screen holds everything you have opened, with a
  thumbnail and how many marks are on it. Work is saved into the app as you type,
  so you can close a form and pick it up later. **My Documents** goes back to that
  list; the red × on a card removes a document for good. Documents live in this
  browser on this device — clearing site data clears them
- **Open PDF** or drag a file onto the page
- **Detect Form Fields** puts a text box on every field a fillable PDF declares;
  on a flat scan, use the Text tool anywhere
- **Signature** draws with the mouse, types your name in a script face, or
  knocks the white paper out of a photographed signature. Signatures are kept in
  this browser for reuse
- **Export Filled PDF** opens a Save As dialog to write the finished file out to
  disk. Exporting again writes to the same file with no dialog

Keyboard: `Ctrl+Z` undo, `Ctrl+S` save, `Delete` removes the selected mark,
arrow keys nudge it (hold Shift for bigger steps), `Esc` deselects.

## Installing it as an app

Served over https, Chrome shows an install button in the address bar. Installed,
it gets its own window and Start-menu entry and keeps working offline.

## Layout

    index.html              the whole app
    lib/                    pdf.js and pdf-lib
    sw.js                   offline cache — bump CACHE when files change
    manifest.webmanifest    app name, icons, standalone window
