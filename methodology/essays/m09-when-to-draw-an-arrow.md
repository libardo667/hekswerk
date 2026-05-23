# Methodology Note · When to Draw an Arrow

**Doc code**: M-09
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-01 Relocation Systems Map · D-03 Dependency Map · the studio's strength-driven visual differentiation per `control-surface-architecture_v2.md`

---

## 1. Why this doc exists

D-03 Dependency Map's most common failure mode is *starburst*: every system connected to every other system with comparable visual weight, the diagram dense enough to be impressive and useless at the same time. The honest read is that the practitioner has confused "this dependency exists" with "this dependency should render." Those are two different decisions.

The case data may capture every meaningful relationship across the engagement; that's the register's job, and the register should be complete. The visual map's job is different — it communicates the gestalt of how the move's systems hang together, which means it has to *choose* which arrows draw. An arrow earns its place when its presence helps the client understand sequencing, fragility, or leverage; an arrow that's drawn just because the relationship exists is visual debt.

This note specifies the discipline for that choice. The strength labels in the case schema (`critical | strong | moderate | weak`) are the input; the rendering rules are the output. The result is a D-01/D-03 visual that lets the client *read* the move's architecture in under a minute, with the register on call for the full picture.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 15 seconds per drafted relationship row.

---

## 2. Working definition

> *Drawing an arrow* is a rendering decision, not a relationship-existence decision. The relationship lives in `case.yaml` regardless of whether any view draws it. The view chooses to render an arrow when (a) the relationship is load-bearing enough that the client should hold it visually, and (b) drawing it improves the diagram's communicative gestalt rather than degrading it.

Two consequences flow from this framing.

First, the question "should this draw?" is *not* the same as "is this dependency real?" Real dependencies live in the register. Drawn dependencies live in the diagram. Most engagements have more of the former than the latter, by design.

Second, the strength label on a relationship is the *primary* input to the rendering decision but not the only one. Strength interacts with visual budget (how many arrows can the diagram carry before legibility collapses), with the dependency's role in the diagram's narrative (does it help the gestalt or distract from it), and with whether other artifacts already render the relationship (an arrow shown in D-02 may not need to repeat in D-03).

---

## 3. The "if this slips, what reacts?" test

The methodology's primary discrimination for whether a relationship is load-bearing enough to *exist* (and therefore belongs in the register) is the slip test from [[m04-leverage-points]] §3: if the source side of the relationship slips by a meaningful margin, does the target side have to revise? If yes, the relationship is real.

For *rendering*, the test runs at a finer grain:

1. **Does the slip trigger a downstream system to revise?** If yes, the relationship is at least *strong*; it has earned a place in the register and likely deserves to draw.
2. **Does the slip propagate to multiple downstream systems?** If yes, the relationship is *critical*; it almost always draws and almost always renders with visual emphasis.
3. **Does the slip cause a *category* of plan to change rather than just a sequence?** If yes, the relationship is structural — likely a leverage point relationship — and renders with the most prominent treatment available in the diagram.

The reverse direction matters too. If a downstream system *doesn't* react to the upstream slip — if it can absorb the slip with no replanning — the relationship may exist as background context but doesn't earn an arrow. The honest treatment is to leave it in the register and let the diagram breathe.

---

## 4. The four strength labels and what each implies for rendering

The case schema's strength enum maps directly to rendering treatment. Each label has a default rendering rule and a defensible deviation.

### Critical

The relationship is load-bearing across the engagement's spine. Slip on the source side requires plan revision on the target side, often cascading further. Critical relationships *always* draw on the view that owns them, and they render with visual emphasis (thicker stroke, more saturated color, or distinct styling per the visual grammar).

*Examples* (L.B. dogfood): housing-destination → registration-anmeldung; documents-credentials → immigration. (M.K. simulated stress test): sponsorship-letter → visa-appointment; housing-destination → registration-anmeldung; capacity → timeline-density.

*Defensible deviation*: a critical relationship may be omitted from one diagram if it's rendered prominently in another and showing it twice would clutter. For example, M-02's capacity → timeline-density may render as an axis overlay in D-02 (per [[m07-capacity-as-a-critical-strength-sequencing-constraint]]) and not as an arrow in D-03 — the same relationship, communicated more effectively as overlay than as arrow.

### Strong

The relationship requires meaningful coordination but may not cascade further. Strong relationships draw by default with standard visual treatment.

*Examples* (L.B.): banking → tax setup; physical-logistics → housing-destination move-in date. (M.K.): registration-anmeldung → banking.

*Defensible deviation*: a strong relationship may be moved to register-only if its diagram presence would crowd more important arrows. The discipline: if the diagram is choosing which strong arrows to draw, document the choice in working notes so future regeneration is consistent.

### Moderate

The relationship affects quality, cost, or stress but does not block progress. Moderate relationships are register-eligible; whether they draw depends on the diagram's narrative.

*Examples* (L.B.): language acquisition → professional network rebuild. (M.K.): language → bureaucratic literacy; identity-community → support structure continuity.

*Defensible deviation*: render moderates when they're part of a chain the diagram wants to surface (e.g., a soft-system chain that would otherwise be invisible), and omit them when the diagram is already at visual budget capacity.

### Weak

The relationship is contextually relevant but not load-bearing. Weak relationships live in the register or in prose. They do not draw by default.

*Examples* (L.B.): general weather → mood baseline; non-relocation-related hobby → recovery time.

*Defensible deviation*: render weak relationships only when illustrating a specific narrative point (e.g., a sidebar example) and clearly distinguish them in the visual grammar so the reader knows they're decorative rather than structural.

---

## 5. Directionality as a judgment call

An arrow has a head, and the head means something. The default reading is *temporal or causal direction*: A → B means A precedes B, or A enables B, or A's state affects B's state.

The practitioner judgment is which of those reads is operative for a given relationship. The same pair of systems can read three different ways:

- **Sequencing**: A must complete before B starts. (housing-destination → registration-anmeldung — Anmeldung requires a registration-eligible address)
- **Enabling**: A creates the conditions for B to be possible. (documents-credentials → immigration — credentials make the application viable, not just sequential)
- **State coupling**: A's ongoing state changes B's state. (capacity → timeline-density — capacity isn't a one-time gate, it modulates the whole plan)

The arrow's directionality should reflect the dominant reading. If the practitioner finds themselves drawing two arrows in opposite directions between the same pair, the relationship is probably either a circular dependency (see [[m08-reusable-circular-dependencies]] for resolution patterns) or a single bidirectional relationship that's being rendered as two arrows for emphasis.

Bidirectional rendering should be rare. Most apparent bidirectional dependencies turn out to be either a real circular structure (M-08 territory) or a single relationship the diagram is over-articulating.

---

## 6. Soft-system dependencies without starburst

Soft systems (capacity, identity, community, support structure, language, household alignment) are *connected to everything*. That's part of why they're soft systems — their dependencies are diffuse rather than gated. Rendering every soft-system dependency as an arrow produces a starburst from each soft-system node that obliterates the diagram.

The methodology's discipline for soft-system rendering:

- **Capacity** renders as an *overlay or axis indicator*, not as arrows from a capacity node to every other system. Per [[m07-capacity-as-a-critical-strength-sequencing-constraint]] and `control-surface-architecture_v2.md`'s capacity overlay schema, capacity's effect is shown by modulating the diagram (density bar, recovery-window markers, capacity-aware sequencing emphasis) rather than by drawing arrows.
- **Identity / community / belonging** render arrows only to the systems where their influence is *specifically* load-bearing (e.g., identity → destination-housing when neighborhood fit is a leverage point; not identity → everything). The register can hold the broader relationships in prose.
- **Language** renders an arrow when it has a sequencing or enabling effect (language → housing-search-feasibility for clients who'll handle the search themselves; language → bureaucratic-literacy for cases where the language is genuinely on the critical path). Otherwise register-only.
- **Support structure** renders to systems where continuity is operationally load-bearing (support-structure → capacity for clients with documented capacity-pattern; support-structure → therapy-continuity as a specific gated relationship). General "support matters" is in the register, not on the diagram.

The general rule: soft-system *importance* is captured by their presence as nodes with appropriate visual weight, not by drawing every relationship they touch. The diagram says "this is a system worth thinking about"; the register says "here's what specifically connects."

---

## 7. The visual budget

Diagrams have a finite legibility budget. Past some threshold, additional arrows degrade understanding rather than adding to it. The methodology's working budget heuristics:

- **D-01 Systems Map**: aim for ≤15 visible connections in the diagram. The map is supposed to communicate the *gestalt* of the systems; ≤15 lets the eye scan it in under a minute. Above 20, the map starts to read as decorative complexity rather than orienting structure.
- **D-03 Dependency Map (page 1)**: aim for ≤20 visible dependencies. D-03 carries more density than D-01 because dependency analysis is its job, but page 2 (the register) holds the full picture. The visual is for the gestalt of *what reacts when*; the register is for completeness.
- **D-02 Critical Path Timeline**: the budget is set by the lanes and the date range, not by a single arrow count. The same principle applies: every dependency arrow on D-02 should communicate sequencing pressure the eye needs to see; dependencies that don't change the visual sequencing belong in D-03's register, not on D-02.

When a diagram exceeds budget, the move is *not* to make the rendering cleverer (smaller arrows, fainter colors, layered groupings). The move is to demote some arrows to register-only and let the diagram breathe. The register is not a consolation prize — it's the proper home for relationships that don't earn visual presence.

---

## 8. Worked examples

### A relationship that obviously draws

> *housing-destination → registration-anmeldung*

Strength: critical. Slip test: if destination housing isn't secured (or isn't registration-eligible), Anmeldung cannot proceed, which gates banking, which gates business setup, which gates the entire DAFT cascade. Draws prominently on D-03; absent from D-02 only because D-02 represents the same constraint as a date dependency.

### A relationship that draws as an overlay, not an arrow

> *capacity → timeline-density*

Strength: critical. The relationship is structural — capacity modulates *every* timeline decision — but rendering it as an arrow from a "capacity" node to every other node creates the worst starburst the methodology can produce. The schema marks the relationship critical; the renderer expresses it as a density overlay on the D-02 axis (per [[m07-capacity-as-a-critical-strength-sequencing-constraint]]) and as soft-system positioning on D-01/D-03 (capacity as a present node, not a connected one).

### A relationship that belongs in the register, not the diagram

> *language → professional-network-rebuild*

Strength: moderate. Slip test: weaker language slows network rebuild but doesn't gate it. The relationship exists; it informs implementation support planning; it doesn't drive the diagram's narrative about sequencing or fragility. Register-only by default. Could draw if the diagram is specifically narrating soft-system chains, but otherwise leave it.

### A relationship that draws or doesn't depending on the client

> *destination-neighborhood → identity-community-fit*

For a client whose stated leverage point is queer-affirming community location, this relationship draws on D-01 and may even appear in D-02 as a sequencing gate around housing search. For a client whose neighborhood criteria are dominated by transit access and price, the relationship exists in the register but doesn't earn the visual real estate. Same relationship, different rendering, justified by which leverage points are active.

### A counter-example: don't draw every "everything is connected"

> *DAFT pathway → [every other system]*

Tempting to draw arrows from the DAFT pathway node to every system it touches. Tempting and wrong: it produces a starburst that says "DAFT is central" by means of visual chaos, when the diagram should say "DAFT is central" through node prominence and selective arrows to the genuinely gated downstream systems. The register can carry the full set of dependencies; the diagram carries the gestalt.

---

## 9. Adjacent vocabulary

- **Render** / **render decision**: the choice to draw a given relationship in a given view. Distinct from whether the relationship exists in case data.
- **Visual budget**: the diagram's legibility ceiling beyond which additional arrows degrade comprehension.
- **Starburst**: the failure mode of drawing every relationship a central node touches; signature of a diagram that's confused "complete" with "useful."
- **Gestalt**: the diagram's communicative whole; what a fresh reader sees in the first ten seconds.
- **Register**: the structured table of all dependencies. Complete; diagram is selective.
- **Overlay**: a non-arrow rendering of a relationship's effect (density bar, capacity band, status modulation).
- **Diagram narrative**: the specific thing this view is communicating about this engagement. Different from the methodology's general claims; each engagement's diagram tells *that* engagement's story.

Drawing an arrow is not the same as:

- **Confirming a relationship**: confirmation is a provenance question (see [[m13-verify-with-authority]]), separate from rendering.
- **Prioritizing a relationship**: priority is about which work gets done first; rendering is about which relationships the client sees in the visual.
- **Asserting causation**: an arrow indicates load-bearing influence in the direction shown; it doesn't claim metaphysical causation.

---

## 10. How to use this in practice

**During D-01 connection drafting**: every connection in the view's `connections[]` array should pass the slip test as at least strong. Moderates and weaks belong in the broader case dependency register, not on D-01. If D-01 currently has more than ~15 connections, the next refinement pass should demote the lowest-leverage ones to register-only.

**During D-03 dependency drafting**: the case-level `dependencies[]` array is complete; D-03's view-level `dependencies[]` array is curated. Critical draws; strong draws by default; moderate draws when it serves the diagram's narrative; weak doesn't draw. The page-2 register holds everything.

**During D-02 dependency drafting**: timeline arrows are for sequencing pressure visible across lanes. A timeline dependency that's structurally critical but doesn't actually change the visual sequencing belongs in D-03's register, not on D-02.

**During the projection step**: when regenerating a view from `case.yaml`, projection should not auto-add every load-bearing dependency to the view's curated subset. Per `control-surface-architecture_v2.md`'s projection behavior rules, "once a view has an intentional selected subset, projection preserves that subset rather than automatically adding every missing case entity." M-09 is the methodology behind that rule.

**During capacity overlay placement** (D-02 / D-03): the capacity-related dependencies render as overlay or density indicator, not as arrows. See [[m07-capacity-as-a-critical-strength-sequencing-constraint]] for the specific overlay treatment.

**During the walkthrough call**: if the client asks "why isn't X connected to Y on the diagram when they're clearly related?" — the answer is honest: the relationship is in the register; the diagram is curated for the gestalt. Show them the register. The question is *informative*, not a critique; it tells you which background relationships are alive enough in the client's head that they expected to see them.

**Across engagements**: track which curated subsets actually serve the diagram's job and which feel like accidents. The discipline matures as the practitioner's eye for "this arrow earns its place vs. this arrow is clutter" sharpens.

---

## 11. Open questions (v0.1)

- **The 15/20 budgets**: working heuristics, not enforced limits. Calibrate against the first 3–5 real engagements to see whether the numbers hold. Too-low budgets force premature demotion; too-high budgets reintroduce starburst.
- **Should weak relationships ever draw?** Working answer: only as explicit decorative or illustrative cases (e.g., a sidebar chain). Whether the renderer should support a "weak" visual class at all is unsettled; lean toward not rendering them by default.
- **Bidirectional rendering**: most apparent bidirectional dependencies are circular structures (M-08) or single relationships rendered twice. The renderer currently has no bidirectional arrow style; if real engagements surface true bidirectional load-bearing relationships, the renderer may need one. Defer until needed.
- **Visual differentiation between strength classes**: the renderer needs to make critical visibly distinct from strong, strong from moderate. The specific visual grammar (stroke weight, color, dash pattern) is a renderer decision rather than a methodology one; this essay sets the rule that strength must be visible, not how to make it visible.
- **Provider-gated vs. document-gated vs. legal-gated** dependency types: should the type be visually distinct (different arrow style) or only in the register's metadata? Lean: register-only metadata; the diagram's job is strength, not type. Test with real engagements.
- **How does diagram narrative interact with strength?** A moderate relationship can earn diagram presence when it serves the engagement's specific narrative. Whether that's an ad hoc judgment per-engagement or a structured field on the relationship (`render_in_diagram: boolean`) is unsettled. Lean: structured field with rationale, so the rendering choice is auditable.
- **Cross-deliverable consistency**: if the same relationship draws on D-02 and D-03, the strength shown should match. Tier 2 cross-deliverable drift checks (per `control-surface-architecture_v2.md`) should flag mismatches.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
