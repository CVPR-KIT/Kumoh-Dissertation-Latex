# Kumoh National Institute of Technology (KIT) - Dissertation LaTeX Template
**We are not responsible for any consequences and losses caused by the use of this template**

This repository contains a clean, organized, and highly customizable LaTeX template for writing a Master's or Doctoral dissertation at the Kumoh National Institute of Technology (KIT).

## 📄 Official Guidelines
This template was strictly built and formatted to adhere to the official KIT thesis formatting guidelines. 

Reference: [KIT Official Thesis Guidelines (Notice No. 551220)](https://cam.kumoh.ac.kr/cam/sub0603.do?mode=view&articleNo=551220&article.offset=0&articleLimit=10)

## 🛠️ Prerequisites

To successfully compile this template, we recommend using the following toolchain:

1. **LaTeX Distribution**: We used [MiKTeX](https://miktex.org/download) to install and manage the necessary LaTeX packages. 
2. **LaTeX Editor**: We used [TeXstudio](https://www.texstudio.org/) as the IDE for writing and compiling the documents.

*(Note: Other distributions like TeX Live and editors like VS Code or Overleaf are also fully supported).*

## 🚀 How to Use

### 1. File Structure
- `thesis.tex`: The main document file. This is the **only** file you need to compile. It acts as the structural skeleton of your thesis.
- `preamble.tex`: Contains all package imports, font configurations, and styling rules. You rarely need to edit this unless you want to add new packages.
- `meta.tex`: Contains your personal metadata (Thesis Title, Author Name, Dates, Department, etc.). **Update this file first.**
- `approvalPage.tex`: Contains the tabular layout for your committee member signatures.
- `chapter*.tex` / `appendix.tex`: The actual content files for your thesis.
- `references.bib`: Your BibTeX references.

### 2. Compilation Instructions
Because this template uses modern fonts and requires Korean language support (via the `kotex` package), it must be compiled using **XeLaTeX**.

**Using TeXstudio (Recommended):**
1. Open `thesis.tex` in TeXstudio.
2. Ensure your default compiler is set to XeLaTeX (Options > Configure TeXstudio > Build > Default Compiler: XeLaTeX).
3. Simply press **F5** (Build & View) or **F6** (Compile). TeXstudio will automatically handle the entire build sequence and bibliography for you!

### 3. Personalizing the Template
1. Open `meta.tex` and fill in your specific details (e.g., `\newcommand{\ThesisTitle}{Your Title}`).
2. Open `approvalPage.tex` to adjust your specific committee members.
3. Write your abstracts in `abstract-eng.tex` and `abstract-kr.tex`.
4. Add your content into `chapter1.tex`, `chapter2.tex`, etc.

## 📝 Template Features
- **Page Numbering**: The template automatically handles Roman numerals (`i, ii, iii`) for the front matter and Arabic numerals (`1, 2, 3`) for the main body. It also features the required `- 1 -` formatting in the footer.
- **TOC Spacing**: The Table of Contents is precisely formatted to mimic the exact spacing of the official DOCX template provided by the university.
- **Section Numbering**: Chapters are numbered with Roman numerals (`Chapter I, Chapter II`), while internal sections, tables, and figures retain standard decimal formatting (`2.1`, `Figure 2.1`).