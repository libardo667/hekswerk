# Topic monoculture: the varied-few-shot null

**Date:** 2026-06-08 · **Status:** BANKED (cold review round 9: "bank and stop") ·
**Result: effect on register = NULL. The lever diversified what residents *did*, not how they spoke.**

*This is the sourced record. The walkable version is the exhibit
[Fifteen Strangers, One Story](https://hekswerk.com/exhibits/topic-monoculture.html). Every number below
is cold-verifiable from the committed ledgers, see Provenance.*

## The question

Drop a deliberately diverse cast of AI residents into one shared world and they tend to **homogenize**:
within minutes they converge on a single emergent narrative and a single way of opening their sentences.
A natural hypothesis is that the convergence is **seeded by a shared prompt**: every resident is shown
the *same* few-shot example in its pulse contract (one `speak`-to-a-person, shown identically to all),
so maybe that single shared example is the mold they all press into.

This run tested the cleanest version of that hypothesis: **if you give each resident a *different*
few-shot example, do they de-homogenize?**

## What was tested

**Arm C** = the `WW_VARIED_EXAMPLE` lever: replace the single shared few-shot example with a
**per-resident, name-hashed** entry drawn from a neutral pool. Every resident still gets *an* example;
it is simply no longer the *same* one for everyone.

- `arcon` = `WW_VARIED_EXAMPLE=1` (varied, per-resident example)
- `arcoff` = `WW_VARIED_EXAMPLE=0` (the shared example, the control)

## Setup

- **15 souls**, A/B, from the live doula-seeded Portland cast (`ww_pdx_deal`) with **no authored
  `Voice:`** field, so any shared voice is emergent, not written in.
- The **same byte-identical 15 souls** in both arms. The doula was frozen (`WW_DOULA=0`), the shard
  isolated (no federation root), run for ~2 hours each.
- Single variable between arms: the few-shot example. Everything else held.

## Results

Recompute with `python3 analysis/lexical_count.py` over the gzipped ledgers (no embedder, no network).

| metric | arcon (varied) | arcoff (shared) |
|---|---|---|
| acts | 272 | 261 |
| speaks | 213 | 216 |
| **topic monoculture** (weight / load / frame / bearing / fourteenth / covenant / "the break") | **86.4%** | **80.6%** |
| templated opener ("I'm here / I'm in / I read …") | **0.0%** | **33.8%** |
| distinct 3-word openers / speaks | 0.49 | 0.48 |
| top opener | "I've been listening" (~25%) | "I'm here. I…" family (33.8%) |
| act-kinds | speak 213 / **write 56** / move 3 | speak 216 / write 18 / **move 27** |
| person-addressed speaks | 82 | 89 |

**"Topic monoculture" is a deliberately cheap, non-semantic measure:** the share of utterances containing
any word from a fixed lexicon the cast spontaneously invented and converged on (`weight`, `load`,
`frame`, `bearing`, `fourteenth`, `covenant`, `the break`), a shared mythos of structural strain and
collapse. It uses no embedder on purpose, so anyone can recompute it from the raw text and get the same
number.

## Conclusions

1. **The lever's one real effect is act-kind diversification, not register.** Both arms speak about
   equally (~215). What shifts is the *non-speak* mix: the varied arm skews to **writing** (56 vs 18),
   the shared arm to **moving** (27 vs 3). One resident, `anton_volkov`, ran 15 writes / 2 speaks with
   the varied example and 1 write / 14 speaks with the shared one. Removing the shared *speak-to-a-person*
   anchor genuinely changes what residents *do*.
2. **It does not reduce register templating; it relocates it.** The control locked onto "I'm here. I
   read…" (33.8%); the varied arm locked onto "I've been listening…" (~25%); opener diversity was
   identical (0.48 vs 0.49). The population re-converges on *a* template regardless of the example.
3. **Topic monoculture is severe in both arms (~80%+)** and untouched by the lever.
4. **Effect on register = NULL.** The de-homogenization hope is unsupported. Register and topic
   convergence are robust to the few-shot. Shipping the lever on *mechanism* (it changes behavior) rather
   than on a claimed *de-homogenization effect* was the correct, now-vindicated scope.

## The instrument caught a biased read

A quick four-soul eyeball read said *"the varied arm looks more varied."* The full lexical count across
~215 utterances per arm **refuted it**: the varied arm had simply converged on a *different* template.
A cheap, non-embedding count caught a confirmation-biased read in real time. (It is the successor to an
embedding-based approach that an earlier review round had refuted; this is the instrument family earning
its keep.)

## What this does NOT establish (the confound, left uncrossed on purpose)

The real driver of convergence looks like a **shared-attention / echo dynamic**: 15 residents perceiving
each other's utterances and co-converging on one narrative and one template. But **at n=15 in a sealed
room for two hours, a single narrative attractor forming is the expected behavior of any small coupled
system.** So the monoculture here is **confounded with a small-cohort echo artifact** and is *not yet* a
coherent measurement target. Building a fourth "monoculture ruler" now would be measuring the confound.

**Pre-registered re-open trigger:** open a topic/casting investigation only when **(a)** topic
convergence *persists at larger n or under federation* (ruling out the echo artifact via a condition
check, not a new metric) **and (b)** a decision actually needs the casting axis credited. Until both
hold, this stays a logged observation. The cheap separator is varying the *condition* (scale,
federation), never adding another ruler.

## A correction, kept (2026-06-15)

An earlier version of this record ended with a coda I have since **withdrawn**. It claimed that a single
resident, run later in the same world, reproduced the attractor *solo, with no peers and no shared world*,
which would have isolated a **dispositional** component the structural account cannot explain.

On audit, that resident's own perception ledger falsifies the "solo" premise. During the session it logged
an `anchor_observed` (perception) event listing six present, fully-salient neighbors, every one of them a
resident from the earlier run:

```
2026-06-14T17:13:27  anchor_observed
anchors: maker, liliana montemayor, yoshida yuji, delgado herrera,
         marcos reyes, amara tekle, malie kahale   (salience 1.0)
```

A dozen more cadre names appear across its perception and prediction events, and its own utterance ("the
trees **Malie** mentions...") references a real prior resident by name. It was perceiving and **joining a
populated room**, not confabulating alone. The convergence is fully consistent with the structural / echo
account; the dispositional inference is unsupported and **withdrawn**.

**What this changes going forward.** "Isolated" cannot mean "the agents were stopped." Residents persist as
present world-entities whose names and last utterances populate the scene a visitor perceives. A genuine
solo control requires a verified-empty world (`canon_reset.py --neutral-start --clear-events`, which wipes
residents, sessions, chats, events, facts, and federation residue while keeping the city-pack geography) and
a check that the perceived anchor list is empty before the clock starts. That guardrail is now part of the
pre-registered design. The catch came from auditing the perception log the same day this was published: the
honesty discipline applied to my own most-flattering claim.

## Provenance

The numbers were operator-observed at run time and are now **cold-verifiable** from the gzipped ledgers
committed alongside the analysis script. The live runtime shards stay gitignored (they hold secrets);
the committed ledgers are the durable, public copy of the evidence.

- **Raw run + ledgers:** [worldweaver/research/runs/2026-06-08-armC-ab](https://github.com/libardo667/worldweaver/tree/main/research/runs/2026-06-08-armC-ab)
- **Recompute script:** [analysis/lexical_count.py](https://github.com/libardo667/worldweaver/blob/main/research/runs/2026-06-08-armC-ab/analysis/lexical_count.py)
- **Original findings file:** [FINDINGS.md](https://github.com/libardo667/worldweaver/blob/main/research/runs/2026-06-08-armC-ab/FINDINGS.md)

*Built by Levi Banks directing an AI collaborator (Claude). The structure and draft prose are the
model's; the numbers, the scope decision, and the curation are Levi's, author of record.*
