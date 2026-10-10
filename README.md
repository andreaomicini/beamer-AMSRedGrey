# beamer-AMSSilverBlue

> A simple Beamer-LaTeX style for presentations by Alma Mater Studiorum —
> Università di Bologna, in the French Blue and the silver greys of the old
> AMSCesenaBleu style, recovered

## author

* Andrea Omicini

## usage

```latex
\documentclass[presentation]{beamer}\mode<presentation>{\usetheme{AMSSilverBlue}}
```

Everything else is AMSUniBo's: the `apice` option for the APICe BibTeX field,
the `bologna` and `cesena` options for the seal watermark — none unless asked
for — and the commands and the bibliography style. The old styles
always carried the Campus di Cesena seal, so a deck moved from them wants
`cesena`:

```latex
\documentclass[presentation,cesena,apice]{beamer}\mode<presentation>{\usetheme{AMSSilverBlue}}
```

A ready-to-use presentation skeleton is available in
[beamer-AMSSilverBlue-template](https://github.com/andreaomicini/beamer-AMSSilverBlue-template).

## relation to beamer-AMSUniBo and to AMSCesenaBleu

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
`AMSCesenaBleu` (2016) defined exactly one colour, *French Blue* `#0073BA`, and
borrowed everything else from Beamer's own `beaver` colour theme — redefining
`beaver`'s `darkred` as the blue, so that the theme's red mixes came out blue
and its greys stayed grey. Those greys are the **silver** of the name. The
style was copied into some eighty decks over the years, in nine variants that
differ in how they mix the colours and never in the colours themselves.

The old style was not satisfying, so only its colours were kept. They were
extracted from every copy of the style found in the archive, as the shades it
actually used, and assigned to the roles AMSUniBo's palette has. Where a role
had no counterpart in the old style, the colour was guessed from the existing
ones, and the colour theme says so beside it.

## structure

<!-- markdownlint-disable MD013 -->
| file | what it is |
| --- | --- |
| `beamerthemeAMSSilverBlue.sty` | the theme: AMSUniBo's, in this palette |
| `beamercolorthemesilverblue.sty` | the palette alone, with the provenance of each colour, loaded by the theme |
| `almabologna-background.pdf` | the background under the `bologna` option: the Ateneo seal, as in AMSUniBo |
| `almacesena-background.pdf` | the same, with the Campus di Cesena seal, for the `cesena` option |
| `apalike-AMS.bst` | the bibliography style, AMSUniBo's |

<!-- markdownlint-enable MD013 -->

Every release attaches a `style.zip` holding all five plus the `LICENSE`.

## the palette

**Blue is the identity colour** — the head line, links, bullets, alerts — as
AMSUniBo's red is; **deep blue and silver are the structural ones**, as its
green is.

<!-- markdownlint-disable MD013 -->
| colour | value | source | where it goes on a slide |
| --- | --- | --- | --- |
| `sbblue` | `#0073BA` | French Blue, frenchblue in AMSCesenaBleu | head line, author, bullets, alerted text, URLs, DOIs, alerted block headers |
| `sbbluedark` | `#00568C` | frenchblue!75!black, Bleu bibliography note | reserved for active states |
| `sbbluedeep` | `#003F66` | frenchblue!55!black, Bleu block title | structure, block headers, emphasis, section in TOC, the APICe marker |
| `sbbluelight` | `#B2D5EA` | frenchblue!30!white, Bleu example block title | reserved |
| `sbbluetint` | `#EBF4F9` | frenchblue!8!white, between Bleu block bodies (4%) and AMSUniBo tints | block bodies |
| `sbblack` | `#000000` | black | title, frame titles |
| `sbtext` | `#000C13` | frenchblue!10!black, Bleu normal text | body text |
| `sbsilver` | `#B3B3B3` | gray!60!white, beamer beaver frame title right | separation lines |
| `sbsilvertint` | `#F2F2F2` | gray!10!white, beaver frame title | frame title band, foot line |
| `sbsilvertint2` | `#D9D9D9` | gray!30!white, beaver palette primary | foot line, frame title right |
| `sbgrey` | `#404040` | darkgray, Bleu quote | institute |
| `sbgreymid` | `#5A5A5A` | gray!70!black, guessed: secondary text | secondary text, footnotes, subtitle, date |
| `sbgreyline` | `#BFBFBF` | lightgray, Bleu \cccite and \uuurl | `\ccite`, `\uuurl`, `\dddoi`, `\aalert`, fine rules |
| `sbgreybg` | `#ECECEC` | gray!15!white, beaver palette secondary | `\cccite`, the lightest of the pair |
| `sbbluefill` | `#DEEDF6` | derived as amsredfill from amsred (13%) | alerted block body |
| `sbblueborder` | `#B5D6EB` | derived as amsredborder (29%) | reserved |
| `sbsilverfill` | `#F1F1F1` | silver!18!white, derived as amsgreenfill from amsgreen (18%) | example block body |
| `sbsilverborder` | `#DCDCDC` | silver!46!white, derived as amsgreenborder (46%) | example block header |

<!-- markdownlint-enable MD013 -->

White on `sbblue` is 5.05:1 and on `sbbluedeep` 11.04:1, so both carry white
text; every text-on-fill pair is at WCAG AA or better. `sbblue` on the silver
frame title band is 4.51:1. The quiet light-on-dark commands are the exception,
as in AMSUniBo: `\ccite` (`sbgreyline`) is 6.00:1 on a block header but only
2.74:1 on the alerted one, where `\cccite` (`sbgreybg`) reaches 4.27:1 — so on
an `alertblock` header, prefer `\cccite`.

The fills follow AMSUniBo's derivation where they are new: the alerted fill and
border are the identity colour at 13% and 29%, as `amsredfill` and
`amsredborder` are `amsred`.

## versioning

The style version is declared in `beamerthemeAMSSilverBlue.sty` as
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
