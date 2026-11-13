[⬅ Back to Main Page](../README.md) | [⬅ Prev: LaTeX](../LaTeX/README.md) | [Next: Doxygen ➡](../Doxygen/README.md)

# Beamer — Complete Class Notes

**Beamer** is a LaTeX document class used to create clean, professional PDF presentations and academic slideshows using plain-text commands.

---

## 1. Basic Presentation Structure
* **Document Class:** `\documentclass{beamer}` (supports options like `[aspectratio=169]` for widescreen or `[11pt]` for font size).
* **Title Page Metadata:** `\title{}`, `\subtitle{}`, `\author{}`, `\institute{}`, `\date{\today}`.
* **Frames (Slides):** Every individual slide is enclosed inside a `frame` environment:
  ```latex
  \(\documentclass{beamer} \usetheme{Madrid}\)

  \(\title{Technical Writing Presentation} \author{Your Name} \institute{Department of CSE} \date{\today}\)

  \(\begin{document}\)

  % Title Slide
  \(\begin{frame} \titlepage \end{frame}\)

  % Content Slide
  \(\begin{frame}{Slide Title}{Optional Subtitle}\)
      Hello, Beamer!
  \(\end{frame}\)

  \(\end{document}\)
  ```

---

## 2. Themes & Color Customization
* **Presentation Themes (`\usetheme{...}`):** Controls overall layout, headers, footers, and sidebars.
  * *Common themes:* `Madrid`, `Berlin`, `Warsaw`, `Copenhagen`, `AnnArbor`, `Boadilla`, `default`.
* **Color Themes (`\usecolortheme{...}`):** Changes the color palette.
  * *Common colors:* `beaver` (red/grey), `dolphin` (blue), `crane` (orange), `seagull` (greyscale), `default`.
* **Font & Inner/Outer Themes:** `\usefonttheme{serif}`, `\useinnertheme{rounded}`, `\useoutertheme{infolines}`.

---

## 3. Navigation & Table of Contents
* **Sections & Subsections:** `\section{Introduction}` and `\subsection{Motivation}` (placed *outside* frames to populate navigation bars).
* **Outline Slide:** Use `\tableofcontents` inside a frame to auto-generate an agenda slide.
* **Highlighting Current Section:**
  ```latex
  \(\AtBeginSection[]{ \begin{frame}{Outline} \tableofcontents[currentsection] \end{frame} }\)
  ```
* **Navigation Symbols:** Remove bottom-right default icons using `\beamertemplatenavigationsymbolsempty`.

---

## 4. Blocks & Callout Boxes
Beamer provides built-in styled boxes to highlight definitions, warnings, and examples:
* **Standard Block:** `\begin{block}{Title} Content \end{block}` (primary theme color).
* **Alert Block:** `\begin{alertblock}{Warning} Content \end{alertblock}` (red highlight for important notes).
* **Example Block:** `\begin{exampleblock}{Example} Content \end{exampleblock}` (green highlight for examples).
* **Math Environments:** Built-in support for `theorem`, `definition`, `lemma`, and `proof` blocks.

---

## 5. Multi-Column Layouts
Split a slide into side-by-side sections (useful for text on the left and an image/diagram on the right):
```latex
\(\begin{columns} \begin{column}{0.5\textwidth} Left side text or bullet points. \end{column} \begin{column}{0.5\textwidth} \includegraphics[width=\textwidth]{diagram.png} \end{column} \end{columns} \%\%\)MAGIT_PARSER_PROTECT%%```

---

## 6. Overlays & Incremental Reveals (Animations)
Overlays reveal slide elements step-by-step across multiple PDF pages within a single frame:
* **`\pause`:** Pauses rendering and reveals remaining content on the next click.
* **Item-by-Item Lists:**
  * `\begin{itemize}[<+->]` — Automatically reveals each `\item` one by one.
  * `\item<2->` — Appears from slide 2 onward.
  * `\item<2-4>` — Visible only on slides 2 through 4.
* **Text Highlighting Commands:**
  * `\alert<2>{Text}` — Highlights text in red on click 2.
  * `\textbf<3>{Text}` — Makes text bold on click 3.
  * `\uncover<2->{Text}` — Reserves space and reveals text on click 2.
  * `\only<2>{Text}` — Displays text *only* on click 2 without reserving space.

---

## 7. Code Blocks, Tables & Images
* **Source Code (`fragile` frame):** Frames containing verbatim code or `\begin{lstlisting}` **must** include `[fragile]`:
  ```latex
  \(\begin{frame}[fragile]{Code Example} \begin{verbatim}\)
      printf("Hello World")\(; \end{verbatim} \end{frame} \%\%\)MAGIT_PARSER_PROTECT%%  ```
* **Tables & Figures:** Uses the same `tabular` and `\includegraphics` syntax as standard LaTeX (captions are optional in slides).

---

## 8. Key Differences: LaTeX (`article`) vs. Beamer

| Feature | LaTeX (`article`) | Beamer (`beamer`) |
| :--- | :--- | :--- |
| **Purpose** | Reports, papers, long documents | Presentations, slideshows |
| **Page Unit** | Continuous pages | Individual `\begin{frame}` slides |
| **Animations** | None (static) | Overlays (`\pause`, `<+->`) |
| **Styling** | Minimal default layout | Built-in themes & color palettes |

---

[⬅ Back to Main Page](../README.md) | [⬅ Prev: LaTeX](../LaTeX/README.md) | [Next: Doxygen ➡](../Doxygen/README.md)
