# QA decks

Internal regression decks for the theme — **not** the public demo (that is `../demo.tex`).
They exercise far more of the template than the demo needs to, so that a change to
`beamerthememidcenturymodern.sty` can be checked against a wide range of real-world usage.

All names, institutions, events and topics in these files are **invented placeholders**,
chosen only for their length and shape. The proper nouns are coinages, each checked by web
search not to match an existing organisation, place or notable person. When adding a case,
coin a new one and check it the same way: a plausible-sounding name picked out of thin air
("Meridian Analytics", "Lakeside Polytechnic") nearly always turns out to be a real company
or school.

| File | What it covers |
|---|---|
| `testing.tex` → `testing.pdf` (66 pages) | Slide structures: blocks (standard/alert/example) of very different sizes across column splits, TikZ diagrams (flow, matrix, hierarchy, timeline, bar chart), tables, overlays, quotes, footnotes, citations. |
| `titlepage.tex` → `titlepage.pdf` (25 pages) | The title page alone, with wildly different amounts of text in each metadata field. |

## Title-page cases

| Page | Case |
|---|---|
| 1 | baseline (same metadata as `demo.tex`) |
| 2–5 | two-character title, title-only, all fields empty, short student defence |
| 6–8 | 12- and 20-word titles; then every field long at once |
| 9–10 | manual `\\` breaks; 45-character unbreakable word |
| 11–15 | long subtitle / nine authors / three-line institute / superscript affiliations / long date |
| 16–18 | no logo, small logo, 6.8 cm wide logo strip |
| 19–20 | `\mcmTitleUppercasefalse`; accented uppercase |
| 21–24 | DeepBlue: baseline, everything long, minimal, 37-word title |
| 25 | realistic conference-paper title page |

Each page carries a tiny label in its top-left corner naming the case.

## Build

From this directory, with the theme on the input path:

```bash
TEXINPUTS=..: lualatex -interaction=nonstopmode testing.tex
biber testing
TEXINPUTS=..: lualatex -interaction=nonstopmode testing.tex
TEXINPUTS=..: lualatex -interaction=nonstopmode testing.tex

TEXINPUTS=..: lualatex -interaction=nonstopmode titlepage.tex
TEXINPUTS=..: lualatex -interaction=nonstopmode titlepage.tex
```

Both need **two** passes at least: `remember picture` places nothing useful on the first
one (every `current page` node collapses to the origin, so the whole slide renders in the
top-left corner — that is not a layout bug). `testing.tex` additionally needs `biber`;
delete a stale `testing.bbl` if the deck ever comes out at 67 pages instead of 66.

What to check afterwards: page counts (66 / 25), and **zero** `Overfull \hbox` in either
log — the title-page auto-fit is supposed to make all 25 cases fit on their own.
