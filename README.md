# Midcenturymodern — a retro-inspired Beamer template


<div align="center">
<img src="/img/sample.png" alt="Sample" width="70%" >
</div>

**Midcenturymodern** is a modern Beamer template with a retro feel. It requires LuaLaTeX.

Open it in [the Overleaf gallery](https://www.overleaf.com/latex/templates/midcenturymodern-beamer-theme/zdvwhytpqvgf) to start from a working project without installing anything, or clone this repository (see [Getting started](#getting-started)).


## Two built-in themes

The template ships with two colour themes. **Kraft** leans warm, with terracotta and kraft paper tones. **DeepBlue** goes in the opposite direction, with a dark navy background and icy blue accents.

Select a theme in your preamble:

```latex
\usepackage{beamerthememidcenturymodern}
\mcmTheme{Kraft}      % warm terracotta palette
% \mcmTheme{DeepBlue} % dark navy palette
```

![Title slide](img/titlepage.png)
*Title slide — Kraft on the left, DeepBlue on the right.*

## A look at the slides

The theme supports standard, alert, and example blocks, each with a coloured accent that adapts to the active theme.

![Alert and example blocks](img/blockspage.png)
*Alert and example blocks — Kraft on the left, DeepBlue on the right.*

Lists are marked with the running font's own en dash at every nesting level, so the mark follows the size and weight of the text it belongs to.

![Itemize and enumerate](img/itemspage.png)
*Itemize and enumerate — Kraft on the left, DeepBlue on the right.*

Section and subsection pages give the audience a clear visual indication of where they are in the talk.

![Section page](img/sectionpages.png)
*Section page — Kraft on the left, DeepBlue on the right.*

The full demo slides [can be found here](demo.pdf).

## Getting started

Clone the repository and place `beamerthememidcenturymodern.sty` in the same directory as your `.tex` file, then:

```latex
\documentclass[aspectratio=169]{beamer}
\usepackage{beamerthememidcenturymodern}
\mcmTheme{Kraft}

\title{Your Title}
\author{Your Name}
\institute{Your Institution}
\date{\today}

\begin{document}
\begin{frame}
  \titlepage
\end{frame}
\end{document}
```

Compile with LuaLaTeX.

## Frame titles

Every frame can carry a subtitle. The coloured band takes it on a second line, in the body face, and opens by 3 mm to make room — not by a whole line, since a one-line band already carries the white for it. It does grow by a full line for a title long enough to wrap, or for a subtitle running to a second line.

```latex
\begin{frame}{Research work}
  \framesubtitle{Axis 1 — combinatorial optimisation}
  ...
\end{frame}
```

## Typography

Body text is set in **TeX Gyre Heros** (a Helvetica) and titles in **TeX Gyre
Adventor** (an Avant Garde Gothic), letterspaced and uppercased. Both ship with
TeX Live, so nothing needs installing and the theme renders the same everywhere.

Override either in your preamble, after loading the theme:

```latex
\setsansfont{Font Name}                      % body
\renewfontfamily\mcmTitleFont{Font Name}     % titles
```

## Availability

The theme is also available in the [Overleaf gallery](https://www.overleaf.com/latex/templates/midcenturymodern-beamer-theme/zdvwhytpqvgf).

## Feedback

Bug reports, suggestions, and pull requests are very welcome.