# Disclosure-Order Review with Hashed Blind Envelopes

**Status: PUBLISHED CANDIDATE surface — not a confirmed component of any
system. Maturity: operator-derived, operationally exercised once in part,
externally unvalidated.**

Provenance of this text: it passed a three-round external adversarial
review gate (two REVISE rounds, then READY_TO_PUBLISH from a third,
previously unexposed reviewer lineage) on 2026-08-21, with every cited
source verified. Its claims of absence are bounded to the documented
search scope stated below.

## The problem this names

When an AI model reviews a creative or scholarly work, what the reviewer
knew — and when — is part of the result. Fragments exist across fields:
forensic science sequences evidence exposure (Dror et al., LSU/LSU-E);
registered reports withhold results at Stage 1; a theory venue staged
author-identity reveal and measured 7.1% of reviews changing (PLOS ONE
0286206); AI-peer-review deployments improvise identity filters at scale
(the AAAI-26 pilot). In evidence synthesis, Cochrane RoB 2 assesses RISK
OF BIAS for a specific RESULT, and GRADE rates CERTAINTY in a BODY OF
EVIDENCE for an outcome, with risk of bias as one input domain — granular
bias assessment of synthesized evidence is established there, and the two
instruments do different jobs. What this protocol adds over those
antecedents is reviewer-side COMMITMENT of the information state per
stage, a deterministic formation-time blindness-control grade per
finding, and an envelope covering LLM-session channels — disclosure
ordering and per-stage documentation themselves are inherited from LSU-E
rather than claimed as novel. The graded object — the FORMATION
CONDITIONS of the reviewer's own outputs — is one neither RoB 2 nor
GRADE addresses. Novelty claims in this document are bounded to a
documented search scope (English-language web, arXiv, methods literature;
surveyed 2026-08-21, medium depth, recorded queries), not asserted
absolutely.

## The mechanism

1. **Disclosure order as method.** A fixed sequence of stages, each
   defined by which CONTEXT CATEGORIES (author identity, authorial
   intent, prior reviews, series position, thematic frame) have been
   released. Later information may interpret earlier observations, never
   rewrite their formation conditions. Per-stage deltas are findings.
2. **The blind input envelope — three channel classes, treated
   differently.**
   (i) CONTENT-LEAKAGE channels (workspace/project context, session
   memory, retrieval stores, prior-round summaries, dispatcher framing,
   coordinator paraphrase — see rule 6 — model-identity leakage across
   routes, and the repository-shaped channels of Code-First Peer Review):
   enumerated as prohibited inputs; their closure status feeds the
   assurance grade.
   (ii) CONFIGURATION CONFOUNDERS (provider-side experimentation / silent
   A/B variation, sampling parameters): recorded as reproducibility
   metadata — they threaten comparability, not blindness, and are not
   graded as leakage.
   (iii) OBSERVABLE SIDE CHANNELS: included only when the threat model
   names an observer, a secret, and an inference path; absent that, they
   are out of scope.
   The envelope object commits (id, work hash, prohibited-input
   enumeration with per-channel status, persistent-context status,
   disclosure state).
3. **Hash semantics, stated plainly.** Every hash in this protocol is a
   COMMITMENT to a declaration at a point in time. It proves the
   declaration did not change; it does not verify the declaration was
   true. Where the runtime cannot attest a channel's closure, the honest
   status is self-reported or UNKNOWN, and the grade reflects that.
4. **Blindness assurance, graded deterministically, per finding.**
   The construct, stated precisely: the grade measures BLINDNESS-CONTROL
   ASSURANCE — the provability of channel closure at the finding's
   formation moment — and nothing else. It is not a correctness, bias, or
   reliability score: a VERIFIED finding can be flatly wrong, and an
   UNVERIFIED finding can be right. Conflating "absence of provable
   leakage" with "epistemic reliability of the finding" is the misreading
   this paragraph exists to prevent.
   VERIFIED — every class-(i) channel closed by attestation or structural
   impossibility; PARTIALLY-VERIFIED — no channel known open, at least one
   closure self-reported; UNVERIFIED — any class-(i) channel open or
   UNKNOWN. Findings inherit their stage's grade BY DEFAULT; a finding
   diverges from its stage when its own formation crossed a boundary the
   stage did not — formed after an intra-stage disclosure event, or citing
   material from a channel opened mid-stage — and carries the grade of the
   WORST channel state at its formation moment, which is what makes the
   grade genuinely per-finding rather than a stage grade copied down.
5. **Freeze objects, with anchoring stated honestly.** A completed stage
   freezes as a record binding work hash, envelope hash, prompt hash,
   output hash, and predecessor links. A predecessor-linked hash chain
   alone can be rewritten in full; the append-only property holds only as
   far as the chain is externally anchored (signed, third-party
   timestamped, or lodged in a non-equivocating log). Without anchoring
   this protocol claims tamper-EVIDENCE within a trusted store, not
   non-equivocation, and says so.
6. **Response labeling and framing hygiene.** An AI reviewer's output is
   a BLIND READING RESPONSE, never a human reader effect. Authorial
   intent supports only `intentional = yes`, never `effect = successful`.
   Coordinator paraphrase — a planner's summary shaping the answer — is
   an instance of demand characteristics / experimenter expectancy
   (Rosenthal) and of framing effects; those literatures already contain
   STRUCTURAL controls (blinding, standardized instructions, role
   separation, automation), and this protocol's no-paraphrase rule is one
   more standardized-information control in that family — applied to the
   coordinator–reviewer flow with per-finding records, claimed as an
   application, not as categorically stricter.

## Rule register

| Rule | State | Enforcement today |
|---|---|---|
| 1 — disclosure order | HARD (protocol-definitional) | procedural |
| 2 — envelope & channel taxonomy | EXPERIMENTAL | procedural |
| 3 — hash commitment semantics | HARD | procedural |
| 4 — deterministic grade rule | HARD (mechanical) | procedural |
| 5 — freeze & anchoring | HEURISTIC (unanchored today) | procedural |
| 6 — labeling rules | HARD | procedural |

States follow a four-value vocabulary (HARD / HEURISTIC / OWNER /
EXPERIMENTAL); promotion requires evidence, not familiarity. Extending or
reclassifying rules is reserved to the operating owner.

## What this is NOT

Not a claim that blinding removes model bias, cultural bias, genre
expectation, or prompt sensitivity. Not a substitute for human reader
studies. Not an anonymization pipeline. Not a venue mandate — written for
review operators needing per-finding evidentiary weight, while
institutional filters may remain the venue equilibrium.

## Simpler-structure comparison

An append-only hashed transcript, extended with signed runtime and
configuration attestations, can carry the same information as the
envelope — conceded. The envelope is then a SCHEMA for what those
attestations must cover (the class-(i) enumeration and per-channel
status) rather than a distinct storage object; implementations may
realize it inside a transcript-attestation record. The protocol's content
is the enumeration, the grade rule, and the disclosure ordering — not the
container.

## Relation to prior art (acknowledged, by name)

Disclosure sequencing: Dror LSU/LSU-E — the closest single ancestor, and
closer than a bare citation suggests: LSU-E already requires experts to
receive information in a controlled order, to DOCUMENT what they saw, and
to RECORD how their opinion changed, with published worksheet
implementations (2022). This protocol's delta over LSU-E is specifically
the deterministic per-finding formation-time semantics (rule 4) and the
committed envelope over LLM-session channels (rule 2), not the
sequencing-and-documentation idea. Also: registered reports; result-blind
review; the ITCS 2023 staged reveal; Ballantyne & Celniker. Claim-level
graded provenance with quarantine routing in multi-agent systems: the
Isnad-Rijal framework (arXiv 2607.24117) — it grades transmitter
reliability; this protocol grades formation-time disclosure state; shared
architectural pattern (claim-level grades), different measured object;
acknowledged, not claimed. Bias grading
of synthesized evidence: Cochrane RoB 2 (per result); GRADE (certainty
per outcome). Prompt-hash commitment: Frontier Lag (arXiv 2605.04135).
Repository-channel enumeration: Code-First Peer Review (arXiv
2606.07683); arXiv 2603.20214; the AAAI-26 pilot (arXiv 2604.13940).
Expectancy/framing: demand characteristics; Rosenthal; LLM framing
literature — including their structural controls, of which rule 6 is an
application.

## Enforcement maturity (self-disclosure)

Provider-side memory or experimentation can violate the envelope
invisibly; that is why grades exist and why UNKNOWN is an admissible
value. One partial instantiation has been operated (a two-arm
framed-versus-clean reading, model held constant, hash-bound work
identity); the full machinery has not run end to end; no anchoring
infrastructure ships with this document.

## Possible relations (not asserted)

This surface emerged from one operating practice in parallel with other
candidate surfaces: lineage-aware-agent-governance, lineage-admission-control, falsifiability-first-protocol, claim-strength-profile, scoped-rejection. Common origin is the only relation asserted.
Composition, dependency, or a unified framework among any of them is
possible and deliberately NOT asserted; no confirmed relation exists, and
none should be inferred from co-ownership, shared vocabulary, or
structural resemblance. Read under a weakest-compatible-relation default:
navigation adjacency. If a composition is ever established it will be
stated explicitly; absence of that statement means it has not been.

## Public / internal boundary

This surface does not expose the operating system behind it: no
operational records, review transcripts, work titles, or infrastructure
appear here. The non-inference runs both ways: absence from this surface
does not imply absence internally, and nothing published here is
sufficient to reconstruct the internal system or the works it reviews.

## Fork / derivative boundary

Source provenance is not inherited authority, and attribution is not
endorsement. A derivative may preserve provenance while developing
different operational logic; downstream decisions belong to the
derivative system and must not be attributed upstream.

## Review questions (refutation invited)

1. Name a published protocol grading the formation conditions of a
   reviewer's own findings, per finding, under a deterministic rule. That
   defeats rule 4's claim within any scope.
2. Does the worst-channel-at-formation-moment rule actually
   individualize grades in practice, or do real stages produce uniform
   grades anyway — and if uniform, is the per-finding claim empty?
3. Is the three-class channel taxonomy sound — name a channel that
   resists classification or belongs to two classes with conflicting
   treatments.
4. Given the anchoring concession in rule 5, is the protocol's
   tamper-evidence claim worth having without non-equivocation, for a
   single-operator context?
5. A simpler structure producing equivalent assurance is a successful
   challenge; the comparison section concedes the container — challenge
   the enumeration, the grade rule, or the ordering instead.

Negative findings are relevant findings.
