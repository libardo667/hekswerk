# Methodology Note · Endorsement Creep

**Doc code**: M-10
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-04 Provider Shortlist · the studio's Tier 3 endorsement-language validator (per `control-surface-architecture_v2.md`)

---

## 1. Why this doc exists

D-04 Provider Shortlist is the deliverable where the practitioner is most likely to slide, without noticing, from *researcher* into *recommender*. The slide is gradual, the language drifts slowly, and the final product can read as a list of vouched-for providers when the spec says it's a list of candidates worth evaluating. The legal and reputational exposure of that drift is real; the methodological cost is greater. A practice that *says* it doesn't recommend providers, but writes provider rows in the voice of someone who does, has quietly broken its own scope discipline.

D-04's existing `boundary_note` field carries the explicit non-vouching disclaimer ("Shortlisted means worth evaluating, not endorsed. Provider availability, pricing, scope, licensing, and fit must be confirmed by the client before hiring."). That note is good. It is also insufficient on its own — a single footer cannot rescue a matrix whose rows have crept into endorsement language. The discipline has to operate per-row, in the prose the client actually reads.

This note defines the four-step gradient from observation to vouching, gives explicit language patterns for each step, names the failure modes that pull drafts toward endorsement, and specifies what the studio's Tier 3 endorsement-language validator should check.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 20 seconds per drafted provider row.

---

## 2. Working definition

> *Endorsement creep* is the gradual drift of provider-row language from *factual observation* (what's verifiable about the provider) through *practitioner opinion* (what the practitioner thinks about the fit) into *recommendation* (what the client should do) and finally *vouching* (the practitioner's reputation backing the provider's performance). The methodology operates at the first step; it is permitted to make the second step explicit; it does not make the third or fourth.

The discipline is not "say nothing about providers" — that would produce a useless deliverable. The discipline is to be *crisp about which step a given sentence is at*, and to mark practitioner-opinion sentences as opinion rather than letting them read as factual.

A useful inversion: D-04's job is to make the client a *better evaluator of providers*, not to do the evaluation for them. The shortlist narrows the field; the client makes the call. Every row should ask itself: am I helping the client evaluate, or am I performing the evaluation on their behalf?

---

## 3. The four-step gradient

Each step has a language register, a test for whether a sentence belongs at that step, and the line that triggers drift to the next step.

### Step 1 — Factual observation

What's verifiable from primary sources: the provider's stated practice area, published fee structure, geography served, languages of operation, licensing status, named partners, public reviews, articles, professional registrations.

*Language pattern*: declarative, sourced, dated.
- *"This firm states DAFT as a practice area on their site, last checked May 14, 2026."*
- *"Hourly rate published as €180 ex VAT on the firm's services page."*
- *"Bar registration confirmed via NL Bar Association directory, 2025 entry."*

*Test*: could a different practitioner verify this claim from the same source in five minutes? If yes, it's factual observation.

*Drift trigger*: when the language stops citing a source and starts implying a practitioner judgment ("this firm handles DAFT" without a source becomes "this firm is good at DAFT").

### Step 2 — Practitioner opinion (when explicit)

What the practitioner concludes from observation, marked as opinion. Practitioner opinion is *allowed* in D-04 because the practice's value-add includes synthesis — but it must be marked, not laundered into apparent factuality.

*Language pattern*: opinion-marked, hedged, scoped.
- *"My read is the firm's published practice list emphasizes employer-sponsored work; whether they handle self-employed DAFT actively is worth confirming."*
- *"The fee structure appears transparent compared to peers I've researched, but I haven't engaged them personally."*
- *"Fit notes: the firm's public-facing language uses gender-neutral pronouns in client materials, which may matter for queer-identifying clients; verify in your own initial conversation."*

*Test*: does the sentence carry an explicit "I", "my read", "appears", "may", or equivalent opinion marker? If no, it has drifted to recommendation.

*Drift trigger*: removing the opinion marker. "My read is they handle DAFT well" → "They handle DAFT well" is the slide from Step 2 to Step 3.

### Step 3 — Recommendation (out of scope)

What the practitioner thinks the client *should* do. The methodology does not operate here.

*Language pattern* (the patterns to *avoid*):
- *"This firm is a good fit for you."*
- *"I recommend reaching out to them first."*
- *"You'll want to work with this lawyer."*
- *"Pick this provider over the other two."*

*Test*: does the sentence assert action or selection on the client's behalf? If yes, rewrite as Step 2 (practitioner opinion the client can weigh) or Step 1 (factual observation the client can verify).

*Drift trigger*: from Step 3 the next slide is to vouching, where the practitioner's reputation gets attached to the provider's future behavior.

### Step 4 — Vouching (forbidden)

The practitioner's reputation backing the provider's performance. This is what the practice explicitly does not do.

*Language pattern* (forbidden):
- *"I can vouch for them."*
- *"They've never let a client of mine down."*
- *"You can trust them."*
- *"If they say it, take it as gospel."*

*Test*: does the sentence make the practice the implicit guarantor of the provider's future actions? If yes, delete and rewrite.

*Drift trigger*: vouching has no further drift because it's already at the limit. The methodology's response is unambiguous removal.

---

## 4. Worked examples

From the L.B. dogfood case (US → NL, DAFT pathway) and the M.K. simulated stress test (US → DE, Blue Card).

### A single provider row, in four versions

**Step 1 — Factual observation (default register)**

> *"Adam & Wolf · Boutique immigration law firm, The Hague, NL. Stephan Roelofs leads DAFT practice; 30+ years immigration law experience per firm bio. Fee structure: €180/hour, 5-hour retainer paid in advance; full DAFT-with-family case estimated at 6–7 hours per Roelofs (May 2026). Bar registration: NL Bar Association, confirmed via directory. Last checked: May 14, 2026."*

Every claim sourced or dated. This is the default register for D-04 matrix rows. It does the most work with the least exposure.

**Step 2 — Practitioner opinion (marked)**

> *"Fit notes: my read is Adam & Wolf is a strong-fit candidate for clients prioritizing experienced solo-attorney attention over packager efficiency; the fee structure is transparent and competitive against the boutique peer set. I've engaged this firm personally for my own DAFT case; that's a single data point, not a track record."*

Opinion is named; personal experience is disclosed; the disclosure makes the data point's limitations explicit. The client can weigh the opinion against their own priorities.

**Step 3 — Recommendation (over the line)**

> *"Adam & Wolf is the right firm for you. Stephan is excellent. You should reach out to him first."*

Three sentences, three Step-3 violations. The methodology rewrites these as Step 1 or Step 2.

**Step 4 — Vouching (forbidden)**

> *"I vouch for Stephan personally. He won't let you down."*

Delete. Rewrite as Step 2 if the underlying observation is worth preserving (e.g., "my read is the firm has responded thoughtfully in our engagement so far"), or delete entirely.

### Personal experience disclosure

When the practitioner has direct experience with a provider — engaged them for the practitioner's own move, received a referral and heard back, observed them through another client's engagement — the experience matters but must be disclosed with scope. The four disclosure shapes:

- **None.** Provider is on the matrix from research only. State so: *"I have not worked with this firm personally."*
- **Direct engagement.** Practitioner has been a client. State explicitly, including the limitations of one data point: *"I engaged this firm for my own DAFT case starting March 2026; my experience is a single sample, not a track record."*
- **Referred and heard back.** Practitioner has referred clients (or peers) and received feedback. State the indirect channel: *"I have referred two prior contacts to this firm; both reported responsiveness and clear scope, but neither engagement is mine to characterize beyond what they shared."*
- **Personal relationship.** Practitioner has a non-engagement personal relationship (friend, former colleague, community contact). State the relationship explicitly: *"Disclosure: the principal at this firm is a former colleague; my read of their work is shaped by that prior context."*

The methodology is *more comfortable* with disclosed bias than with unstated bias. A row that says "disclosure: this is my own attorney" carries less endorsement-creep risk than the same row written as detached research because the prospect can calibrate accordingly.

### Counter-example: when factuality reads as endorsement

Sometimes a Step 1 sentence drifts toward endorsement through accumulation, even when each individual claim is sourced:

> *"This firm has 30 years of experience, a transparent fee structure, NL Bar registration, and partners with deep DAFT experience including ex-IND counsel."*

Each clause is verifiable. Together, the sentence reads as a pitch. The fix isn't to delete the claims — they're true and useful — but to break them apart and avoid the pile-on register. A list-of-facts presented as bullet points reads as data; the same facts strung together with "and"s read as a sales pitch.

---

## 5. The two writing-discipline failures

Most endorsement-creep failures fall into one of two patterns. Identifying them in the moment is the practitioner's main defense.

### Failure 1 — Adjective inflation

Adjectives are where Step 1 drifts toward Step 2 without the opinion marker that would make the drift legitimate. *"This firm has DAFT experience"* (Step 1) becomes *"This firm has strong DAFT experience"* — "strong" is an unmarked opinion. The fix is either remove the adjective ("This firm has DAFT experience, with X years of practice in that area per firm bio") or mark it explicitly as opinion ("My read is the firm's DAFT experience is strong relative to the peer set I've researched").

Watch words: *strong, weak, solid, excellent, reliable, trustworthy, responsive, professional, experienced, dedicated, thorough, careful, sloppy, expensive, reasonable.* Each of these can be Step 1 if sourced ("the firm describes itself as 'experienced'" with citation) or Step 2 if marked ("my read is the firm appears experienced based on..."), but unmarked they slide.

### Failure 2 — Verb directness

Imperative or directive verbs ("reach out to," "engage," "consider," "evaluate," "explore," "talk to," "schedule with") quietly shift the row from a candidate description into a directive. *"Reach out to this firm for an initial consultation"* is a Step 3 sentence even if everything around it is Step 1.

The fix is to make the directive *optional and client-owned*: *"If you choose to evaluate this firm, an initial consultation is the appropriate next step; their published intake process is X."* The verb register shifts from imperative to conditional, and the client's agency is preserved.

---

## 6. The boundary note is necessary but not sufficient

D-04's `boundary_note` field carries the explicit non-vouching disclaimer. Every D-04 delivery includes it. Without it, the deliverable lacks the explicit scope statement that protects both client and practice.

But the boundary note is a *floor*, not a *defense against drift*. A matrix full of Step 3 / Step 4 language with a footer that says "shortlisted means worth evaluating, not endorsed" is the worst possible combination: the practice has said the right thing in the footer and contradicted it in the body. A discriminating reader (which includes regulators, professional-misconduct reviewers, and the prospect's own attorney) will read the body, not the footer.

The defense against drift is per-row discipline. The boundary note states the scope; the rows have to honor it. Tier 3 validation (per `control-surface-architecture_v2.md`) is the studio-side enforcement: keyword and pattern checks on `category_notes` and `outreach_prompts` flag drift toward Step 3/4 language for practitioner review before delivery.

---

## 7. What the studio's Tier 3 endorsement-language validator should check

Specifications for the validator (to be implemented per the v0.2 milestone in `roadmap_v2.md`):

### Flagged patterns (warning tier)

Sentences in `category_notes` or `outreach_prompts` containing any of:

- Unmarked adjectives from the watchlist above (strong, excellent, reliable, etc.) outside of quoted material.
- Imperative verbs ("reach out to," "engage with," "pick," "choose") without conditional framing.
- First-person directives ("I recommend," "I suggest," "you should," "you'll want to").
- Vouching phrases ("trust them," "won't let you down," "I can vouch," "rest assured").

### Flagged structures (warning tier)

- Provider rows lacking a `last_checked` date (the M-11 freshness field — drift toward endorsement often correlates with stale rows being defended past their freshness).
- Provider rows with personal-experience claims but no explicit disclosure of the relationship.
- `category_notes` exceeding a length threshold without any opinion markers (suggests Step 1 → Step 2 drift through volume).

### Validator behavior

Warnings, not errors. The validator catches drift before delivery walkthroughs; it does not block exploratory drafting. False positives are expected (an adjective in a quoted client statement, for example) and easily dismissed. The cost of a false positive is a second's review; the cost of a missed drift is a credibility hit at delivery.

When the validator fires repeatedly on a single row, the row is probably written from the wrong register. The fix is usually to rewrite from Step 1 + explicit Step 2, not to silence the validator.

---

## 8. Adjacent vocabulary

- **Endorsement**: the practice attaching its reputation to a provider's future performance. Forbidden.
- **Recommendation**: the practice telling the client which provider to choose. Out of scope.
- **Opinion**: the practitioner's read of fit or quality, marked as opinion. Permitted with explicit marking.
- **Observation**: a verifiable factual claim about the provider, sourced or dated. The default register.
- **Drift**: gradual slide from observation to opinion to recommendation through unmarked language.
- **Disclosure**: an explicit statement of the practitioner's relationship to the provider, scoped to its limits (one engagement is one data point; a personal relationship is a bias not a credential).
- **Boundary note**: D-04's explicit non-vouching footer. Necessary; not sufficient on its own.

Endorsement creep is not the same as:

- **Provider research quality**. A row can be well-researched and still drift to endorsement; a row can be light on research and still hold the discipline.
- **Provider aging** (see [[m11-provider-research-aging]]). Aging concerns whether the row's claims are still current; endorsement creep concerns whether the row's language has stayed in the right register.
- **Privacy posture** (see [[m12-privacy-posture]]). Endorsement creep is about how the practice talks about providers; privacy posture is about what information the practice retains. Adjacent but distinct.

---

## 9. How to use this in practice

**During D-04 matrix drafting**: write rows in Step 1 register by default. Cite the source and date every load-bearing claim. Resist the urge to add adjectives. The matrix is for client evaluation, not practitioner conclusions.

**During category-notes drafting**: this is where Step 2 (practitioner opinion) is most appropriate, because category notes are explicitly synthesis. Mark every opinion sentence with "my read is," "appears," "in my judgment," or equivalent. Watch the cumulative register — three marked-opinion sentences in a row can still read as a recommendation through volume.

**During outreach-prompt drafting**: outreach prompts are templates the client uses to contact providers. They should center the *client's* voice and questions, not the practitioner's evaluation. *"You may want to ask about..."* (client-owned framing) beats *"Ask them about..."* (imperative). The prompt's job is to help the client conduct their own evaluation conversation.

**During boundary-note drafting**: keep it short, explicit, and present in every D-04 delivery. The exact wording can flex, but it should always assert: (a) shortlisted is worth evaluating, not endorsed; (b) provider availability, pricing, scope, licensing, and fit must be confirmed by the client; (c) the practice receives no commissions or referral fees (assuming this remains true).

**During personal-experience disclosure**: be explicit. If the practitioner has engaged a provider, name it. If the practitioner has a personal relationship, name it. Disclosed bias is methodologically clean; undisclosed bias is the failure mode this whole essay exists to address.

**During the walkthrough call**: when discussing the matrix with the client, the practitioner's verbal language is *also* subject to the gradient. Verbal Step 3 / Step 4 ("I'd really go with this one") undoes the written discipline. Use the walkthrough to surface client questions about the matrix; resist closing those questions with verbal endorsement.

**Across engagements**: track whether providers on D-04 matrices turn out well or badly in actual client engagements. This is the practice's longitudinal data on provider fit. It does *not* become public testimonial — it informs future matrix drafting and personal-experience disclosure shape. See also [[m11-provider-research-aging]] on how to fold real-engagement feedback into matrix rows over time.

---

## 10. Open questions (v0.1)

- **The boundary-note exact wording.** Current language is functional but slightly formal. Worth testing against early prospects to see whether the framing lands or feels legalistic. Lean: keep the explicit non-endorsement assertion; soften the surrounding register if early feedback suggests it reads as defensive.
- **Personal experience disclosure threshold.** When is the practitioner's prior contact with a provider substantial enough to require disclosure? Lean: any engagement, any referral the practitioner heard back from, and any personal relationship triggers disclosure; passing acquaintance does not. The line is fuzzy and may shift with experience.
- **Validator false-positive tolerance.** Tier 3 endorsement-language validator will catch some quoted material, some idiomatic uses, and some legitimate Step 2 language. The false-positive rate determines whether practitioners dismiss the validator (bad) or treat it as helpful nudging (good). Calibrate against the first 3–5 D-04 deliveries.
- **What about implementation support.** If the practice provides Implementation Support (a paid scope beyond the Roadmap Package), the practitioner is closer to the provider's actions and the endorsement-creep risk increases. May need a separate sub-discipline for how D-04 language shifts during Implementation Support. Defer until Implementation Support is a real product.
- **Commission and referral-fee policy.** The boundary note currently asserts the absence of commissions. If the practice ever takes a commission or referral fee, the entire endorsement-creep discipline shifts — disclosed bias around incentive is a different methodological problem. Lean: keep no-commission as a policy commitment; revisit only if the economics force a re-examination.
- **Cross-provider comparison.** D-04 matrices sometimes invite comparison ("which of these three should I use?"). The methodology's answer is "you, after evaluating each on the questions in the category notes." Whether that's enough or whether the matrix needs explicit comparative dimensions (a comparison table?) is unsettled. Lean: no comparison tables in v0.1; surface this if real engagements show clients struggling to compare cleanly.
- **Walkthrough verbal discipline.** The written discipline is clear; the verbal one is harder. May need a short pre-walkthrough internal note: "do not verbally close on a specific provider during this call." Worth piloting.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
