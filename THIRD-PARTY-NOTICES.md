# Third-party notices

`mr21-image-converter.html` bundles these components, each under its own license. They are embedded as readable script blocks inside the HTML file; replacing any of them in the file is possible.

| Component | Version | License | Used for | Upstream |
|---|---|---|---|---|
| pako (inflate) | 1.0.11 | MIT | TIFF decompression | https://github.com/nodeca/pako |
| UTIF.js | 3.1.0 | MIT | TIFF decoding | https://github.com/photopea/UTIF.js |
| libheif-js (libheif + libde265, WebAssembly) | 1.19.8 | LGPL-3.0 | HEIC/HEIF decoding | https://github.com/catdad-experiments/libheif-js, https://github.com/strukturag/libheif, https://github.com/strukturag/libde265 |
| dcraw.js (port of dcraw by Dave Coffin) | 1.0.3 | GPL-2.0 | Developing camera RAW sensor data | https://www.dechifro.org/dcraw/ |

The original code of this project (everything outside those blocks) is MIT licensed, see `LICENSE`.

Because the file includes GPL-2.0 and LGPL-3.0 components, the combined single-file HTML is distributed under the terms of those licenses as well. This is not legal advice; if you need a different license situation, remove the component in question or contact the authors.
