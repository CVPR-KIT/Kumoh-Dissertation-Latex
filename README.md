# Kumoh National Institute of Technology Dissertation LaTeX Template

**Disclaimer:** This community-maintained template is provided as-is. Users are responsible for confirming that the final thesis satisfies the current official university requirements.

This repository contains a LaTeX template for Master's and Doctoral dissertations at Kumoh National Institute of Technology (KIT). The template has been refreshed from a completed 2026 dissertation project so that the page size, margins, front matter, table/list formatting, citation setup, and appendix structure match the latest working style in that project.

## Official Guidelines

The reference documents from KIT are included in `학위논문작성법(양식)/`. Check the university website for the newest rules before final submission.

Previous reference notice: [KIT Official Thesis Guidelines](https://cam.kumoh.ac.kr/cam/sub0603.do?mode=view&articleNo=551220&article.offset=0&articleLimit=10)

## Quick Start With MiKTeX and TeXstudio

This is the easiest setup for most Windows users.

1. Install [MiKTeX](https://miktex.org/download).
2. During MiKTeX setup, allow missing packages to be installed automatically. 
3. Install [TeXstudio](https://www.texstudio.org/).
4. Open `thesis-main/thesis.tex` in TeXstudio.
5. Go to **Options > Configure TeXstudio > Build**.
6. Set **Default Compiler** to `PdfLaTeX`.
7. Set **Default Bibliography Tool** to `BibTeX`.
8. Press **F5** to build and view the PDF.

If references appear as question marks, run the build a few more times or use this sequence:

```text
PdfLaTeX -> BibTeX -> PdfLaTeX -> PdfLaTeX
```

In TeXstudio, this can be configured as a custom quick build command:

```text
txs:///pdflatex | txs:///bibtex | txs:///pdflatex | txs:///pdflatex | txs:///view-pdf
```

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

## 한국어 안내

이 저장소는 국립금오공과대학교 석사/박사 학위논문 작성을 위한 LaTeX 템플릿입니다. 기본 작업 폴더는 `thesis-main/`이며, `thesis-main/thesis.tex` 파일을 컴파일하면 됩니다.

### 1. 처음 사용할 때

1. `thesis-main/meta.tex`에서 논문 제목, 이름, 학과, 지도교수, 심사위원, 날짜를 수정합니다.
2. `abstract-eng.tex`와 `abstract-kr.tex`에 영문 초록과 국문 요약을 작성합니다.
3. `chapter1.tex`, `chapter2.tex` 등 장 파일에 본문을 작성합니다.
4. 참고문헌은 `references.bib`에 추가하고 본문에서 `\textcite{key}` 또는 `\parencite{key}`로 인용합니다.
5. GKS 장학금 페이지가 필요 없으면 `thesis.tex`에서 `\input{gks.tex}` 부분을 주석 처리합니다.

### 2. MiKTeX 설치

1. [MiKTeX](https://miktex.org/download)를 설치합니다.
2. 설치 중 패키지 자동 설치 옵션이 나오면 **Yes**를 선택합니다.
3. 처음 컴파일할 때 필요한 패키지가 자동으로 설치될 수 있으므로 인터넷 연결이 필요할 수 있습니다.

### 3. TeXstudio에서 쉽게 빌드하기

1. [TeXstudio](https://www.texstudio.org/)를 설치합니다.
2. TeXstudio에서 `thesis-main/thesis.tex`를 엽니다.
3. **Options > Configure TeXstudio > Build**로 이동합니다.
4. **Default Compiler**를 `PdfLaTeX`로 설정합니다.
5. **Default Bibliography Tool**을 `BibTeX`로 설정합니다.
6. **F5**를 눌러 PDF를 생성하고 확인합니다.

참고문헌이나 목차가 제대로 표시되지 않으면 아래 순서로 다시 빌드합니다.

```text
PdfLaTeX -> BibTeX -> PdfLaTeX -> PdfLaTeX
```

TeXstudio의 사용자 명령 또는 Quick Build에 아래 명령을 넣어두면 한 번에 빌드할 수 있습니다.

```text
txs:///pdflatex | txs:///bibtex | txs:///pdflatex | txs:///pdflatex | txs:///view-pdf
```

### 4. 명령어로 빌드하기

PowerShell 또는 명령 프롬프트에서 다음 순서로 실행합니다.

```powershell
cd thesis-main
pdflatex -interaction=nonstopmode -halt-on-error thesis.tex
bibtex thesis
pdflatex -interaction=nonstopmode -halt-on-error thesis.tex
pdflatex -interaction=nonstopmode -halt-on-error thesis.tex
```

### 5. 제출 전 확인

생성된 `thesis.pdf`를 대학원 최신 학위논문 작성 지침과 반드시 비교하십시오. 이 템플릿은 작성 편의를 위한 것이며, 최종 형식 확인 책임은 사용자에게 있습니다.

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
