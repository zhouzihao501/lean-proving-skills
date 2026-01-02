# Lean 4 Proving Skills Library

A comprehensive collection of mathematical proving techniques for Lean 4, organized by pure knowledge domains.

## Usage

Reference this skill library when working on Lean 4 proofs:

```
@lean-proving-skills
```

## Structure

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

## Files

- `skill.json` - Configuration and file index
- `TEMPLATE.md` - Format specification with complete example
- `knowledge/` - All skill files organized by category

## Adding New Skills

See `TEMPLATE.md` for the format specification and guidelines.

When adding a new skill:
1. Increment the skill number in the file
2. Update `skill_count` in the file header
3. Update `skill_count` in `skill.json`
4. Follow the format exactly

## Capacity

This structure supports 3000-5000+ skills across all mathematical domains.
