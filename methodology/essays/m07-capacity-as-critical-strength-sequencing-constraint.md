# Methodology Note · Capacity as a Critical-Strength Sequencing Constraint

**Doc code**: M-07
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-02 Critical Path Timeline · D-03 Dependency Map (capacity overlay) · the studio's D-02 capacity density indicator per `control-surface-architecture_v2.md`

---

## 1. Why this doc exists

A relocation timeline that looks workable on the calendar can fail in execution because it asks the client for more bandwidth than they have. The technical sequence is valid; the operational sequence is not. The gap between the two is capacity — the client's available practical, cognitive, emotional, and bodily bandwidth across the windows the plan asks them to act in.

Most relocation methodologies treat capacity as a soft constraint, advisory rather than load-bearing. The Hekswerk methodology takes the opposite position: capacity is structurally equivalent to a legal deadline or provider gate. A timeline that ignores it is not a timeline; it's a wish. The studio's case schema already commits to this position — `dep_capacity_to_timeline_density` exists as a `strength: critical` dependency — but the essay that justifies the schema has been pending until now.

This note codifies why capacity earns critical-strength treatment, what capacity-respecting sequencing looks like in D-02 timeline decisions, and how the studio's D-02 capacity density indicator (currently named in `control-surface-architecture_v2.md` as "field TBD pending essay") should render. The companion essay [[m15-capacity-as-a-non-pathologizing-risk-category]] covers capacity in the D-06 risk register; M-07 covers capacity in the D-02 critical path.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 30 seconds per drafted timeline window or sequencing decision.

---

## 2. Working definition

> *Capacity as a sequencing constraint* is the methodology's stance that the client's available bandwidth across the engagement is a load-bearing input to D-02 at the same level as legal deadlines, provider lead times, and hard external dates. A timeline that is calendar-feasible but capacity-infeasible is *not* feasible. Capacity-respecting resequencing is the methodology's primary tool for translating calendar feasibility into operational feasibility.

Capacity is not the same as effort. Effort can be willed; capacity has to be respected. A client can decide to work harder; they cannot decide to have more bandwidth than their nervous system, household, or job permits. Treating capacity as effort is one of the methodology's most consequential category errors — it produces timelines that look ambitious and reasonable on paper and crash on contact with real weeks.

The methodology's position on capacity composes with [[m15-capacity-as-a-non-pathologizing-risk-category]]'s non-pathologizing rule: failure to respect capacity locates failure in the *plan*, not in the client. A capacity-overrun timeline is a plan that consumed its own assumptions about bandwidth. The fix is plan revision, not client exhortation.

---

## 3. Why critical-strength

The strength labels in the case schema (`critical | strong | moderate | weak`, per [[m09-when-to-draw-an-arrow]] §4) carry specific operational meaning. Capacity earns *critical*, not *strong* or *moderate*, for three reasons.

### 1. Capacity-failure cascades across multiple systems

A plan that exceeds capacity doesn't just slow down — it produces missed appointments, deferred decisions, skipped recovery, and (in clients with documented crash patterns) the full collapse pattern the engagement was supposed to prevent. The cascade is multi-system: legal-side appointments missed, housing decisions deferred, document orders forgotten, soft-system support eroded. Per [[m04-leverage-points]] §3's connectedness criterion, anything that cascades across three or more systems on failure is critical.

### 2. Capacity-failure is hard to recover from

A missed legal appointment can usually be rescheduled. A capacity collapse takes weeks to recover from — sometimes longer in clients with documented crash patterns (e.g., the L.B. dogfood case's 2023 six-week medical leave; the M.K. simulated case's stated under-ask-then-crash pattern). The recovery window itself becomes a sequencing constraint downstream. Critical-strength reflects the irreversibility of the failure mode, not just its likelihood.

### 3. Capacity-respecting plans are *better plans*, not weaker plans

A capacity-respecting timeline often takes longer than the calendar-feasible version. The naive read is that this is a trade-off — slower plan vs. more aggressive plan. The methodology's read is sharper: the capacity-respecting plan is the only plan that can actually execute. The "more aggressive" version isn't more aggressive; it's more *speculative*. Critical-strength treatment makes that visible — capacity-respecting resequencing is a feature of the plan, not a concession against it.

---

## 4. The five capacity-respecting sequencing moves

When a draft D-02 timeline asks more capacity than the client has in a given window, the methodology has five moves. Most plans use several in combination.

### 1. Defer

Move non-critical work out of the high-density window into a later window where capacity is higher. The classic example: deferring permanent housing search until after arrival, when temporary housing has stabilized the basic-life systems (per [[m16-stabilize-before-optimize]]).

*When to use*: when the work isn't actually critical-path for the current window and can be moved without cascading consequences.

*Failure mode*: deferring critical-path work creates downstream compression. Defer freely from the optimization pile; defer cautiously from critical path.

### 2. Delegate

Route work to a provider, the practitioner, or another household member rather than the client. The classic example: provider conversations the practitioner can run on the client's behalf (with the engagement letter's permission), reducing the client's decision-load during a density peak.

*When to use*: when someone other than the client can hold the cognitive and execution load without quality loss. The provider's expertise often makes delegation strictly better, not just bandwidth-cheaper.

*Failure mode*: delegating decisions only the client can make. Practitioners can hold information, schedule, and follow-up; they cannot hold the client's values for them.

### 3. Sequence earlier

Move work *backwards* into a lower-density window where it's currently absent. The intuition is counterintuitive — earlier is harder in many timeline frameworks because earlier feels premature. Capacity-aware sequencing recognizes that *premature execution at high capacity beats on-time execution at low capacity*.

*Classic example* (L.B.): apostille order moved from "when we need it" timing to "as early as the documents allow," because apostille timing has slack on the upstream side and the alternative is a high-density window in pre-departure month.

*When to use*: when the work has *slack* on its upstream side (the inputs are already available) and is *gated only by execution capacity* downstream.

*Failure mode*: pulling work earlier than its inputs are ready, producing rework when the inputs land.

### 4. Reduce parallel work

Serialize what could theoretically be parallel. The trade is calendar time for cognitive bandwidth — sequential execution of two pieces of work that could run in parallel costs more total calendar time but less peak cognitive load.

*Classic example* (M.K. anticipated): document apostilles + visa appointment preparation + housing search are technically parallelizable, but the simultaneous cognitive load exceeds capacity for the client's stated weekly bandwidth. Sequencing them into a defined order reduces peak load.

*When to use*: when parallel execution is technically possible but the peak load violates the client's stated capacity. Trade calendar deliberately.

*Failure mode*: serializing things that genuinely need to be in flight together (e.g., apostille and visa appointment that both have lead time pressure). The discipline is to identify the *true* parallelism floor, not assume everything can be serialized.

### 5. Build recovery windows

Block calendar windows that are explicitly *not for relocation work*. The recovery window is not a luxury; it's structural. Without recovery, density peaks compound and the next window's capacity is already eroded before it starts.

*Classic example* (L.B.): two recovery days per week protected during the pre-departure density peak, even when the calendar pressure is high. The recovery isn't earned by work completion; it's pre-allocated.

*When to use*: any window where density is approaching the client's stated capacity ceiling. The recovery should be *visible in D-02* (as a calendar block, an axis annotation, or a watchpoint), not implicit.

*Failure mode*: treating recovery as "if we have time," which means recovery never happens because plans always expand to fill available time. Pre-allocate or it doesn't exist.

---

## 5. Resequencing versus drift

These look identical from a date-shift perspective and are methodologically opposite.

### Resequencing

A *deliberate* adjustment of the timeline made by the practitioner and client together, in response to a capacity signal, with a documented rationale and an updated plan. The plan is now *different* in a specific way, with a reason. Future review can see what changed and why.

Markers of resequencing:
- Triggered by a named capacity signal (intake-stated bandwidth, observed signal during engagement, documented crash pattern, density peak forecast).
- The new sequence is documented in case data with provenance pointing to the resequencing decision.
- The client is aware of the change and has accepted it (or driven it).
- Downstream dependencies are checked and updated.

### Drift

An *unmanaged* slippage of timeline dates because the client fell behind, the practitioner didn't catch it, and the plan quietly degraded. The dates move; the rationale doesn't exist; downstream consequences accumulate as surprises.

Markers of drift:
- No documented capacity signal triggered the slippage.
- The plan still says one thing while actuals say another.
- Downstream cascades are discovered later, often at a moment that forces emergency mitigation.
- The client may not be aware the plan is no longer the plan.

The methodology's job is to convert drift into resequencing in real time — when a date is slipping for capacity reasons, name it, document the resequencing decision, and update downstream. Drift unmanaged is the failure mode; drift caught early is just a resequencing opportunity.

---

## 6. Capacity signals from intake to D-02 decisions

D-00 (per `control-surface-architecture_v2.md`) captures capacity signals as first-class `capacity_signals[]` in case data. M-07's job is to translate those signals into D-02 timeline decisions.

Common signal → response mappings:

- **Stated weekly bandwidth ceiling** ("I can give about 8–10 hours/week to this") → D-02 windows assume that ceiling; windows whose decision load exceeds the ceiling trigger one of the five sequencing moves.
- **Documented crash pattern** (prior burnout, medical leave, overcommit-then-collapse history) → recovery windows pre-allocated more aggressively; density peaks reduced via deferral + delegation; the plan's high-density windows are flagged as watchpoints.
- **Capacity-shaped preferences** (written-first communication, async-over-sync, prefer fewer larger decisions to many small) → communication cadence in D-02 reflects the preference; sync calls scheduled at lower-density windows; decision batches consolidated.
- **Soft-system support continuity** (therapy continuity, household co-regulation, community contacts) → support-structure events appear in D-02 as protected calendar items, not as work to do.
- **Identity-specific load** (ND, chronic illness, queer-marginalized — disclosed as capacity context) → density peaks treated with extra resequencing margin; per-week ceiling treated as soft maximum, not target.

The studio's `capacity_signals[]` array captures these as structured records; D-02 projection should respect them rather than treating the timeline as bandwidth-blind.

---

## 7. The D-02 capacity density indicator

The studio's D-02 currently renders timeline events, dependency arrows, watchpoints, and the next-30-days strip. `control-surface-architecture_v2.md` names "M-07 (scaffold) capacity density indicator alongside the axis; field name TBD pending essay" as forward work. This essay defines the indicator's shape.

### What it shows

A density profile along the D-02 axis showing, for each window, the *concentration of decision-load* the plan asks of the client. Computed from the timeline's event density (point events + range events overlapping that window) weighted by event kind (decisions cost more than confirmations; cross-system decisions cost more than within-system ones).

The indicator is *not* an attempt to quantify bandwidth precisely — that would imply false precision the methodology rejects. It's a *visual heuristic* that surfaces density peaks where capacity-respecting attention is needed.

### Visual treatment

A band running along (or below) the D-02 axis showing relative density across the timeline. Higher density = more saturated color or thicker band; lower density = lighter or thinner. Threshold markers at:
- The client's stated weekly capacity ceiling (sourced from `capacity_signals[]`).
- Pre-allocated recovery windows (shown as explicit gaps in the density band).
- Watchpoint triggers (where density crosses the threshold).

### What it enables

When a draft D-02 is rendered, the density indicator immediately shows whether any window violates the stated capacity ceiling. The five sequencing moves (§4) become *visibly applicable* — the practitioner can see exactly where deferral, delegation, sequencing, parallel-reduction, or recovery-building is needed.

The indicator also feeds into [[m14-risk-theater-versus-risk-register]]'s capacity-risk row authoring: density peaks visible on the axis correspond to specific capacity risk rows in D-06 with concrete early-warning signals.

### Field name and schema

Working name: `axis.capacity_density`. Shape (sketched, to be refined in studio implementation):

```yaml
axis:
  capacity_density:
    enabled: true | false
    source: capacity_signals  # or explicit override
    weekly_ceiling_hours: <number from capacity_signals or override>
    recovery_windows:
      - start: <date>
        end: <date>
        label: <optional>
    threshold_markers:
      warning_at: <fraction of ceiling, default 0.8>
      ceiling_at: <fraction of ceiling, default 1.0>
```

The indicator is opt-in via `enabled` because not every engagement needs it surfaced visually; some clients' capacity profiles are uniform enough that the overlay would add noise rather than signal.

---

## 8. Practitioner capacity as internal constraint

The methodology's discipline about capacity applies to the practitioner as well. A practice running at 97% capacity utilization (per the revenue projection's Scenario 3) is a practice that has no slack for revision cycles, emergency engagements, methodology development, or recovery — which means client work degrades.

[[m15-capacity-as-a-non-pathologizing-risk-category]] §8 covers practitioner capacity as an internal-only risk category. M-07's complement: practitioner capacity is a sequencing input to *which engagements the practice takes on in which windows*. The practice's calendar should run the same five sequencing moves against its own engagement load:

- **Defer**: a new engagement starting later when the current engagement's density peak is high.
- **Delegate**: not yet possible at sole-practitioner scale, but a forward consideration.
- **Sequence earlier**: pre-engagement scaffolding (Pre-Engagement Brief, scheduling) moved earlier in calendar to spread practitioner load.
- **Reduce parallel work**: cap concurrent engagements rather than treating practitioner bandwidth as elastic.
- **Build recovery windows**: practitioner-side calendar blocks honored as structural, not advisory.

This is internal-visibility material per [[m12-privacy-posture]]; practitioner capacity decisions are not part of client-facing deliverables. But the discipline composes with client-side capacity work — a practice that respects its own capacity is the practice clients in the target audience can actually rely on.

---

## 9. Worked examples

### L.B. dogfood case (US → NL, DAFT)

**Decluttering across checkpoints, not pre-departure month**

Original draft: decluttering compressed into the four weeks before departure, when household activity is already at peak. Capacity-respecting revision: decluttering spread across six fortnightly checkpoints starting six months before departure, with each checkpoint scoped to a specific room or category. Result: pre-departure month decision-load reduced by ~30%, decluttering quality higher (no panic-decisions about keep-or-toss).

**Permanent housing deferred until after arrival**

Original draft: permanent housing search starts six weeks before arrival, concurrent with apostille work, attorney conversations, capital deposit, and household wind-down. Capacity-respecting revision: only temporary registration-eligible housing secured before arrival; permanent search deferred to post-Anmeldung (per [[m16-stabilize-before-optimize]]). Result: pre-arrival cognitive load reduced; permanent search happens with better information (lived experience of neighborhoods) and lower simultaneous load.

**Vehicle donation chosen over private sale**

Original draft (implicit): private sale of vehicle for higher proceeds. Capacity-respecting revision: donation, accepting lower proceeds in exchange for the eliminated cognitive overhead of listing, scheduling viewings, negotiating, and managing transfer paperwork. Result: ~$3k in foregone proceeds against ~15–20 hours of cognitive load eliminated during a window where every hour matters more than its dollar value.

### M.K. simulated stress test (US → DE, Blue Card)

**September–November density peak**

Plan as initially sketched: legal, housing, medical, pet, logistics all running concurrently during August–November. Capacity-respecting revision: explicit pre-decided deferral list (decluttering deferred to per-month checkpoints; non-acute medical decisions deferred to post-arrival; permanent housing search deferred to post-Anmeldung); recovery windows pre-allocated (2 days/week minimum during peak); high-load communication routed through Hekswerk where engagement letter permits. Result: a peak that's still genuinely demanding but operationally feasible against M.K.'s stated under-ask-then-crash pattern.

**RSU vest + tax conversation sequenced earlier**

July 15 RSU vest creates a known tax decision point. Default draft might leave the cross-border CPA conversation to "when convenient." Capacity-respecting revision: cross-border CPA engaged by early June, conversation completed before the RSU vest, decisions held against the timeline instead of triggering reactive decisions in July. Result: the July 15 date arrives with decisions already made; no last-minute decision-load.

### Counter-example: a technically feasible plan that ignores capacity

A pre-departure compression in which every relocation system has its work crammed into the last six weeks because that's when "the move feels real." Technically the calendar permits it; operationally it's a near-guaranteed crash for any client with stated capacity constraints. The plan looks decisive on paper; the plan is speculative. The methodology rejects it not because the dates don't fit but because the bandwidth assumption is wrong.

---

## 10. Adjacent vocabulary

- **Capacity**: available practical, cognitive, emotional, and bodily bandwidth across a given window.
- **Load**: what the plan asks of capacity in a given window.
- **Density peak**: a window where multiple systems require simultaneous attention; the place capacity-respecting sequencing earns its keep.
- **Recovery window**: a calendar block explicitly reserved for non-relocation work. Pre-allocated; not earned by completion.
- **Resequencing**: deliberate, capacity-aware adjustment of the timeline with documented rationale.
- **Drift**: unmanaged slippage of timeline dates for capacity reasons; the failure mode.
- **Sequencing move**: one of the five (defer / delegate / sequence earlier / reduce parallel / build recovery) used to translate calendar-feasible into capacity-feasible.
- **Capacity-density indicator**: D-02's axis-level overlay surfacing decision load per window. New in M-07.

Capacity is not the same as:

- **Effort**: willable. Capacity is structural.
- **Motivation**: separate dimension. Highly motivated clients can still hit capacity ceilings.
- **Discipline**: separate dimension. Highly disciplined clients can still hit capacity ceilings.
- **Project management skill**: the methodology doesn't critique the client's planning ability; it critiques plans that don't respect bandwidth.

---

## 11. How to use this in practice

**During D-00 intake**: surface capacity signals explicitly. Capture stated weekly bandwidth, prior crash patterns, support-structure continuity, and capacity-shaped preferences as `capacity_signals[]` records (per [[m02-reading-the-room]] for the discipline of capturing these without pathologizing).

**During D-02 drafting**: draft the calendar-feasible version first, then run the density check. Every window where decision load exceeds the stated bandwidth ceiling triggers one or more of the five sequencing moves. Document the move in working notes; the resequenced version becomes the actual plan.

**During D-02 rendering**: the capacity density indicator (when enabled) surfaces peaks visually. If a peak crosses the warning threshold without an accompanying sequencing move or recovery window, the timeline is incomplete.

**During the walkthrough call**: walk the density indicator with the client. Ask: *"this window shows X hours/week of decision load against your stated ceiling of Y; does that feel right? What would you defer or delegate if you had to?"* The conversation surfaces both calibration on the indicator and pre-decided deferral candidates.

**During mid-engagement re-evaluation**: when actuals diverge from plan, the first diagnostic is capacity, not effort. Did a window's actual load exceed the assumed load? Did a sequencing move not fire when it should have? Was a recovery window violated? Each of these is a *plan* diagnosis, not a *client* one (per [[m15-capacity-as-a-non-pathologizing-risk-category]]).

**During projection from case to view**: D-02 projection should respect the `capacity_signals[]` array. If a projected timeline window shows density exceeding the stated ceiling, projection surfaces a Tier 2 warning (per `control-surface-architecture_v2.md`) — the case data and the view are consistent, but the view is asking more than the case data says the client can give.

**Across engagements**: track which sequencing moves fire most often per engagement type. Pattern recognition over time sharpens the practitioner's eye for which moves apply where, and whether the methodology's defaults need adjustment.

---

## 12. Open questions (v0.1)

- **Density-indicator computation**: the heuristic for weighting events by kind (decisions vs. confirmations, cross-system vs. within-system) needs empirical calibration. Lean: start with equal weighting in v0.2; adjust when 3–5 real engagements show patterns.
- **Weekly ceiling source**: capacity signals can express a ceiling as a number (e.g., "8–10 hours/week") or qualitatively ("not much in September"). The indicator needs numeric input; conversion of qualitative signals is currently a practitioner judgment call. Unsettled.
- **Recovery window granularity**: pre-allocated recovery windows can be days, half-days, or weeks. The renderer needs to handle all three. Probably granularity-aware visual treatment; defer specifics to studio implementation.
- **Indicator opt-in**: is the indicator on by default with an opt-out, or off by default with an opt-in? Lean: off by default; opt-in via `axis.capacity_density.enabled` when the engagement's capacity profile is genuinely uneven enough to warrant visual surfacing.
- **Sharing the indicator with the client**: should the rendered density indicator appear in the client-facing D-02, or only in the practitioner-internal version? Lean: client-facing for engagements where capacity is an explicit named concern (most of Hekswerk's target audience); internal-only for engagements where surfacing it would feel performative.
- **Practitioner-side capacity rendering**: should there be an analogous indicator for the practice's calendar across engagements? Out of scope for v0.2; revisit if engagement concurrency becomes a real planning question (i.e., when the practice has ≥3 concurrent engagements).
- **Compositional consistency with M-15**: D-02's density indicator and D-06's capacity risk rows should be consistent — the same density peak should drive both the indicator's threshold-crossing and the risk row's early-warning signal. Cross-deliverable validation (Tier 2) should check this. Detail in studio implementation.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
