# Methodology Note · Privacy Posture

**Doc code**: M-12
**Version**: v0.1 — May 2026
**Owner**: Levi Banks · Hekswerk
**Status**: Draft (pre-first-engagement)
**Used by**: D-00 Intake & Situation Brief · D-04 Provider Shortlist · D-05 Document Readiness Checklist · all studio architecture decisions about storage, transit, and AI use

---

## 1. Why this doc exists

Most advisory practices that work with relocation clients accumulate sensitive material as a side effect of working carefully: scanned passports, financial summaries, medical descriptions, immigration filings, correspondence with attorneys and accountants. The default trajectory of an advisory engagement is toward more custody, not less — every new document request feels load-bearing in the moment, and the cumulative pile is rarely audited.

Hekswerk's methodology is built around the opposite default: **ask less by default, take custody only when there's a specific named reason, and never let client data exit the connected engagement directory**. This is a methodology choice, not just an operational preference. The kind of clients Hekswerk serves (ND, chronic illness, queer-marginalized, complex-household) are statistically more likely to have material they'd prefer not float in third-party systems — and a practice that didn't notice this would already be misaligned with its audience.

This note codifies the discipline. The studio architecture (see `studio/roadmap_v2.md` Privacy Architecture; `studio/control-surface-architecture_v2.md` Privacy Architecture) is the operational embodiment; this essay is the methodology that justifies the architecture and gives the practitioner the rules for cases the architecture alone can't decide.

Reading time: ~10 minutes end-to-end. Reference time once internalized: under 30 seconds per drafted document request or storage decision.

---

## 2. Working definition

> *Privacy posture* is the methodology's standing position on what to ask for, what to keep, and where keep-decisions live. The Hekswerk posture has three rules: (1) **ask for descriptions, not artifacts**; (2) **custody requires named justification and a defined endpoint**; (3) **client data stays in the connected engagement directory and only there**.

The posture is *default-restrictive*. The methodology defaults to *less* — fewer documents requested, fewer scans accepted, fewer fields populated, fewer copies stored — and requires explicit justification to move toward *more*. This inverts the standard advisory-practice trajectory, where the default is to accumulate "in case it's useful later."

The posture is also *architecturally enforced*, not merely disciplined. A practitioner who tries hard to ask less but uses cloud-synced storage, third-party AI services, or browser-managed drafts is not running the Hekswerk posture; they're running aspiration on top of a leaky substrate. The architecture is part of the methodology.

---

## 3. The three rules

Apply in the moment. Each rule comes with a discriminating test and a failure mode that pre-empties the rule when it breaks.

### Rule 1 — Ask for descriptions, not artifacts

The default request shape is *describe what you have*, not *send me a copy*. "Client has birth certificate, original, located in Atlanta safe deposit box; needs apostille from Georgia Secretary of State" is enough information for D-05 Document Readiness Checklist planning. The scan is not.

*Test*: would the next step of the methodology change if I had the artifact rather than the description? If no, ask for the description.

*Failure mode*: artifact-creep. Practitioner requests scans "to be thorough" or "in case I need to look at them later." The pile of received scans becomes a parallel store the practitioner now has to secure, retain, eventually delete, and (if subpoenaed) produce. None of those obligations existed if the description had been sufficient.

### Rule 2 — Custody requires named justification and a defined endpoint

When an artifact must enter the engagement — because a provider needs it, because a name-mismatch requires visual inspection, because a translation is being commissioned — custody is taken with: (a) a specific named reason, (b) a defined recipient or use, (c) a defined retention window or deletion trigger.

*Test*: can I say, in one sentence, why I need this artifact, what I'll do with it, and when it goes away? If any of those three is vague, the custody isn't justified yet.

*Failure mode*: indefinite custody. The artifact arrives for a specific reason ("Stephan needs to see the apostille before submission"), the reason resolves, and the artifact sits in the engagement directory through the rest of the engagement and into archive. The practice now retains material it has no operational reason to retain.

### Rule 3 — Client data stays in the connected engagement directory

The only place client-identifiable content lives is the practitioner's encrypted local engagement directory, accessed through the studio's File System Access API path. Browser-managed storage (localStorage, sessionStorage, IndexedDB content, cookies, cache), cloud sync, third-party AI services, telemetry, error reports, analytics — all forbidden for client content. The architecture fails closed: if the studio cannot save to the connected directory, it warns rather than silently caching elsewhere.

*Test*: name the disk location where this piece of client data lives. If the answer is "I'm not sure" or "the browser is keeping a draft," the architecture has failed and the data has propagated where it shouldn't.

*Failure mode*: ambient propagation. Client data lands in browser drafts, exported reports left in Downloads, copies in email attachments, screenshots in clipboard history, AI conversation logs in cloud-hosted services. Most of these happen by drift, not decision. The architecture's job is to make them impossible by default; the methodology's job is to notice when the architecture isn't being run.

---

## 4. Description versus custody

The cleanest single move the methodology makes is the explicit distinction between *describing* a document and *holding* it. Both produce useful information for planning; only one creates an ongoing custody obligation.

**Description (default)** captures the document's *operational shape*:

- What it is (passport, birth certificate, marriage certificate, medical record category, prior-employer letter)
- Whether the client has the original, a certified copy, or nothing
- Where the original physically lives
- What treatment it needs (replacement, apostille, translation, certified copy)
- Whether any other party (lawyer, registrar, school) has already seen or processed it
- A `source_ref` back to where this came up in D-00

This is enough information to draft D-05 rows, sequence D-02 around document timing, and identify D-04 provider categories who need to engage with the document downstream.

**Custody** captures the *artifact itself*: the scan, the photograph, the file. Custody triggers:

- Encrypted storage in the engagement directory
- A `received_at` timestamp
- A specific `received_for` justification (named recipient / use case)
- A `retention_until` or `delete_when` trigger
- An access log if the artifact is opened after initial receipt

The methodology's D-05 schema (per the studio's control-surface architecture stub) operates from descriptions. Custody fields are present in the schema for the cases where they're needed, but they're explicitly *optional* and require justification.

---

## 5. What justifies custody

Five cases, in roughly descending frequency, where taking custody is the right move:

1. **Provider submission packet.** A lawyer, accountant, or government office requires the artifact to act on the client's behalf, and the cleanest transfer route runs through the practice (rather than client-direct). Custody is short, defined, and ends at handoff.
2. **Name or detail inspection.** A potential discrepancy between documents (e.g., birth-certificate name vs. passport name) requires visual inspection to plan around. Custody is brief and ends when the discrepancy is resolved or referred.
3. **Translation commissioning.** The artifact must be translated, and the translator works from the practitioner's hand-off. Custody ends at delivery to the translator.
4. **Apostille / certification coordination.** Rare; usually the client handles directly. Justified only when the client has explicitly delegated and the cleanest route runs through the practice.
5. **Receiving-institution requirement.** A bank, school, or municipal office has stated they need to receive the document from a particular party. Verify with the authority (per [[m13-verify-with-authority]]) before assuming the requirement is real.

What is *not* on this list:

- "I might need it later."
- "It would be more convenient if I had it."
- "The client offered, so I accepted."
- "It came through email automatically."

These are all artifact-creep. Decline the custody if no named justification applies.

A note on offered material: clients often want to send more than the methodology needs. The practice's response to spontaneous over-disclosure is *thank them for the offer, restate what's actually needed, and decline the rest*. This is a kindness, not a refusal — clients who over-disclose are often doing it from anxiety, and a practitioner who absorbs everything offered amplifies the anxiety on the next round. The opposite happens too: a practitioner who consistently declines unnecessary material teaches the client that the practice is trustworthy with information limits.

---

## 6. The studio-side privacy architecture

The methodology's posture is enforced by the studio's architecture, not just by practitioner discipline. The studio's job is to make ambient propagation *impossible by default* and to surface privacy-relevant decisions as explicit moves.

Key architectural commitments (full detail in `studio/roadmap_v2.md` and `studio/control-surface-architecture_v2.md`):

- **Engagement directory connection**: client data is read and written only through the File System Access API directory handle. No `fetch()`-based loading from cloud paths; no Blob downloads to the user's Downloads folder containing client content.
- **No client data in browser-managed storage**: localStorage is allowed for UI preferences (editor pane width, last-opened engagement id, FileSystemDirectoryHandle stubs) but forbidden for any client-identifiable content. This is enforced by a Tier 3 privacy-boundary validator (per `control-surface-architecture_v2.md`).
- **No remote AI services for client content**: methodology-shaped questions can be discussed with cloud AI when anonymized; client data never goes through a remote AI provider. Local AI use (if any) operates against the engagement directory only.
- **Section 8 redaction-to-question discipline**: D-00's internal-only practitioner inferences never appear in client-facing artifacts unless rewritten as questions via the `client_facing_questions[]` schema (per [[m03-inference-versus-statement]] §6). This is the in-engagement form of "ask less; expose less."
- **Visibility per record**: every D-00 section, every case-level claim, carries an explicit `visibility` field (`internal | client-facing | redacted`). Renderers and validators respect the field; leakage is an error, not a warning.

The architecture *codifies* the posture so that a future second practitioner inheriting the studio cannot accidentally violate the posture by writing different code. That is the test of whether the architecture is correct: does it survive a practitioner who hasn't read this essay?

---

## 7. Where privacy violations hide

The methodology's most common privacy failures are not malice; they are drift. The places to watch:

- **Email and messaging.** Client correspondence about the engagement often happens in regular email or chat. Treat the engagement's email folder as a custody location: review periodically; delete artifacts that no longer have a justification; do not let attachments accumulate.
- **Screenshots and clipboard.** Studio screenshots taken to share renders, slack snippets pasted to discuss methodology — both can carry client content into systems with different privacy guarantees. Anonymize before sharing.
- **Exports.** SVG and PDF exports from the studio are intended for the client; they should not accumulate in the practice's local Downloads folder. Move to engagement directory or delete.
- **Working notes outside the directory.** Notebook scribbles, voice memos, calendar entries, todo apps — any of these can hold client data outside the connected directory's privacy guarantees. The discipline is to treat the engagement directory as the *only* place client material lives, and to use that directory's note-taking affordances for anything that needs to persist.
- **Drafts of correspondence.** Email drafts that quote D-00 sections, attorney updates that paste case context — these are derivative custody. Either write them inside the engagement directory (and copy out for sending) or write them ephemerally (and delete on send).
- **Recordings and transcripts.** D-00 Deep-Dive Interview recordings, when consented, are high-sensitivity. They live in the engagement directory; they don't go to cloud transcription services unless the client has explicitly consented to that specific service. The practice's default transcription should be local where possible, manual where the local option is unavailable.
- **Backups.** If the engagement directory is backed up, the backup destination must satisfy the same privacy posture as the primary directory. Cloud-synced backup folders ([Drive/Dropbox/iCloud]) violate the posture unless explicitly configured to exclude the engagement directory.

The practical move is a periodic audit: monthly, walk through the disk, the email folder, the export folder, and the clipboard, and ask the Rule 2 test of every piece of client material — *why is this here, what's it for, when does it go away*.

---

## 8. Adjacent vocabulary

- **Posture**: the methodology's default stance; what the practice does in the absence of explicit instruction.
- **Architecture**: the technical implementation of the posture; what the studio makes possible or impossible regardless of practitioner discipline.
- **Description**: structured information about an artifact, not the artifact itself.
- **Custody**: holding the artifact; carries retention, security, and deletion obligations.
- **Justification**: the named reason custody is taken; must be specific, time-bound, and recipient-defined.
- **Endpoint**: the deletion trigger or transfer event that ends custody.
- **Connected directory**: the practitioner's encrypted local engagement directory accessed through the File System Access API. The only acceptable persistence location for client-identifiable content.
- **Ambient propagation**: client data spreading by drift rather than by decision; the primary failure mode this discipline addresses.
- **Artifact-creep**: the default trajectory of an advisory practice toward more custody over time.

Privacy is not the same as:

- **Confidentiality**: an ethical commitment to not disclose. Confidentiality without privacy architecture is a promise that depends on practitioner memory and discipline.
- **Security**: technical protection of stored data. Necessary but not sufficient; secure storage of data that shouldn't have been collected is still a violation of the posture.
- **Compliance**: meeting legal minimum standards (e.g., GDPR, HIPAA-adjacent norms). Important; the Hekswerk posture is more restrictive than the compliance floor and treats the floor as the *minimum*, not the target.

---

## 9. How to use this in practice

**During D-00 intake**: ask for descriptions of documents, not the documents themselves. The Pre-Engagement Brief is explicit about this ("we'll ask about what you have, not for files"). The Deep-Dive Interview surfaces document state at description-level. The intake artifacts ([transcripts, notes]) live in the engagement directory and reference (rather than embed) sensitive material.

**During D-04 provider research**: information about providers (name, scope, fees, contact) is not client data and follows normal storage rules. Information about the *client* shared with providers — what's been described, what's been confirmed, who's been told what — is engagement-directory-only and follows the same rules as any other client material. See [[m11-provider-research-aging]] on how to handle provider records over time without accumulating stale or sensitive client-shared context.

**During D-05 document checklist drafting**: every row operates from a description by default. Custody columns (`received_at`, `received_for`, `delete_when`) are explicit fields that the practitioner fills *only when custody is justified*. A populated `received_at` without a populated `delete_when` is a row-level validation warning (Tier 3 in `control-surface-architecture_v2.md`).

**During provider handoffs**: when transferring a document to an attorney, accountant, mover, or other engaged provider, use the provider's stated secure channel (encrypted upload, in-person, recorded mail). Do not default to email attachment unless the provider has named email as their accepted channel. Log the transfer in the engagement directory; if the transfer was for a one-time use, set a `delete_when` trigger for the practice-side copy.

**During studio-side editor work**: the privacy architecture handles the heavy lifting. The practitioner's contribution is to *notice* when the architecture is being run — when a save fails because the directory isn't connected, do not work around it by pasting YAML somewhere; reconnect or pause. When a Tier 3 privacy-boundary validator fires, treat it as an error, not a nuisance.

**During walkthroughs with the client**: name the posture explicitly when it matters. *"We didn't ask you to send the medical records because the planning doesn't need them; we asked you to describe what you have. If a provider downstream needs the records, you'll send those to them directly, not through us."* Clients in the target audience (ND, chronic illness, queer-marginalized) often react with visible relief when this is named — it's part of why the posture is methodologically distinctive, not just operationally tidy.

**Across engagements**: the engagement directory's end-of-engagement state should be cleanly reviewable. Archive what the engagement letter says to archive; delete what custody-justifications have expired; hand back to the client what's theirs. The post-engagement archive is *itself* a custody location and follows the same retention rules.

---

## 10. Open questions (v0.1)

- **Backup architecture for the engagement directory.** The directory needs *some* backup against disk failure, but the backup must satisfy the privacy posture. Working approach: encrypted external drive cycled offline; no cloud backup of engagement directories. Worth pressure-testing against real-engagement disaster recovery once a few engagements have completed.
- **Post-engagement retention windows.** The engagement letter currently mentions retention but doesn't specify exact durations per artifact class. Working defaults: D-00 through D-07 final deliverables retained 5 years (matching DAFT pathway long-tail support questions); raw intake notes deleted within 1 year of engagement close; received artifacts deleted at engagement close unless explicitly retained with client consent. Calibrate against legal review and real-engagement need.
- **Client-side privacy education.** Some clients will want to send more than the methodology asks for, and will keep asking. The practice's response (gentle decline, restate what's needed) is right, but a small client-facing privacy document explaining *why* the practice operates this way may reduce the friction. Lean: add a short "How Hekswerk handles your information" page to the website and reference it from the engagement letter.
- **The "seen by practitioner" vs "client-reported" distinction.** D-05 schema may want fields that track which document state the practitioner has actually inspected (rare) vs. what the client has reported (the default). Worth adding only if real engagements surface confusion about who has confirmed what.
- **Recording transcription.** Deep-Dive Interview transcriptions are currently manual or local. Some clients may consent to specific cloud transcription services (e.g., Otter.ai) for accessibility reasons; the protocol for handling consent + service-specific privacy terms is unsettled. Lean: keep manual / local as the default; honor explicit consent for named services with disclosure of their terms in the engagement letter.
- **AI-tool exception cases.** Local AI tools running entirely on the practitioner's workstation (e.g., a local LLM operating against the engagement directory) may be acceptable under the architecture even though remote AI is not. The line between "local AI working on client content" and "AI service that happens to run locally but phones home" needs explicit definition before any AI tool is integrated. Lean: forbid by default; allow only after explicit network-isolation verification.
- **Client requests to share material outside the practice.** Sometimes clients want the practice to email a deliverable to a third party (a parent, a partner not part of the engagement, an unengaged advisor). The protocol for handling these requests — getting explicit consent, logging the disclosure, etc. — needs to be defined. Lean: client makes the disclosure themselves whenever possible; practice-mediated disclosure is a custody event with all the same rules.

---

*v0.1 · May 2026 · this document is a living methodology note; revise after each real engagement and version-bump quarterly*
