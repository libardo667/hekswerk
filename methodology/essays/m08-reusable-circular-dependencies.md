# Methodology Note · Reusable Circular Dependency Resolutions

**Doc code**: M-08
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-03 Dependency Map · D-07 First 90 Days Landing Plan · pattern library work

---

## 1. Why this doc exists

Circular dependencies are the genre of planning problem that does the most damage to relocation clients, because they generate the felt-sense of "the system itself is broken" rather than "this part of the plan is hard." In the L.B. dogfood case (US → NL, DAFT pathway), the BSN / housing / banking / KVK tangle initially looked like a closed loop with no entry point. The resolution — splitting "address" into a residential chain and a business chain — turned out to be a reusable pattern, not a one-off cleverness.

This note exists so that the next time a similar tangle shows up, the practitioner reaches for a named pattern instead of reinventing the resolution under deadline. D-03 surfaces circular dependencies; this note tells the practitioner what to do with them.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 60 seconds to recognize a pattern in a live tangle.

---

## 2. Working definition

> A *circular dependency* is a situation where system A appears to require system B in order to proceed, while system B appears to require system A. A *reusable resolution* is a transformation of the apparent loop — by disaggregation, bridging, substitution, parallelization, or temporary sufficiency — that changes the dependency structure enough for movement to begin.

Crucially: real circular dependencies are rarer than they look. Many apparent loops are artifacts of imprecise language — one word being used for two different things — or of treating a preference as a requirement. The methodology asks the practitioner to first verify the loop is real, then choose a resolution pattern.

The patterns named in this note are not legal or jurisdiction-specific advice. They are structural moves. The legal mechanics that make a given move work in a given country are the attorney's territory; the structural recognition is the practitioner's.

---

## 3. Diagnosing the loop

Before reaching for a pattern, run the loop through four diagnostic questions. If any of the first three is "yes," there is no real circular dependency — only a language problem.

### 1. Is the loop caused by one overloaded word?

"Address" in NL context can mean residential registration address, mailing address, business domicile, or proof-of-residence document. Treat them as the same thing and the loop appears closed. Distinguish them and the loop often opens.

*Test*: Write the loop out longhand, replacing each instance of the suspect word with the most specific meaning that applies in that position. If two of the instances need different replacements, the loop is a language artifact.

### 2. Is one side actually a preference rather than a requirement?

"I need a permanent home before I get a BSN" sometimes turns out to mean "I would prefer not to register from temporary housing." Preferences can be revised; requirements cannot. The loop is only real if both sides are non-negotiable in the relevant jurisdiction.

*Test*: For each side of the loop, ask: what specifically goes wrong if we violate this? If the answer is "it would be more comfortable if we did it the other way," it is a preference.

### 3. Is the loop downstream of an assumption that no longer holds?

Many loops are inherited from out-of-date research — what was true two years ago, or true in a sibling country, but not true here, now. The municipality changed its rules; the bank no longer requires the document; the registration office accepts the temporary address.

*Test*: Date the source of each constraint in the loop. If one is older than 18 months and undated, verify it before treating it as load-bearing.

### 4. If yes to none of the above — what is the minimum modification that breaks the loop?

Now reach for a pattern.

---

## 4. The five reusable patterns

### Pattern 1 — Disaggregation

The loop closes because one node in the dependency graph is actually two nodes with the same name. Split the node.

**Canonical example (L.B. dogfood, May 2026): the dual-address pattern.**

The apparent loop:

- BSN requires a Dutch address.
- Banking (personal and business) requires BSN.
- DAFT capital deposit requires a business bank account.
- Residence card requires DAFT approval, which requires capital deposit.
- "Address" cannot be established without somewhere to live, which is hard to commit to without a residence card.

The resolution: recognize that "address" is doing two jobs. Split it.

- **Personal chain**: temporary residential housing → residential address → BSN → personal banking → zorgverzekering.
- **Business chain**: Trifium (or comparable) business domicile service → business address → KVK registration → business banking → DAFT capital deposit.
- **Convergence**: with personal banking, BSN, KVK, and capital deposit all in hand, the IND/DAFT application has the inputs it needs.

Once the two chains are visible as separate chains, neither one is a closed loop. Each is a normal linear sequence with its own provider gates.

*When to reach for disaggregation*: any time a single word appears on both sides of an apparent loop. Almost always worth checking before trying any other pattern.

### Pattern 2 — Bridge document

A temporary or interim artifact satisfies the downstream gate for long enough to make progress, even though it is not the final form of the document the downstream system ultimately wants.

**Examples**:

- A letter of intent or hotel booking confirmation satisfies an "address" field on an initial form long enough to start the chain, even though a permanent registered address is what is ultimately required.
- A proof-of-funds bank letter satisfies an immigration intake step even though the final capital deposit happens later in the chain.
- An "in-progress" credential evaluation receipt is acceptable to an employer for hiring purposes while the full evaluation is still in transit.

*When to reach for bridge document*: when the downstream gate is procedural rather than substantive — i.e., the gate exists to confirm that *some* version of the input exists, not to verify the final form. Always verify with the relevant authority or provider that the bridge artifact will actually satisfy the gate; this pattern fails ugly when it is assumed rather than confirmed.

*Failure mode*: presenting a bridge artifact as final and discovering at a later step that the final form is still required. Always plan the swap-out path when introducing a bridge.

### Pattern 3 — External actor substitution

A provider or service stands in for client-side capacity or eligibility that the client cannot yet satisfy directly. The provider's eligibility is borrowed long enough to open the gate.

**Examples**:

- A business domicile service provides a business address (and the legal standing behind it) that the client cannot yet provide from their own residence.
- A relocation provider's local entity sponsors initial bank account opening that an arriving non-resident could not directly obtain.
- A pet relocation company's import license satisfies a documentation step the individual client could not navigate alone.

*When to reach for external actor substitution*: when the gate is one of standing, eligibility, or registration that the client genuinely cannot satisfy at this point in the move — and a provider exists whose business model is exactly to satisfy it for clients in this position. The market has usually already built the substitution where it is genuinely needed; if you cannot find a provider doing this, suspect that the gate is solvable some other way and you are looking at the wrong pattern.

### Pattern 4 — Parallel chains

Two or more chains advance independently without waiting for each other, converging at a later step that requires the outputs of both.

**Examples**:

- The dual-address pattern (above) is also a parallel-chain resolution: personal and business chains run independently and converge at IND/DAFT.
- Document apostille work running in parallel with attorney engagement and capital accumulation. None of those gate each other; they converge at the application package.
- Pet transport preparation running parallel to residence card processing — both have to be done before arrival but neither blocks the other.

*When to reach for parallel chains*: when the loop is actually a sequencing illusion — the systems do not depend on each other directly, but the client has been treating them as if they did because they share an end-state. Disentangle and run in parallel.

*Failure mode*: insufficient attention to the convergence point. The chains rejoin somewhere; if the practitioner has not named that somewhere, the parallel work can finish at different times and the slower chain becomes a bottleneck no one is watching.

### Pattern 5 — Temporary sufficiency

Settle for a "good enough" version of one system that satisfies its current external obligations, deferring the full version until later when more inputs are available.

**Examples**:

- Temporary housing operates as the registered address long enough to obtain BSN and open banking; permanent housing search runs as a separate, slower track once those are in hand.
- Bridge health insurance covers the gap until destination enrollment is possible, rather than waiting for full destination coverage before traveling.
- A simplified initial business structure (sole proprietorship under the DAFT umbrella) handles the early needs; conversion to a more complex structure happens later if and when it becomes advantageous.

*When to reach for temporary sufficiency*: when the system in question has a "minimum viable" form that satisfies the immediate downstream demand, and the gap between minimum-viable and final is fixable later without penalty. Verify "without penalty" carefully — some temporary forms create lock-in.

---

## 5. Worked counterexample

**The "I cannot apply for X until I have decided Y" trap.**

A client recently said, in effect: "I cannot start gathering DAFT documents until I have decided whether DAFT is definitely the right pathway." This sounds like a circular dependency — DAFT-vs-not gates document work, but document gathering is necessary to evaluate DAFT-vs-not.

Run the diagnostics:

1. Overloaded word? No — "DAFT" means one thing.
2. Preference? Yes — partially. Most of the early-stage documents (passports, birth certificates, education records) are needed under any plausible pathway. The preference was for "don't do work that might be wasted."
3. Stale assumption? No.
4. Real loop? No.

**Verdict**: Not a circular dependency. A psychological reluctance dressed up as a logical loop. Resolution: name the documents needed under any plausible pathway and start them; defer only the DAFT-specific items until the pathway is confirmed. No pattern needed — just a reframe.

The point: most loops the practitioner will encounter dissolve on diagnostic. The five named patterns are for the loops that survive diagnostic and still need a structural move.

---

## 6. The pattern library and its governance

The five patterns above are the v0.1 set. The studio's pattern library will grow as engagements surface new tangles and as resolutions prove themselves across multiple cases.

**Promotion criteria** for adding a new pattern to the library:

- The pattern has resolved a similar tangle in at least two engagements (or once in a live engagement plus once in a stress-tested hypothetical).
- The pattern is describable in structural terms, not jurisdiction-specific procedure. "Use the dual-address pattern" generalizes; "use Trifium" does not.
- The pattern has a known failure mode that the practitioner can warn the client about.

**Versioning**: when a new pattern joins the library, the note version bumps. The studio's pattern data store should keep the version pinned per engagement so that historical Maps remain readable against the pattern set in use at the time.

**Jurisdictional flexibility**: patterns are described at the level of structural moves; specific implementations (which provider, which document, which authority) belong in the engagement's working notes and in [[m04-leverage-points]] when the pattern itself becomes a leverage point. The note must never read as legal advice. When the resolution pattern requires legal mechanics, the methodology routes to D-04 provider conversations — the practitioner names the pattern, the provider verifies the mechanics.

---

## 7. Adjacent vocabulary

A pattern is bigger than a trick and smaller than a methodology:

- **Trick**: a one-off resolution that worked for one client and may not generalize. Stays in working notes.
- **Pattern**: a structural resolution that has worked across multiple tangles and can be named and taught.
- **Methodology**: the discipline of recognizing when to reach for which pattern.

Patterns also coexist with:

- **Gate**: the thing that must be satisfied. Patterns transform gates, but do not eliminate them.
- **Bridge**: an artifact that temporarily satisfies a gate. Bridges are the mechanism inside the bridge-document pattern; the word is not the pattern.
- **Convergence point**: the place where parallel chains rejoin. Always name it when using the parallel-chains pattern.

---

## 8. How to use this in practice

**During D-03 dependency mapping**: when a loop appears in the register, do not immediately label it "circular dependency." Run the four diagnostic questions first. Most apparent loops dissolve on the first or second question.

**For loops that survive diagnostic**: reach for the pattern that fits the structural shape. The five patterns are roughly ordered by how often they apply in practice — disaggregation first, then bridge document, then external actor substitution, then parallel chains, then temporary sufficiency. The ordering is empirical, not normative; if a different pattern obviously fits, use it.

**In the D-03 companion document (Section 3)**: when a circular dependency is resolved by a pattern, name the pattern in plain language and explain the move. "We have split what looked like a single 'address' problem into two parallel chains — one for residential registration and one for business domicile — that meet again only at the DAFT application." Do not show the client the pattern catalog; trust the work.

**In D-07 landing plan**: some patterns extend into the first 90 days. Temporary sufficiency, in particular, often persists past arrival — the permanent-housing search runs in parallel with already-completed administrative stabilization. Note where landing-phase work depends on swapping out a bridge artifact for its final form, and time those swaps deliberately.

**Across engagements**: log patterns observed and their failure modes. A pattern that fails ugly twice has either been misapplied or has a precondition the library has not yet captured. Quarterly review: what new patterns deserve promotion, what failures deserve a warning note in an existing pattern.

---

## 9. Open questions (v0.1)

- **Library scope.** Where does this note end and a free-standing Pattern Library document begin? Working assumption: once the pattern count exceeds eight, spin out into its own document and leave a stub here.
- **Visual representation in D-03.** Currently planning to mark resolved loops with a dashed bypass arrow showing the pattern in use. Untested. May need different visual language per pattern type.
- **Pattern overlap.** The dual-address case is both *disaggregation* and *parallel chains*. The patterns are not strictly orthogonal. Working rule: name the pattern that did the active structural work, not the one that describes the resulting shape. Disaggregation in the L.B. case; the parallel chains are the consequence, not the move.
- **Jurisdictional generalization.** All five patterns are written from a US → NL DAFT perspective. Other pathways and destinations will surface patterns the library does not yet have, and some named patterns may not generalize. Track per engagement.
- **Client-facing language for patterns.** Should the client ever hear the pattern name ("we used the dual-address pattern") or should the language always stay in plain description? Lean: plain description in client artifacts, named patterns in practitioner notes and methodology. Revisit.
- **Pattern naming.** "Disaggregation," "bridge document," "external actor substitution," "parallel chains," "temporary sufficiency" — these are functional but not memorable. May rename as the library matures. Names that stick beat names that are precise.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
