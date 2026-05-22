# Methodology Note · Inference Versus Statement

**Doc code**: M-03
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-00 Intake & Situation Brief · case.yaml provenance rules · all downstream deliverables that inherit from D-00

---

## 1. Why this doc exists

The Intake & Situation Brief is the first document a Hekswerk engagement produces, and almost every claim in it is downstream of either something the client said in the deep-dive or something the practitioner inferred from how they said it. Both are useful. Both are dangerous if they get confused. An inference written confidently in April becomes an established fact by June if nobody challenged it, and by August the plan is built on a sentence the client never actually said.

This note defines a four-way distinction — *statement*, *inference*, *assumption*, *confirmation* — and the writing discipline that keeps each one labeled. The discipline is small enough to apply in the moment, durable enough to survive the document's hop through case.yaml into D-01 through D-07, and honest enough that the client can challenge an inference without first having to identify it as an inference.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 30 seconds per drafted sentence in D-00.

---

## 2. Working definition

> A *statement* is something the client said. An *inference* is something the practitioner concluded from what the client said, did, or did not say. An *assumption* is something the plan is currently treating as true for working purposes without confirmation. A *confirmation* is something checked against an authoritative source.

Each of the four has a different epistemic status, a different decay rate, and a different rule for what happens when it turns out to be wrong. The discipline is to keep the four labeled, so that when something goes wrong the practitioner can name which kind of claim broke and respond accordingly.

The discipline is a client-care issue as much as a data-integrity issue. A client who reads "you said X" when they did not say X feels misheard; a client who reads "I am taking from this that X" can correct the inference without feeling overruled.

---

## 3. The four categories

### Statement

What the client said, in their own words or close paraphrase. Provenance: the deep-dive session, the intake form, an email, a follow-up call. Provenance must be traceable — ideally to a quote, a form field, or a dated note.

*Test*: could the practitioner point to the moment the client said this, or to the form field where they wrote it?

*Failure mode*: paraphrase drift. The practitioner writes "the client wants a six-month timeline" when the client said "I'd rather start now and have margin than wait and have to compress." Those are not the same sentence. The paraphrase is more decisive than the source.

### Inference

A practitioner conclusion drawn from statements, behavior, or absence. Inferences are necessary — clients do not narrate their own situations completely, and part of the practitioner's value is in seeing what the client has not yet named. Inferences must be marked as such.

*Test*: would a different practitioner with the same source material reach the same conclusion? If yes, the inference is relatively safe to draw. If no, the inference is provisional and the practitioner should note the basis.

*Failure mode*: hardening. An inference written confidently in week one is quoted as established by week six. The remedy is the language marker — see Section 4.

### Assumption

A claim the plan is currently treating as true for working purposes, distinct from inference because it is held provisionally for *planning convenience* rather than because the practitioner believes it. "The destination housing market will produce viable options within two weeks of search start" is an assumption; the practitioner does not really know, but the plan needs to move and this is the working number.

*Test*: would the plan have to be revised if this turned out to be false? If yes, it is an assumption and belongs explicitly labeled.

*Failure mode*: assumptions presented as facts. The plan looks more certain than it is, and the client trusts it accordingly. When the assumption breaks, the failure is read as plan failure rather than as a planning assumption that did not survive contact with the world.

### Confirmation

A claim checked against an authoritative source — an attorney, an official document, a provider quote, a municipal office. Confirmations carry weight that inferences and assumptions do not. They also have provenance: who confirmed, when, against what. See [[m13-verify-with-authority]] for the verification discipline that produces confirmations.

*Test*: can the practitioner name the source, the date, and the form of the confirmation?

*Failure mode*: confirmations that are actually consensus. "Several relocation forums say apostille processing takes 3–6 weeks" is not a confirmation; it is an aggregated assumption. The methodology distinguishes the two.

---

## 4. Language markers

The discipline lives in the prose. The four categories each have a small set of phrases that mark them; using the phrases is the practice.

**Statement markers**:

- *"The client said…"*
- *"In the intake form, X."*
- *"During the deep-dive, the client described…"*
- Direct quote, where sharpness matters: *"…losing track of what I've decided versus what I'm still figuring out."*

**Inference markers**:

- *"I am taking from this that…"*
- *"This appears to indicate…"*
- *"My read is…"*
- *"The pattern suggests…"*

**Assumption markers**:

- *"Planning assumption, not established fact: …"*
- *"Working figure, to be confirmed: …"*
- *"For now, the plan treats X as true; this needs verification before [milestone]."*

**Confirmation markers**:

- *"Confirmed with [source] on [date]: …"*
- *"Per [authority], …"*
- *"Source: [official document / quote / provider response]."*

These are not stylistic flourishes. They are load-bearing — the markers are how the document tells future readers (including future Levi) which sentences to trust how much. A document without markers is a document where everything reads at the same confidence level, which means the client cannot tell what to push back on.

---

## 5. Worked examples

From the Mason Kirsch dogfood test case (single adult, Atlanta → Berlin, Blue Card pathway, target August 2026 arrival):

### Statement

> *"The client said: 'I keep doing the planning in my head and then losing track of what I've decided versus what I'm still figuring out.'"*

Direct quote from the intake form. Provenance: intake submission, April 28, 2026. Treat as established input to the engagement.

### Inference from the same statement

> *"I am taking from this that the client will benefit disproportionately from a written, dated, single-source-of-truth artifact — and from explicit confidence labels that distinguish decided from in-progress. The pain he names is exactly the pain provenance discipline addresses."*

A different practitioner could reach a different read of the same sentence — they might infer, for instance, that the client would benefit from a coaching relationship rather than a documentation discipline. The inference is reasonable but provisional, and is marked as such.

### Assumption

> *"Planning assumption, not established fact: Blue Card processing for an employer-sponsored case at this employer typically lands within 8–12 weeks. The plan currently works backward from August arrival using this figure. To be confirmed with the employer's mobility team and/or immigration counsel before D-02 is finalized."*

The practitioner does not really know this figure for this employer at this consulate at this volume; the plan needs a working number and this is it. Marking it as an assumption is what allows D-02 to use it without lying.

### Confirmation

> *"Confirmed via Mason's employer mobility team, May 10, 2026: company-side document packet for Blue Card sponsorship is typically issued 6–8 weeks before relocation date; client must respond within 10 business days of receipt."*

This sentence carries different weight than the three above. It survives challenge; the others may not.

### A failure mode in the wild

A first-draft D-00 line that reads: *"Mason needs structure and tends to overcommit-and-crash."*

Diagnose: that is an inference written as a statement. The client did say *"I do better with structure than without"* and *"I tend to under-ask for help because I assume I can figure things out, and then I overcommit and crash."* The drafted line collapses two of the client's sentences into a third-person characterization that sounds like a finding. Rewrite:

> *"The client said: 'I do better with structure than without' and 'I tend to under-ask for help because I assume I can figure things out, and then I overcommit and crash.' I am taking from this that the engagement should pre-commit to delegation and recovery windows rather than relying on Mason to ask for them in the moment."*

Longer, but honest. The statement is in the client's voice; the inference is in the practitioner's voice; the response is the practitioner's design move, not a property of the client. See also [[m15-capacity-as-a-non-pathologizing-risk-category]] on locating failure in the plan rather than the client.

---

## 6. The redaction-versus-questions move

D-00 is delivered to the client. The client reads what the practitioner wrote about them, and reacts. A document that mixes the four categories sloppily produces friction at this step — the client agrees with some sentences, disagrees with others, and cannot easily tell which the practitioner is most committed to.

The discipline is to convert inferences into *questions* in the client-facing draft wherever feasible, and to retain the practitioner's working interpretation in a separate practitioner note. The client-facing form reads:

> *"Working read: the engagement will benefit from explicit confidence labels because of how you described the pain of 'losing track of what I've decided.' Is that landing for you, or is it slightly off?"*

The internal form reads:

> *"Inference: client is symptom-naming a provenance problem; the plan should use confidence labels as a primary affordance."*

The client-facing version invites correction. The internal version commits to a working interpretation. Both are honest. The mistake is to use the internal form's confidence in the client-facing version, where it reads as a verdict.

For load-bearing inferences — the ones the rest of the plan depends on — the question form is mandatory. For incidental inferences, the marker (*"my read is…"*) is enough.

---

## 7. Provenance in case.yaml

The studio's case.yaml structure should carry the four categories as first-class fields wherever a claim is load-bearing. The exact schema is open (see open questions), but the working rule is: every claim that drives a downstream deliverable should carry a `provenance` field with values drawn from `{statement, inference, assumption, confirmation}` and a source pointer.

What this enables:

- Studio validation can flag any inferred or assumed claim that has propagated to D-02 sequencing without being upgraded.
- Walkthrough preparation can produce a focused list of inferences for the client to challenge, separately from confirmations that need no challenge.
- Post-engagement archive preserves the difference between what the client said and what the practice concluded, which protects both client and practitioner if the file is ever revisited.

What this prevents:

- Inference hardening. An inference written in week one cannot quietly upgrade itself to confirmation in week six because the provenance field is sticky.
- Source loss. A confirmation that loses its source pointer is no longer a confirmation; it is a quote from a forgotten place, which is an assumption with a confidence costume on.

---

## 8. Adjacent vocabulary

- **Quote**: a verbatim or near-verbatim record of what the client said. Strongest form of statement.
- **Paraphrase**: a restatement of what the client said in the practitioner's words. Statement-shaped, but introduces drift; mark when paraphrasing.
- **Working figure**: an assumption used in calculations. Always label.
- **Authority**: see [[m13-verify-with-authority]] for what counts as one and what does not.
- **Confidence label**: a related discipline applied to dates and quantitative claims; see [[m06-confidence-labels]].

The four categories of this note are about *the basis* of a claim. Confidence labels are about *how certain* the claim is given that basis. The two disciplines compose: a confirmation with high confidence is the strongest claim; an inference with low confidence is the weakest; the cells in between are populated honestly.

---

## 9. How to use this in practice

**During the deep-dive session**: write statements verbatim where possible. Aim for quote fidelity on the sentences the client returns to or emphasizes. Mark inferences mentally but resist writing them as statements in the live notes.

**During D-00 drafting**: every sentence that asserts something about the client should be inspectable for category. The drafting question is not "is this sentence true?" but "what kind of claim is this, and is it marked as such?" Most first-draft D-00 problems are category problems, not factual problems.

**During the D-00 walkthrough**: lead with the inferences. *"Here is what I am taking from what you said — does this land?"* Invite correction. The client is the only person who can confirm that an inference is right. Confirmations and statements need less walkthrough attention because they are already grounded.

**Across the lifecycle of the engagement**: when an inference or assumption resolves — into confirmation, or into "actually, no" — update case.yaml's provenance field. Do not let it linger as an inference once the world has weighed in.

**Studio validation**: a useful first validator is "no D-02 entry depends on a claim whose provenance is `inference` or `assumption` without an explicit upgrade plan." If such an entry exists, the plan is leaning on an unverified claim and the practitioner should know.

---

## 10. Open questions (v0.1)

- **Schema depth.** Should every D-00 sentence carry provenance, or only the load-bearing claims that propagate downstream? Lean: load-bearing only, but the rule for what counts as load-bearing needs sharper definition. Probably: anything that drives a system identification, a date, a sequencing decision, or a risk row.
- **Client-facing provenance language.** The internal markers are crisp. Whether the client should see "Planning assumption, not established fact: …" verbatim or a softened version is unsettled. Early lean: keep the markers — they are part of the trust signal — but pair with a short reading guide in D-00 Section 1.
- **Inference budget per document.** A D-00 with too many inferences is a deep-dive that did not get enough statements out of the client. A D-00 with too few inferences is a practitioner who did not synthesize. Untested working range: 20–40% of load-bearing claims as inference at first draft, dropping toward 10% by walkthrough close as inferences resolve.
- **Studio validators.** Likely yes for category presence (every load-bearing claim has a provenance value); harder for category correctness (is this *actually* a statement or has the practitioner labeled an inference as one?). Manual review remains necessary for the harder check.
- **Post-engagement provenance retention.** How much of the provenance metadata survives into the client's archived deliverable? Lean: keep it. The client may revisit in two years and benefit from the same epistemic transparency the practitioner did. Cost is small; benefit is real.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
