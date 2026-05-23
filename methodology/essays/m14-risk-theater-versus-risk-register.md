# Methodology Note · Risk Theater vs. Risk Register

**Doc code**: M-14
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-06 Budget & Risk Register · the studio's Tier 3 risk-completeness validator (per `control-surface-architecture_v2.md`)

---

## 1. Why this doc exists

D-06 Budget & Risk Register's most common failure mode is risk theater — a long list of named exposures that produces dread without producing action. A page of "things that could go wrong" reads as thoroughness to a careless author and as anxiety amplification to a careful client. It does not help anyone make decisions.

A useful risk register names a specific exposure, pairs it with a response (mitigation, contingency, or explicit acceptance), names the owner of that response, and gives the client an early-warning signal that tells them when the response should fire. Every row meets all four conditions or it is incomplete. Rows that don't meet them are theater regardless of how much detail they carry on the other dimensions.

This note specifies the four-constraint rule, defines the three response shapes (mitigation, contingency, acceptance), gives the tone discipline that keeps risk language operational rather than catastrophic, and specifies what the studio's Tier 3 risk-completeness validator should check. The schema for D-06's `risks[]` array in `control-surface-architecture_v2.md` is built around this discipline; this essay justifies the schema.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 20 seconds per drafted risk row.

---

## 2. Working definition

> *Risk theater* is the production of risk-shaped language without paired response. *A risk register* is a structured artifact in which every named exposure carries an explicit response (mitigation, contingency, or accepted with rationale), a named owner, an early-warning signal, and a status. The discipline is to refuse to ship the former while producing the latter.

The distinction matters because both forms can look identical at a glance. A row titled "Late apostille could delay filing" reads as risk-aware. Without a paired response, it's theater: it names the fear without giving the client anything to do about it. The same row with mitigation ("order apostille no later than [date]; confirm turnaround with provider before relying on it") and an early-warning signal ("if turnaround estimate exceeds 4 weeks at order time, escalate") becomes operational.

The methodology's position is unambiguous: **risks without responses are warnings, not register rows.** They belong in working notes until a response is identified; they do not belong in a delivered D-06.

---

## 3. The four constraints

Every row in the D-06 risk register must satisfy all four. A row missing any one is incomplete and gets held back from delivery (or marked explicitly as "monitor" with a planned date for response definition).

### Constraint 1 — Specific exposure

The risk names a *specific* failure mode, not a category of fears.

*Test*: can you complete the sentence "if this risk fires, what specifically happens?" with a concrete consequence? Not "things go wrong" — *what* goes wrong, *which* downstream system reacts, *what's* the visible signal.

*Failure mode*: vague-dread rows. "Immigration risk." "Housing risk." "Capacity risk." Each names a domain, not an exposure. They feel comprehensive (you've covered the topic) but provide no operational value.

### Constraint 2 — Named response

The risk carries exactly one of three response shapes:
- `mitigation`: a planned action that reduces the likelihood or impact before the risk fires.
- `contingency`: a planned action that takes effect *if* the risk fires.
- `accepted`: explicit acknowledgment that the risk is real, the response is to absorb the consequence, and the rationale is named.

*Test*: name the specific action the client (or owner) will take. If the answer is "we'll figure it out" or "we'll see what happens," the row is incomplete.

*Failure mode*: empty-response rows. The exposure is named (sometimes vividly) and the response field is blank, vague, or aspirational ("we'll be careful"). The row produces anxiety without giving the client a move.

### Constraint 3 — Named owner

Every response has an owner. The owner is the person who *does* the response when it's needed, not the person who *worries about* the risk.

*Test*: if this response fires tomorrow, who picks up the action? If the answer is "the client and Levi" without further specification, the row needs sharpening — which one initiates, which one executes, which one watches for the signal.

*Failure mode*: diffuse-ownership rows. Everyone is responsible, so no one is. The risk is "tracked" but unowned.

### Constraint 4 — Early-warning signal

The risk carries an observable signal that tells the owner the response should fire. Without a signal, the owner is doing constant vigilance — which is the same as no vigilance.

*Test*: name the observable thing. A missed appointment. A provider quote exceeding X. A specific date passing. A specific symptom from the client. A specific external event (regulator announcement, market shift). Not "things feel off" — a *thing*.

*Failure mode*: signal-less rows. The risk and response are well-defined but there's no trigger; the response is supposed to fire "when needed." This often means it fires too late (the client notices the problem after the response would have helped) or never (vigilance fatigues).

---

## 4. The three response shapes

Each row commits to exactly one. The shape determines what fields are required.

### Mitigation

A planned action that *reduces likelihood or impact* before the risk fires. The standard shape: identify the precondition that increases risk, take an action before that precondition lands, reduce the chance the bad outcome occurs.

*When to use*: risks where pre-action is cheaper than post-action and the cost of pre-action is bounded.

*Required fields*: `mitigation` text (the action), `owner`, `early_warning_signal` (what tells the owner to do the mitigation), `status`.

*Example* (from L.B. dogfood case):
> *Risk*: Apostille turnaround exceeds available window before visa filing.
> *Mitigation*: Order birth certificate and diploma apostilles no later than June 1, 2026. Confirm turnaround estimate with Georgia Secretary of State at order time; if estimate exceeds 4 weeks, escalate to expedited service.
> *Owner*: Client.
> *Early warning signal*: Order placed and turnaround estimate confirmed >4 weeks at intake.
> *Status*: active.

### Contingency

A planned action that *takes effect if the risk fires*. The standard shape: name the trigger condition, name the response to that condition, name what happens after the contingency executes.

*When to use*: risks where pre-action isn't possible or proportionate, but the response if the risk fires can be defined in advance to reduce reaction time and emotional load.

*Required fields*: `contingency` text (the if/then action), `owner`, `early_warning_signal` (the trigger), `status`.

*Example* (from M.K. simulated stress test):
> *Risk*: No registration-eligible short-term housing in Berlin secured before arrival.
> *Contingency*: If no housing with confirmed Anmeldung-eligible address is secured by July 10, 2026, escalate to backup providers in matrix section X and revise D-02 timeline to defer Anmeldung dependency-chain steps by 2–4 weeks.
> *Owner*: Levi (escalation), client (final housing selection).
> *Early warning signal*: July 10, 2026 calendar trigger; concurrently, weekly check of inventory in the connected housing-search providers as of July 1.
> *Status*: active.

### Accepted

Explicit acknowledgment that the risk is real, the response is to absorb the consequence rather than mitigate or hedge, and the rationale for accepting is named. Acceptance is *not* "we don't have a plan"; it's a deliberate stance with stated reasoning.

*When to use*: risks where mitigation and contingency are either unavailable, disproportionately expensive, or in tension with another design constraint the client has prioritized. Accepted risks are *part of the design*, not gaps in it.

*Required fields*: `accepted_rationale` (why acceptance is the right response), `owner` (still required — the person who absorbs the consequence), `status: accepted`.

*Example* (from L.B. dogfood case):
> *Risk*: Founder's own DAFT case encounters unanticipated regulatory friction that delays arrival beyond September 2026.
> *Accepted rationale*: The household has a multi-year savings runway and Elie's W-2 income continues regardless. The cost of further mitigation (engaging additional counsel, pre-staging in another country) exceeds the expected value at current likelihood. Delay is absorbed by extending Atlanta-side lease and letting Hekswerk launch timeline shift correspondingly.
> *Owner*: Levi (timeline-shift execution); household (lease-extension decision).
> *Status*: accepted.

Accepted rows are *especially* important to write well. A client reading "this risk is accepted" without rationale will reasonably worry that the practice has given up. The rationale makes acceptance a deliberate stance, not a default.

---

## 5. The tone discipline

Risk register language sits on a knife-edge. Minimize, and the row becomes false reassurance ("nothing to worry about here"); catastrophize, and the row produces dread without giving the client somewhere to put it. The right register is **calm, concrete, neither minimizing nor catastrophizing**.

Practical rules:

- **Name the exposure plainly.** No softening adjectives ("a small possibility that..."), no amplifying ones ("a serious risk of..."). Just the specific thing.
- **Quantify when possible, range when not.** "4–6 weeks beyond plan" beats "significant delay." "$1,500–$3,000 over budget" beats "expensive."
- **Use observable language for triggers.** "If the apostille hasn't shipped by June 7" beats "if things look behind schedule."
- **Match impact language to actual impact.** A row about apostille delay is operationally inconvenient; a row about pet quarantine is more emotionally weighted. Match the register to the actual weight rather than flattening to a single tone across the register.
- **Avoid disaster-framing.** "Could be catastrophic" / "worst-case scenario" / "everything could fall apart" rarely add information and reliably amplify anxiety. The reader knows risks are bad; the methodology's job is to make them tractable.
- **Capacity rows get special tone treatment.** See [[m15-capacity-as-a-non-pathologizing-risk-category]] — capacity risks locate failure in the plan's design, not in the client's character. The Tier 3 anti-pathologizing validator checks this register specifically.

The tone is not about hiding bad news; it's about not amplifying bad news beyond what's operationally useful. A row that triggers proportionate concern is doing its job. A row that triggers panic has overshot.

---

## 6. Worked examples — bad / better pairs

### From legal/document risk

**Bad** (theater):
> *Risk*: Immigration might go wrong.

Names a fear, not an exposure. No mechanism, no response, no signal.

**Better** (operational):
> *Risk*: Late apostille of birth certificate or diploma compresses DAFT filing window below safe submission timeline.
> *Mitigation*: Order both apostilles by June 1, 2026; confirm Georgia Secretary of State current turnaround at order time.
> *Contingency*: If turnaround exceeds 4 weeks, escalate to expedited service (additional $50/document); if exceeds 6 weeks, shift visa appointment booking by equivalent.
> *Owner*: Client (orders, escalations); Levi (timeline adjustment).
> *Early warning signal*: Turnaround estimate at order time > 4 weeks.
> *Status*: active.

### From housing/Anmeldung risk (M.K. case)

**Bad** (theater):
> *Risk*: Housing is risky.

**Better** (operational):
> *Risk*: Berlin short-term housing inventory in late July through August is fast-aging (per M-11) and may not produce registration-eligible options on the client's first-week-of-August arrival window.
> *Mitigation*: Confirm at least two pre-vetted options with confirmed Anmeldung eligibility by July 1, 2026, holding at least one as backup.
> *Contingency*: If no eligible option held by July 10, defer Anmeldung-dependent steps (banking, residence permit follow-up) by 2–4 weeks and extend short-term housing search.
> *Owner*: Client (housing selection); Levi (timeline revision).
> *Early warning signal*: July 1 checkpoint; concurrent weekly inventory checks starting July 1.
> *Status*: active.

### From capacity risk (paired with M-15)

**Bad** (pathologizing theater):
> *Risk*: Client may become overwhelmed during September.

This is both theater (no response) and pathologizing (locates failure in the client). Both problems compound.

**Better** (operational + non-pathologizing):
> *Risk*: September–November concentrates legal, housing, medical, pet, and logistics decision load; design currently assumes >12 hrs/week of client decision time during this window.
> *Mitigation*: Pre-decide deferrals before density peak (specific list in D-06 mitigation notes); externalize provider conversations to Levi where the engagement letter permits; protect at least 2 recovery days per week (Saturday–Sunday default; movable to fit client rhythm).
> *Contingency*: If actuals drop below 8 hrs/week of effective decision time, escalate to scope reduction (defer permanent housing search to post-arrival; consolidate provider conversations).
> *Owner*: Client (signal flag); Levi (deferral execution, scope adjustment).
> *Early warning signal*: Two consecutive missed provider appointments OR client-reported decision-queue >5 unresolved items OR sleep/recovery time below client-stated baseline.
> *Status*: active.

Note the row names the load the *plan* places on the client, not properties of the client. Triggers are concrete and client-reportable. Response is pre-decided.

### From accepted risk

**Bad** (vague resignation):
> *Risk*: Move might be delayed.
> *Response*: Accept the delay.

Acceptance without rationale reads as giving up. The client doesn't know whether the practitioner has thought about this or not.

**Better** (deliberate acceptance):
> *Risk*: Founder's DAFT case may encounter unanticipated regulatory friction delaying arrival past September 2026.
> *Accepted rationale*: Household runway absorbs delay (multi-year savings + Elie's continued W-2 income). Further mitigation (additional counsel, pre-staging in alternate jurisdiction) costs more than the expected delay damage at current likelihood. Strategy: extend Atlanta lease, shift Hekswerk launch timeline accordingly, treat delay as planned rather than crisis.
> *Owner*: Levi (timeline-shift execution); household (lease-extension call).
> *Status*: accepted (May 2026); revisit if regulatory friction surfaces or runway changes.

---

## 7. Subclasses worth naming

Not every risk has the same shape. Three specific subclasses get explicit handling.

### Capacity risks

Handled by [[m15-capacity-as-a-non-pathologizing-risk-category]]. The methodology's strictest tone discipline applies: failure is located in plan design, not client character. The studio's Tier 3 anti-pathologizing validator (per `control-surface-architecture_v2.md`) checks `risk_type: capacity` rows specifically.

### Low-probability, high-impact risks

These are real but rare: catastrophic regulatory shift, serious medical event, sudden political instability, family emergency. The temptation is either to over-detail them (theater amplification) or omit them (false reassurance). The methodology's stance: include them, write them tersely, name acceptance as the response with explicit rationale (usually some form of "this is what insurance / community / household runway is for"), and don't dwell.

A useful test: would the client be better served by reading this row, or by not having it in the document at all? If the row names something the client should know exists but can't usefully prepare for beyond what they're already doing, brevity is correct.

### Risks that gate leverage points

Some risks aren't just about plan execution — they affect whether a leverage point (see [[m04-leverage-points]]) can resolve at all. These risks deserve elevated visibility because their consequence is structural, not just delayed.

*Example*: a risk that the chosen visa pathway becomes unavailable mid-engagement. This isn't a delay risk; it's a *pathway-collapse* risk that forces the entire engagement to re-architect. Such risks should be flagged with `affects_leverage_point: [id]` in the schema so they can be surfaced in walkthrough discussion at higher priority.

### Risks the client has already accepted before engagement

Some risks are *already accepted* by the client's prior decisions — they engaged the practice knowing the risk existed. The methodology surfaces these as accepted rows with the client's own framing as the rationale. *"Client has accepted the founder-credibility risk of engaging a pre-launch practice; engagement letter Section X reflects this."* This makes the prior acceptance visible rather than implicit.

---

## 8. Adjacent vocabulary

- **Risk theater**: naming exposures without responses. The failure mode this essay addresses.
- **Risk register**: the structured artifact in which every exposure carries a response, owner, and signal.
- **Mitigation**: pre-action that reduces likelihood or impact.
- **Contingency**: if/then action that fires when the risk does.
- **Accepted (risk)**: explicit deliberate-stance acceptance with named rationale. Not the same as "ignored" or "unplanned."
- **Early-warning signal**: the observable trigger that tells the owner the response should fire.
- **Owner**: the person who executes the response, distinguished from "the person who worries about it."
- **Density peak**: a window where multiple risks could fire simultaneously (see [[m15-capacity-as-a-non-pathologizing-risk-category]]). The risk register interacts with density-peak planning.

Risk is not the same as:

- **Uncertainty**: lack of information. Uncertainty becomes risk when it has identifiable downside; not all uncertainty is risk-shaped.
- **Anxiety**: emotional response. The methodology takes anxiety seriously as a capacity input but does not let it shape risk-register content. A row exists or doesn't based on operational criteria, not on how much the client is currently worrying.
- **Worst-case planning**: scenario-building exercise. Useful as a separate exercise; not how the risk register is populated. Worst cases that have responses become rows; worst cases that have no possible response are not on the register (they may be in working notes or in walkthrough conversation).

---

## 9. How to use this in practice

**During D-06 risk-row drafting**: write the exposure first (specific, concrete, observable). Then the response shape. Then the owner. Then the signal. Then status. If any of the four is missing or vague, the row is not yet ready to ship — move it to a working-notes file with a planned date for completion.

**During D-06 review pre-delivery**: read every row through the four constraints out loud. Most theater fails the "specific response" or "observable signal" tests; both are easy to catch in review.

**During the walkthrough call**: do not present the register as a list to be acknowledged. Walk through 3–5 highest-priority rows explicitly, asking the client to react to each. Their reaction is the operational test of whether the row is well-framed. Vague concern from the client suggests the row hasn't given them traction; the response is to refine, not to reassure.

**During capacity-row drafting**: pair with [[m15-capacity-as-a-non-pathologizing-risk-category]] explicitly. The non-pathologizing rule is harder to honor in the moment than it sounds; the M-15 §3 checks must be run on every capacity row.

**During mid-engagement re-evaluation**: risks resolve, transform, and replace each other across the engagement. A monthly register review surfaces rows that have been overtaken by events (resolved, no longer relevant) and gaps where new risks have emerged but haven't been logged. The register is not a one-shot artifact.

**During acceptance decisions**: when accepting a risk, write the rationale as if explaining to a future Levi who has forgotten the context. *"This is accepted because [external constraint] and [household economics]; revisit if [trigger]."* Future Levi will thank current Levi for the explicit reasoning.

**For Tier 3 validator triage**: when the studio's risk-completeness validator flags a row, the most common fixes are:
- Add an early-warning signal (the row had everything else but no observable trigger).
- Specify the owner more precisely (the row said "everyone" or "client and Levi" without splitting).
- Convert an aspirational mitigation ("be careful") into a concrete action.
- Add accepted-rationale to a row that was accepted by default but not by decision.

---

## 10. Open questions (v0.1)

- **Likelihood and impact scoring.** D-06 schema currently lists `likelihood: low | medium | high | unknown` and `impact: low | medium | high`. Whether to enforce these on every row, allow them to be optional, or replace with a more nuanced shape (e.g., 1–5 matrix) is unsettled. Lean: required low/medium/high for v0.1; revisit if real engagements show the discrimination is too coarse.
- **Risk delta tracking across engagement phases.** A risk can be "active" in Week 3 and "resolved" by Week 10; the studio currently captures status but not history. Whether to track the transition explicitly is a v0.3 question.
- **How aggressive should the risk-completeness validator be?** Tier 3 in v0.2 currently warns; whether it should error at delivery is a judgment call. Lean: error at delivery (you should not ship D-06 with incomplete rows) but warn at draft (drafting needs to be friendly to in-progress thought). Implement as warn-only first; tighten if real engagements show theater leaking past the warning.
- **Walkthrough discipline for accepted risks.** Accepted risks are at risk of being skipped in the walkthrough because they're already "decided." But the client may want to revisit acceptance. Protocol: surface accepted rows explicitly in walkthrough and ask "does this acceptance still hold given what you know now?" before moving on.
- **Risk-cost interaction.** D-06 holds both budget and risk; some rows are pure-cost, some are pure-risk, and some are cost-with-risk (e.g., "FX exposure on capital deposit"). The schema treats these as separate arrays; the walkthrough may benefit from a combined view for the latter category. Pilot in real engagements.
- **Contingency-budget connection.** Mitigation and contingency often have costs; D-06 budget should reflect them. Currently the schema doesn't enforce that a contingency with cost implications also appears in the budget rows. Worth adding a Tier 2 drift check.
- **Disaster-class risks the client doesn't want named.** Some clients explicitly don't want to discuss catastrophic risks (sudden death, major illness, political collapse). The methodology should not force inclusion but should note in working files that the practitioner asked about scope and the client requested exclusion. This is a respectful-disclosure question.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
