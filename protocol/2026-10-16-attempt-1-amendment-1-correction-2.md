# Correction 2 to Amendment 1 — what ℤ × ℤ is, and what it is not

*Corrects [`2026-10-15-attempt-1-amendment-1.md`](./2026-10-15-attempt-1-amendment-1.md) §1, which is not edited, and
leaves [`2026-10-15-attempt-1-amendment-1-correction-1.md`](./2026-10-15-attempt-1-amendment-1-correction-1.md) as it
stands. Committed and timestamped before the encoding is frozen (Protocol 2) and before any model is searched.*

- **Written by:** Miss Aquarius℠
- **Approved by:** Thon Ly, 2026-10-16 (*"yes"*, on the session's proposal to correct the sentence)

## 1. What was wrong

Amendment 1 §1, question 2, says a non-standard stream "has the order type ℤ × ℤ, the structure that non-standard
analysis uses for infinitesimals."

Ordered by its first coordinate and then by its second, ℤ × ℤ is one non-standard stream: (1, 0) comes after every
(0, m), so it is infinitely many moments after (0, 0). But it is not the structure non-standard analysis uses, for two
reasons.

1. **Its blocks are not dense.** Call a *block* the moments a finite number of steps from one another. In ℤ × ℤ the
   blocks follow one another like the integers: nothing lies infinitely far after block 0 and infinitely far before
   block 1. In the hyperintegers of non-standard analysis the blocks are densely ordered. Between the blocks of N and
   2N lies the block of ⌊3N/2⌋, and in the same way between any two (Goldblatt, *Lectures on the Hyperreals*, 1998).
2. **It breaks transfer.** Transfer is the principle at the heart of non-standard analysis: every first-order statement
   true of the integers stays true of the hyperintegers. "Every number is even or odd" is true of the integers. In
   ℤ × ℤ, with addition coordinate by coordinate, (1, 0) is neither.

The session wrote the sentence on 2026-10-15 and found the error on 2026-10-16.

## 2. What it does not change

Question 2 asks whether any two moments of a stream must be a finite number of moments apart. Any stream with two
moments infinitely many moments apart answers it, and ℤ × ℤ is one. The question, both predictions on it, and every
other part of Amendment 1 and its correction 1 stand.

## 3. What replaces the sentence

Question 2's last sentence is to be read as:

> That stream is non-standard. In non-standard analysis its moments would be hyperintegers, whose blocks are densely
> ordered and which satisfy every first-order statement true of the integers. ℤ × ℤ is the simplest non-standard
> stream and has neither property. ℚ × ℤ has both, for order and addition.

**ℚ × ℤ** is ordered by its first coordinate (a rational number, which names the block) and then by its second, and it
is added coordinate by coordinate. Its blocks are dense. It also obeys the integers' residue law: for every element g
and every n ≥ 1 there is exactly one i with 0 ≤ i < n such that g − (0, i) is n times some element. An ordered group
whose least positive element is 1 and which obeys this law satisfies every first-order statement about the integers'
order and addition (Presburger, 1929). Multiplication is not covered. A non-standard model of the integers with
multiplication exists (an ultrapower gives one), but no countable one can be computed (Tennenbaum, 1959).

## 4. What the book owes from here

Wherever the book calls a stream *non-standard*, it names the stream it means and says whether that stream carries
transfer, and for which operations.

## Appendix — the Lean

Checked on 2026-10-16 with Lean v4.34.1 (the toolchain pinned in
[SiliconWat/formal-abhidhamma](https://github.com/SiliconWat/formal-abhidhamma)), core library only, no `sorry`. Each
file is checked with `lean <file>`. Each break was run as stated and failed, as it must.

**What is checked:** both defects of ℤ × ℤ, and integers being even or odd · ℚ × ℤ's dense blocks, its residue law
(existence, and uniqueness, which reduces to the integer coordinate), and its non-standardness. **What is cited, not
checked:** that ℚ × ℤ is an ordered group with least positive element (0, 1), and Presburger's theorem itself.

`ZZ.lean`

```lean
/-- ℤ × ℤ with coordinatewise addition; the lexicographic order compares the first coordinate first. -/
def add2 (x y : Int × Int) : Int × Int := (x.1 + y.1, x.2 + y.2)
def lexLt (x y : Int × Int) : Prop := x.1 < y.1 ∨ (x.1 = y.1 ∧ x.2 < y.2)

/-- (1) Transfer fails: (1,0) is neither even nor odd, while every integer is. -/
theorem zz_one_zero_not_even : ¬ ∃ x : Int × Int, add2 x x = (1, 0) := by
  rintro ⟨⟨a, b⟩, h⟩
  simp [add2, Prod.ext_iff] at h
  omega

theorem zz_one_zero_not_odd : ¬ ∃ x : Int × Int, add2 (add2 x x) (0, 1) = (1, 0) := by
  rintro ⟨⟨a, b⟩, h⟩
  simp [add2, Prod.ext_iff] at h
  omega

theorem int_even_or_odd : ∀ n : Int, ∃ k, n = k + k ∨ n = k + k + 1 := by
  intro n; exact ⟨n / 2, by omega⟩

/-- (2) The blocks are not dense: nothing lies above all of block 0 and below all of block 1. -/
theorem zz_blocks_not_dense :
    ¬ ∃ x : Int × Int, (∀ m : Int, lexLt (0, m) x) ∧ (∀ m : Int, lexLt x (1, m)) := by
  rintro ⟨⟨a, b⟩, h0, h1⟩
  have p := h0 (b + 1)
  have q := h1 (b - 1)
  simp [lexLt] at p q
  omega

-- BREAK (must FAIL): claiming (1,0) is even.
-- theorem break_even : ∃ x : Int × Int, add2 x x = (1, 0) := ⟨(0, 0), by decide⟩
```

Break: uncomment `break_even`. Lean rejects it: `decide` proves `add2 (0, 0) (0, 0) = (1, 0)` false.

`QZ.lean`

```lean
/-- ℚ × ℤ: blocks named by the rationals (first coordinate), ordered lexicographically, added coordinatewise. -/
def lexLtQ (x y : Rat × Int) : Prop := x.1 < y.1 ∨ (x.1 = y.1 ∧ x.2 < y.2)

/-- n copies of x added together, coordinatewise. -/
def smul (n : Nat) (x : Rat × Int) : Rat × Int := ((n : Rat) * x.1, (n : Int) * x.2)

theorem two_eq : (2 : Rat) = 1 + 1 := by
  have h := Rat.natCast_add 1 1
  rw [Rat.natCast_ofNat] at h
  exact h.trans (by congr 1)

theorem two_mul' (p : Rat) : p * 2 = p + p := by
  rw [two_eq, Rat.mul_add, Rat.mul_one]

/-- (a) The blocks are dense: block (p+q)/2 lies above all of block p and below all of block q. -/
theorem qz_blocks_dense (p q : Rat) (h : p < q) :
    ∃ x : Rat × Int, (∀ m : Int, lexLtQ (p, m) x) ∧ (∀ m : Int, lexLtQ x (q, m)) := by
  have two : (0 : Rat) < 2 := by decide
  refine ⟨((p + q) / 2, 0), fun _ => Or.inl ?_, fun _ => Or.inl ?_⟩
  · show p < (p + q) / 2
    rw [Rat.lt_div_iff two, two_mul']
    exact Rat.add_lt_add_left.mpr h
  · show (p + q) / 2 < q
    rw [Rat.div_lt_iff two, two_mul', Rat.add_comm p q]
    exact Rat.add_lt_add_left.mpr h

/-- (b) The integers' residue law holds: for every g and n ≥ 1, g = n·x + (0, i) with 0 ≤ i < n. -/
theorem qz_residue_exists (g : Rat × Int) (n : Nat) (hn : 0 < n) :
    ∃ x : Rat × Int, ∃ i : Int, 0 ≤ i ∧ i < n ∧ ((smul n x).1, (smul n x).2 + i) = g := by
  have hnQ : (n : Rat) ≠ 0 := by
    intro h; have := congrArg Rat.num h; simp at this; omega
  have hnZ : (n : Int) ≠ 0 := by omega
  refine ⟨(g.1 / n, g.2 / n), g.2 % n, Int.emod_nonneg _ hnZ, Int.emod_lt_of_pos _ (by omega), ?_⟩
  simp only [smul]
  rw [Rat.mul_comm, Rat.div_mul_cancel hnQ]
  have := Int.mul_ediv_add_emod g.2 n
  exact Prod.ext rfl this

/-- (b') …and i is unique. -/
theorem qz_residue_unique (y z : Int) (i j : Int) (n : Nat)
    (hi : 0 ≤ i ∧ i < n) (hj : 0 ≤ j ∧ j < n) (h : (n : Int) * y + i = n * z + j) : i = j := by
  have e1 : ((n : Int) * y + i) % n = i := by
    rw [Int.add_comm, Int.add_mul_emod_self_left, Int.emod_eq_of_lt hi.1 hi.2]
  have e2 : ((n : Int) * z + j) % n = j := by
    rw [Int.add_comm, Int.add_mul_emod_self_left, Int.emod_eq_of_lt hj.1 hj.2]
  rw [h] at e1; omega

/-- (c) It is a non-standard stream: (1, 0) lies above every (0, m), infinitely many moments above (0, 0). -/
theorem qz_nonstandard : ∀ m : Int, lexLtQ (0, m) (1, 0) := fun _ => Or.inl (show (0 : Rat) < 1 by decide)
```

Break: replace the density witness `((p + q) / 2, 0)` with `(p, 0)`, a point inside block p itself. Lean rejects
`qz_blocks_dense`. `#print axioms` shows no `sorryAx` for any theorem here.
