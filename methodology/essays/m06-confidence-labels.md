# Methodology Note · Confidence Labels

**Doc code**: M-06
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-02 Critical Path Timeline · D-05 Document Readiness Checklist · D-06 Budget & Risk Register · case.yaml date and quantity fields

---

## 1. Why this doc exists

A relocation plan that looks more certain than it is, is worse than a plan that admits what it does not know. False precision invites the client to commit emotionally and financially to dates and figures the plan was never confident about, and produces a plan-failure narrative when those numbers move — when the honest reading was always "this is our best current estimate."

D-02 and D-05 in particular are full of dates and quantities. Some are confirmed (a booked attorney appointment), some are provider estimates (an apostille turnaround range), some are planning assumptions (when the destination housing market will produce viable options), and some are explicit client preferences (the desired departure window). Treating all four the same in the visual artifact is the failure mode. This note specifies a labeling discipline that makes the differences visible.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 15 seconds per drafted row.

---

## 2. Working definition

> A *confidence label* marks a date, range, or quantity with the basis on which it should be trusted. Labels are: *confirmed*, *provider estimate*, *planning assumption*, *client preference*, and *monitor/unknown*. Every load-bearing date or figure in a delivered artifact must carry one.

Confidence labels operate alongside provenance categories (see [[m03-inference-versus-statement]]). Provenance answers "where did this claim come from?" Confidence answers "how much should you trust it?" The two compose: a confirmed claim with a named source carries the most weight; a planning assumption without a verification path carries the least.

The discipline is small and visible. The client sees the labels, learns what they mean once, and after that can read the plan with calibrated trust per item.

---

## 3. The five labels

### Confirmed

The date or quantity comes from a booked appointment, signed agreement, official document, or provider commitment with a named contact and date. Confirmations are the highest-confidence claim the plan makes.

*Required provenance*: source, date of confirmation, named contact where applicable.

*Decay*: confirmations can degrade. An attorney's quoted lead time, confirmed in May, may not survive into August if the attorney's caseload changes. Confirmation has a half-life; the plan should note it when relevant.

*Visual treatment*: solid bar in the timeline, no surrounding range, distinct color.

### Provider estimate

The date or range comes from a specialist with relevant expertise, but is not a commitment. Apostille turnarounds, mover availability windows, immigration counsel processing estimates, vet certificate scheduling — all are typically provider estimates rather than confirmations.

*Required provenance*: which provider, when stated, in what form.

*Decay*: provider estimates age. They were the provider's read on the world at the time of speaking. See [[m11-provider-research-aging]] for the aging discipline.

*Visual treatment*: range bar with the provider source noted in the legend or tooltip.

### Planning assumption

A Hekswerk-generated estimate used to build a workable draft when no provider or authoritative source has weighed in yet. Planning assumptions are explicit working figures, not hidden guesses. They are honest about being placeholders.

*Required provenance*: the basis of the assumption (prior engagements? public-source aggregate? practitioner estimate?), and the verification path (when and how this will be upgraded to provider estimate or confirmation).

*Decay*: planning assumptions are expected to be upgraded as the engagement proceeds. A planning assumption that has not been upgraded after its planned verification date is a red flag.

*Visual treatment*: dashed bar or hatched fill, with the assumption explicitly named in the companion document.

### Client preference

A date the client has stated they want, distinct from a date that has been externally validated. A target arrival of August 15 is a client preference until it is anchored to a flight, a lease, or a sponsor-side commitment.

*Required provenance*: where the client stated this (form, quote, conversation), and what would convert preference into anchored date.

*Decay*: client preferences are usually the most stable category — the client is unlikely to forget what they wanted — but they are also the most likely to be quietly overruled by the world.

*Visual treatment*: marker rather than bar, distinct from anchored dates; the visual difference is the whole point.

### Monitor / unknown

A field that the plan has identified as material but cannot yet estimate. Naming "monitor/unknown" is more honest than inventing a planning assumption when no basis exists.

*Required provenance*: what would let this become a planning assumption or estimate, and roughly when.

*Decay*: monitor/unknown fields should resolve into one of the other four labels by the time the engagement reaches the relevant phase. A monitor/unknown that persists past its window is a planning gap.

*Visual treatment*: gap or "?" marker; visible without being alarming.

---

## 4. Worked examples

From the Mason Kirsch dogfood test case (Atlanta → Berlin, Blue Card pathway, target August 2026 arrival):

### A timeline row, in five versions

**Without a label**: *"Blue Card application processing: 8 weeks."*

This is the failure mode. The client reads it as a fact. The plan inherits it as a fact. When it turns out the processing window is closer to 12 weeks for this employer's volume at this consulate this quarter, the plan looks wrong rather than appropriately uncertain.

**As planning assumption**:

> *"Blue Card application processing: 8–12 weeks (planning assumption, not established fact). Basis: public-source aggregate from comparable employer-sponsored Blue Card cases, May 2026. Upgrade path: confirm with employer mobility team and/or immigration counsel before D-02 is finalized."*

The plan can use the figure. The client knows the figure is provisional. When it changes, the plan adapts without losing trust.

**As provider estimate**:

> *"Blue Card application processing: 9–11 weeks (provider estimate). Source: employer mobility team, May 10, 2026, based on Q1 2026 actuals at this consulate."*

Stronger claim. Plan can sequence more confidently.

**As confirmed**:

> *"Blue Card application filed: June 3, 2026 (confirmed). Decision received: August 4, 2026 (confirmed)."*

After-the-fact, both endpoints are confirmed. The processing-time row may now be archived rather than displayed.

**As client preference**:

> *"Target arrival: August 15, 2026 (client preference). Anchored: not yet. Conversion path: contingent on Blue Card decision date and Atlanta lease end (June 30, 2026, confirmed)."*

The August 15 date is real — the client said it — but the plan does not pretend it is anchored. Mason's lease end is confirmed; his arrival date is not.

### A document row

> *"Apostilled birth certificate: order by June 1, 2026 (planning assumption: 3–4 week turnaround from Georgia Secretary of State; verify before relying on this for filing date). Status: monitor — order not yet placed."*

The label discipline forces the practitioner to be explicit: this is an assumption *and* a monitor. Two labels in one row, because the row carries both an estimate that needs verification and a status that needs to advance.

### A budget row

> *"Berlin temporary housing, first 30 days: €3,500–€5,000 (planning assumption: range from public-source aggregate of mid-tier serviced apartments, May 2026). Upgrade: refine after provider shortlist in D-04."*

The range is wide. The range is honest. Tightening it before any provider has been asked would produce false precision; widening it later would erode trust. The label says "this is the right shape of estimate for this point in the engagement."

---

## 5. The upgrade trail

A claim's life in the plan is typically:

`monitor/unknown` → `planning assumption` → `provider estimate` → `confirmed`

Not every claim travels the full chain. Some skip steps; some never reach confirmation because confirmation is not available; some remain client preferences throughout because the client retains decision authority.

The discipline:

- When a claim upgrades, its label changes and its visual treatment changes. Both the case data and the view data update; see [[m01-what-counts-as-a-system]] on the case/view distinction.
- The history of upgrades is preserved in case.yaml so that the engagement can trace how a number moved from "we guessed" to "we know."
- A claim that downgrades — confirmation that lost its basis, provider estimate that turned out to be stale — must downgrade visibly. Quietly retaining a confirmed label after the basis evaporates is the worst failure mode in this discipline. See [[m11-provider-research-aging]] for the aging discipline that catches this.

This trail also dictates the verification path embedded in each label: every non-confirmed label should have an answer to *"what would upgrade this, and when?"* A planning assumption without a verification path is a hidden assumption with a label sticker on it, which is worse than no label.

---

## 6. Why this discipline reduces both rework and anxiety

**Rework**: when an unlabeled date moves, the plan has to be rebuilt because every downstream sequencing decision relied on the appearance of certainty. When a labeled date moves, only the dependents that explicitly relied on the locked-in case need to update; rows that were already sequenced around a planning assumption can absorb the change.

**Anxiety**: clients who feel the plan is honest with them tolerate uncertainty better than clients who feel the plan is hiding it. A confirmed date next to a planning assumption tells the client where to focus their attention and where to relax. A plan where everything looks the same forces the client to be vigilant everywhere.

This is especially load-bearing for clients like Mason (autistic, thorough, regulatory-text comfortable) who will *notice* when the plan papers over uncertainty. Such clients will respect a labeled assumption far more than an unlabeled date that turns out to be wrong, because the labeled assumption is congruent with how they themselves process information. The discipline is also a fit signal — clients who find the labels condescending or excessive are surfacing a fit mismatch the practitioner should hear.

---

## 7. Adjacent vocabulary

- **Provenance**: where the claim came from. Confidence labels and provenance are paired disciplines. See [[m03-inference-versus-statement]].
- **Anchor**: a date locked by an external commitment. Anchors are typically confirmed and have low-decay.
- **Range**: a date or quantity expressed as a band rather than a point. Most provider estimates and planning assumptions should be ranges, not points.
- **Verification path**: the specific next step that would upgrade a label. Every non-confirmed label has one or should.
- **False precision**: presenting a range as a point, or an assumption as a confirmation. The primary failure mode this discipline addresses.

---

## 8. How to use this in practice

**During D-02 drafting**: as each date or range is entered, attach a label. The drafting question is not "what is the date?" but "what is the date, and how do we know?" If the second question has no answer, the label is monitor/unknown — which is itself useful information.

**In the visual timeline**: the legend should explain the five labels in plain language, with a worked example of each. The visual differences between labels (solid bar, range bar, dashed, marker, gap) should be obvious without color (clients may print, or may have color-vision differences) and clear with color.

**In D-05 document checklist**: every row carries a label for its turnaround estimate and a label for its current status. Two labels per row sounds heavy but is right — they answer different questions.

**In D-06 risk register**: cost ranges and risk likelihoods carry confidence labels. A risk register full of planning assumptions reveals where provider conversations would tighten the picture; this is itself useful for planning [[m04-leverage-points]].

**During walkthroughs**: explicitly call out where the plan is leaning on planning assumptions and what the verification path is. The client should leave the walkthrough knowing which figures are firm and which are working numbers awaiting upgrade.

**Across the engagement**: review label states at each phase boundary. Any planning assumption that has not been upgraded along its planned verification path needs either an upgrade or an explicit note that it will remain a planning assumption — and why.

---

## 9. Open questions (v0.1)

- **Field scope.** Should confidence labels live on every case entity or only timeline, document, and budget fields? Working answer: any field that drives a sequencing or commitment decision. System inventory entries probably do not need labels per se; their constituent dates do.
- **Labeling cardinality.** Some rows want two labels (e.g., a document with a status and a turnaround estimate). Should case.yaml normalize this with `status_confidence` and `estimate_confidence` as distinct fields, or treat it as a single composite label? Lean: separate fields, because they decay independently.
- **"Confirmed" vs. "client-stated".** A client says "I have a vet appointment on June 14" — is that a confirmation, a statement, or a client preference? Working answer: it is a confirmation *of what the client said* (a statement) but not a confirmation of the underlying reality (the appointment may move, the client may have misremembered). When practical, ask for the source artifact (the vet's confirmation email) to upgrade from statement to confirmation. When not practical, treat as confirmed-on-client-report and note the caveat.
- **Visual treatment for color-vision differences.** Currently planning to use shape (bar vs. dashed bar vs. marker) as the primary distinction, with color as reinforcement. Untested on real clients.
- **Studio validators.** A useful validator is "no row in D-02, D-05, D-06 has a missing confidence label." A second is "no label has been static past its planned verification date without an explicit note." Both are mechanical and feasible.
- **Mason-specific test.** A regulatory-text-comfortable client may find five labels too few or too many. Working bet: five is right for most clients, and Mason in particular will appreciate the discrimination. Verify in walkthrough.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
