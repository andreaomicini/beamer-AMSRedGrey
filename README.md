# beamer-AMSRedGrey

> A simple Beamer-LaTeX style for presentations by Alma Mater Studiorum —
> Università di Bologna, in the reds and the greys of the old AMSCesena style,
> recovered

## author

* Andrea Omicini

## usage

```latex
\documentclass[presentation]{beamer}\mode<presentation>{\usetheme{AMSRedGrey}}
```

Everything else is AMSUniBo's: the `apice` option for the APICe BibTeX field,
the `bologna` and `cesena` options for the seal watermark — none unless asked
for — and the commands and the bibliography style. The old styles
always carried the Campus di Cesena seal, so a deck moved from them wants
`cesena`:

```latex
\documentclass[presentation,cesena,apice]{beamer}\mode<presentation>{\usetheme{AMSRedGrey}}
```

A ready-to-use presentation skeleton is available in
[beamer-AMSRedGrey-template](https://github.com/andreaomicini/beamer-AMSRedGrey-template).

## relation to beamer-AMSUniBo and to AMSCesena

This style is [beamer-AMSUniBo](https://github.com/andreaomicini/beamer-AMSUniBo)
with a different palette, exactly as
[beamer-AMSBolognaFC](https://github.com/andreaomicini/beamer-AMSBolognaFC) is:
the theme is AMSUniBo's, generated from it with every colour name replaced and
a handful of assignments changed where a role needed a different shade. The
options, the commands (`\speaker`, `\ccite`, `\uurl`, `\ddoi`, `\apicepubpar`,
`\aalert` and their pairs), the workarounds, the references frame and
`apalike-AMS.bst` are all AMSUniBo's — see
[its README](https://github.com/andreaomicini/beamer-AMSUniBo#readme) for all of
them. The faces are not: like AMSBolognaFC, this style keeps LaTeX's own
Computer Modern, as the old one did, rather than AMSUniBo's Merriweather.

The palette is the one thing that is not, and it is a **recovery**.
`AMSCesena` (2010–2013, the first of the three) defined three reds — `darkred`
`#CC001A`, `darkerred` `#BF001A`, `darkestred` `#990000` — and borrowed
everything else from Beamer's own `beaver` colour theme, redefining `beaver`'s
`darkred` along the way, so that the theme's red mixes came out in its red and
its greys stayed grey. Those greys are the **grey** of the name. The style was
copied into some 120 decks over the years, in eight variants that differ in
extra environments and in `\emph`, and never in the colours themselves.

The old style was not satisfying, so only its colours were kept. They were
extracted from every copy of the style found in the archive, as the shades it
actually used, and assigned to the roles AMSUniBo's palette has. Where a role
had no counterpart in the old style, the colour was guessed from the existing
ones, and the colour theme says so beside it.

## structure

<!-- markdownlint-disable MD013 -->
| file | what it is |
| --- | --- |
| `beamerthemeAMSRedGrey.sty` | the theme: AMSUniBo's, in this palette |
| `beamercolorthemeredgrey.sty` | the palette alone, with the provenance of each colour, loaded by the theme |
| `almabologna-background.pdf` | the background under the `bologna` option: the Ateneo seal, as in AMSUniBo |
| `almacesena-background.pdf` | the same, with the Campus di Cesena seal, for the `cesena` option |
| `apalike-AMS.bst` | the bibliography style, AMSUniBo's |

<!-- markdownlint-enable MD013 -->

Every release attaches a `style.zip` holding all five plus the `LICENSE`.

## the palette

**Red is the identity colour** — the head line, links, alerts — as AMSUniBo's
red is; **deep red and grey are the structural ones**, as its green is.

<!-- markdownlint-disable MD013 -->
| colour | value | source | where it goes on a slide |
| --- | --- | --- | --- |
| `rgred` | `#CC001A` | darkred in AMSCesena | head line, author, alerted text, URLs, DOIs, alerted block headers |
| `rgreddark` | `#990000` | darkestred in AMSCesena, its bullets | bullets |
| `rgreddeep` | `#850011` | darkred!65!black, AMSCesena block title | structure, block headers, emphasis, section in TOC, the APICe marker |
| `rgredlight` | `#F0B2BA` | darkred!30!white, guessed: the light red | reserved |
| `rgredtint` | `#FBEBED` | darkred!8!white, guessed: the faintest red | reserved |
| `rgblack` | `#000000` | black | title, frame titles |
| `rgtext` | `#140003` | darkred!10!black, beaver palette sidebar primary | body text |
| `rgsilver` | `#B3B3B3` | gray!60!white, beamer beaver frame title right | separation lines |
| `rgsilvertint` | `#F2F2F2` | gray!10!white, beaver frame title, AMSCesena block body | block bodies, frame title band, foot line |
| `rgsilvertint2` | `#D9D9D9` | gray!30!white, beaver palette primary | foot line, frame title right |
| `rggrey` | `#404040` | darkgray, guessed: institute | institute |
| `rggreymid` | `#5A5A5A` | gray!70!black, guessed: secondary text | secondary text, footnotes, subtitle, date |
| `rggreyline` | `#BFBFBF` | lightgray, guessed: \ccite, \uuurl | `\ccite`, `\uuurl`, `\dddoi`, `\aalert`, fine rules |
| `rggreybg` | `#ECECEC` | gray!15!white, beaver palette secondary, AMSCesena alerted body | `\cccite`, the lightest of the pair |
| `rgredfill` | `#F8DEE1` | derived as amsredfill from amsred (13%) | alerted block body |
| `rgredborder` | `#F0B5BD` | derived as amsredborder (29%) | reserved |
| `rgsilverfill` | `#F1F1F1` | silver!18!white, derived as amsgreenfill from amsgreen (18%) | example block body |
| `rgsilverborder` | `#DCDCDC` | silver!46!white, derived as amsgreenborder (46%) | example block header |

<!-- markdownlint-enable MD013 -->

White on `rgred` is 5.86:1 and on `rgreddeep` 10.47:1, so both carry white
text; every text-on-fill pair is at WCAG AA or better. `rgred` on the grey frame
title band is 5.24:1. The quiet light-on-dark commands are the exception, as in
AMSUniBo: `\ccite` (`rggreyline`) is 5.69:1 on a block header but only 3.19:1
on the alerted one, where `\cccite` (`rggreybg`) reaches 4.96:1 — so on an
`alertblock` header, prefer `\cccite`.

AMSCesena's third red, `darkerred` `#BF001A`, survived only in its mixes for
the alerted and example block headers; the alerted header takes the identity
red instead, as AMSUniBo's does, and the example header the grey of the scheme.

The fills follow AMSUniBo's derivation where they are new: the alerted fill and
border are the identity colour at 13% and 29%, as `amsredfill` and
`amsredborder` are `amsred`.

## versioning

The style version is declared in `beamerthemeAMSRedGrey.sty` as
`\stylemajor` / `\styleminor` / `\stylepatch`, giving `Major.Minor[.Patch]`.
`\stylepatch` is optional: comment it out to release as `Major.Minor`.

Releases are tagged `Major.Minor[.Patch]-<UTC time-stamp>`, with the time-stamp
appended automatically by the CI at release time.

## licence

This work is distributed under the
[LaTeX Project Public License](LICENSE), version 1.3c or later, and has the
LPPL maintenance status `maintained`.

One file is **not** covered by that licence: `apalike-AMS.bst` is a modified,
renamed derivative of Oren Patashnik's `apalike.bst` (Copyright © 1988, 2010
Oren Patashnik) and remains subject to its own terms, which permit modification
and redistribution provided the resulting file is renamed — as it is here.
