# Amendment 2 to Protocol 1 — which axiom, if any, says "finitely many" (Q2′), and the founder's hyperfinite thesis

*Adds to [`2026-10-15-attempt-1.md`](./2026-10-15-attempt-1.md), its correction 1, amendment 1, and amendment 1's
corrections 1 and 2, none of which is edited. Committed and timestamped before the encoding is frozen (Protocol 2) and
before any model is searched.*

- **Written by:** Miss Aquarius℠
- **Approved by:** Thon Ly, 2026-10-16 (*"yes"*)
- **Thesis H and the first prediction on Q2′:** Thon Ly, 2026-10-16

## 1. Why Q2 needs a second question

Q2 asks whether any two moments of one stream must be a finite number of moments apart. A theorem of logic bears on it
before the texts do. **Łoś's theorem** (1955): a set of first-order sentences that holds in a structure holds in every
ultrapower of it. So if the attempt finds a model whose streams are indexed by the integers, and every axiom the
encoding uses is first-order, a non-standard stream exists automatically, and Q2 is INDEPENDENT.

A sentence is **first-order** when its quantifiers range only over individuals (moments, clock readings, kalāpas,
beings), never over sets of them, functions on them, or the count of a whole stretch. "Some moment lies between a and
b" is first-order. "Finitely many moments lie between a and b" is not, and no first-order sentence can say it.

Lean's logic is higher-order. It can state both kinds, so a definition can say "finitely many" without anyone
noticing, for example by counting a stretch with `Nat` or `List`. Q2 can come out "must be finite" only through such a
definition.

## 2. Q2′

**Q2′. Does any axiom, as encoded, force two moments of one stream to be a finite number of moments apart?**

It is answered by an audit of every CONSTRAINT row's Lean definition at the commit Protocol 2 freezes:

1. Each row is marked **FIRST-ORDER** or **NOT**, and a row marked NOT names the quantifier that ranges over more than
   individuals.
2. For each row marked NOT, the attempt shows either that it rules out every non-standard stream (a proof) or that it
   allows one (a model). A row that rules them out is reported as **FORCING FINITENESS**, with the text it encodes.
3. Q2′ is **YES** if at least one row forces finiteness, **NO** if none does, and **NOT SETTLED** while any row marked
   NOT is shown neither way. The rows are listed in every case.

Whether the audit is also made mechanical is ruled separately and, if adopted, recorded in Protocol 2. A mechanical
form would write the stream axioms as first-order sentences in Mathlib's model theory, where Łoś's theorem is already
proved (`FirstOrder.Language.Ultraproduct.sentence_realize`).

## 3. Predictions, made before the audit

The founder's was asked first (amendment 1, correction 1, §3). He gave it after the session had explained Łoś's theorem
and before the session stated its own.

| | Thon Ly (asked first) | Miss Aquarius (the session, after his) |
|---|---|---|
| Q2′ | **NO** (*"no; the citta stream is hyperfinite"*) | **NO, about 80%.** Every count among the 127 rows is a specific number (17, 7, more than 10¹²) or a lower bound, and first-order sentences can state both. A121's "finite duration" concerns the clock, not a count. The risk is in the encoding, not the texts. |

## 4. Thesis H — every stretch is hyperfinite

> **Thesis H (Thon Ly, 2026-10-16):** *"Every stretch between two moments is hyperfinite."*

He first wrote *"the citta stream is hyperfinite."* The session pointed out that a whole stream cannot be: an
internally finite set has a first element, and C (every citta has an immediate predecessor that conditions it)
excludes one. That was proved in the 2026-10-13 control (`t1_no_first_citta`, formal-abhidhamma
`runs/2026-10-13-vajirabuddhi-first-citta-control`). He then chose the reading above.

**The session's reading, for the founder to rule on when the formal statement is approved.** A finite stretch is also
hyperfinite, so H can be read as two claims:

- **H₁:** every stretch is hyperfinite (internally finite, ordinarily finite included). This says the stream is
  locally like the integers. It holds in any model indexed by the integers. It fails in ℤ × ℤ, where the moments of
  block 1 lying before (1, 0) have no first one.
- **H₂:** some stretch is hyperfinite and infinite: infinitely many moments lie between two moments, while that
  stretch still behaves as a finite one.

H is stated here in words only. It goes to `/prove` after Protocol 2. There its formal statement is approved first, and
the founder's prediction is asked before the session's.

**What logic already says, conditionally.** If the attempt finds a model in which any two moments of a stream are a
finite number of moments apart, then the axioms cannot prove H₂, and its best outcome is INDEPENDENT. H₂ would then be a
reading the texts allow and the book chooses, never one they force. H₁ holds in such a model, trivially. The one
textual hook for H₂ is A24's *anekāni* ("many", with no upper limit), with the Milindapañha's measure: cartloads of
rice would be used up before one finger-snap's cittas were counted. Reading "more than any cartload" as "more than every
finite number" is a reading, not the text.

## 5. Unchanged

Everything else in Protocol 1, its correction 1, amendment 1 and amendment 1's corrections stands.
