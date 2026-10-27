# Academic CV — Michael Lehn

This repository contains my application documents for teaching-focused
university positions (e.g., Lecturer):

- 📄 **[Academic CV](cv.pdf)**
- 📄 **[Teaching Statement](teaching_statement.pdf)**
- 📄 **[Evidence of Teaching Effectiveness](teaching_effectiveness_public.pdf)**
  (summary of official student evaluation results; individual student
  comments are not reproduced)
- 📄 **[References](references.pdf)**

## Building

Each PDF is generated from the `.tex` file of the same name with LuaLaTeX,
for example:

```sh
lualatex cv.tex
lualatex cv.tex
```

`teaching_effectiveness_public.tex` uses a table that spans pages and needs
a third LuaLaTeX run.

The documents use Calibri if it is installed and otherwise the
metric-compatible Carlito font (included in TeX Live).

The committed PDFs were built with a fixed timestamp:

```sh
export SOURCE_DATE_EPOCH=1792800000 FORCE_SOURCE_DATE=1
lualatex cv.tex && lualatex cv.tex
```

Rebuilding this way reproduces the same content and layout; only the PDF's
internal document ID depends on the build directory.
