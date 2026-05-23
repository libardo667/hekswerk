# Methodology Note · The Complement Test Beyond Systems

**Doc code**: M-05
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-01 Relocation Systems Map · D-04 Provider Shortlist · the case-builder's system-promotion workflow

---

## 1. Why this doc exists

[[m01-what-counts-as-a-system]] §5 introduced the *complement test* as one of two heuristics for identifying systems: *"Is there a category of professional specialist who handles this?"* If yes, it's almost certainly a real system, because markets only specialize around real clusters. The complement test catches the systems the gut heuristic misses — language acquisition, credential recognition, cross-border tax — and is one of the methodology's most reliable discovery tools.

The trap: the complement test is a *discovery* tool, not a *promotion* rule. Professional specialties exist around many things that don't apply to a given client. School-placement consultants exist; the child-free household has no school-placement system. Pet relocation companies exist; the no-pet household does not need pet transport. Credential evaluators exist; an unregulated profession in the destination country doesn't need credential evaluation. Misreading the complement test produces D-01 maps full of dormant systems that look thorough and obscure the actual architecture of the move.

This note codifies the inverse discipline: how to recognize when the complement test surfaces a candidate that is *not* a system for *this* client, how to record the demotion without losing the consideration, and how the result flows through to D-01 and D-04. M-05 is the essay you reach for when drafting a Systems Map and asking "should this be on here?" The answer is sometimes no — and saying so explicitly is part of how the methodology stays honest.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 15 seconds per candidate system.

---

## 2. Working definition

> The *complement test* asks whether a professional specialty exists around a candidate cluster. The test discovers systems that *could* exist; it does not assert that they *do* exist for a given client. *Client circumstance* (household composition, destination rules, profession, timeline, risk tolerance, stated preferences) determines which candidates land as *active*, *dormant*, *latent*, or *ruled out* for the engagement. The methodology records the demotion decision explicitly rather than letting the candidate fall silently off the map.

Four landing states for any complement-test candidate:

- **Active**: the system is real for this client right now. Goes on D-01; appears in D-02 sequencing if it has dates; appears in D-04 if it needs provider specialists.
- **Dormant**: the system would exist if circumstances were different, but is currently not load-bearing. Tracked in case data with rationale; not on D-01's visual map; may appear in the companion document as an explicit non-system.
- **Latent**: the system isn't active now but could become active during the engagement's window under specific named conditions. Tracked in case data with the conditions named; watchpoint in D-02.
- **Ruled out**: the system genuinely doesn't apply. Documented once with rationale so the practitioner doesn't reconsider repeatedly; not on D-01; appears in D-04's "not currently needed" category list with a one-line note.

The default is *active* — when a candidate passes the M-01 six-criterion checklist *and* applies to the client's circumstance, it's a system. The four demoted states are the named alternatives when active doesn't fit.

---

## 3. The five circumstance criteria

Each candidate runs against these five before promotion to active. A candidate that fails one or more lands in one of the demoted states.

### 1. Household composition

Does the household actually contain the entity the candidate system orbits around? Children for school-placement; pets for pet transport; co-decision-makers for partner-alignment systems; cohabiting elders for aging-parent caregiving.

*Test*: name the specific household member or entity the system serves. If no such member exists, the system is ruled out.

*Failure mode*: building D-01 against a template household instead of the actual household. The template may have children, pets, and a working partner; the actual household may have none of those, and rendering those slots produces clutter that obscures what *is* there.

### 2. Destination rules

Does the destination's legal, regulatory, or institutional structure require this system to be navigated? Credential recognition for regulated professions in the destination; vehicle import for destinations that allow it on relevant terms; particular insurance categories that exist only in certain healthcare structures.

*Test*: the destination's actual rules, not generic relocation lore. See [[m13-verify-with-authority]] §3 — the receiving institution decides what's required.

*Failure mode*: importing requirements from a sibling destination. Many DAFT-pathway methodology assumptions don't transfer to Blue Card; many EU-Blue-Card assumptions don't transfer to Highly Skilled Migrant routes. Destination specificity matters.

### 3. Profession

Does the client's work fall into a category where the candidate system applies? Credential evaluation matters for regulated professions (medicine, law, engineering with certain regulators, accounting in certain destinations); it doesn't matter for unregulated knowledge work. Cross-border employment-of-record systems matter for clients whose employer requires it; not for self-employed or directly-employed clients.

*Test*: does the client's specific profession + destination intersection trigger the candidate? If unsure, verify with the destination's regulator or relevant licensing body before promoting.

*Failure mode*: assuming all knowledge workers face the same systems. A software engineer's profession-side systems are narrow; an attorney's are extensive; a healthcare provider's are different again.

### 4. Timeline

Does the engagement's timeline make the candidate live during the window the engagement covers? Some systems (e.g., long-term financial planning, eventual citizenship questions) exist for the client in the abstract but don't have action items inside the engagement window. These land *latent* — they'll matter, but not in the next 6–12 months.

*Test*: is there a decision or action the engagement needs to support for this system during the engagement's calendar window? If no, latent (with named re-trigger conditions).

*Failure mode*: cramming long-horizon systems into a short-horizon engagement. The engagement's job is the move; eventual-citizenship planning is post-move work in most cases.

### 5. Risk tolerance and stated preference

Has the client explicitly declined to engage a system, or chosen to defer it, with rationale? Some clients explicitly want to handle their own taxes; some want to defer permanent housing search; some want to skip community-building as an engagement scope. Stated preferences land candidates in *ruled out* with the client's framing recorded.

*Test*: did the client name the preference at intake or during the engagement, with rationale that holds up against the methodology's read of risk? If yes, honor and record.

*Failure mode*: overriding stated preference because the methodology thinks the system matters. The practice's job is to *surface* the system, not to insist on it. See [[m10-endorsement-creep]] for the related discipline on respecting client agency.

---

## 4. False positives the complement test surfaces

Common candidate systems that the discipline often demotes. Each carries a default state and the circumstance that flips it.

### School / dependent placement

*Specialist exists*: international school consultants, placement services.
*Default state for single-adult or child-free households*: **ruled out**.
*Flips to active when*: school-age children in the household.

### Pet transport

*Specialist exists*: pet relocation companies (Crown, Animals Away, etc.).
*Default state for pet-free households*: **ruled out**.
*Flips to active when*: any cohabiting pet, even small ones.

### Credential evaluation / recognition

*Specialist exists*: international credential evaluators (WES, etc.); destination-side recognition bodies.
*Default state for unregulated professions*: **ruled out** (with destination check).
*Flips to active when*: profession is regulated in the destination (often medicine, law, certain engineering categories, accounting in certain jurisdictions, teaching with state certification, social work, psychology).

*Note*: degree recognition for the *visa application itself* (e.g., demonstrating sufficient education for a Blue Card) is a *documents-and-credentials* system question, not a credential-evaluation-as-system question. The former is binary paperwork; the latter is an ongoing professional-licensing system.

### Real property disposition

*Specialist exists*: real estate agents, property managers.
*Default state for renters with no owned property*: **ruled out**.
*Flips to active when*: owned real estate of any kind (residence, investment, inherited, or property partway through sale).

### Partner alignment / cross-border employment for partner

*Specialist exists*: cross-border tax specialists for working partners; EOR (employer-of-record) services; immigration counsel for partner pathways.
*Default state for single-adult households*: **ruled out**.
*Flips to active when*: partner exists and has their own employment, immigration, or professional considerations.

### Caregiving obligations

*Specialist exists*: elder-care coordinators, family caregiving support, long-distance caregiving services.
*Default state when no caregiving relationship*: **ruled out** or **dormant** depending on family structure.
*Flips to active when*: client has named caregiving responsibility (parent, sibling, other dependent) whose situation the move affects.

### Vehicle disposition / import

*Specialist exists*: vehicle import services, automotive shippers.
*Default state when client has no vehicle*: **ruled out**.
*Default state when client has a vehicle that won't be imported*: **active** (as a *disposition* system) until resolved (sale, donation, transfer); then archive.
*Flips to active as an import system when*: the destination permits import on terms the client wants.

### Cross-border tax / equity

*Specialist exists*: cross-border tax CPAs, equity-compensation specialists.
*Default state for US-side clients moving to most destinations*: **active**. The exception is rare (e.g., a client with no US tax obligations to begin with, which is uncommon).
*Flips to ruled out only when*: client has named (and the practitioner has verified) that no cross-border tax complexity exists.

This category is the *inverse* of most of the list — the complement test correctly surfaces it for almost every US-side client. The discipline here is to confirm it's active early, not to demote it.

### Vehicle / mover / international shipping

*Specialist exists*: international movers, shipping services.
*Default state varies*: depends on whether the client is shipping household goods.
*Decision point*: shipping vs. sell-down. Often deferred during intake; flips between active and ruled out depending on the decision.

---

## 5. The "make sure to include" inverse

The complement test can also be *too narrow*. Some systems are real for the client but don't map cleanly to a single professional specialty, and a strict complement-test reading misses them. The methodology compensates by including these as systems even when the specialty side is fragmented or informal.

### Identity / community

*Specialty fragmentation*: the relevant specialists exist (identity-affirming therapists, community organizations, demographic-specific resource networks) but no single professional category orbits the system. A queer immigrant adult moving to a new city has community-building as a real system; no single "queer expat coach" specialty owns it.

*Methodology stance*: include as a system when identity is named at intake as load-bearing, even though the specialist landscape is informal.

### Soft-system support continuity

*Specialty fragmentation*: therapy continuity spans the therapist (professional, regulated) + the household + the home-side friend network. The relevant *specialty* (therapist) covers one slice; the system as a whole is broader.

*Methodology stance*: include as a system; record the specialist-handled slice (therapy continuity, professional support coordination) separately from the non-specialty work (household support, friend networks).

### Capacity / pacing

*Specialty fragmentation*: capacity work crosses ND coaching, chronic-illness coaching, occupational therapy, executive-function coaching, and various adjacent fields. No single specialty owns "capacity as a relocation-planning input."

*Methodology stance*: include as a system; it is what [[m07-capacity-as-critical-strength-sequencing-constraint]] and [[m15-capacity-as-a-non-pathologizing-risk-category]] codify. The complement test would miss it; the methodology insists on it.

### Household alignment

*Specialty fragmentation*: depending on the dynamic, the relevant specialty is couples therapy, family financial planning, parenting coordination, or co-decision-making facilitation. Each owns a slice; the system is broader.

*Methodology stance*: include as a system for any multi-decision-maker household; map specialty needs to slices.

### Meta-relocation

*Specialty fragmentation*: the practice itself (Hekswerk) is the specialty. By M-01's reasoning, this is a system because there's a specialty around it. The methodology shouldn't be coy about this — the meta-relocation work is part of D-01's architecture, often centered or implicit.

*Methodology stance*: the practice's engagement appears in D-01 as the practitioner-owned spine; not as a node like the others, but as the structure that holds them.

---

## 6. Recording the demotion

Demoted systems do not disappear. They're recorded explicitly so future Levi can see what was considered, and so the practitioner doesn't re-derive the same demotion across review cycles.

The shape:

```yaml
# In case.yaml, alongside the systems[] array:
not_currently_needed_systems:
  - id: school_placement
    label: School / dependent placement
    state: ruled_out
    rationale: Single adult household; no school-age dependents.
    flip_conditions: []
    source_ref: intake.module_a + intake.pre_engagement_brief
  - id: aging_parent_caregiving
    label: Aging-parent caregiving obligations
    state: dormant
    rationale: Family alive and cordial; not central to the move; mentioned at intake as not currently engaged.
    flip_conditions:
      - Parent health change requiring active coordination.
      - Client decision to bring caregiving into engagement scope.
    source_ref: intake.module_c
```

States are `ruled_out | dormant | latent`. Active systems live in the main `systems[]` array per the existing schema.

### D-01 treatment

Demoted systems do *not* appear on D-01's visual map. The map's job is the active architecture; cluttering it with placeholders for non-systems defeats the purpose.

The D-01 *companion document* may list demoted systems in Section 2 or as an appendix, with one-line rationale, so the client can see what was considered. The discipline: brief and matter-of-fact, not exhaustive. The companion shouldn't read as a list of every system the practitioner could have considered.

### D-04 treatment

D-04's Provider Needs Summary includes a "Provider categories not currently needed" section per the existing spec. Demoted systems with associated specialist categories appear here with one-line rationale. The client sees that the practice considered the category and ruled it out, which is part of the trust-building work the deliverable does.

### D-02 treatment

Latent systems with named flip conditions appear in D-02's Watchpoints (per the existing spec). The watchpoint names the condition; if the condition fires, the system re-enters active and D-01/D-04 update.

---

## 7. Worked examples

The M.K. (Mason Kirsch) simulated stress-test case (US → DE, Blue Card, single adult, August 2026 target) provides the clearest set of demotion decisions in the current dogfood material.

### M.K. — ruled out

- **School / dependent placement**: no children. *State*: ruled out. *Source*: pre-engagement brief, household composition.
- **Pet transport**: no pets. *State*: ruled out. *Source*: pre-engagement brief.
- **Real property disposition**: client is a renter in Atlanta; no owned property. *State*: ruled out. *Source*: deep-dive interview, housing-origin module.
- **Partner alignment / cross-border employment for partner**: single adult; no partner. *State*: ruled out. *Source*: pre-engagement brief.
- **Credential recognition / evaluation**: client is a software engineer (fintech); destination (Germany) does not regulate the profession in a way that requires credential evaluation. *State*: ruled out. *Note*: degree documentation for the Blue Card itself is a documents-and-credentials system question, separate. *Source*: deep-dive interview, immigration module; verified against Blue Card requirements.
- **Vehicle import**: client's vehicle in Atlanta will be donated, not imported. *Note*: this becomes a *vehicle disposition* sub-decision within physical logistics, not its own active system.

### M.K. — dormant

- **Aging-parent caregiving obligations**: family alive and cordial in Alabama; not central to the move; not currently engaged as caregiving responsibility. *State*: dormant. *Flip conditions*: parent health change requiring active coordination; client decision to bring family-coordination into scope. *Source*: pre-engagement brief, "what's making this hardest" + deep-dive Module C clarifications.

### M.K. — latent

- **Eventual citizenship / long-term immigration questions**: Blue Card → permanent residency path → eventual citizenship is a real long-term consideration but not active during the engagement window (engagement covers move + first 90 days; citizenship questions are years later). *State*: latent. *Flip conditions*: residence permit renewal timing approaches; client decides to pursue permanent residency on a specific timeline. *Source*: deep-dive interview, immigration module.

### M.K. — active (where the complement test correctly fires)

- **Cross-border tax / equity**: RSU vest July 15 + dual US/Germany filing obligations. *State*: active and high-priority. The complement test correctly identifies this as a system; the engagement needs a cross-border CPA per D-04 provider shortlist.
- **Immigration / Blue Card pathway**: employer-sponsored, but with client-side action (documents, apostille, visa appointment). *State*: active. Per M-01.
- **Healthcare / insurance**: gesetzlich vs. privat decision, GP registration, prescription continuity for ongoing therapy needs. *State*: active.
- **Therapy continuity / soft-system support**: the M-05 "make sure to include" inverse fires — therapy is a specialty, but the broader support-continuity system includes household, friends, and post-arrival community. *State*: active.

### M.K. — make-sure-to-include

- **Identity / community**: M.K.'s intake names identity context (autistic, late-diagnosed, single adult moving alone to a city where he knows almost no one); the complement test's specialty side is informal but the system is load-bearing. *State*: active per the M-05 inverse rule.
- **Capacity / pacing**: documented crash pattern, stated under-ask-then-overcommit. No clean specialty owns this; the system is critical per [[m07-capacity-as-critical-strength-sequencing-constraint]] and [[m15-capacity-as-a-non-pathologizing-risk-category]]. *State*: active.

### Counter-example from the L.B. dogfood case

For L.B. (US → NL, DAFT, partner-coordinated household):

- **Partner alignment**: would be *ruled out* for M.K., but is *active* for L.B. — the household has a co-decision-maker (Elie) whose work, immigration, and capacity profile are part of the move. Same candidate, different state, because circumstance differs.

The contrast is the point: M-05 isn't a static list of demoted candidates. It's a *per-engagement* discipline applied against each candidate.

---

## 8. Adjacent vocabulary

- **Candidate**: a system the complement test surfaces; not yet promoted.
- **Active**: the default landing state for candidates that pass circumstance criteria. On D-01.
- **Dormant**: candidate exists in the abstract but isn't load-bearing for this client now. Off D-01; in `not_currently_needed_systems[]`.
- **Latent**: candidate isn't active now but could become active during the engagement under named conditions. Watchpoint in D-02.
- **Ruled out**: candidate doesn't apply. One-line rationale; D-04 not-needed list.
- **Flip conditions**: the specific named circumstances that would move a candidate from dormant/latent to active.
- **Make-sure-to-include**: the inverse of the false-positive list — systems the complement test would *miss* because the specialty side is fragmented, but that the methodology insists on including.

The complement test is not the same as:

- **The gut heuristic** (M-01 §5): "damn, that's a lot to hold." The two are complementary discovery tools.
- **The six-criterion checklist** (M-01 §3): whether a candidate passes as a system at all. Complement test surfaces candidates; six-criterion checks them.
- **Promotion to leverage point** (per [[m04-leverage-points]]): leverage is about which active systems drive sequencing; M-05 is about which candidates become active at all.

---

## 9. How to use this in practice

**During D-00 intake**: as the practitioner runs the modules, internally track every candidate the complement test surfaces. Mark each as active, dormant, latent, or ruled out *with rationale* in working notes. Don't promote candidates silently; don't demote them silently either.

**During Phase 1 system identification (D-01 production Step 3)**: walk through the systems library from M-01 §4 systematically. For each candidate, run the five circumstance criteria. Active candidates go on the map; demoted ones go in the `not_currently_needed_systems[]` record with rationale.

**During the D-01 walkthrough**: clients sometimes ask "why isn't X on here?" — the answer is in the demotion record. Show them. The practice considered it; the rationale held; this is part of how the practice's thinking is auditable. See also [[m09-when-to-draw-an-arrow]] for the parallel discipline (why some relationships exist in the register but not on the diagram).

**During D-04 drafting**: the demoted-system list with associated specialist categories populates D-04's "Provider categories not currently needed" section. Be brief; one line per category with rationale. The discipline is to make the consideration visible without padding the deliverable.

**During mid-engagement re-evaluation**: latent candidates with flip conditions get re-checked when the named condition fires. The discipline is *to actually check* — a latent candidate whose flip condition fires but doesn't get promoted is a hidden gap.

**Across engagements**: track which candidates are most often demoted across the practice's case base. Patterns reveal which generic relocation-methodology assumptions the practice should actively question (e.g., "school placement" appearing as a default in generic methodologies because most clients have children; for Hekswerk's target audience, that's often not true).

**When uncertain**: when a candidate sits ambiguously between active and dormant, the methodology's lean is *active with low priority* rather than *dormant*. The cost of including a low-priority system on D-01 is small; the cost of demoting a system that turns out to matter is larger.

---

## 10. Open questions (v0.1)

- **`not_currently_needed_systems[]` in case.yaml**: the schema sketched in §6 isn't yet in `control-surface-architecture_v2.md`. Should be added in the next studio doc revision. Lean: separate array from `systems[]` to preserve the active/demoted distinction in projection.
- **Should demoted systems carry `provenance` / `source_ref` like other case records?** Working answer: yes, same shape as other case records. The discipline that protects active claims also protects demotion claims.
- **D-04 "not currently needed" length**: should this list cap at some number of entries to avoid bloat? Lean: no cap; the list naturally stays short because most candidates the practitioner internally considers don't reach the "worth recording publicly" threshold.
- **Re-evaluation cadence for dormant and latent candidates**: should the methodology enforce a periodic re-check (e.g., monthly), or rely on flip conditions firing? Lean: rely on flip conditions; periodic re-check turns into theater. But the engagement's monthly review pass should at least scan the demoted list.
- **Cross-engagement learning**: the demotion-pattern data across engagements is potentially valuable for sharpening the practice's defaults. How (or whether) to record this without violating privacy posture (per [[m12-privacy-posture]]) is unsettled. Probably anonymous, aggregate-only.
- **The "make-sure-to-include" list**: should be expanded as new engagements surface systems the complement test misses. Currently five entries (identity, soft-system support, capacity, household alignment, meta-relocation); calibrate against real engagements.
- **How explicitly to surface demotion in client-facing material**: D-04 currently does this; D-01 companion document might. The discipline is to surface enough that the client trusts the practice's thoroughness without padding the deliverable with non-content. Calibrate.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
