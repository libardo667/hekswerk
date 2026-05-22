# Methodology Note · Verify With the Authority

**Doc code**: M-13
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-05 Document Readiness Checklist · D-02 Critical Path Timeline · D-04 Provider Shortlist · all deliverables that propagate a non-Hekswerk claim

---

## 1. Why this doc exists

Document readiness, immigration rules, pet entry requirements, healthcare enrollment procedures, banking onboarding requirements — all live in a volatile zone between official rules, provider preferences, and practical enforcement. The internet is full of confident-sounding answers from forum threads, blog posts, and outdated firm pages. Many of those answers were correct two years ago, were correct in a sibling country, or were correct for a different visa category. The methodology fails when those answers are inherited without verification and harden into "what we know."

This note specifies a verification discipline: what counts as an authority, what does not, when to verify, how to record verification, and what to do when authority and provider disagree. The goal is not to verify everything — that is paralysis — but to verify the load-bearing claims before they become commitments. The discipline is especially load-bearing for clients like Mason (worried about "things I don't know I don't know") whose relocation will be built on the methodology's claims about what is true.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 30 seconds per drafted load-bearing row.

---

## 2. Working definition

> An *authority* is the entity whose word actually determines the outcome of a procedural question. Authorities are: (a) the government office or regulator that issues, accepts, or rejects the artifact; (b) the licensed provider whose professional opinion governs the procedure; (c) the receiving institution that actually decides whether to honor the artifact. *Verify with the authority* means: route a load-bearing procedural claim to one of those three before treating it as established, and record what was asked, who answered, when, and in what form.

What is *not* an authority: an internet forum, an expat blog, a generic relocation guide, a previous client's experience, a sibling-country procedure, an out-of-date firm webpage, or the practitioner's own recollection from a different engagement. These are all useful for shaping questions and narrowing fields. They are not load-bearing.

The discipline composes with confidence labels (see [[m06-confidence-labels]]) and with the inference/statement distinction (see [[m03-inference-versus-statement]]). Authority verification is what upgrades a planning assumption to a provider estimate or confirmation. Without verification, a claim stays a planning assumption, no matter how confident the prose around it.

---

## 3. The three authorities

### Government office or regulator

The body that issues the artifact (passport agency, secretary of state for apostilles, foreign ministry, vital records office), that grants the permission (immigration authority, municipal registration), or that regulates the activity (consulate, customs, veterinary authority). The government authority's word is final for procedural questions about its own artifacts.

*Examples*: Georgia Secretary of State on apostille turnaround. German consulate (or BAMF / Ausländerbehörde, depending) on Blue Card filing requirements. IND on DAFT documentation. CDC and destination customs on pet entry.

*How to verify*: official website (treat as authority only if the page is dated within a sensible window and is on the official domain), direct inquiry (email, phone, in-person appointment), or an attorney's interpretation of current regulation. Forum reports of what the office did are not the office speaking.

*Limit*: government authorities often do not answer hypotheticals quickly or in writing. The verification path may have to route through a licensed provider who is in regular contact with the authority.

### Licensed provider

The professional whose license governs the procedure: immigration attorney for visa procedures, accountant or tax attorney for cross-border tax, licensed mover for customs paperwork, veterinarian for pet certificates. Their professional opinion is treated as authority for the scope of their license. Outside their scope, they are an informed party but not an authority.

*Examples*: immigration counsel on whether a specific document is needed for this specific filing. Tax attorney on RSU vesting treatment across a US-to-Germany move. Vet on health certificate timing.

*How to verify*: direct engagement and a documented response (email, written summary of a consultation, signed advice memo). A provider's marketing language is not provider opinion; an actual response to an actual question is.

*Limit*: providers age along with provider research. See [[m11-provider-research-aging]] for the aging discipline. A provider's response from six months ago, in a fast-moving area, may need refresh.

### Receiving institution

The body that will actually accept (or reject) the artifact when it arrives: the destination bank that opens the account, the destination employer that processes the work authorization, the destination school that enrolls the child, the destination insurer that issues the policy. The receiving institution's *acceptance criteria* are authority for the question "will this work?" even when the government authority issued the artifact.

*Examples*: destination bank's specific document list for non-resident account opening. Destination employer's mobility team's list of what they need from the candidate's side of the file. Destination GP's intake requirements.

*How to verify*: direct inquiry to the institution. Their public documentation is a starting point; their stated requirements at intake are the operative truth.

*Limit*: receiving-institution requirements vary by branch, by year, and sometimes by individual intake officer. Verification is per-institution, not per-category.

---

## 4. The verify-versus-trust threshold

Verification is expensive. Verifying everything turns the engagement into a research project the client cannot afford. The discipline is to verify the load-bearing claims, not all of them.

A claim is *load-bearing* if:

- A downstream system depends on it for sequencing.
- A budget row uses it as a cost or timing input.
- A risk row treats it as a likelihood or impact assumption.
- The client is about to commit money, time, or an irreversible action on its basis.

A claim is *not load-bearing* if:

- It is contextual (the practitioner needs to understand it to ask good questions) but no plan element depends on it.
- It is downstream of another claim that has already been verified.
- The cost of being wrong is small and recoverable.

Working rule: every D-02 critical-path entry, every D-05 document row, and every D-06 risk row with high-impact rating needs an answer to *"what authority would confirm this?"* If the answer is "we have not asked," the claim stays a planning assumption (per [[m06-confidence-labels]]) and the verification path is part of the deliverable.

---

## 5. Worked example: the apostille-rule pattern

A common shape of error in relocation work, illustrated with a generic apostille scenario that recurs across pathways and countries:

**The inherited claim**: "Apostilles older than six months will be rejected." Found in three expat forum threads, two firm blog posts, and one prior client's anecdote. Confident-sounding. Routed into a D-02 planning row that builds the document timeline backward from filing date using a six-month freshness window.

**Diagnostic questions** (run against the four diagnostic moves from [[m08-reusable-circular-dependencies]] when the claim is part of a tangle, or run standalone otherwise):

- Is the source an authority? (Forums and blogs: no. Firm pages: possibly, but check date and jurisdiction.)
- Is the rule jurisdiction-specific? (Apostille acceptance is governed by the receiving authority, not the issuing one. The German consulate's rule and the Dutch IND's rule may differ.)
- Is the source dated within a window where the rule is likely still current? (If undated or older than 18 months in a fast-moving area, treat as stale.)
- Does any authority — government office or licensed provider — confirm the specific number for the specific pathway in question? (For Mason's Blue Card case: this is a question for the German consulate's published guidance and for immigration counsel.)

**The verification move**: route the question to one of the three authorities. For procedural questions of this kind, an immigration attorney serving the relevant pathway is usually the fastest path. Their response carries authority within their license; the response is then recorded with date, source, and form.

**The outcome**: often, the inherited claim is roughly right and the verification simply confirms it (planning assumption → provider estimate). Sometimes, the claim turns out to be wrong, stale, or pathway-specific in a way the inherited version did not capture. In either case, the plan now stands on something. Without verification, the plan stands on forum consensus, which is not standing on anything.

**The failure mode this prevents**: the client orders apostilles in February against a six-month-rule plan, and the consulate rejects them in October because the rule turned out to be different. The error is months old by the time it surfaces, and the cost is rework plus a slipped filing window. Verification at the time the rule entered the plan would have caught this.

---

## 6. When authority and provider disagree

Not rare, in practice. The government office's published guidance says one thing; the attorney's experience of how the office actually behaves says another. The destination bank's web page says one document list; the branch officer at intake asks for a different list. What to do.

**Working rule**: when an authority and a provider disagree, name the disagreement explicitly in the plan and route the decision based on which one will be the operative judge at the moment that matters. The bank branch officer is operative for the bank-opening procedure on the day of the appointment, even when the website says something different. The consulate's published policy is operative for the visa decision, even when an attorney's experience suggests informal flexibility.

**What the plan does**: prepare for the stricter of the two readings, and have the more flexible reading available as a fallback. Do not pretend the disagreement is not there.

**What the prose says**: explicitly: *"Source A says X; source B says Y. The plan prepares for X because the institution that will judge this is in the position to enforce X. If Y turns out to be operative, the plan absorbs the easier version without rework."*

**What this protects against**: the client following the more convenient reading and being caught by the stricter one at the worst moment. Many relocation failures are not "we did not know" but "we knew, in part, and bet on the convenient half."

---

## 7. Recording the verification

Every confirmation needs provenance. Verifications without recorded sources decay into half-remembered claims and are no better than the forum posts they replaced.

**Minimum fields**:

- Authority type: government / licensed provider / receiving institution.
- Specific authority: which office, attorney, branch.
- Date of verification.
- Form of verification: published guidance URL, email, consultation note, intake conversation.
- Scope: what specifically was confirmed.
- Decay note: when this confirmation might need refresh (e.g., "valid through filing date; refresh if filing slips past Q4 2026").

In case.yaml: the `provenance` field on a confirmation claim must carry these. A claim labeled "confirmed" without authority metadata is not a confirmation; it is a confidence label that lost its basis.

**Practitioner-facing benefit**: future Levi, working on a similar engagement six months later, can pull up the prior verification rather than re-asking. The knowledge accumulates instead of evaporating.

**Client-facing benefit**: when the client asks "why are we doing it this way?", the answer is a dated, named authority — not "I read somewhere" and not "I think." Trust survives questions.

---

## 8. Adjacent vocabulary

- **Authority**: the entity whose word actually determines the outcome. Three types (above).
- **Consensus**: aggregated reports from non-authorities. Useful for shaping questions; not load-bearing.
- **Inherited claim**: a claim entering the engagement from prior research, prior engagements, or general lore. All inherited claims start as planning assumptions until verified.
- **Decay**: the rate at which a verified claim degrades back toward uncertainty as conditions change.
- **Refresh**: re-verification of a previously confirmed claim that has decayed past confidence.
- **Verification path**: the specific next step that would upgrade a planning assumption to a provider estimate or confirmation. Pairs with [[m06-confidence-labels]].

---

## 9. How to use this in practice

**During D-00 drafting**: most claims at the intake brief stage are planning assumptions or inferences. That is correct; verification has not yet happened. The discipline at this stage is to mark each load-bearing claim with its verification path: *"to be confirmed with [authority] before [milestone]."*

**During D-04 provider conversations**: provider engagement is itself a verification opportunity. Bring the inherited claims that fall in the provider's scope and convert them from planning assumptions to provider opinions. Record the conversion.

**During D-05 document checklist drafting**: every document row needs an authority for its acceptance criteria. "Apostilled birth certificate" is not specific enough; the row needs to say *which receiving authority* will accept this and *what their stated requirements are* (or, if requirements are not yet verified, that they are not yet verified and routing through which provider).

**During D-02 finalization**: any critical-path entry whose timing depends on an unverified claim should not be treated as final. Either upgrade the claim, or explicitly mark the entry as planning-assumption-dependent and name the verification path.

**When inheriting prior research**: every inherited claim arrives as a planning assumption regardless of how confident the original source sounded. The discipline is to date-check, jurisdiction-check, and authority-check before treating it as anything stronger.

**Across engagements**: build the verification archive. Confirmed claims with intact provenance from prior engagements are the practice's compounding asset. Lose the provenance and the archive is just memory; keep the provenance and the archive is a tool.

---

## 10. Open questions (v0.1)

- **Verification budget.** Verification has a real cost in attorney hours, practitioner hours, and elapsed calendar. How much verification is included in the Roadmap Package vs. routed to Implementation Support? Working lean: D-00 through D-06 include verification of the *load-bearing* claims at the level the deliverables actually depend on; deeper verification is Implementation Support scope.
- **Recheck cadence.** A claim confirmed in May may need a refresh by August if the regulatory landscape moves. The right default cadence is unsettled. Lean: high-volatility categories (immigration rules in active reform, housing market) refresh quarterly within an engagement; stable categories refresh only on triggers.
- **"Verified by" field schema.** case.yaml should carry authority metadata on confirmations. The exact schema (free-text vs. structured enums for authority type, source, scope) is open. Probably structured enums for type and free-text for the specifics.
- **Authority conflict logging.** When government and provider disagree, the disagreement itself is a piece of knowledge worth keeping. Where should this live — in the row's notes field, in a dedicated `disagreements` collection, or both? Worth deciding before the first D-03 with material conflicts is delivered.
- **Authority-vs-receiving-institution priority.** The current note prioritizes the receiving institution for "will this work?" questions but the government authority for "is this allowed?" questions. The split is right but the language for explaining it to clients needs polishing.
- **The Mason test.** A regulatory-text-comfortable client will instinctively want to verify everything themselves. The methodology should welcome this (it is on-mission) without losing the structural role of the practitioner as the one routing claims to the right authority. Working approach: invite the client to bring their own verifications into the engagement record, with the same provenance discipline applied. Worth testing whether this scales or whether it produces conflict logs at the wrong level of detail.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
