# Academic CV — Michael Lehn

This repository contains my application documents for teaching-focused
university positions (e.g., Lecturer):

- 📄 **[Academic CV](cv.pdf)**
- 📄 **[Teaching Statement](teaching_statement.pdf)**

## Building

Each PDF is generated from the `.tex` file of the same name with LuaLaTeX,
for example:

```sh
lualatex cv.tex
lualatex cv.tex
```

The documents use Calibri if it is installed and otherwise the
metric-compatible Carlito font (included in TeX Live).

The committed PDFs were built with a fixed timestamp:

```sh
export SOURCE_DATE_EPOCH=1792800000 FORCE_SOURCE_DATE=1
lualatex cv.tex && lualatex cv.tex
```

Rebuilding this way reproduces the same content and layout; only the PDF's
internal document ID depends on the build directory.
