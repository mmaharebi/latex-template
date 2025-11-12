# Physical-Style Mathematical Notation Template# Physical-Style Mathematical Notation for LaTeX



A comprehensive, production-ready LaTeX template for technical documents requiring clear and consistent mathematical notation. Ideal for physics, engineering, mathematics, and scientific writing.A reusable LaTeX template providing consistent, physics-inspired typographic conventions for scalars, vectors, matrices, and tensors in scientific manuscripts and technical reports.



## Author---



**Mohammadmahdi Maharebi**## Table of Contents

- Email: mmaharebi@gmail.com

- GitHub: @mmaharebi- [Purpose](#purpose)

- [Motivation](#motivation)

---- [LaTeX Macros](#latex-macros)

- [Notation Conventions](#notation-conventions)

## 📋 Table of Contents- [Symbol Reference Table](#symbol-reference-table)

- [Usage Examples](#usage-examples)

1. [Overview](#overview)- [How to Use This Template](#how-to-use-this-template)

2. [Features](#features)- [Best Practices](#best-practices)

3. [Quick Start](#quick-start)- [Contributing](#contributing)

4. [Project Structure](#project-structure)- [License](#license)

5. [Notation System](#notation-system)

6. [Using Colored Theorem Boxes](#using-colored-theorem-boxes)---

7. [Advanced Features](#advanced-features)

8. [Compilation](#compilation)## Purpose

9. [Customization](#customization)

10. [Examples](#examples)This template establishes a **unified typographic system** for mathematical objects commonly used in physics, engineering, and applied mathematics. By adopting visual distinctions based on tensor order (scalars, vectors, matrices, higher-order tensors), readers can immediately identify the nature of each quantity, reducing ambiguity and cognitive load.



---**Key features:**

- **Scalars** are italic (standard mathematical notation)

## Overview- **Vectors** are bold and single-underlined

- **Matrices** are bold and double-underlined

This template implements a systematic physical-style notation system:- **Tensors (order ≥ 3)** use bold calligraphic or explicit index notation



| Type | Style | Command | Example |This convention is particularly valuable in disciplines where vectors and matrices appear frequently (e.g., mechanics, electromagnetism, quantum theory, robotics, machine learning).

|------|-------|---------|---------|

| **Scalar** | Italic | `\scalar{x}` | *x* |---

| **Vector** | Bold + underline | `\vec{v}` | **v̲** |

| **Matrix** | Bold + double underline | `\mat{A}` | **A̲̲** |## Motivation

| **Tensor** | Bold calligraphic | `\tensor{T}` | **𝓣** |

### Why adopt a physical-style notation?

---

1. **Visual clarity:** In equations mixing scalars, vectors, and matrices (e.g., $\matrix{A}\vector{x} = \scalar{\lambda}\vector{x}$), each object's type is instantly recognizable.

## Features2. **Consistency across documents:** Using predefined macros ensures uniform rendering throughout multi-author projects or multi-document dissertations.

3. **Pedagogical value:** Students and reviewers benefit from explicit visual cues that distinguish a vector field $\vector{E}$ from a scalar energy $\scalar{E}$.

### Core Features4. **Alignment with established practice:** Many physics and engineering textbooks employ similar conventions (bold for vectors, double-underline or hat for matrices).

✅ **Consistent Notation System** - Clear visual distinction between mathematical objects  

✅ **Colored Theorem Boxes** - Professional tcolorbox environments (theorem, definition, note, etc.)  ### When to use this template

✅ **Glossary & Acronyms** - Built-in support with the `glossaries` package  

✅ **TikZ Diagrams** - Enhanced figures with improved scales and styling  - Theses and dissertations in physics, mechanical/electrical engineering, applied math

✅ **SI Units** - `siunitx` package for proper unit formatting  - Research papers in continuum mechanics, control theory, robotics, quantum information

✅ **Bibliography Support** - BibTeX ready with `references.bib`  - Technical reports requiring clear distinction between vector quantities and scalar parameters

✅ **Modular Structure** - Organized config files for easy customization- Educational materials where pedagogical clarity is paramount



### Enhanced Math Commands---

- **Derivatives**: `\pd{f}{x}`, `\pdd{f}{x}`, `\pdc{f}{x}{y}`, `\td{f}{x}`

- **Operators**: `\grad`, `\Div`, `\curl`, `\vnabla`, `\trace`, `\rank`## LaTeX Macros

- **Utilities**: `\abs{x}`, `\norm{x}`, `\Prob{A}`, `\eqdef`

- **Unit Vectors**: `\xhat`, `\yhat`, `\zhat`, `\rhohat`, `\phihat`, `\Rhat`, `\thetahat`Add the following macros to your LaTeX document preamble (before `\begin{document}`):

- **Vector Operations**: `\vdot`, `\vproj{a}{b}`, `\vang{a}{b}`

- **Quantum Notation**: `\ket{ψ}`, `\bra{ψ}`, `\braket{ψ}{φ}`, `\hop{H}`, `\comm{A}{B}````latex

% Scalar: italic (default math mode, explicit wrapper for consistency)

---\newcommand{\scalar}[1]{\mathit{#1}}



## Quick Start% Vector: bold + single underline

\newcommand{\vect}[1]{\mathbf{\underline{#1}}}

### 1. Clone or Download

```bash% Matrix: bold + double underline

git clone https://github.com/mmaharebi/latex-notation-template.git\newcommand{\matr}[1]{\mathbf{\underline{\underline{#1}}}}

cd latex-notation-template

```% Tensor (order >= 3): bold calligraphic (optional)

\newcommand{\tensor}[1]{\boldsymbol{\mathcal{#1}}}

### 2. Compile```

```bash

make pdf          # Recommended**Note:** We use `\vect` and `\matr` instead of `\vector` and `\matrix` to avoid conflicts with the `amsmath` package. Some journals discourage underlining; check your target venue's style guide before submission.

# OR

pdflatex main.tex---

pdflatex main.tex # Run twice for references

```## Notation Conventions



### 3. Customize| Type | Macro | Example | Rendering Convention |

- Edit `config/metadata.tex` - Set your name, title, PDF metadata|------|-------|---------|---------------------|

- Edit `config/glossary.tex` - Add your glossary entries and acronyms| **Scalar** | `\scalar{a}` | `\scalar{\alpha}`, `\scalar{E}` | Italic (single real or complex number) |

- Edit `references.bib` - Add your bibliography entries| **Vector** | `\vec{v}` | `\vec{E}`, `\vec{F}`, `\vec{v}` | **Bold + single underline** (column vector) |

- Modify `sections/` - Replace example content with your own| **Matrix** | `\mat{A}` | `\mat{M}`, `\mat{K}` | **Bold + double underline** (2D array) |

| **Tensor (≥3)** | `\tensor{T}` | `\tensor{C}`, or $C_{ijkl}$ | **Bold calligraphic** or explicit indices |

---| **Unit vector** | `\hat{\vec{e}}_i` | `\hat{\vec{x}}` | Hat over underlined bold vector |

| **Zero** | `\vec{0}`, `\mat{0}` | — | Underlined bold zero |

## Project Structure| **Identity** | `\mat{I}_n` | — | Double-underlined bold I |



```**Operators and special functions** (det, tr, rank, div, grad, etc.) should be typeset in upright roman using `\det`, `\operatorname{tr}`, `\nabla`, etc.

.

├── main.tex                    # Main document file---

├── references.bib              # Bibliography database

├── Makefile                    # Build automation## Symbol Reference Table

│

├── config/                     # Configuration files| Symbol | Name | Notation | Description / Example |

│   ├── packages.tex           # Package imports|--------|------|----------|----------------------|

│   ├── macros.tex             # Custom notation macros| `\scalar{a}` | Scalar | italic, $\scalar{a}\in\mathbb{R}$ | Single numeric value |

│   ├── theorems.tex           # Theorem environments| `\vec{v}` | Vector | bold + underline, $\vec{v}\in\mathbb{R}^n$ | Column vector, e.g. $\vec{v}=[v_1,\dots,v_n]^\top$ |

│   ├── metadata.tex           # Author, title, PDF metadata| `\mat{A}` | Matrix | bold + double underline, $\mat{A}\in\mathbb{R}^{m\times n}$ | Linear map; entries $A_{ij}$ |

│   └── glossary.tex           # Glossary and acronym definitions| `\mat{A}^\top` | Transpose | superscript $^\top$ | Rows ↔ columns |

│| `\mat{A}^*` or `\mat{A}^\dagger` | Conjugate transpose | Hermitian conjugate | $(\mat{A}^*)_{ij}=\overline{A_{ji}}$ |

├── sections/                   # Content sections (modify these)| `\langle\vec{u},\vec{v}\rangle` | Inner product | angle brackets | $\langle\vec{u},\vec{v}\rangle=\vec{u}^\top\vec{v}$ (real) |

│   ├── introduction.tex| `\|\vec{v}\|` | Norm | double bars | Euclidean norm $\|\vec{v}\|_2=\sqrt{\langle\vec{v},\vec{v}\rangle}$ |

│   ├── basic_notation.tex| `\vec{u}\otimes\vec{v}` | Tensor product | $\otimes$ | Rank-1 tensor / outer product |

│   ├── linear_algebra.tex| `\vec{u}\vec{v}^\top` | Outer product | vector × transpose | Matrix with entries $u_i v_j$ |

│   ├── physics.tex| `\mat{I}_n` | Identity matrix | $n\times n$ | $\mat{I}_n \vec{x} = \vec{x}$ |

│   ├── engineering.tex| `\vec{0}`, `\mat{0}` | Zero vector/matrix | | All entries zero |

│   ├── quantum_mechanics.tex| `\det(\mat{A})` | Determinant | scalar | Volume scaling factor |

│   ├── applications.tex| `\operatorname{tr}(\mat{A})` | Trace | scalar | Sum of diagonal entries |

│   ├── conclusion.tex| `\operatorname{rank}(\mat{A})` | Rank | integer | Dimension of column space |

│   └── appendix.tex| $(\scalar{\lambda},\vec{x})$ | Eigenpair | $\mat{A}\vec{x}=\scalar{\lambda}\vec{x}$ | Eigenvalue $\scalar{\lambda}$, eigenvector $\vec{x}\neq\vec{0}$ |

│| $\{\vec{e}_i\}$ | Canonical basis | standard basis | $\vec{e}_i$ has 1 at position $i$, 0 elsewhere |

├── figures/                    # TikZ diagrams

│   ├── least_squares_projection.tex---

│   ├── rigid_body.tex

│   ├── waveguide_geometry.tex## Usage Examples

│   ├── te10_mode.tex

│   └── metasurface_reflection.tex### Example 1: Linear system

│```latex

└── build/                      # Compiled output (auto-generated)Consider the linear system

```\[

  \mat{A}\vec{x} = \vec{b},

---\]

where $\mat{A}\in\mathbb{R}^{n\times n}$ is a square matrix, 

## Notation System$\vec{x}\in\mathbb{R}^n$ is the unknown vector, 

and $\vec{b}\in\mathbb{R}^n$ is the right-hand side.

### Basic Usage```



```latex### Example 2: Eigenvalue problem

% Scalars (italic by default)```latex

Let $\scalar{x} = 5$ and $\scalar{y} = 3$.The eigenvalue problem for $\mat{A}$ is

\[

% Vectors (bold + underline)  \mat{A}\vec{x} = \scalar{\lambda}\vec{x},

The velocity vector is $\vec{v} = \vec{v}_0 + \vec{a}t$.\]

where $\scalar{\lambda}\in\mathbb{C}$ is the eigenvalue 

% Matrices (bold + double underline)and $\vec{x}\neq\vec{0}$ is the corresponding eigenvector.

The transformation matrix $\mat{A}$ satisfies $\mat{A}\vec{x} = \vec{b}$.```



% Tensors (bold calligraphic)### Example 3: Physics (Newton's second law)

The stress tensor $\tensor{σ}$ relates stress to strain.```latex

```Newton's second law in vector form:

\[

### Common Patterns  \vec{F} = \scalar{m}\vec{a},

\]

```latexwhere $\vec{F}$ is the net force, $\scalar{m}$ is the scalar mass, 

% Unit vectorsand $\vec{a}$ is the acceleration vector.

$\xhat, \yhat, \zhat$                    % Cartesian```

$\rhohat, \phihat, \zhat$               % Cylindrical  

$\Rhat, \thetahat, \phihat$             % Spherical### Example 4: Inline text

```latex

% Vector operationsThe electric field $\vec{E}$ at position $\vec{r}$ 

$\vec{a} \vdot \vec{b}$               % Dot productis computed from the potential $\scalar{\phi}$ as 

$\vproj{a}{b}$                          % Projection of b onto a$\vec{E} = -\nabla\scalar{\phi}$.

$\vang{a}{b}$                           % Angle between vectors```



% Derivatives---

$\pd{f}{x}$                             % ∂f/∂x

$\pdd{f}{x}$                            % ∂²f/∂x²## How to Use This Template

$\pdc{f}{x}{y}$                         % ∂²f/∂x∂y

$\td{s}{t}$                             % ds/dt### Option 1: Use the Complete LaTeX Template



% OperatorsThis repository includes a ready-to-use LaTeX template with comprehensive examples:

$\vnabla \times \vec{E}$               % Curl

$\vnabla \cdot \vec{B}$                % Divergence**Files included:**

$\grad f$, $\Div \vec{F}$, $\curl \vec{A}$- `main.tex` - Complete LaTeX document with examples from physics, linear algebra, engineering

```- `Makefile` - Build automation with multiple targets

- `.gitignore` - Excludes LaTeX build artifacts

---

**Quick start:**

## Using Colored Theorem Boxes```bash

# Clone or download this repository

### Numbered Environments (tcolorbox style)cd report



For fancy colored boxes with numbering, use the tcolorbox syntax:# Compile the template

make pdf

```latex

% Theorem (blue box)# Or compile and view

\begin{theorem}{Pythagorean Theorem}{pythag}make view

  In a right triangle, $a^2 + b^2 = c^2$.

\end{theorem}# For quick single-pass compilation

make quick

% Definition (green box)

\begin{definition}{Vector Space}{vecspace}# Clean build artifacts

  A vector space is a set $V$ with addition and scalar multiplication...make clean

\end{definition}

# See all available commands

% Note (yellow/orange box)make help

\begin{note}{Important Point}{important}```

  This property only holds for finite-dimensional spaces.

\end{note}### Option 2: Copy Macros to Your Own Document



% Lemma, Proposition, Corollary (blue boxes)Place the following macro definitions in your `.tex` file's preamble (after `\documentclass`, before `\begin{document}`):

\begin{lemma}{Auxiliary Result}{aux}...

\begin{proposition}{Main Claim}{claim}...```latex

\begin{corollary}{Direct Consequence}{consequence}...% Scalar: italic

```\newcommand{\scalar}[1]{\mathit{#1}}



### Plain Environments (backward compatible)% Vector: bold + single underline

\newcommand{\vect}[1]{\mathbf{\underline{#1}}}

For simple amsthm-style boxes (no fancy colors), use the standard syntax:

% Matrix: bold + double underline

```latex\newcommand{\matr}[1]{\mathbf{\underline{\underline{#1}}}}

% Example (plain style)

\begin{example}[Optional Title]% Tensor (order >= 3): bold calligraphic

  Let $\mat{A} = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}$.\newcommand{\tensor}[1]{\boldsymbol{\mathcal{#1}}}

\end{example}```



% Remark (plain style)**Usage in equations:**

\begin{remark}[Note about convergence]```latex

  The series converges for all $x \in [0,1]$.\mat{A}\vec{x} = \vec{b}

\end{remark}```



% Definition (plain style - also available)### Option 3: Overleaf Integration

\begin{definition}[Vector]

  A vector is an element of a vector space.1. Create a new blank project or open an existing one

\end{definition}2. Copy the macro definitions from `main.tex` to your preamble

```3. Start writing equations using `\vec{v}`, `\mat{A}`, etc.

4. Or upload the entire `main.tex` file as a starting template

### Utility Boxes (non-numbered)

### Makefile Commands

```latex

% Warning box (red)| Command | Description |

\begin{warningbox}|---------|-------------|

  This operation may fail for singular matrices!| `make` or `make all` | Full build with two passes (default) |

\end{warningbox}| `make quick` | Fast single-pass compilation |

| `make pdf` | Full build with references |

% Tip box (orange, numbered)| `make bib` | Build with BibTeX support |

\begin{tipbox}{Performance Tip}{perf1}| `make view` | Compile and open PDF viewer |

  Use sparse matrices for better performance.| `make watch` | Auto-recompile on file changes |

\end{tipbox}| `make clean` | Remove build artifacts |

| `make distclean` | Remove all generated files |

% Answer box (blue, for homework)| `make check` | Verify LaTeX installation |

\begin{answerbox}| `make help` | Show help message |

  The solution is $x = 42$.

\end{answerbox}### Journal Submission Checklist



% Solution box (green, with title)- **Before submission:** Check if your target journal permits or discourages underlined symbols

\begin{solutionbox}- Some publishers prefer bold-only for vectors. If needed, redefine:

  Step 1: Factor the equation...  ```latex

\end{solutionbox}  \renewcommand{\vect}[1]{\mathbf{#1}}

  \renewcommand{\matr}[1]{\mathbf{#1}}

% Important box (orange)  ```

\begin{importantbox}- Search-and-replace is straightforward since all notation uses macros

  Remember to check the boundary conditions!

\end{importantbox}---

```

## Best Practices

---

1. **Apply macros uniformly:** Don't mix `\mathbf{v}` and `\vec{v}` in the same document.

## Advanced Features2. **Index notation clarity:** For tensors of order ≥3, consider explicit indices (e.g., $C_{ijkl}$) if your audience is more familiar with that style.

3. **Unit vectors:** Use `\hat{\vec{e}}_i` or `\hat{\vec{n}}` to denote normalized direction vectors.

### Glossary and Acronyms4. **Operators in roman:** Always use `\det`, `\operatorname{tr}`, `\operatorname{rank}`, `\nabla` (upright) to distinguish them from variables.

5. **Color for emphasis (optional):** In presentations or lecture notes, you may combine underlining with color (e.g., `\textcolor{blue}{\vec{v}}`), but avoid this in print journals.

Add entries in `config/glossary.tex`:6. **Compatibility with math fonts:** The underlining works with most standard LaTeX fonts (Computer Modern, Latin Modern, etc.). Test with your chosen font package.

7. **Avoid amsmath conflicts:** We use `\vect` and `\matr` instead of `\vector` and `\matrix` to prevent conflicts with the `amsmath` package.

```latex

% Glossary entry---

\newglossaryentry{bandwidth}{

  name=bandwidth,## Contributing

  description={The range of frequencies over which a system operates}

}Contributions are welcome! If you have suggestions for additional macros, alternative notation styles, or improved examples:



% Acronym1. Fork this repository (or copy this template to your own repo).

\newacronym{fft}{FFT}{Fast Fourier Transform}2. Make your changes in a new branch.

```3. Submit a pull request with a clear description of the enhancement.



Use in your document:**Feedback:** Open an issue to discuss notation conventions, request new examples, or report rendering problems with specific LaTeX distributions.



```latex---

The \gls{bandwidth} determines the \gls{fft} resolution.

% First use: "bandwidth ... Fast Fourier Transform (FFT)"## License

% Later: "bandwidth ... FFT"

```This template is provided under the **MIT License** (or adapt to your preferred open-source license). You are free to use, modify, and distribute this template in your academic and commercial work. Attribution is appreciated but not required.



To print the glossary (add to your document):**Quick Reference:**



```latex| Type | Macro | Rendering |

\printglossary[type=\acronymtype, title=Acronyms]|------|-------|-----------|

\printglossary| Scalar | `\scalar{a}` | $\mathit{a}$ |

```| Vector | `\vec{v}` | **$\underline{\mathbf{v}}$** |

| Matrix | `\mat{A}` | **$\underline{\underline{\mathbf{A}}}$** |

### Bibliography| Tensor | `\tensor{T}` | $\boldsymbol{\mathcal{T}}$ |



Add entries in `references.bib`:**Suggested citation:**

> Maharebi, M. M. (2025). Physical-Style Mathematical Notation for LaTeX. GitHub: @mmaharebi

```bibtex

@article{einstein1905,---

  author = {Einstein, Albert},

  title = {On the Electrodynamics of Moving Bodies},## Acknowledgments

  journal = {Annalen der Physik},

  year = {1905},This notation system draws inspiration from classical physics and engineering textbooks that use typographic distinctions to clarify tensor order. Special thanks to the LaTeX community for maintaining robust typesetting tools that make such conventions feasible.

  volume = {17},

  pages = {891--921}---

}

```**Last updated:** October 2025  

**Maintained by:** Mohammadmahdi Maharebi  

Cite in your document:**Contact:** mmaharebi@gmail.com | GitHub: @mmaharebi

```latex
As shown by \cite{einstein1905}, the speed of light is constant.
```

### SI Units (siunitx package)

```latex
The speed is \SI{3e8}{\meter\per\second}.
The temperature is \SI{273.15}{\kelvin}.
The range is \SIrange{10}{20}{\micro\meter}.
```

### Custom Lists (enumitem package)

```latex
\begin{itemize}[label=→, itemsep=0pt]
  \item First item
  \item Second item
\end{itemize}

\begin{enumerate}[label=(\alph*), leftmargin=2cm]
  \item First step
  \item Second step
\end{enumerate}
```

---

## Compilation

### Using Makefile (Recommended)

```bash
make pdf          # Compile PDF (2 passes for references)
make clean        # Remove build artifacts
make cleanall     # Remove all generated files including PDF
```

### Manual Compilation

```bash
pdflatex main.tex
pdflatex main.tex    # Second pass for cross-references
```

### With Bibliography

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

### With Glossary

```bash
pdflatex main.tex
makeglossaries main
pdflatex main.tex
```

---

## Customization

### Change Notation Style

Edit `config/macros.tex`:

```latex
% Current: Bold + underline for vectors
\newcommand{\vect}[1]{\mathbf{\underline{#1}}}

% Alternative: Just bold
\renewcommand{\vect}[1]{\mathbf{#1}}

% Alternative: Bold with arrow
\renewcommand{\vect}[1]{\vec{\mathbf{#1}}}
```

### Add New Theorem Types

Edit `config/theorems.tex`:

```latex
% Add custom colored box
\newtcbtheorem[use counter from=theorem]{axiom}{Axiom}{
  colback=cyan!5,
  colframe=cyan!75!black,
  fonttitle=\bfseries,
  boxrule=0.5pt,
  arc=2pt
}{ax}
```

### Adjust Page Layout

Edit `config/packages.tex`:

```latex
\geometry{
  margin=1in,        % Change margins
  top=1.25in,       % Custom top margin
  bottom=1.25in     % Custom bottom margin
}
```

### Change Color Scheme

Edit `config/packages.tex`:

```latex
\definecolor{vectorcolor}{RGB}{200,50,50}     % Darker red
\definecolor{forcecolor}{RGB}{50,150,50}      % Darker green
```

---

## Examples

The template includes comprehensive examples in `sections/`:

- **Basic Notation** - Introduction to the notation system
- **Linear Algebra** - Matrices, eigenvalues, least squares
- **Physics** - Kinematics, dynamics, electromagnetic fields
- **Engineering** - Waveguides, TE modes, metasurfaces  
- **Quantum Mechanics** - Bra-ket notation, operators, commutators
- **Advanced Topics** - Bridging notations, operator theory

**To start fresh:**
1. Delete content from `sections/*.tex` files
2. Keep the structure and replace with your content
3. Or create new section files and include them in `main.tex`

---

## Citation

If you use this template in your work, please cite:

```bibtex
@misc{maharebi2025notation,
  author = {Maharebi, Mohammadmahdi},
  title = {Physical-Style Mathematical Notation: A LaTeX Template},
  year = {2025},
  publisher = {GitHub},
  howpublished = {\url{https://github.com/mmaharebi/latex-notation-template}}
}
```

---

## License

This template is provided as-is for educational and research purposes. Feel free to modify and redistribute with attribution.

---

## Support

For questions, issues, or suggestions:
- Open an issue on GitHub
- Email: mmaharebi@gmail.com

**Happy writing! 📝✨**
