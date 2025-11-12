# Physical-Style Mathematical Notation for LaTeX# Physical-Style Mathematical Notation Template# Physical-Style Mathematical Notation for LaTeX



A reusable LaTeX template providing consistent, physics-inspired typographic conventions for scalars, vectors, matrices, and tensors in scientific manuscripts and technical reports.



---A comprehensive, production-ready LaTeX template for technical documents requiring clear and consistent mathematical notation. Ideal for physics, engineering, mathematics, and scientific writing.A reusable LaTeX template providing consistent, physics-inspired typographic conventions for scalars, vectors, matrices, and tensors in scientific manuscripts and technical reports.



## Table of Contents



- [Purpose](#purpose)## Author---

- [Motivation](#motivation)

- [Quick Start](#quick-start)

- [LaTeX Macros](#latex-macros)

- [Notation Conventions](#notation-conventions)**Mohammadmahdi Maharebi**## Table of Contents

- [Symbol Reference Table](#symbol-reference-table)

- [Usage Examples](#usage-examples)- Email: mmaharebi@gmail.com

- [Project Structure](#project-structure)

- [How to Use This Template](#how-to-use-this-template)- GitHub: @mmaharebi- [Purpose](#purpose)

- [Compilation](#compilation)

- [Best Practices](#best-practices)- [Motivation](#motivation)

- [Contributing](#contributing)

- [License](#license)---- [LaTeX Macros](#latex-macros)



---- [Notation Conventions](#notation-conventions)



## Purpose## 📋 Table of Contents- [Symbol Reference Table](#symbol-reference-table)



This template establishes a **unified typographic system** for mathematical objects commonly used in physics, engineering, and applied mathematics. By adopting visual distinctions based on tensor order (scalars, vectors, matrices, higher-order tensors), readers can immediately identify the nature of each quantity, reducing ambiguity and cognitive load.- [Usage Examples](#usage-examples)



**Key features:**1. [Overview](#overview)- [How to Use This Template](#how-to-use-this-template)

- **Scalars** are italic (standard mathematical notation)

- **Vectors** are bold and single-underlined2. [Features](#features)- [Best Practices](#best-practices)

- **Matrices** are bold and double-underlined

- **Tensors (order ≥ 3)** use bold calligraphic or explicit index notation3. [Quick Start](#quick-start)- [Contributing](#contributing)



This convention is particularly valuable in disciplines where vectors and matrices appear frequently (e.g., mechanics, electromagnetism, quantum theory, robotics, machine learning).4. [Project Structure](#project-structure)- [License](#license)



---5. [Notation System](#notation-system)



## Motivation6. [Using Colored Theorem Boxes](#using-colored-theorem-boxes)---



### Why adopt a physical-style notation?7. [Advanced Features](#advanced-features)



1. **Visual clarity:** In equations mixing scalars, vectors, and matrices (e.g., $\mat{A}\vec{x} = \scalar{\lambda}\vec{x}$), each object's type is instantly recognizable.8. [Compilation](#compilation)## Purpose



2. **Consistency across documents:** Using predefined macros ensures uniform appearance throughout long manuscripts or multi-author projects.9. [Customization](#customization)



3. **Flexibility:** Changing the entire notation style (e.g., switching from underlines to bold-only) requires modifying only a few lines in `config/macros.tex`.10. [Examples](#examples)This template establishes a **unified typographic system** for mathematical objects commonly used in physics, engineering, and applied mathematics. By adopting visual distinctions based on tensor order (scalars, vectors, matrices, higher-order tensors), readers can immediately identify the nature of each quantity, reducing ambiguity and cognitive load.



4. **Professional quality:** Clean separation of content and styling improves readability and aesthetics.



------**Key features:**



## Quick Start- **Scalars** are italic (standard mathematical notation)



### 1. Clone or Download## Overview- **Vectors** are bold and single-underlined



```bash- **Matrices** are bold and double-underlined

git clone https://github.com/mmaharebi/latex-notation-template.git

cd latex-notation-templateThis template implements a systematic physical-style notation system:- **Tensors (order ≥ 3)** use bold calligraphic or explicit index notation

```



### 2. Compile

| Type | Style | Command | Example |This convention is particularly valuable in disciplines where vectors and matrices appear frequently (e.g., mechanics, electromagnetism, quantum theory, robotics, machine learning).

```bash

make pdf          # Recommended|------|-------|---------|---------|

# OR

pdflatex main.tex| **Scalar** | Italic | `\scalar{x}` | *x* |---

pdflatex main.tex # Run twice for references

```| **Vector** | Bold + underline | `\vect{v}` | **v̲** |



### 3. Customize| **Matrix** | Bold + double underline | `\mat{A}` | **A̲̲** |## Motivation



- Edit `config/metadata.tex` - Set your name, title, PDF metadata| **Tensor** | Bold calligraphic | `\tensor{T}` | **𝓣** |

- Edit `config/glossary.tex` - Add your glossary entries and acronyms

- Edit `references.bib` - Add your bibliography entries### Why adopt a physical-style notation?

- Create your content in `chapters/` directory

- Add figures to `figures/` directory---



---1. **Visual clarity:** In equations mixing scalars, vectors, and matrices (e.g., $\matrix{A}\vector{x} = \scalar{\lambda}\vector{x}$), each object's type is instantly recognizable.



## LaTeX Macros## Features2. **Consistency across documents:** Using predefined macros ensures uniform rendering throughout multi-author projects or multi-document dissertations.



The core notation macros are defined in `config/macros.tex`:3. **Pedagogical value:** Students and reviewers benefit from explicit visual cues that distinguish a vector field $\vector{E}$ from a scalar energy $\scalar{E}$.



```latex### Core Features4. **Alignment with established practice:** Many physics and engineering textbooks employ similar conventions (bold for vectors, double-underline or hat for matrices).

% Scalar: italic (default math mode)

\newcommand{\scalar}[1]{\mathit{#1}}✅ **Consistent Notation System** - Clear visual distinction between mathematical objects  



% Vector: bold + single underline✅ **Colored Theorem Boxes** - Professional tcolorbox environments (theorem, definition, note, etc.)  ### When to use this template

\renewcommand{\vec}[1]{\underline{\bm{#1}}}

✅ **Glossary & Acronyms** - Built-in support with the `glossaries` package  

% Matrix: bold + double underline

\newcommand{\mat}[1]{\underline{\underline{\bm{#1}}}}✅ **TikZ Diagrams** - Enhanced figures with improved scales and styling  - Theses and dissertations in physics, mechanical/electrical engineering, applied math



% Tensor (order >= 3): bold calligraphic (optional)✅ **SI Units** - `siunitx` package for proper unit formatting  - Research papers in continuum mechanics, control theory, robotics, quantum information

\newcommand{\tensor}[1]{\boldsymbol{\mathcal{#1}}}

```✅ **Bibliography Support** - BibTeX ready with `references.bib`  - Technical reports requiring clear distinction between vector quantities and scalar parameters



**Note:** We use `\vec` and `\mat` as short, convenient command names. The template redefines the standard `\vec` command to match the physical-style notation.✅ **Modular Structure** - Organized config files for easy customization- Educational materials where pedagogical clarity is paramount



---



## Notation Conventions### Enhanced Math Commands---



| Type | Macro | Example | Rendering Convention |- **Derivatives**: `\pd{f}{x}`, `\pdd{f}{x}`, `\pdc{f}{x}{y}`, `\td{f}{x}`

|------|-------|---------|---------------------|

| **Scalar** | `\scalar{a}` | `\scalar{\alpha}`, `\scalar{E}` | Italic (single real or complex number) |- **Operators**: `\grad`, `\Div`, `\curl`, `\vnabla`, `\trace`, `\rank`## LaTeX Macros

| **Vector** | `\vec{v}` | `\vec{E}`, `\vec{F}`, `\vec{v}` | **Bold + single underline** (column vector) |

| **Matrix** | `\mat{A}` | `\mat{M}`, `\mat{K}` | **Bold + double underline** (2D array) |- **Utilities**: `\abs{x}`, `\norm{x}`, `\Prob{A}`, `\eqdef`

| **Tensor** | `\tensor{T}` | `\tensor{R}`, `\tensor{C}` | **Bold calligraphic** (order ≥ 3) |

- **Unit Vectors**: `\xhat`, `\yhat`, `\zhat`, `\rhohat`, `\phihat`, `\Rhat`, `\thetahat`Add the following macros to your LaTeX document preamble (before `\begin{document}`):

### Special Symbols

- **Vector Operations**: `\vdot`, `\vproj{a}{b}`, `\vang{a}{b}`

| Symbol | Macro | Usage | Notes |

|--------|-------|-------|-------|- **Quantum Notation**: `\ket{ψ}`, `\bra{ψ}`, `\braket{ψ}{φ}`, `\hop{H}`, `\comm{A}{B}````latex

| **Zero** | `\vec{0}`, `\mat{0}` | — | Underlined bold zero |

| **Unit vector** | `\uvec{n}` | `\uvec{x}`, `\uvec{r}` | Hat + bold underline |% Scalar: italic (default math mode, explicit wrapper for consistency)

| **Identity** | `\mat{I}_n` | — | Double-underlined bold I |

---\newcommand{\scalar}[1]{\mathit{#1}}

---



## Symbol Reference Table

## Quick Start% Vector: bold + single underline

### Scalar, Vector, Matrix, Tensor

\newcommand{\vect}[1]{\mathbf{\underline{#1}}}

| Macro | Description | Rendering | Usage |

|-------|-------------|-----------|-------|### 1. Clone or Download

| `\scalar{x}` | Scalar | italic, $\scalar{x}\in\mathbb{R}$ or $\mathbb{C}$ | Physical quantity, coordinate |

| `\vec{v}` | Vector | bold + underline, $\vec{v}\in\mathbb{R}^n$ | Position, velocity, force |```bash% Matrix: bold + double underline

| `\mat{A}` | Matrix | bold + double underline, $\mat{A}\in\mathbb{R}^{m\times n}$ | Linear map; entries $A_{ij}$ |

| `\vec{x}^\top` | Transpose | superscript $^\top$ | Row vector |git clone https://github.com/mmaharebi/latex-notation-template.git\newcommand{\matr}[1]{\mathbf{\underline{\underline{#1}}}}

| `\mat{A}^\top` | Transpose | superscript $^\top$ | Rows ↔ columns |

| `\vec{x}^*` | Conjugate | superscript $^*$ | Complex conjugate |cd latex-notation-template

| `\mat{A}^*` or `\mat{A}^\dagger` | Conjugate transpose | Hermitian conjugate | $(\mat{A}^*)_{ij}=\overline{A_{ji}}$ |

```% Tensor (order >= 3): bold calligraphic (optional)

### Common Constructs

\newcommand{\tensor}[1]{\boldsymbol{\mathcal{#1}}}

| Macro | Description | Size | Usage |

|-------|-------------|------|-------|### 2. Compile```

| `\mat{I}_n` | Identity matrix | $n\times n$ | $\mat{I}_n \vec{x} = \vec{x}$ |

| `\vzero` | Zero vector | $n\times 1$ | Additive identity |```bash

| `\vec{0}`, `\mat{0}` | Zero vector/matrix | | All entries zero |

| `\uvec{n}` | Unit vector | | Direction indicator, $\|\uvec{n}\|=1$ |make pdf          # Recommended**Note:** We use `\vect` and `\matr` instead of `\vector` and `\matrix` to avoid conflicts with the `amsmath` package. Some journals discourage underlining; check your target venue's style guide before submission.

| `\det(\mat{A})` | Determinant | scalar | Volume scaling factor |

| `\operatorname{tr}(\mat{A})` | Trace | scalar | Sum of diagonal entries |# OR

| `\operatorname{rank}(\mat{A})` | Rank | integer | Dimension of column space |

| $(\scalar{\lambda},\vec{x})$ | Eigenpair | $\mat{A}\vec{x}=\scalar{\lambda}\vec{x}$ | Eigenvalue $\scalar{\lambda}$, eigenvector $\vec{x}\neq\vec{0}$ |pdflatex main.tex---



---pdflatex main.tex # Run twice for references



## Usage Examples```## Notation Conventions



### Example 1: Linear System



```latex### 3. Customize| Type | Macro | Example | Rendering Convention |

\mat{A}\vec{x} = \vec{b},

```- Edit `config/metadata.tex` - Set your name, title, PDF metadata|------|-------|---------|---------------------|



where $\mat{A}\in\mathbb{R}^{n\times n}$ is a square matrix, - Edit `config/glossary.tex` - Add your glossary entries and acronyms| **Scalar** | `\scalar{a}` | `\scalar{\alpha}`, `\scalar{E}` | Italic (single real or complex number) |

$\vec{x}\in\mathbb{R}^n$ is the unknown vector, 

and $\vec{b}\in\mathbb{R}^n$ is the right-hand side.- Edit `references.bib` - Add your bibliography entries| **Vector** | `\vect{v}` | `\vect{E}`, `\vect{F}`, `\vect{v}` | **Bold + single underline** (column vector) |



### Example 2: Eigenvalue Problem- Modify `sections/` - Replace example content with your own| **Matrix** | `\mat{A}` | `\mat{M}`, `\mat{K}` | **Bold + double underline** (2D array) |



```latex| **Tensor (≥3)** | `\tensor{T}` | `\tensor{C}`, or $C_{ijkl}$ | **Bold calligraphic** or explicit indices |

\mat{A}\vec{v} = \scalar{\lambda}\vec{v}

```---| **Unit vector** | `\hat{\vect{e}}_i` | `\hat{\vect{x}}` | Hat over underlined bold vector |



### Example 3: Vector Calculus| **Zero** | `\vect{0}`, `\mat{0}` | — | Underlined bold zero |



```latex## Project Structure| **Identity** | `\mat{I}_n` | — | Double-underlined bold I |

\vec{F} = q\vec{E} + q\vec{v} \times \vec{B}

```



### Example 4: Maxwell's Equations```**Operators and special functions** (det, tr, rank, div, grad, etc.) should be typeset in upright roman using `\det`, `\operatorname{tr}`, `\nabla`, etc.



```latex.

\begin{align}

  \vnabla \cdot \vec{E} &= \frac{\rho}{\epsilon_0} \\├── main.tex                    # Main document file---

  \vnabla \times \vec{E} &= -\pd{\vec{B}}{t} \\

  \vnabla \cdot \vec{B} &= 0 \\├── references.bib              # Bibliography database

  \vnabla \times \vec{B} &= \mu_0\vec{J} + \mu_0\epsilon_0\pd{\vec{E}}{t}

\end{align}├── Makefile                    # Build automation## Symbol Reference Table

```

│

---

├── config/                     # Configuration files| Symbol | Name | Notation | Description / Example |

## Project Structure

│   ├── packages.tex           # Package imports|--------|------|----------|----------------------|

```

.│   ├── macros.tex             # Custom notation macros| `\scalar{a}` | Scalar | italic, $\scalar{a}\in\mathbb{R}$ | Single numeric value |

├── LICENSE                    # MIT License

├── Makefile                   # Build automation│   ├── theorems.tex           # Theorem environments| `\vect{v}` | Vector | bold + underline, $\vect{v}\in\mathbb{R}^n$ | Column vector, e.g. $\vect{v}=[v_1,\dots,v_n]^\top$ |

├── README.md                  # This file

├── main.tex                   # Main document│   ├── metadata.tex           # Author, title, PDF metadata| `\mat{A}` | Matrix | bold + double underline, $\mat{A}\in\mathbb{R}^{m\times n}$ | Linear map; entries $A_{ij}$ |

├── references.bib             # Bibliography database

├── .gitignore                 # Git ignore rules│   └── glossary.tex           # Glossary and acronym definitions| `\mat{A}^\top` | Transpose | superscript $^\top$ | Rows ↔ columns |

│

├── config/│| `\mat{A}^*` or `\mat{A}^\dagger` | Conjugate transpose | Hermitian conjugate | $(\mat{A}^*)_{ij}=\overline{A_{ji}}$ |

│   ├── packages.tex           # LaTeX package imports

│   ├── macros.tex             # Custom mathematical notation macros├── sections/                   # Content sections (modify these)| `\langle\vect{u},\vect{v}\rangle` | Inner product | angle brackets | $\langle\vect{u},\vect{v}\rangle=\vect{u}^\top\vect{v}$ (real) |

│   ├── theorems.tex           # Theorem environment definitions

│   ├── metadata.tex           # Author, title, PDF metadata│   ├── introduction.tex| `\|\vect{v}\|` | Norm | double bars | Euclidean norm $\|\vect{v}\|_2=\sqrt{\langle\vect{v},\vect{v}\rangle}$ |

│   └── glossary.tex           # Glossary and acronym definitions

││   ├── basic_notation.tex| `\vect{u}\otimes\vect{v}` | Tensor product | $\otimes$ | Rank-1 tensor / outer product |

├── chapters/

│   ├── 01_notation_system.tex        # Notation examples│   ├── linear_algebra.tex| `\vect{u}\vect{v}^\top` | Outer product | vector × transpose | Matrix with entries $u_i v_j$ |

│   ├── 02_math_commands.tex          # Mathematical macros

│   ├── 03_theorem_boxes.tex          # Colored theorem boxes│   ├── physics.tex| `\mat{I}_n` | Identity matrix | $n\times n$ | $\mat{I}_n \vect{x} = \vect{x}$ |

│   ├── 04_advanced_features.tex      # Glossary, SI units, quantum

│   └── 05_complete_example.tex       # Full EM wave problem│   ├── engineering.tex| `\vect{0}`, `\mat{0}` | Zero vector/matrix | | All entries zero |

│

├── figures/                   # Your figures go here│   ├── quantum_mechanics.tex| `\det(\mat{A})` | Determinant | scalar | Volume scaling factor |

│

└── build/                     # Compiled outputs (generated)│   ├── applications.tex| `\operatorname{tr}(\mat{A})` | Trace | scalar | Sum of diagonal entries |

    ├── main.pdf               # Final PDF

    └── *.aux, *.log, etc.     # Build artifacts│   ├── conclusion.tex| `\operatorname{rank}(\mat{A})` | Rank | integer | Dimension of column space |

```

│   └── appendix.tex| $(\scalar{\lambda},\vect{x})$ | Eigenpair | $\mat{A}\vect{x}=\scalar{\lambda}\vect{x}$ | Eigenvalue $\scalar{\lambda}$, eigenvector $\vect{x}\neq\vect{0}$ |

---

│| $\{\vect{e}_i\}$ | Canonical basis | standard basis | $\vect{e}_i$ has 1 at position $i$, 0 elsewhere |

## How to Use This Template

├── figures/                    # TikZ diagrams

### Step 1: Set Metadata

│   ├── least_squares_projection.tex---

Edit `config/metadata.tex`:

│   ├── rigid_body.tex

```latex

\newcommand{\doctitle}{[Your Document Title]}│   ├── waveguide_geometry.tex## Usage Examples

\newcommand{\docauthor}{[Your Name]}

\newcommand{\docemail}{[your.email@example.com]}│   ├── te10_mode.tex

\newcommand{\docdate}{\today}

```│   └── metasurface_reflection.tex### Example 1: Linear system



### Step 2: Write Content│```latex



Create your chapters in the `chapters/` directory. Each chapter is a separate `.tex` file that will be included in `main.tex`.└── build/                      # Compiled output (auto-generated)Consider the linear system



### Step 3: Add References```\[



Edit `references.bib` to add your bibliography entries:  \mat{A}\vect{x} = \vect{b},



```bibtex---\]

@article{einstein1905,

  author = {Einstein, Albert},where $\mat{A}\in\mathbb{R}^{n\times n}$ is a square matrix, 

  title = {On the electrodynamics of moving bodies},

  journal = {Annalen der Physik},## Notation System$\vect{x}\in\mathbb{R}^n$ is the unknown vector, 

  year = {1905},

  volume = {322},and $\vect{b}\in\mathbb{R}^n$ is the right-hand side.

  number = {10},

  pages = {891--921}### Basic Usage```

}

```



### Step 4: Compile```latex### Example 2: Eigenvalue problem



```bash% Scalars (italic by default)```latex

make pdf          # Recommended (handles multiple passes)

# ORLet $\scalar{x} = 5$ and $\scalar{y} = 3$.The eigenvalue problem for $\mat{A}$ is

make rebuild      # Clean and rebuild from scratch

```\[



---% Vectors (bold + underline)  \mat{A}\vect{x} = \scalar{\lambda}\vect{x},



## CompilationThe velocity vector is $\vect{v} = \vect{v}_0 + \vect{a}t$.\]



### Using the Makefilewhere $\scalar{\lambda}\in\mathbb{C}$ is the eigenvalue 



```bash% Matrices (bold + double underline)and $\vect{x}\neq\vect{0}$ is the corresponding eigenvector.

make pdf          # Compile the document

make clean        # Remove build artifactsThe transformation matrix $\mat{A}$ satisfies $\mat{A}\vect{x} = \vect{b}$.```

make rebuild      # Clean and rebuild from scratch

make view         # Open the PDF (platform-dependent)

```

% Tensors (bold calligraphic)### Example 3: Physics (Newton's second law)

The Makefile handles:

- 3-pass compilation for cross-referencesThe stress tensor $\tensor{σ}$ relates stress to strain.```latex

- Glossary generation with `makeglossaries`

- Error logging to `build/build.log````Newton's second law in vector form:

- Concise terminal output

\[

### Manual Compilation

### Common Patterns  \vect{F} = \scalar{m}\vect{a},

```bash

pdflatex -output-directory=build main.tex\]

makeglossaries -d build main

pdflatex -output-directory=build main.tex```latexwhere $\vect{F}$ is the net force, $\scalar{m}$ is the scalar mass, 

pdflatex -output-directory=build main.tex

```% Unit vectorsand $\vect{a}$ is the acceleration vector.



---$\xhat, \yhat, \zhat$                    % Cartesian```



## Best Practices$\rhohat, \phihat, \zhat$               % Cylindrical  



### 1. Notation Consistency$\Rhat, \thetahat, \phihat$             % Spherical### Example 4: Inline text



- Use `\scalar{...}` for all scalar variables```latex

- Use `\vec{...}` for all vectors

- Use `\mat{...}` for all matrices% Vector operationsThe electric field $\vect{E}$ at position $\vect{r}$ 

- Use `\tensor{...}` for tensors of order ≥ 3

$\vect{a} \vdot \vect{b}$               % Dot productis computed from the potential $\scalar{\phi}$ as 

### 2. Physical Units

$\vproj{a}{b}$                          % Projection of b onto a$\vect{E} = -\nabla\scalar{\phi}$.

Use the `siunitx` package for physical quantities:

$\vang{a}{b}$                           % Angle between vectors```

```latex

\SI{3e8}{\meter\per\second}     % Speed of light

\SI{9.8}{\meter\per\second\squared}  % Gravitational acceleration

```% Derivatives---



### 3. Theorem Environments$\pd{f}{x}$                             % ∂f/∂x



Use the predefined colored boxes:$\pdd{f}{x}$                            % ∂²f/∂x²## How to Use This Template



```latex$\pdc{f}{x}{y}$                         % ∂²f/∂x∂y

\begin{theorem}[Pythagorean Theorem]

  In a right triangle, $a^2 + b^2 = c^2$.$\td{s}{t}$                             % ds/dt### Option 1: Use the Complete LaTeX Template

\end{theorem}



\begin{definition}[Vector Space]

  A set $V$ with addition and scalar multiplication...% OperatorsThis repository includes a ready-to-use LaTeX template with comprehensive examples:

\end{definition}

```$\vnabla \times \vect{E}$               % Curl



### 4. Code Organization$\vnabla \cdot \vect{B}$                % Divergence**Files included:**



- Keep macros in `config/macros.tex`$\grad f$, $\Div \vect{F}$, $\curl \vect{A}$- `main.tex` - Complete LaTeX document with examples from physics, linear algebra, engineering

- Keep content in separate chapter files

- Use meaningful label names (e.g., `\label{eq:maxwell_faraday}`)```- `Makefile` - Build automation with multiple targets



---- `.gitignore` - Excludes LaTeX build artifacts



## Contributing---



Contributions are welcome! Please:**Quick start:**



1. Fork the repository## Using Colored Theorem Boxes```bash

2. Create a feature branch (`git checkout -b feature/your-feature`)

3. Make your changes# Clone or download this repository

4. Test compilation

5. Submit a pull request### Numbered Environments (tcolorbox style)cd report



---



## LicenseFor fancy colored boxes with numbering, use the tcolorbox syntax:# Compile the template



This template is released under the [MIT License](LICENSE).make pdf



**Copyright (c) 2025 Mohammadmahdi Maharebi**```latex



Permission is hereby granted, free of charge, to any person obtaining a copy of this template to use, modify, and distribute it for any purpose, including commercial projects, subject to the terms of the MIT License.% Theorem (blue box)# Or compile and view



---\begin{theorem}{Pythagorean Theorem}{pythag}make view



## Author  In a right triangle, $a^2 + b^2 = c^2$.



**Mohammadmahdi Maharebi**\end{theorem}# For quick single-pass compilation

- Email: mmaharebi@gmail.com

- GitHub: [@mmaharebi](https://github.com/mmaharebi)make quick



---% Definition (green box)



## Acknowledgments\begin{definition}{Vector Space}{vecspace}# Clean build artifacts



This template was designed to support clear mathematical communication in physics, engineering, and applied mathematics. It incorporates best practices from scientific typesetting and modern LaTeX workflows.  A vector space is a set $V$ with addition and scalar multiplication...make clean



---\end{definition}



**Happy LaTeXing! 📝**# See all available commands


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

  The series converges for all $x \in [0,1]$.\mat{A}\vect{x} = \vect{b}

\end{remark}```



% Definition (plain style - also available)### Option 3: Overleaf Integration

\begin{definition}[Vector]

  A vector is an element of a vector space.1. Create a new blank project or open an existing one

\end{definition}2. Copy the macro definitions from `main.tex` to your preamble

```3. Start writing equations using `\vect{v}`, `\mat{A}`, etc.

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

1. **Apply macros uniformly:** Don't mix `\mathbf{v}` and `\vect{v}` in the same document.

## Advanced Features2. **Index notation clarity:** For tensors of order ≥3, consider explicit indices (e.g., $C_{ijkl}$) if your audience is more familiar with that style.

3. **Unit vectors:** Use `\hat{\vect{e}}_i` or `\hat{\vect{n}}` to denote normalized direction vectors.

### Glossary and Acronyms4. **Operators in roman:** Always use `\det`, `\operatorname{tr}`, `\operatorname{rank}`, `\nabla` (upright) to distinguish them from variables.

5. **Color for emphasis (optional):** In presentations or lecture notes, you may combine underlining with color (e.g., `\textcolor{blue}{\vect{v}}`), but avoid this in print journals.

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

```| Vector | `\vect{v}` | **$\underline{\mathbf{v}}$** |

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
