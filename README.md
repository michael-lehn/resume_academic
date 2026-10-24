# Academic CV — Michael Lehn

This repository contains my academic CV for teaching-focused university
positions (e.g., Lecturer).

📄 **[cv.pdf](cv.pdf)**

## Building

The PDF is generated from [`cv.tex`](cv.tex) with LuaLaTeX:

```sh
lualatex cv.tex
lualatex cv.tex
```

The document uses Calibri if it is installed and otherwise the
metric-compatible Carlito font (included in TeX Live).

The committed PDF was built with a fixed timestamp:

```sh
export SOURCE_DATE_EPOCH=1792800000 FORCE_SOURCE_DATE=1
lualatex cv.tex && lualatex cv.tex
```

Rebuilding this way reproduces the same content and layout; only the PDF's
internal document ID depends on the build directory.
