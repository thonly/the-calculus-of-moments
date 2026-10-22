# Correction 6 to Protocol 1 — the lesser deferred items, closed or declared

*Corrects [`2026-10-15-attempt-1.md`](./2026-10-15-attempt-1.md), its corrections 1–5 and its amendments, none of which is edited. Committed and timestamped before the encoding is frozen (Protocol 2) and before any model is searched.*

- **Written by:** Miss Aquarius℠
- **Asked for by:** Thon Ly, 2026-10-21 (*"3: do"*), the lesser items correction 5 §2 left
- **Approval:** the change to the table is **not yet approved**; `2026-10-21-table-approved-at-correction-5.md` covers `TABLE.md` at `08d74a2`.
- **Built in:** `SiliconWat/formal-abhidhamma` `9c71553504224913d537fb5619c4c1301a022f45`.

## 1. Closed (each with its forbidden world and the blind reader's English)

1. **A42, the vibration.** A very slight object (ten to fifteen past moments) now needs at least one life-continuum step: *bhavaṅgacalanameva hoti* is "the vibration happens", not only "nothing else does". An empty process no longer passes.
2. **A89, javana only.** A repetition fact needs both occurrences recorded as performing the javana function (`Occ.kicca`, a new optional field). *A reading: a function that is not recorded fails the test.*
3. **A46, the non-percipient.** *The non-percipient beings have no citta at all*: a process may name its being (`Process.being`, optional) and a process of a being that has no mind is barred (`a46_non_percipient`).

## 2. Declared as freedoms (not built)

4. **A111, persons.** "Open to non-returners and arahants" needs a person type that tells a non-returner from other noble persons; `Person` is worldling · noble · arahant. The row's persons are carried as a freedom.
5. **A5, geometry.** Space is "the delimitation between kalāpas, present exactly when both neighbours are": the model has no adjacency of kalāpas, and the texts give none to invent. The `gaps` list is well-formedness only, as before.

## 3. Effect

`TABLE.md` is now 2,524 lines (SHA-256 `f71418d03494e3b3c79d8fe31bc19d82a4bb9ba9d2c8f55a7c19e1558a770e1e`); the forbidden-world suite passes with 242 worlds and `leanchecker` replays every constant. Everything else is unchanged. The vocabulary gains two optional fields (`Occ.kicca`, `Process.being`).
