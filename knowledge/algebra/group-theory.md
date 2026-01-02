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
