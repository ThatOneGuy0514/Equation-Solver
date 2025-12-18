# Equation Solver

An extensible Python framework for modeling, solving, and analyzing linear and quadratic equations using object-oriented design and analytical mathematics.

This project focuses on enforcing mathematical validity at the code level while providing clear, interpretable solutions and diagnostics for each equation type.

---

## Features

- Object-oriented modeling of mathematical equations using abstract base classes
- Support for linear and quadratic equations
- Closed-form analytical solutions (no numerical approximation)
- Automatic validation of mathematical constraints (degree, coefficient type, non-degeneracy)
- Structured analysis of equation properties (roots, slope, intercept, concavity, extrema)
- Clean, formatted textual output for solutions and diagnostics

---

## Design Overview

The core abstraction is the `Equation` base class, which enforces:
- Required attributes (`degree`, `type`)
- Correct number of coefficients
- Valid numeric input
- Non-degenerate equations (leading coefficient ≠ 0)

Concrete subclasses implement equation-specific logic:

- `LinearEquation`: solves first-degree equations and analyzes slope/intercept
- `QuadraticEquation`: solves second-degree equations using the quadratic formula and analyzes concavity and extrema

Each equation must implement:
- `solve()` — computes exact analytical solutions
- `analyze()` — extracts qualitative mathematical properties

This structure allows for easy extension to higher-degree equations or additional analytical features.

---

## Example Usage

```python
from equation_solver import LinearEquation, QuadraticEquation, solver

lin_eq = LinearEquation(2, 3)          # 2x + 3 = 0
quad_eq = QuadraticEquation(1, 5, 3)   # x^2 + 5x + 3 = 0

print(solver(lin_eq))
print(solver(quad_eq))
