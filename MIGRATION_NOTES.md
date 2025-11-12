# Migration to Physics Package

## Overview
The template has been **fully migrated** to use the industry-standard **physics** package for mathematical notation. All document sections now use physics package commands directly for better robustness, maintenance, and compatibility.

## What Changed

### ✅ Now Using Physics Package

All commands are now powered by the physics package:

#### Derivatives
- **Partial derivatives**: `\pdv{f}{x}` → ∂f/∂x
- **Higher-order partials**: `\pdv[n]{f}{x}` → ∂ⁿf/∂xⁿ
- **Mixed partials**: `\pdv{f}{x}{y}` → ∂²f/∂x∂y
- **Total derivatives**: `\dv{f}{x}` → df/dx
- **Higher-order total**: `\dv[n]{f}{x}` → dⁿf/dxⁿ

#### Quantum Mechanics
- **Ket vectors**: `\ket{\psi}` → |ψ⟩
- **Bra vectors**: `\bra{\phi}` → ⟨φ|
- **Braket**: `\braket{\phi}{\psi}` → ⟨φ|ψ⟩
- **Expectation**: `\expval{A}{\psi}` → ⟨ψ|A|ψ⟩
- **Matrix element**: `\matrixel{\phi}{A}{\psi}` → ⟨φ|A|ψ⟩
- **Commutator**: `\comm{A}{B}` → [A,B]
- **Anticommutator**: `\acomm{A}{B}` → {A,B}

#### Vector Calculus
- **Gradient**: `\grad f` → ∇f
- **Divergence**: `\div \vec{F}` → ∇·F
- **Curl**: `\curl \vec{E}` → ∇×E
- **Laplacian**: `\laplacian f` → ∇²f

#### Special Functions & Operators
- **Absolute value**: `\abs{x}` → |x|
- **Norm**: `\norm{\vec{v}}` → ‖v‖
- **Trace**: `\tr(A)` → tr(A)
- **Determinant**: `\det(M)` → det(M)
- **Rank**: `\rank(M)` → rank(M)

### ✨ Custom Notation Preserved

Our unique underline-based notation is still available and **preserved** (these are NOT from the physics package):

```latex
\vec{v}        % vector with single underline: v̲
\mat{A}        % matrix with double underline: A̲̲
\tensor{T}     % tensor with triple underline: T̲̲̲
```

### ⚠️ Breaking Changes from Old Custom Macros

The following custom commands have been **removed** in favor of physics package equivalents:

1. **`\pd{f}{x}` → `\pdv{f}{x}`**: Partial derivative
2. **`\pdd{f}{x}` → `\pdv[2]{f}{x}`**: Second partial derivative
3. **`\pdc{f}{x}{y}` → `\pdv{f}{x}{y}`**: Mixed partial derivative
4. **`\pdt{u}` → `\pdv{u}{t}`**: Partial time derivative
5. **`\td{s}{t}` → `\dv{s}{t}`**: Total derivative
6. **`\tdd{s}{t}` → `\dv[2]{s}{t}`**: Second total derivative
7. **`\Div` → `\div`**: Divergence operator (now lowercase)
8. **`\vdot` → `\vecdot`**: Dot product (renamed to avoid conflict)
9. **`\vnabla` → removed**: Use `\grad`, `\div`, `\curl`, or `\laplacian` instead

## Command Reference

### Recommended Usage

All documents should now use physics package commands directly:
```latex
\pdv{f}{x}           % partial derivative
\dv{s}{t}            % total derivative
\grad f              % gradient
\div \vec{F}         % divergence
\curl \vec{E}        % curl
\laplacian \psi      % Laplacian (∇²)
```

## Examples from the Template

### Derivatives
```latex
% First-order partial
\pdv{f}{x}

% Second-order partial
\pdv[2]{f}{x}

% Mixed partial
\pdv{f}{x}{y}

% Time derivative
\pdv{u}{t}

% Total derivative
\dv{s}{t}
```

### Vector Calculus
```latex
% Gradient
\grad f = \pdv{f}{x}\xhat + \pdv{f}{y}\yhat + \pdv{f}{z}\zhat

% Divergence
\div \vec{F} = \pdv{F_x}{x} + \pdv{F_y}{y} + \pdv{F_z}{z}

% Curl
\curl \vec{E} = -\pdv{\vec{B}}{t}

% Laplacian
\laplacian \vec{E} = \mu_0\epsilon_0 \pdv[2]{\vec{E}}{t}
```

## Benefits

1. **Industry Standard**: The physics package is widely used and well-maintained
2. **Better Formatting**: Automatic sizing and spacing optimizations
3. **More Features**: Access to additional commands like `\expval`, `\comm`, etc.
4. **Robustness**: Fewer conflicts with other packages
5. **Documentation**: Comprehensive [physics package documentation](https://ctan.org/pkg/physics)

## Files Modified

- `config/packages.tex` - Added physics package
- `config/macros.tex` - Removed all backward-compatible aliases, using physics package directly
- `sections/02_math_commands.tex` - Migrated all commands to physics syntax
- `sections/05_complete_example.tex` - Updated to use `\laplacian` and `\pdv[2]`

## Migration Checklist

If you have existing documents using the old custom macros, update them as follows:

- [ ] Replace `\pd{f}{x}` with `\pdv{f}{x}`
- [ ] Replace `\pdd{f}{x}` with `\pdv[2]{f}{x}`
- [ ] Replace `\pdc{f}{x}{y}` with `\pdv{f}{x}{y}`
- [ ] Replace `\pdt{u}` with `\pdv{u}{t}`
- [ ] Replace `\td{s}{t}` with `\dv{s}{t}`
- [ ] Replace `\tdd{s}{t}` with `\dv[2]{s}{t}`
- [ ] Replace `\Div` with `\div`
- [ ] Replace `\vdot` with `\vecdot`
- [ ] Replace `\vnabla^2` with `\laplacian`

## Need Help?

See the physics package [documentation](http://mirrors.ctan.org/macros/latex/contrib/physics/physics.pdf) for the complete command reference.
