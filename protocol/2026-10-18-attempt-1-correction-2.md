# Correction 2 to Protocol 1 — what the taxonomy encoding found in the rows

*Corrects [`2026-10-15-attempt-1.md`](./2026-10-15-attempt-1.md) and its correction 1, neither of which is edited, and
amendment 1 in one title. Committed and timestamped before the encoding is frozen (Protocol 2) and before any model is
searched.*

- **Written by:** Miss Aquarius℠
- **Approved by:** Thon Ly, 2026-10-18 (*"reconcile all per your recommendation"*)
- **Found by:** the TAX encoding ([`SiliconWat/formal-abhidhamma`](https://github.com/SiliconWat/formal-abhidhamma)
  `model/Tax.lean`, `917b4ea`), roadmap A423's exact-spelling sweep of `kala/AXIOMS.md`, the reading of A118's line
  that the sweep called for, and the refuter of the founder's hyperfinite sentence (roadmap A424). The changes below
  are in the Lean repository at `605b5ec`.

## 1. A row that misreads its line: A38

A38 says that "5 take any object". The Saṅgaha says six (ch. 3 §59, `abh07t.nrf.xml:1077`): the four
knowledge-associated sense-sphere functional cittas, the functional super-knowledge and determining
(*ñāṇasampayuttakāmāvacarakiriyāni ceva kiriyābhiññāvoṭṭhabbanañceti sabbathāpi sabbārammaṇāni*). The verse agrees
(`abh07t.nrf.xml:1105`, *pañca sabbattha chacceti*). Five is the count of a different group, those that take every
object except the arahant's path and fruit (§58, `abh07t.nrf.xml:1073`, *arahattamaggaphalavajjitasabbārammaṇāni*).

**The rule:** for this attempt, A38's clause reads "six take any object; five take every object except the arahant's path
and fruit", and `kala/AXIOMS.md` carries a dated note on the row. The row's old reading, "five", is the forbidden world
of its definition (`a38_forbids_fiveAny`).

## 2. Rows that name a list without its members

Protocol 1 §7.1 encodes "what a row's own words say". Four rows name a list whose members their words do not give, though
the lines they cite do:

| Row | What the row says | What its cited lines give |
|---|---|---|
| A35 | 14 functions; 68 · 2 · 9 · 8 · 2 citta-types with one to five | which types perform each function (§20–32, `abh07t.nrf.xml:893–941`) |
| A38 | 25 limited · 21 concepts · any object | the other three groups: 6 exalted · 20 all but the supramundane · 5 all but the arahant's path and fruit (§57–58, §60) |
| A62 | "base or not; door or not; faculty or not" | six, seven and eight kinds (§20–22, `abh07t.nrf.xml:2141–2149`) |
| A105 | "which subjects reach absorption, and which jhāna" | the table (ch. 9 §19–25, `abh07t.nrf.xml:3125–3149`) |

Encoded from the row's words alone, these rows constrain nothing at those points. A dyad with no members, or a count
with no members, leaves the model free exactly where the text is not.

**The rule:** a row's OWN cited lines may supply the members of a list the row names. They are encoded as separate
definitions, marked as coming from the cited lines. Lines the row does not cite never supply anything (§7.1's purpose,
which stands: no scope from another text). The eight definitions written this way (`a35_which`, `a38_six_exalted`,
`a38_twenty`, `a38_five_but_agga`, `a62_base`, `a62_door`, `a62_faculty`, `a105_absorption`) enter the encoding. Each
has its forbidden world. The absorption table also reproduces the text's own totals: 30 subjects reach absorption
(§20) and 26 a fine-material jhāna (§24).

## 3. Citations repaired (the content of each row unchanged)

- **A14.** *asaṅkhyeyyo appameyyo* ("countless, immeasurable") water is not at the Mahāniddesa line the row cites
  (`s0515m.mul.xml:8009`, which gives the ocean's depth). The phrase is in the Saṃyutta (`s0305m.mul.xml:9203`), the
  Aṅguttara (`s0402m3.mul.xml:2332`; `s0403m1.mul.xml:1392` spells it *asaṅkheyyo*) and the Atthasālinī, beside the same
  84,000-yojana depth (`abh01a.att.xml:413`).
- **A118.** *tayidamakāraṇaṃ* ("that is no reason") is at `abh02t.tik.xml:4949`, which the row does not cite (A120
  does). The sweep suspected the row's attribution, because CST's file is titled the Vibhaṅga-mūlaṭīkā. Read at its
  headings, the file holds two books: the Vibhaṅga-mūlaṭīkā, then the Vibhaṅga-anuṭīkā from its title at
  `abh02t.tik.xml:4625`. Line 4949 is in the anuṭīkā, commenting on the mūlaṭīkā's own words
  (*yo cettha … vicāretabbo*, `abh02t.tik.xml:313`, quoted at `abh02t.tik.xml:4941`). So the row and correction 1 §2.4 are right: the mūlaṭīkā
  (Ānanda) reads the Yamaka's "no" literally (`abh02t.tik.xml:317`), and the anuṭīkā rejects that reading
  (*tayidamakāraṇaṃ*), restricting the "no" to the formless world or to mind-born matter. These are two teachers, not
  one teacher on both sides. Only the cite is added.

## 4. Three answers added to the test bank (no row changes)

Protocol 1 §10 checks the model against every row of `kala/ANSWERS.md`. Its sort rule sends a debate's conclusion
there, never to the axioms. Three Kathāvatthu debates on how long a citta lasts, and what time is, had no row. They
now do:

- **Kv 2.7** (`abh03m3.mul.xml:4501–4557`): no citta lasts a day, or any longer stretch up to 84,000 aeons. The
  commentary says the view came from seeing a series of cittas as one (`abh03a.att.xml:3361`). It is an upper bound
  only.
- **Kv 15.3** (`abh03m3.mul.xml:11065`): time is not a produced thing, and **Kv 15.4** (`abh03m3.mul.xml:11105`): nor
  is a moment, a *laya* or a *muhutta*. The commentary: "apart from the mere designation of time"
  (`abh03a.att.xml:5401`), and the moment and the rest are "only words for time" (`abh03a.att.xml:5413`).

Each conclusion is also asserted at a later layer: A24 for Kv 2.7 (the Saṃyutta commentary), and A7 (the Atthasālinī)
and A104 (the manual) for Kv 15.3 and 15.4. By the sort rule's layer clause, each answer therefore tests only the
Piṭaka layer, and A7, A24 and A104 stay axioms. No live row is held out, and the attempt's rows stay 127. The test
bank now has twelve rows. Protocol 2 freezes the commit of `ANSWERS.md` together with the encoding.

## 5. A title (amendment 1 §6)

Amendment 1 §6 names Henk Barendregt's paper as *The Abhidhamma Model AM₀ of Consciousness* (2006). Its title is ***The
Abhidhamma Model of Consciousness AM₀ and some of its Consequences*** (7 May 2006; in Kwee, Gergen and Koshikawa, eds.,
*Buddhist Psychology: Practice, Research and Theory*, Taos Institute, pp. 331–349).

## 6. Unchanged

Everything else in Protocol 1, its correction 1, and amendments 1 and 2 with their corrections stands: the 127 rows and
their classes, the occurrence conditions, the layers, the encoding rules (§7.1 as narrowed in §2 above), the controls,
the reporting and every prediction.
