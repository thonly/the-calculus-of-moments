# Amendment 1 to Protocol 1 — the calculus question, a second encoder, the subtitles, and five more rules

*Adds to [`2026-10-15-attempt-1.md`](./2026-10-15-attempt-1.md) and
[`2026-10-15-attempt-1-correction-1.md`](./2026-10-15-attempt-1-correction-1.md), which are not edited. Committed and
timestamped before the encoding is frozen (Protocol 2) and before any model is searched.*

- **Written by:** Miss Aquarius℠
- **Approved by:** Thon Ly, 2026-10-15 22:37 PDT (*"approve all"*, on eight recommendations), with the subtitles in §3
  chosen by him the same night

## 1. The calculus question

The title promises calculus, and calculus is the mathematics of the continuum. Protocol 1 asks only whether the axioms
can hold together. This section adds four questions. Each is answered PROVED, REFUTED, INDEPENDENT (two models), or NOT
FORMALIZABLE, on the base encoding:

1. **Must a stream's moments be discrete?** That is, must every mind-moment have one just before it, and every moment
   except an arahant's last have one just after it?
2. **Must any two moments of one stream be a finite number of moments apart?** Or do the axioms also allow a
   **non-standard** stream, in which two of its moments have infinitely many moments between them? That stream has the
   order type ℤ × ℤ, the structure that non-standard analysis uses for infinitesimals.
3. **Can the clock be continuous?** Time is a designation on what occurs (A7), so the clock's values are a choice. They
   could be whole numbers, or a dense or continuous scale.
4. **Can matter's places be continuous?** Must the places where kalāpas arise form a discrete grid, or can they lie in a
   continuum?

The answers make a **discreteness map**. For each part of the world, it says whether the axioms force that part to be
discrete, force it to be continuous, or leave it open.

**What this changes in the encoding.** A stream indexed by the whole numbers makes questions 1 and 2 true by
construction. So the stream is re-encoded over an arbitrary order, and the clock over an arbitrary ordered scale. The
first encoding (formal-abhidhamma `c59fff2`) is replaced.

**Predictions, made before the attempt:**

| | Miss Aquarius (the session) | Thon Ly |
|---|---|---|
| Q1 discrete | PROVED, about 85% | — |
| Q2 a non-standard stream | INDEPENDENT (it is allowed), about 65% | INDEPENDENT (*"Yes, allowed"*) ⚠️ given after he had seen the session's prediction in the question, so not independent of it |
| Q3 a continuous clock | possible, about 70% | — |
| Q4 continuous places | possible, about 60% | — |

## 2. A second encoder

One encoder cannot measure its own reliability. Back-translation checks a definition against its row, never against a
second honest encoding of the same row.

- **Roster:** the CONSTRAINT rows of the census at the commit declared **encoding complete**, in census order.
- **Sample:** 25 rows, drawn with a seed that no one controls. The seed is the hash of the first Bitcoin block mined
  after that commit's push. Each row is ranked by SHA-256 of the seed followed by the row's ID, and the 25 lowest are
  taken. Anyone can recompute the draw.
- **The second encoder** is a fresh agent that has never seen `model/`. It gets the `World` type's fields and their
  types (no definitions, no comments) and the row's text from `kala/AXIOMS.md`, and it writes the definition.
- **Agreement is decided by Lean**, pair by pair: EQUIVALENT (both directions proved), ONE STRONGER (one direction
  proved, a countermodel for the other), DIFFERENT (countermodels both ways), or UNDECIDED.
- **Threshold:** at least 20 of 25 EQUIVALENT. Every other pair goes to the refuter, who reads both definitions against
  the Pāli and says which one is faithful. If the first encoding loses more than two of those readings, every
  CONSTRAINT row gets a second pass before Protocol 2.
- Protocol 2 reports the draw, every pair's result and every adjudication, failures included.

## 3. The subtitles, chosen before the result

This replaces Protocol 1 §10's "the new wording is the founder's to choose after the result":

| Result | Subtitle |
|---|---|
| A model at every layer | *One Model of the Whole Abhidhamma* (as ruled 2026-10-15) |
| A model up to some layer, then a break | *One Model of the Abhidhamma, and Where It Breaks* |
| No model even at the Piṭaka layer | *Where the Abhidhamma's Axioms Part* |

A clash between rival readings (correction 1) never counts as a break. Only the base encoding decides the subtitle.

## 4. Two human readers, before the freeze

Two people read Protocol 2's table (every row, beside its Lean in plain English) **before any model is searched**,
while what they find can still change the encoding. One is a scholar of the Abhidhamma who also works in formal logic,
and reads the encoding. The other is a logician who works in Lean, and reads the model. Each is named in Protocol 2
once they have accepted. Protocol 2 publishes their findings with the decision on each. If either declines, Protocol 2
says so once.

## 5. Checks a reader can repeat

- **Independent kernel check.** The final Lean is re-checked by a kernel checker other than the one that built it
  (lean4checker, or an external checker fed by lean4export), if one runs on this build. If none does, the book says so.
- **Every theorem the book cites** names its Lean declaration, the commit, and that commit's Software Heritage
  identifier.
- **One command** reruns every check and regenerates every number the book quotes.

## 6. No claim of priority without a census

Before any sentence that says this work is the first, or new, a full census of prior work is run and published, failed
conjuncts included. Its controls are the known neighbors:

- the tables in Bhikkhu Bodhi's *A Comprehensive Manual of Abhidhamma*
- `AloofBuddha/abhidhamma` (a Haskell model, 2026-09-18)
- `takuya50/buddhist-comparative-logic` (Lean 4, 2026-09-20)
- Henk Barendregt's *The Abhidhamma Model AM₀ of Consciousness* (2006)
- the Kathāvatthu itself, the tradition's own machine for consistency: each debate refutes a view by drawing a
  contradiction out of what its holder admits

## 7. The book walks up the layers

The book's parts follow the layers in Protocol 1 §5's order. Each part adds one layer to the model and says what that
layer costs. A break, if one comes, lands in the part where it happens. The detailed outline is ruled after Protocol 2.

## 8. The independent core

For every CONSTRAINT, the attempt tries two things: to derive it from the other constraints of its layer, and to build a
model of those others in which it fails. Each row is reported as FOLLOWS, INDEPENDENT or NOT SETTLED, and the counts are
given. If a smallest set that carries all the rest is found, it is reported. One case is already known: in the first
encoding, A77 (the round is beginningless) follows from C (every citta has a proximate predecessor).

## 9. Unchanged

Everything else in Protocol 1 and correction 1 stands.
