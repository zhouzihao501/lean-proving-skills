# Lean 4 Proving Skills - Template

## Skill Format

Each skill uses this compact structure:

---

# [Topic Name] (skill_count: N)

---

## N. [Descriptive Title Including Context]

**Strategy**:
[1-3 sentences describing when to use this and how. Start with the scenario/context,
then explain the approach and key insight.]

```lean
-- Show key steps and structure, use sorry for routine parts
theorem name (hypotheses) : goal := by
  main_tactic
  key_construction
  critical_step
  sorry  -- Omit straightforward calculations
```

**Pitfalls**: [Common Lean-specific mistakes] | **Related**: [Mathlib theorems/tactics]

---

## Complete Example

---

# Group Theory (skill_count: 1)

---

## 1. Proving Sylow p-Subgroup Existence via Group Actions

**Strategy**:
When you need to prove a finite group has a subgroup of prime power order p^n,
construct a G-action on all size-p^n subsets. By counting argument, p doesn't
divide the orbit count, so a fixed point exists, giving the desired subgroup.

```lean
theorem sylow_exists (p : Nat) [Fact p.Prime] (G : Type*) [Group G] [Fintype G]
  (hdvd : p ^ n ∣ Fintype.card G) : ∃ H : Subgroup G, Fintype.card H = p ^ n := by
  classical
  -- Construct action on subsets of size p^n
  let X := {S : Finset G | S.card = p ^ n}
  -- Key: p doesn't divide |X|
  have : ¬(p ∣ Fintype.card X) := Nat.Prime.not_dvd_choose_of_dvd hdvd
  -- Find fixed point via orbit-stabilizer
  obtain ⟨S, _, _⟩ := exists_fixed_point_of_prime_not_dvd_card_orbits p X this
  use Subgroup.closure S
  sorry  -- Cardinality calculation omitted
```

**Pitfalls**: Requires `classical` for existence proof | **Related**: `MulAction.fixed_points`, `Sylow.exists`

---

## Guidelines for Adding New Skills

These guidelines are for when you (Claude Code or maintainers) add new skills to any file.

**Title Guidelines:**
- Make titles descriptive and context-rich
- Include WHEN to use (the scenario) in the title when possible
- Examples:
  - Good: "Proving Sylow Subgroup Existence via Group Actions"
  - Good: "Verifying Homomorphism Property"
  - Good: "Constructing Quotient via Universal Property"
  - Avoid: "Sylow's Theorem" (too vague)
  - Avoid: "Group Homomorphisms" (what about them?)

**Strategy Section:**
- First sentence: When/why you'd use this (the context)
- Following sentences: How to do it and key insights
- Keep to 1-3 sentences total
- Be informal but precise

**Code Style:**
- Show KEY steps and structure only
- Use `sorry` for routine calculations or long proofs
- Include critical tactics and constructions
- Add brief comments for non-obvious steps
- Target ~10-20 lines for most proofs

**Token Budget:**
- Simple skill: 200-300 tokens
- Medium skill: 300-400 tokens
- Complex skill: 400-500 tokens
- Target average: ~350 tokens per skill
- File capacity: 60-80 skills = 21,000-28,000 tokens

**File Structure:**
- Header: `# [Topic] (skill_count: N)` with no description
- Skills numbered sequentially
- No intro/outro text needed

**When Adding a New Skill:**
1. Increment the skill number (e.g., if last is #42, new one is #43)
2. Update skill_count in file header: `(skill_count: 42)` -> `(skill_count: 43)`
3. Update skill_count in skill.json for this file
4. Follow the format exactly as shown in the example above
5. Keep token budget in mind (~350 tokens average per skill)
