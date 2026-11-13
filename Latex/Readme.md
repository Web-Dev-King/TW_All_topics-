[⬅ Back to Main Page](../README.md) | [Next: Beamer ➡](../Beamer/README.md)

# LaTeX — Complete Class Notes

**LaTeX** is a plain-text typesetting system used to produce structured, publication-quality technical documents, reports, and research papers.

---

## 1. Document Structure & Preamble
* **Document Classes:** `\documentclass[12pt, a4paper]{article}` (other classes: `report`, `book`, `letter`, `beamer`).
* **Essential Packages:**
  * `\usepackage[utf8]{inputenc}` — Character encoding.
  * `\usepackage{geometry}` — Page margins (e.g., `\usepackage[margin=1in]{geometry}`).
  * `\usepackage{amsmath, amssymb}` — Advanced math formulas and symbols.
  * `\usepackage{graphicx}` — Inserting images.
  * `\usepackage{hyperref}` — Clickable URLs and internal links (`\url{...}`, `\href{url}{text}`).
  * `\usepackage{listings}` — Formatting programming source code blocks.
* **Title Block:** `\title{}`, `\author{}`, `\date{\today}`, rendered inside the body via `\maketitle`.
* **Document Body:** All content goes between `\begin{document}` and `\end{document}`.

---

## 2. Sections, Table of Contents & Page Control
* **Hierarchy:** `\part{}`, `\chapter{}` (book/report only), `\section{}`, `\subsection{}`, `\subsubsection{}`, `\paragraph{}`.
* **Unnumbered Sections:** Add an asterisk, e.g., `\section*{Acknowledgement}`.
* **Auto-Generated Lists:** `\tableofcontents`, `\listoffigures`, `\listoftables`.
* **Spacing & Breaks:** `\\` (line break), `\par` (new paragraph), `\newpage` (page break), `\vspace{1cm}` / `\hspace{1cm}` (custom spacing).

---

## 3. Text Formatting & Special Characters
* **Styles:** `\textbf{bold}`, `\textit{italic}`, `\underline{underline}`, `\texttt{monospace/code}`, `\emph{emphasis}`.
* **Font Sizes:** `\tiny`, `\small`, `\normalsize`, `\large`, `\Large`, `\huge`, `\Huge`.
* **Alignment:** `\begin{center}`, `\begin{flushleft}`, `\begin{flushright}`.
* **Escaping Reserved Symbols:** Use a backslash for `#`, `$`, `%`, `&`, `_`, `{`, `}` (e.g., `\$`, `\%`, `\&`).
* **Comments:** Lines starting with `%` are ignored by the compiler.

---

## 4. Lists
* **Bulleted List (`itemize`):** Uses `\item` for bullet points.
* **Numbered List (`enumerate`):** Uses `\item` for auto-numbered items.
* **Description List (`description`):** Uses `\item[Term] Definition` for key-value lists.
* **Nested Lists:** Lists can be placed inside another list up to 4 levels deep.

---

## 5. Mathematical Typesetting
* **Modes:**
  * **Inline Math:** `$ a^2 + b^2 = c^2 $`
  * **Display Math:** `$$ x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$` or `\begin{equation} ... \end{equation}` (auto-numbered).
* **Core Syntax:**
  * Powers & Subscripts: `x^2`, `x_{i,j}`
  * Fractions & Roots: `\frac{num}{den}`, `\sqrt[n]{x}`
  * Greek Letters: `\alpha`, `\beta`, `\gamma`, `\theta`, `\pi`, `\Sigma`, `\Omega`
  * Operators: `\sum_{i=1}^{n}`, `\int_{a}^{b}`, `\lim_{x \to \infty}`, `\leq`, `\geq`, `\neq`, `\approx`
  * Matrices: `\begin{pmatrix} a & b \\ c & d \end{pmatrix}` or `bmatrix` (square brackets).

---

## 6. Tables & Figures (Floats)
* **Tables (`tabular` inside `table`):**
  * Column alignment: `l` (left), `c` (center), `r` (right), `|` (vertical border).
  * Cell separator: `&` | Row end: `\\` | Horizontal line: `\hline`
* **Images (`\includegraphics` inside `figure`):**
  * Example: `\includegraphics[width=0.7\textwidth]{image.png}`
* **Placement Specifiers:** `[h]` (here), `[t]` (top), `[b]` (bottom), `[p]` (separate page), `[!htbp]` (force placement).
* **Captions & Cross-Referencing:**
  * Add `\caption{Description}` and `\label{fig:arch}` inside the float.
  * Reference anywhere in text using `Figure~\ref{fig:arch}` or `Table~\ref{tab:data}`.

---

## 7. Citations & Bibliography
* **Manual Bibliography:**
  ```latex
  \(\begin{thebibliography}{9} \bibitem{knuth84}\) Donald E. Knuth\(, \textit{The TeXbook}, 1984. \end{thebibliography} \%\%\)MAGIT_PARSER_PROTECT%%  ```
* **BibTeX (`.bib` file):** Store references in `references.bib`, cite in text with `\cite{knuth84}`, and render with `\bibliographystyle{plain}` and `\bibliography{references}`.

---

## 8. Compilation Workflow
* **Editors Used:** Overleaf (cloud-based collaborative editor) or TeXstudio / VS Code (local).
* **Compilers:** `pdflatex`, `xelatex`, or `lualatex` convert `.tex` source files into `.pdf` output (alongside auxiliary `.aux` and `.log` files).

---

[⬅ Back to Main Page](../README.md) | [Next: Beamer ➡](../Beamer/README.md)
