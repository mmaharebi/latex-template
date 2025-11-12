# Physical-Style Mathematical Notation for LaTeX

A reusable LaTeX template that enforces consistent, physics-inspired notation for scalars, vectors, matrices, and tensors in scientific manuscripts and technical reports.

## Table of Contents

- [Purpose](#purpose)
- [Motivation](#motivation)
- [Quick Start](#quick-start)
- [LaTeX Macros](#latex-macros)
- [Notation Conventions](#notation-conventions)
- [Symbol Reference Table](#symbol-reference-table)
- [Usage Examples](#usage-examples)
- [Project Structure](#project-structure)
- [How to Use This Template](#how-to-use-this-template)
- [Compilation](#compilation)
- [Best Practices](#best-practices)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

---

## Purpose

This template establishes a **unified typographic system** for mathematical objects used in physics, engineering, and applied mathematics. By visually distinguishing scalars, vectors, matrices, and higher-order tensors, readers can immediately identify the nature of each quantity, reducing ambiguity and cognitive load.

**Key features**

- **Scalars**: italic  
- **Vectors**: bold + single underline  
- **Matrices**: bold + double underline  
- **Tensors (order $\geq 3$)**: bold calligraphic (or explicit index notation)

---

## Motivation

**Why adopt a physical-style notation?**

1. **Visual clarity** – In mixed equations (e.g., `\mat{A}\vec{x}=\scalar{\lambda}\vec{x}`), each object’s type is instantly recognizable.  
2. **Consistency** – Macros ensure uniform rendering across long or multi-author documents.  
3. **Flexibility** – Global style changes require editing only a few lines in `config/macros.tex`.  
4. **Professional quality** – Clean separation of content and styling improves readability.

---

## Quick Start

### 1) Clone

```bash
git clone https://github.com/mmaharebi/latex-scientific-template.git
cd latex-scientific-template
```

### 2) Compile

```bash
make pdf          # Recommended (handles 3-pass compilation + glossaries)
# OR
pdflatex main.tex
pdflatex main.tex # Run twice for references
```

### 3) Customize

- Edit `config/metadata.tex` – Set title, author, date, email
- Edit `config/glossary.tex` – Add glossary entries and acronyms  
- Edit `references.bib` – Add bibliography entries  
- Create content in `sections/` directory  
- Add figures to `figures/` directory

---

## LaTeX Macros

The core notation macros are defined in `config/macros.tex`:

```latex
% Scalar: italic (default)
\newcommand{\scalar}[1]{\mathit{#1}}

% Vector: bold + single underline
\renewcommand{\vec}[1]{\underline{\bm{#1}}}

% Matrix: bold + double underline
\newcommand{\mat}[1]{\underline{\underline{\bm{#1}}}}

% Tensor (order $\geq$ 3): bold calligraphic
\newcommand{\tensor}[1]{\boldsymbol{\mathcal{#1}}}
```

**Note:** The template redefines `\vec` to match the physical-style notation. Use `\mat` (not `\matrix`) to avoid conflicts with `amsmath`.

---

## Notation Conventions

| Type       | Macro         | Example                      | Style                       |
|------------|---------------|------------------------------|-----------------------------|
| Scalar     | `\scalar{a}`  | `\scalar{\alpha}`, `\scalar{E}` | Italic                     |
| Vector     | `\vec{v}`     | `\vec{E}`, `\vec{F}`         | Bold + single underline    |
| Matrix     | `\mat{A}`     | `\mat{M}`, `\mat{K}`         | Bold + double underline    |
| Tensor     | `\tensor{T}`  | `\tensor{R}`, `\tensor{C}`   | Bold calligraphic          |

### Special Symbols

| Symbol          | Macro                  | Description              |
|-----------------|------------------------|--------------------------|
| Zero vector/matrix | `\vec{0}`, `\mat{0}` | Underlined bold zero    |
| Unit vector     | `\uvec{n}`            | Hat + bold underline     |
| Identity matrix | `\mat{I}_n`           | Double-underlined bold I |

---

## Symbol Reference Table

### Common Operations

| Macro                  | Description          | Usage                                  |
|------------------------|----------------------|----------------------------------------|
| `\vec{x}^\top`         | Transpose            | Row vector                             |
| `\mat{A}^\top`         | Transpose            | Rows $\leftrightarrow$ columns         |
| `\vec{x}^*`            | Conjugate            | Complex conjugate                      |
| `\mat{A}^\dagger`      | Hermitian conjugate  | $(\mathbf{A}^\dagger)_{ij} = \overline{A_{ji}}$ |
| `\det(\mat{A})`        | Determinant          | Scalar                                 |
| `\trace(\mat{A})`      | Trace                | Sum of diagonal entries                |
| `\rank(\mat{A})`       | Rank                 | Dimension of column space              |

### Vector Calculus Operators

```latex
\vnabla           % Bold nabla: ∇
\grad             % Gradient: ∇
\Div              % Divergence: ∇·
\curl             % Curl: ∇×
```

---

## Usage Examples

### Example 1: Linear System

```latex
\mat{A}\vec{x} = \vec{b}
```

where $\underline{\underline{\bm{A}}}\in \mathbb{R}^{n\times n}$ is a square matrix, $\underline{\bm{x}}\in \mathbb{R}^{n}$ is the unknown vector, and $\underline{\bm{b}}\in \mathbb{R}^{n}$ is the right-hand side.

### Example 2: Eigenvalue Problem

```latex
\mat{A}\vec{v} = \scalar{\lambda}\vec{v}
```

where $\lambda$ is the eigenvalue and $\underline{\bm{v}}$ is the corresponding eigenvector.

### Example 3: Lorentz Force

```latex
\vec{F} = q\vec{E} + q\vec{v} \times \vec{B}
```

where $q$ is the charge, $\underline{\bm{E}}$ is the electric field, $\underline{\bm{v}}$ is velocity, and $\underline{\bm{B}}$ is the magnetic field.

### Example 4: Maxwell's Equations

```latex
\begin{align}
  \vnabla \cdot \vec{E} &= \frac{\rho}{\epsilon_0} \\
  \vnabla \times \vec{E} &= -\pd{\vec{B}}{t} \\
  \vnabla \cdot \vec{B} &= 0 \\
  \vnabla \times \vec{B} &= \mu_0\vec{J} + \mu_0\epsilon_0\pd{\vec{E}}{t}
\end{align}
```

---

## Project Structure

```
.
├── LICENSE                    # MIT License
├── Makefile                   # Build automation
├── README.md                  # This file
├── main.tex                   # Main document
├── references.bib             # Bibliography database
├── .gitignore                 # Git ignore rules
│
├── config/
│   ├── packages.tex           # LaTeX package imports
│   ├── macros.tex             # Custom notation macros
│   ├── theorems.tex           # Colored theorem environments
│   ├── metadata.tex           # Author, title, PDF metadata
│   └── glossary.tex           # Glossary and acronym definitions
│
├── sections/
│   ├── 01_notation_system.tex      # Notation examples
│   ├── 02_math_commands.tex        # Mathematical macros
│   ├── 03_theorem_boxes.tex        # Colored theorem boxes
│   ├── 04_advanced_features.tex    # Glossary, SI units, quantum
│   └── 05_complete_example.tex     # Full EM wave problem
│
├── figures/                   # Your figures go here
│
└── build/                     # Compiled outputs (auto-generated)
    ├── main.pdf               # Final PDF
    └── *.aux, *.log, etc.     # Build artifacts
```

---

## How to Use This Template

### Step 1: Set Metadata

Edit `config/metadata.tex`:

```latex
\newcommand{\doctitle}{[Your Document Title]}
\newcommand{\docauthor}{[Your Name]}
\newcommand{\docemail}{[your.email@example.com]}
\newcommand{\docdate}{\today}
```

### Step 2: Write Content

Create your sections in the `sections/` directory. Each section is a separate `.tex` file included in `main.tex`:

```latex
\input{sections/01_introduction}
\input{sections/02_methodology}
\input{sections/03_results}
```

### Step 3: Add References

Edit `references.bib`:

```bibtex
@article{einstein1905,
  author  = {Einstein, Albert},
  title   = {On the electrodynamics of moving bodies},
  journal = {Annalen der Physik},
  year    = {1905},
  volume  = {322},
  number  = {10},
  pages   = {891--921}
}
```

### Step 4: Compile

```bash
make pdf          # Recommended
# OR
make rebuild      # Clean and rebuild from scratch
```

---

## Compilation

### Using the Makefile

```bash
make pdf          # Compile the document
make clean        # Remove build artifacts
make rebuild      # Clean and rebuild from scratch
make view         # Open the PDF (platform-dependent)
```

**Features:**
- 3-pass compilation for cross-references
- Glossary generation with `makeglossaries`
- Error logging to `build/build.log`
- Concise terminal output

### Manual Compilation

```bash
pdflatex -output-directory=build main.tex
makeglossaries -d build main
pdflatex -output-directory=build main.tex
pdflatex -output-directory=build main.tex
```

---

## Best Practices

### 1. Notation Consistency

- Use `\scalar{...}` for all scalar variables
- Use `\vec{...}` for all vectors  
- Use `\mat{...}` for all matrices  
- Use `\tensor{...}` for tensors of order ≥ 3

### 2. Physical Units

Use the `siunitx` package for physical quantities:

```latex
\SI{3e8}{\meter\per\second}              % Speed of light
\SI{9.8}{\meter\per\second\squared}      % Gravitational acceleration
\SI{1.602e-19}{\coulomb}                  % Elementary charge
```

### 3. Theorem Environments

Use the predefined colored boxes:

```latex
\begin{theorem}[Pythagorean Theorem]
  In a right triangle, $a^2 + b^2 = c^2$.
\end{theorem}

\begin{definition}[Vector Space]
  A set $V$ with addition and scalar multiplication...
\end{definition}
```

### 4. Code Organization

- Keep all macros in `config/macros.tex`
- Keep content in separate section files
- Use meaningful label names (e.g., `\label{eq:maxwell_faraday}`)
- Add comments to explain complex derivations

---

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Make your changes
4. Test compilation (`make rebuild`)
5. Submit a pull request

---

## License

This template is released under the [MIT License](LICENSE).

**Copyright © 2025 Mohammadmahdi Maharebi**

Permission is hereby granted, free of charge, to any person obtaining a copy of this template to use, modify, and distribute it for any purpose, including commercial projects, subject to the terms of the MIT License.

---

## Author

**Mohammadmahdi Maharebi**
- Email: mmaharebi@gmail.com
- GitHub: [@mmaharebi](https://github.com/mmaharebi)

---

## Acknowledgments

This template was designed to support clear mathematical communication in physics, engineering, and applied mathematics. It incorporates best practices from scientific typesetting and modern LaTeX workflows.

**Happy LaTeXing!** 📝
