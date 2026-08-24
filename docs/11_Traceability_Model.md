# MBSA Lab OS — Traceability Model

## 1. Purpose

This document defines the public traceability model used to connect engineering intent, architecture, implementation, verification, validation, evidence, decisions, change, POC work and reusable patterns.

The model is tool-neutral. It defines semantics, identities and control rules; it does not prescribe a database, file format or application.

## 2. Core principles

1. Every traceable element has a stable identity and a controlled version.
2. A link has its own meaning, owner, state and evidence; proximity in a document is not a trace link.
3. Direction matters: evidence supports a claim, while a claim does not manufacture evidence.
4. Verification and validation remain distinct.
5. Negative results, findings and limitations remain visible.
6. A baseline freezes an identified configuration; it does not prove correctness.
7. Change impact is evaluated through explicit relations.
8. A successful POC does not automatically create an admitted Pattern.

## 3. Conceptual metamodel

The model contains five primary concepts:

- **TraceableElement** — an identified engineering or assurance object;
- **TraceLink** — a typed, directed relation between two elements;
- **LinkRule** — the permitted source type, relation and target type;
- **LinkAssessment** — the review of a link's validity, sufficiency and current state;
- **Baseline** — an immutable reference to a selected set of element and link versions.

An element may participate in multiple baselines. A new version does not silently replace an earlier baselined version.

## 4. Traceable-element envelope

Each TraceableElement should expose at least:

| Field | Meaning |
|---|---|
| `element_id` | Stable identity |
| `element_type` | Type from the public catalogue |
| `title` | Human-readable name |
| `version` | Controlled version |
| `state` | Lifecycle state |
| `owner` | Accountable owner |
| `scope` | Applicability and boundary |
| `source_reference` | Authoritative location or origin |
| `configuration` | Relevant configuration identity |
| `classification` | Access and publication constraint |
| `created_at`, `updated_at` | Lifecycle timestamps |
| `supersedes` | Earlier version, when applicable |

## 5. Element-type catalogue

The public type codes are:

| Code | Element |
|---|---|
| SRC | Source |
| PRB | Problem statement |
| NED | Stakeholder or engineering need |
| REQ | Requirement |
| ACC | Acceptance criterion |
| ARC | Architecture element |
| SAF | Safety or assurance assessment |
| CTL | Risk control |
| IMP | Implementation element |
| VFC | Verification case |
| VFR | Verification result |
| VAC | Validation case |
| VAR | Validation result |
| EVI | Evidence item or package |
| CLM | Claim |
| LIM | Limitation |
| DEC | Decision |
| FND | Finding |
| ANO | Anomaly |
| CHG | Change request |
| BLN | Baseline |
| POC | Proof of concept |
| WPR | Work product |
| PAT | Pattern candidate or admitted Pattern |
| RUA | Reuse-applicability assessment |
| DSP | Disposition |

## 6. Common TraceLink contract

A TraceLink contains `link_id`, `relation_id`, source identity and version, target identity and version, rationale, owner, state, creation and review dates, applicable baseline, supporting evidence, limitations and supersession information.

The source and target shall conform to the LinkRule. A reviewer shall reject ambiguous direction, missing versions, invalid endpoint types or a rationale that merely repeats the relation name.

## 7. Canonical relation vocabulary

| ID | Source | Relation | Target |
|---|---|---|---|
| TRL-01 | SRC | informs | PRB |
| TRL-02 | PRB | justifies | NED |
| TRL-03 | NED | is refined by | REQ |
| TRL-04 | REQ or NED | has acceptance criterion | ACC |
| TRL-05 | REQ | is allocated to | ARC |
| TRL-06 | REQ or ARC | is assessed by | SAF |
| TRL-07 | SAF | results in control | CTL |
| TRL-08 | ARC | is realized by | IMP |
| TRL-09 | CTL | is implemented by | IMP |
| TRL-10 | REQ | is verified by | VFC |
| TRL-11 | VFC | produces verification result | VFR |
| TRL-12 | NED | is validated by | VAC |
| TRL-13 | VAC | produces validation result | VAR |
| TRL-14 | VFR, VAR, DEC, FND or DSP | is evidenced by | EVI |
| TRL-15 | EVI | supports | CLM |
| TRL-16 | EVI, CLM, RUA or PAT | is limited by | LIM |
| TRL-17 | DEC | governs | Any controlled element |
| TRL-18 | BLN | contains version | Any controlled element or link |
| TRL-19 | CHG | requests change to | Any controlled element |
| TRL-20 | CHG | potentially impacts | Any controlled element |
| TRL-21 | CHG, ANO or FND | is disposed by | DSP |
| TRL-22 | ANO or FND | affects | Any controlled element |
| TRL-23 | Any element | supersedes | Earlier element of the same type |
| TRL-24 | POC | produces candidate | PAT |
| TRL-25 | EVI | supports applicability | RUA |
| TRL-26 | RUA | assesses candidate | PAT |
| TRL-27 | POC, engineering framework or lifecycle | produces | WPR |
| TRL-28 | WPR | traces to | Any controlled element |

The semantic invariant for TRL-15 may be represented as `EVI_SUPPORTS_CLM`. TRL-28 is a packaging or migration bridge and shall not replace a more precise relation when one exists.

## 8. Link states and validity

Permitted link states are `PROPOSED`, `IN_REVIEW`, `ACTIVE`, `INVALID`, `OBSOLETE`, `SUPERSEDED` and `WAIVED`.

Only an `ACTIVE` link contributes to normal coverage. A `WAIVED` link requires an identified authority, rationale, expiry or review condition, and compensating control when relevant. `INVALID`, `OBSOLETE` and `SUPERSEDED` links remain retained for history but do not satisfy current coverage.

## 9. Coverage and completeness

Coverage is evaluated by rule and by baseline. At minimum, the model supports:

- needs refined by requirements;
- requirements allocated to architecture;
- requirements connected to acceptance criteria and verification cases;
- verification and validation cases connected to actual results;
- claims connected to supporting evidence and limitations;
- changes connected to potentially impacted elements and dispositions.

A coverage percentage never masks a missing Critical relation. Required, optional, waived and not-applicable relations are counted separately. Not-applicable status requires rationale and authority.

## 10. Change impact and controlled evolution

When an element changes, its incoming and outgoing active links are reviewed. Impact review considers requirements, architecture, controls, implementation, V&V, evidence, claims, decisions, baselines, published material and reusable Patterns.

Changes may create findings, invalidate links, require new results, reopen decisions or supersede a baseline. A new baseline records the accepted configuration; prior baselines remain immutable.

## 11. Evidence, claims and decisions

Evidence shall be attributable to an actual source, activity or result and shall carry provenance and configuration. Claims state what the evidence is asserted to support. Limitations bound both the evidence and the claim.

A decision records authority, inputs, rationale, outcome, conditions and reopening triggers. The decision relation does not make its governed element correct; it records controlled authority over that element.

## 12. POC and Pattern traceability

A POC may produce work products, evidence and a Pattern candidate. Admission as a reusable Pattern requires a separate applicability assessment and authorized admission decision. The chain POC → candidate → applicability assessment → admission preserves that distinction.

The Emergency Stop Button may be used as a provisional reference candidate. Door Interlock Safety System and Overtemperature Protection System remain conceptual alternatives. None is selected or authorized for implementation by this model.

## 13. Views

Recommended public views include:

- source–problem–need–requirement map;
- requirement–architecture–implementation map;
- requirement–verification–result–evidence map;
- need–validation–result–evidence map;
- claim–evidence–limitation matrix;
- change-impact and disposition view;
- baseline and supersession view;
- POC-to-Pattern applicability view.

Views are projections. They do not replace the identified elements, links or Evidence Packages from which they are derived.

## 14. Tailoring

- **T1** uses a lightweight register and the minimum relations needed to expose intent, verification, evidence and decisions.
- **T2** uses structured registers, explicit reviews and broader coverage analysis.
- **T3** adds stronger independence, assurance, integrity and change-impact controls.

Tailoring may change depth, formality and review independence. It shall not remove stable identity, provenance, negative evidence, Critical relations, decision authority or controlled change.

## 15. Roles and authority

Element owners maintain content; link owners maintain relation validity; reviewers assess sufficiency and consistency; configuration authority controls baselines; decision authority accepts, rejects, conditions or reopens governed outcomes.

One person may hold several roles for a small activity, but the roles and decisions remain explicit.

## 16. Maturity and limitations

This is a public logical model. It defines the minimum semantics needed for interoperable traceability but does not claim tool implementation, complete project population, safety certification or verified end-to-end operation. Conformance is demonstrated only by populated, reviewed and baselined records for a stated scope.
