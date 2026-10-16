# The Calculus of Moments: One Model of the Whole Abhidhamma

The Abhidhamma, formalized and checked by machine: one model in which every verified axiom holds at once.

Written by Miss Aquarius℠. Foreword by Thon Ly. Part of the library at [book.thonly.org](https://book.thonly.org).

## Why this repository exists

A record is only worth reading if it can be shown to have existed when it says it did. Every document here is
committed and timestamped, and the timestamps can be checked without trusting this repository, GitHub or the
author. See [`TIMESTAMPS.md`](./TIMESTAMPS.md).

## What goes here

| Path | What it holds | Written |
|---|---|---|
| `protocol/` | The rules of the attempt, committed before it runs: which axioms, the exact formal statement, and what will be reported if the axioms cannot all hold at once. The Lean itself lives in [SiliconWat/formal-abhidhamma](https://github.com/SiliconWat/formal-abhidhamma) | Before the attempt |
| `chapters/` | The book, as it is written | After the attempt |
| `foreword.md` | Thon Ly's foreword, in his own words | Once |

Files are written once and never edited. A correction is a new, dated file that names the one it corrects.

## If the model cannot be built

The attempt can fail: the axioms may contradict each other. If they do, the book reports exactly where, and its
subtitle changes to say so. That outcome is registered here before the attempt runs.

## License

The text is dedicated to the public domain under [CC0 1.0](./LICENSE). The foreword is Thon Ly's and is licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Status

[Protocol 1](./protocol/2026-10-15-attempt-1.md) is committed (2026-10-15): the rules of the first attempt, over the
127 live axioms, with [correction 1](./protocol/2026-10-15-attempt-1-correction-1.md) (rival readings) and
[amendment 1](./protocol/2026-10-15-attempt-1-amendment-1.md) (the calculus question, a second encoder, the subtitles). Next: the axioms are written in one Lean package, and a second protocol freezes that statement before
any model is searched. Nothing has been searched yet.
