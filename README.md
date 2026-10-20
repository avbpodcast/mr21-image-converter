# Mr21 - image converter

A single-file tool that converts images to **PNG, JPEG or WebP** in your browser. Open `mr21-image-converter.html` and drop your files in. Nothing is uploaded, no install, no server.

- **One file, works offline**: all decoders are built into the page. A Content-Security-Policy (`connect-src 'none'`) blocks every network connection from the page.
- **Many input formats**: JPEG, PNG, WebP, GIF, BMP, AVIF, ICO, TIFF, HEIC/HEIF, camera RAW (DNG, CR2, NEF, ARW, RW2), PNM (PBM/PGM/PPM/PAM), XPM, XBM.
- **Batch**: add many files or whole folders (drop, choose or paste). Download one by one or all at once as a `.zip`.
- **Privacy by default**: location and camera data are removed from every converted image. Optionally keep date and camera info, and separately opt in to location.
- **Quality control**: PNG is lossless; JPEG and WebP have a quality slider. Transparent areas become white in JPEG.
- **Keyboard**: `Enter` converts, `Esc` cancels or clears (undoable), `Ctrl+V` pastes screenshots, `1` `2` `3` pick PNG / JPEG / WebP.

## Use

1. Open `mr21-image-converter.html` in a browser (ideally while offline).
2. Add images. With "Convert as soon as files are added" on (default), they convert right away.
3. Pick the output format and quality, then download.

## RAW files

Most cameras store a full-size JPEG inside the RAW file; that one is used when present (fast, camera colours). If there is none (typical for Android DNGs), the sensor data is developed with `dcraw`, which can take a while for large files.

## Limitations

- Output is PNG, JPEG or WebP only. WebP output depends on the browser.
- Animated GIF/APNG: only the first frame is converted.
- Colour profiles (ICC) are not kept. Photo info is copied only from JPEG, HEIC, PNG and WebP originals.
- Everything is processed in memory; very large images can hit the browser's canvas limit.
- A single `.zip` is limited to 4 GB.
- The Content-Security-Policy has to allow `unsafe-eval`, because the bundled HEIC and RAW decoders (Emscripten builds) need it. Network access stays blocked.

## Verify the download

```
sha256sum -c SHA256SUMS
```

## Value-4-Value

This tool is free to use, no ads, no tracking. It runs on the Value-4-Value model: if it saved you time, give back what it was worth to you at https://allesvoorbitcoin.be/donate

## License

The original code is MIT licensed, see [LICENSE](LICENSE).

The HTML file bundles third-party components that keep their own licenses: pako (MIT), UTIF.js (MIT), libheif-js with libheif and libde265 (LGPL-3.0) and dcraw.js (GPL-2.0). Because of the GPL-2.0 and LGPL-3.0 parts, the combined single file is distributed under those terms as well. Details and upstream links: [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
