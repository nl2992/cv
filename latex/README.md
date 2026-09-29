# LaTeX CV sources

Each version is a standalone `.tex` file; layout, fonts and shared URLs live in
[`cv.sty`](cv.sty). Compiled PDFs are committed in [`pdf/`](pdf/).

| Version | Source | PDF |
|---|---|---|
| General | [Nigel_Li_CV.tex](Nigel_Li_CV.tex) | [pdf](pdf/Nigel_Li_CV.pdf) |
| Hong Kong · Buy-Side | [NigelLi_CV_HK_BuySide.tex](NigelLi_CV_HK_BuySide.tex) | [pdf](pdf/NigelLi_CV_HK_BuySide.pdf) |
| Hong Kong · Sell-Side | [NigelLi_CV_HK_SellSide.tex](NigelLi_CV_HK_SellSide.tex) | [pdf](pdf/NigelLi_CV_HK_SellSide.pdf) |
| United States · Buy-Side | [NigelLi_CV_US_BuySide.tex](NigelLi_CV_US_BuySide.tex) | [pdf](pdf/NigelLi_CV_US_BuySide.pdf) |
| United States · Sell-Side | [NigelLi_CV_US_SellSide.tex](NigelLi_CV_US_SellSide.tex) | [pdf](pdf/NigelLi_CV_US_SellSide.pdf) |

## Build

```bash
cd latex && make                 # tectonic (brew install tectonic)
cd latex && make ENGINE=xelatex  # or any TeX Live / MacTeX install
```

On Overleaf: upload `cv.sty` plus a `.tex` file and set the compiler to **XeLaTeX**.

## Adding a version

Copy the closest `.tex` file, rename it, edit, run `make`. The Makefile picks up
every `.tex` in this folder automatically.

## Links

Every version has clickable links for email, LinkedIn, **Winning Team** (IAQF
announcement) and **firm-wide recognized** (Wellington memo). The URLs are
defined once in `cv.sty` — change them there. Use `\cvlink{url}{text}` for new ones.

The IAQF link deliberately uses the stable `iaqf.org/resources/...` path: it
redirects to a freshly signed CDN URL on each visit. Don't paste the signed
`cdn.wildapricot.com/...&Signature=...` URL, which expires (the one in the
original Google Docs PDF expired on 25 Jul 2026).
