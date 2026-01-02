# Lean 4 Proving Skills Library

A comprehensive collection of mathematical proving techniques for Lean 4, organized by pure knowledge domains.

## Installation

Place the `lean-proving-skills` folder in your `.claude/skills` directory:

```bash
# Project-level (recommended for project-specific use)
cp -r lean-proving-skills /path/to/your/project/.claude/skills/

# User-level (global access across all projects)
cp -r lean-proving-skills ~/.claude/skills/
```

## Usage

Reference this skill library when working on Lean 4 proofs:

```
@lean-proving-skills
```

## File Structure

```
lean-proving-skills/
├── skill.json              # Configuration and file index
├── README.md               # This file
├── TEMPLATE.md             # Format specification and example
└── knowledge/              # All skill files by category
    ├── algebra/
    │   ├── group-theory.md
    │   ├── ring-theory.md
    │   ├── field-theory.md
    │   ├── homological-algebra.md
    │   ├── representation-theory.md
    │   ├── module-theory.md
    │   └── commutative-algebra.md
    ├── geometry/
    │   ├── euclidean-geometry.md
    │   ├── differential-geometry.md
    │   ├── algebraic-geometry.md
    │   ├── projective-geometry.md
    │   ├── symplectic-geometry.md
    │   └── complex-geometry.md
    ├── analysis/
    │   ├── real-analysis.md
    │   ├── complex-analysis.md
    │   ├── functional-analysis.md
    │   ├── harmonic-analysis.md
    │   ├── pde-techniques.md
    │   └── operator-theory.md
    ├── topology/
    │   ├── point-set-topology.md
    │   ├── algebraic-topology.md
    │   ├── differential-topology.md
    │   ├── homotopy-theory.md
    │   └── geometric-topology.md
    ├── logic/
    │   ├── mathematical-logic.md
    │   ├── type-theory.md
    │   ├── homotopy-type-theory.md
    │   ├── model-theory.md
    │   └── proof-theory.md
    ├── number-theory/
    │   ├── elementary-number-theory.md
    │   ├── algebraic-number-theory.md
    │   ├── analytic-number-theory.md
    │   └── arithmetic-geometry.md
    ├── combinatorics/
    │   ├── enumerative-combinatorics.md
    │   ├── graph-theory.md
    │   ├── ramsey-theory.md
    │   ├── extremal-combinatorics.md
    │   ├── algebraic-combinatorics.md
    │   └── probabilistic-method.md
    ├── probability/
    │   ├── probability-theory.md
    │   ├── stochastic-processes.md
    │   ├── martingale-theory.md
    │   └── ergodic-theory.md
    ├── set-theory/
    │   ├── axiomatic-set-theory.md
    │   ├── ordinals-cardinals.md
    │   ├── forcing.md
    │   └── descriptive-set-theory.md
    ├── category-theory/
    │   ├── category-theory.md
    │   ├── topos-theory.md
    │   ├── higher-category-theory.md
    │   └── homological-algebra-categorical.md
    ├── computation/
    │   ├── computability-theory.md
    │   ├── computational-complexity.md
    │   ├── algorithm-analysis.md
    │   └── formal-verification.md
    ├── optimization/
    │   ├── convex-optimization.md
    │   ├── discrete-optimization.md
    │   └── variational-methods.md
    └── other/
        └── other.md
```

## Categories

The library is organized into 13 mathematical categories:

| Category | Topics |
|----------|--------|
| **Algebra** | Group theory, ring theory, field theory, modules, homological algebra |
| **Geometry** | Euclidean, differential, algebraic, projective, symplectic, complex |
| **Analysis** | Real, complex, functional, harmonic analysis, PDEs, operators |
| **Topology** | Point-set, algebraic, differential topology, homotopy theory |
| **Logic** | Mathematical logic, type theory, HoTT, model theory, proof theory |
| **Number Theory** | Elementary, algebraic, analytic, arithmetic geometry |
| **Combinatorics** | Enumerative, graph theory, Ramsey, extremal, probabilistic method |
| **Probability** | Probability theory, stochastic processes, martingales, ergodic theory |
| **Set Theory** | Axiomatic, ordinals/cardinals, forcing, descriptive set theory |
| **Category Theory** | Categories, topos theory, higher categories |
| **Computation** | Computability, complexity, algorithm analysis, formal verification |
| **Optimization** | Convex, discrete optimization, variational methods |
| **Other** | Other knowledge and techniques that don't fit elsewhere |

## Skill Format

Each skill follows a compact format:

```markdown
## N. [Descriptive Title Including Context]

**Strategy**:
[When to use this and how - 1-3 sentences]

\`\`\`lean
-- Key proof structure with sorry for routine parts
\`\`\`

**Pitfalls**: [Common mistakes] | **Related**: [Mathlib references]
```

## Adding New Skills

See `TEMPLATE.md` for the format specification and guidelines.

When adding a new skill:
1. Increment the skill number in the file
2. Update `skill_count` in the file header
3. Update `skill_count` in `skill.json`
4. Follow the format exactly

## Capacity

This structure supports 3000-5000+ skills across all mathematical domains.
