# Kumoh National Institute of Technology Dissertation LaTeX Template

**Disclaimer:** This community-maintained template is provided as-is. Users are responsible for confirming that the final thesis satisfies the current official university requirements.

This repository contains a LaTeX template for Master's and Doctoral dissertations at Kumoh National Institute of Technology (KIT). The template has been refreshed from a completed 2026 dissertation project so that the page size, margins, front matter, table/list formatting, citation setup, and appendix structure match the latest working style in that project.

## Official Guidelines

The reference documents from KIT are included in `학위논문작성법(양식)/`. Check the university website for the newest rules before final submission.

Previous reference notice: [KIT Official Thesis Guidelines](https://cam.kumoh.ac.kr/cam/sub0603.do?mode=view&articleNo=551220&article.offset=0&articleLimit=10)

## Project Structure

The working LaTeX project is in `thesis-main/`.

- `thesis.tex`: main file to compile; controls the order of pages and chapters.
- `preamble.tex`: packages, page geometry, fonts, citations, headings, theorem styles, and table/list formatting.
- `meta.tex`: thesis title, author, department, supervisor, date, and committee names.
- `cover.tex`, `titlePage.tex`, `approvalPage.tex`, `gks.tex`: front-matter page layouts.
- `abstract-eng.tex`, `abstract-kr.tex`, `acknowledgements.tex`: front-matter content.
- `notations.tex`, `abbreviations.tex`: optional lists included before the main chapters.
- `chapter*.tex`, `appendix.tex`: sample thesis content.
- `references.bib`: BibTeX bibliography database.
- `fonts/`: bundled Korean and monospace fonts used by the template.

## Compilation

The refreshed template uses `natbib` and BibTeX. The tested build sequence is:

```powershell
cd thesis-main
pdflatex -interaction=nonstopmode -halt-on-error thesis.tex
bibtex thesis
pdflatex -interaction=nonstopmode -halt-on-error thesis.tex
pdflatex -interaction=nonstopmode -halt-on-error thesis.tex
```

In TeXstudio, set the default compiler to `pdfLaTeX` and the bibliography tool to `BibTeX`. In VS Code LaTeX Workshop, use the `latexmk (pdflatex)` recipe or another recipe that runs BibTeX.

## Citation Style

Citation style is controlled in `preamble.tex`:

```latex
\numericcitationstrue   % numeric citations, e.g., [1]
% \numericcitationsfalse % author-year citations, e.g., (Author, 2026)
```

The template defines compatibility aliases:

```latex
\textcite{key}   % maps to \citet{key}
\parencite{key}  % maps to \citep{key}
```

## Personalizing the Template

1. Edit `thesis-main/meta.tex` first.
2. Replace the sample abstracts, acknowledgements, chapters, appendices, notation list, and abbreviation list.
3. If the GKS scholarship page does not apply, comment the `gks.tex` block in `thesis.tex`.
4. For a Master's thesis, remove unused committee rows from `approvalPage.tex`.
5. Add references to `references.bib` and cite them from the chapter files.

Keep a generated `thesis.pdf` for reviewers, but do not rely on it as proof of compliance; always compare the final PDF against the latest official KIT documents.
