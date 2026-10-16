# Cryptographic timestamps

This repository exists so that the rules of the attempt can be shown to have been fixed before it ran. Three independent dates back that up:

1. **The push.** GitHub records when each commit reached this public repository.
2. **OpenTimestamps.** Every protocol, prediction and ledger file carries a `<name>.md.ots` proof beside
   it, which commits the file's SHA-256 to the Bitcoin blockchain. Anyone can check it without trusting
   this repository, GitHub or the author.
3. **RFC 3161.** A weekly manifest of every tracked file is signed by three independent trust
   authorities, one of them eIDAS-qualified. See [`timestamps/README.md`](./timestamps/README.md).

## One file, one stamp

`ots stamp` overwrites an existing proof, so a file here is written once and never edited. A new
edition's protocol is a new file; a correction is a new, dated file that names the one it corrects.
The weekly job adds a proof to any document that has none and never touches an existing one. A
new document is stamped by hand when it is pushed, not left to the weekly job.

## What a proof does not show

A timestamp proves that this exact text existed no later than a given moment and has not changed
since. It says nothing about who wrote it, whether it is original, or whether it is right.

## Checking a proof

```sh
pip install opentimestamps-client
ots verify <file>.md.ots
./tsa-verify.sh <file>.md
```

A full check against Bitcoin uses a local node. Without one, the proof still names a specific block,
whose Merkle root can be compared with any public block explorer.

## Log

*Stamps, rotations and checks are recorded here, newest first.*

### 2026-10-16 — Correction 2's Lean, re-checked on the pinned toolchain

Correction 2's appendix says its Lean was "checked on 2026-10-16 with Lean v4.34.1". At its push that was not true: the
checks ran on v4.35.0, elan's default toolchain outside the formal-abhidhamma repository. Re-checked the same day on
v4.34.1 (`lean +leanprover/lean4:v4.34.1`): `ZZ.lean` and `QZ.lean`, exactly as printed, check with no `sorryAx`, and
both breaks fail on their own lines (`break_even`: `decide` proves it false; the moved density witness: the proof of
`qz_blocks_dense` fails). The stamped correction is not edited. The Lean check behind amendment 2 §4's H₁ example ran
on v4.34.1 too.

### 2026-10-16 — Protocol 1, amendment 2

`protocol/2026-10-16-attempt-1-amendment-2.md` stamped by hand at its push. Protocol 1, its correction 1, amendment 1
and amendment 1's corrections are not edited.

### 2026-10-16 — Amendment 1, correction 2

`protocol/2026-10-16-attempt-1-amendment-1-correction-2.md` stamped by hand at its push. Amendment 1 and its
correction 1 are not edited.

### 2026-10-15 — Amendment 1, correction 1

`protocol/2026-10-15-attempt-1-amendment-1-correction-1.md` stamped by hand at its push. Amendment 1 is not edited.

### 2026-10-15 — Protocol 1, amendment 1

`protocol/2026-10-15-attempt-1-amendment-1.md` stamped by hand at its push. Protocol 1 and correction 1 are not edited.

### 2026-10-15 — Protocol 1, correction 1

`protocol/2026-10-15-attempt-1-correction-1.md` stamped by hand at its push. Protocol 1 itself is not edited.

### 2026-10-15 — Protocol 1

`protocol/2026-10-15-attempt-1.md` stamped by hand at its push (`protocol/2026-10-15-attempt-1.md.ots`); the weekly
RFC 3161 manifest covers it from its next run.

### 2026-10-15 — repository created

The timestamping is in place before the first document.
