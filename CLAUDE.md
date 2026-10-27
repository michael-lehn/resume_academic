# Instructions for this repository

This repository holds Michael Lehn's academic application documents. Some of
them exist in a private and a public version.

## Private master, public derivative

The private version is always the authoritative master. The public version is
always a sanitized derivative of the private version, never the other way
around.

1. Make every substantive edit or correction in the private master first.
2. Derive the public version from the private master, removing only material
   that must not be published.
3. Never reconstruct, overwrite, or update a private master from its public
   version.
4. Keep both versions identical in all non-confidential content. After each
   change, diff the two sources: the only differences may be the sanitized
   material listed below and layout commands such as page breaks.
5. Before any application is submitted, rebuild and visually check the private
   submission PDF on its own (page count, completeness, recent changes).
   Checking the public PDF is not enough.
6. Never commit or push private documents or confidential supporting
   materials.

## Document pairs

| Private master (never committed) | Public derivative (committed) |
|---|---|
| `teaching_effectiveness.tex` / `.pdf` | `teaching_effectiveness_public.tex` / `.pdf` |

The public version of the evidence of teaching effectiveness differs from the
private master only in these respects:

- verbatim student comments and their translations are replaced by summaries
  ("Summary of Student Comments", "Recurring critical comments"), and the
  quotation macro is removed;
- wording that refers to individual student comments is neutralized (e.g., the
  Summer 2020 table note);
- layout commands may differ so that each PDF breaks pages cleanly.

The CV, teaching statement, and references have no private master and are
edited directly. If a private variant of any document is created, the rules
above apply to it.

## Confidential material (git-ignored, never publish)

- `Evaluationen/` / `evaluationen/`: original student evaluation reports
- `Lehrbonus/` / `lehrbonus/`: original teaching-award and teaching-bonus
  nominations
- `teaching_effectiveness.tex` / `.pdf`: private master
- cover letters (`*cover_letter*`, `/bowdoin*`) and Word files (`*.docx`)

Stage files explicitly by name and check `git diff --cached --name-only` before
every commit. Do not rewrite Git history.

## Building

Build with LuaLaTeX and a fixed timestamp so that rebuilt PDFs are
reproducible:

```sh
export SOURCE_DATE_EPOCH=1792800000 FORCE_SOURCE_DATE=1
lualatex file.tex && lualatex file.tex
```

The evidence documents use a long table and need a third run. Keep the
teaching statement at two pages and cover letters at one page without reducing
font sizes or margins.

## Commits

Use short, descriptive commit messages without AI attribution or
`Co-Authored-By` trailers.
