[⬅ Back to Main Page](../README.md) | [⬅ Prev: Beamer](../Beamer/README.md) | [Next: Google Docs ➡](../Google-Docs/README.md)

# Doxygen — Complete Class Notes

**Doxygen** is a standard automated documentation generator for C, C++, Java, Python, and other programming languages. It extracts specially formatted comments directly from source code to build structured technical documentation in HTML, LaTeX/PDF, and other formats.

---

## 1. Why Use Doxygen?
* **Code & Docs Stay Synced:** Documentation lives right above functions and classes in the source file, making updates easy.
* **Multi-Format Output:** Generates interactive web pages (`HTML`), printable manuals (`LaTeX`/`PDF`), `RTF`, and `XML`.
* **Visual Diagrams:** Integrates with **Graphviz (`dot`)** to automatically draw class hierarchies, call graphs, and collaboration diagrams.

---

## 2. Doxygen Comment Styles
Doxygen ignores regular comments (`//` or `/* */`) unless they use special markers:

* **Javadoc Style (C/C++/Java):**
  ```cpp
  /**
   * Multi-line documentation comment
   */
  ```
* **Qt Style:**
  ```cpp
  /*!
   * Multi-line documentation comment
   */
  ```
* **Single-Line Documentation:**
  ```cpp
  /// Single-line documentation comment
  //! Alternative single-line comment
  ```
* **Inline / Trailing Member Documentation (put *after* a variable or parameter):**
  ```cpp
  int count; ///< Stores the total number of items
  ```

---

## 3. Essential Doxygen Tags (`@` or `\`)
Tags can start with either `@` (Javadoc style) or `\` (Doxygen/LaTeX style):

### File & Project Metadata
* `@file` — Documents the current source or header file (required for global functions/variables to appear).
* `@brief` — Short one-line summary of a file, class, or function.
* `@details` — Detailed explanation following the brief summary.
* `@author` — Specifies the author's name.
* `@date` — Specifies creation or modification date.
* `@version` — Mentions the version number.

### Function & Parameter Tags
* `@param [in|out|in,out] name` — Describes a function parameter and its data direction.
* `@return` (or `@returns`) — Explains the return value of a function.
* `@throws` / `@exception` — Documents exceptions thrown by the function.
* `@pre` / `@post` — Specifies pre-conditions and post-conditions.

### Structural & Cross-Reference Tags
* `@class` / `@struct` — Documents a class or structure.
* `@see` — Adds a "See also" cross-reference link to another function or file.
* `@note` / `@warning` / `@todo` / `@bug` — Creates highlighted callout boxes in the generated docs.
* `@code ... @endcode` — Embeds formatted example code snippets inside documentation.

---

## 4. Complete Documented Code Example (`calculator.cpp`)
```cpp
/**
 * @file calculator.cpp
 * @brief Basic arithmetic operations for TW Doxygen Lab.
 * @author Your Name
 * @date 2026-11-13
 */

/**
 * @brief Divides two floating-point numbers.
 * @details Checks for division by zero before performing calculation.
 * 
 * @param[in] a Numerator value.
 * @param[in] b Denominator value (must not be zero).
 * @return Quotient of a divided by b, or 0 if b is zero.
 * @warning Prints an error message if b equals 0.
 */
float divide(float a, float b) {
    if (b == 0) return 0;
    return a / b;
}
```

---

## 5. Step-by-Step Workflow (CLI & GUI)

### Method A: Command Line (Terminal)
1. **Generate Default Configuration File:**
   ```bash
   doxygen -g
   ```
   *(Creates a file named `Doxyfile` in your project directory.)*
2. **Edit Key Settings in `Doxyfile`:**
   * `PROJECT_NAME = "My CSE Project"`
   * `INPUT = ./src` (folder containing source files)
   * `RECURSIVE = YES` (scan subfolders)
   * `EXTRACT_ALL = YES` (document even uncommented functions)
   * `GENERATE_HTML = YES` and `GENERATE_LATEX = YES`
   * `HAVE_DOT = YES` (enable call/class graphs via Graphviz)
3. **Build the Documentation:**
   ```bash
   doxygen Doxyfile
   ```
4. **View Output:** Open `html/index.html` in any web browser.

### Method B: Doxywizard (GUI Tool)
* Launch `doxywizard` to configure project paths, select diagram options, and click **Run doxygen** using a graphical interface.

---

[⬅ Back to Main Page](../README.md) | [⬅ Prev: Beamer](../Beamer/README.md) | [Next: Google Docs ➡](../Google-Docs/README.md)
