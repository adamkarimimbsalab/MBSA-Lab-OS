# MBSA Lab OS — Evidence Package Model

## 1. Purpose

This document defines a tool-neutral Evidence Package: a controlled, reviewable assembly of evidence items, results, claims, findings, limitations, decisions and provenance for a stated scope and configuration.

An Evidence Package improves assessment and transfer. Its existence does not by itself prove completeness, correctness, safety or acceptance.

## 2. Foundational principles

1. Identity is established before inclusion.
2. Evidence precedes the claim it supports.
3. Actual results are distinguished from plans and expected results.
4. Configuration bounds meaning.
5. Limitations travel with evidence and claims.
6. Negative evidence remains visible.
7. Views and summaries do not replace source items.
8. Access classification and public release are separate decisions.
9. Completeness is stated and assessed explicitly.
10. Defining the model is not evidence that it has been implemented.

## 3. Logical package contract

Each package should expose:

| Field | Meaning |
|---|---|
| `package_id` | Stable package identity |
| `title`, `version`, `state` | Human-readable identity and lifecycle |
| `poc_id` | Related POC, if applicable |
| `scope`, `applicability`, `tailoring` | Boundary and proportionality |
| `owner`, `review_authority`, `acceptance_authority` | Responsibilities |
| `classification` | Access constraint |
| `baseline` | Configuration reference |
| `content_index` | Identified included and referenced items |
| `open_findings`, `limitations` | Unresolved or bounding information |
| `created_at`, `updated_at`, `reviewed_at` | Lifecycle timestamps |
| `supersedes` | Earlier package version |
| `retention` | Retention and disposal rule |

Items may be embedded, referenced or deliberately excluded. A reference includes enough identity and access information to retrieve the controlled source. An exclusion records rationale, authority and effect on completeness.

## 4. Evidence item metadata

Every evidence item should include stable identity, type, title, version, producer, creation method, source, configuration, applicable requirement or criterion, result, integrity information, classification, review state, limitations and retention.

Common types include requirement records, architecture descriptions, analyses, safety assessments, test specifications, logs, measurements, review records, images, recordings, configuration records, decisions, findings, waivers and release records.

File extension is not an evidence type. A screenshot or video is evidence only to the extent that provenance, scope, configuration, integrity and interpretation are controlled.

## 5. Claims and acceptance criteria

A claim is a bounded assertion. It records claim identity, wording, scope, owner, supporting evidence, counter-evidence, limitations, assessment state and authority.

An acceptance criterion is testable or otherwise assessable. It is linked to the requirement or need it qualifies, the verification or validation method, the actual result and the relevant evidence. Criteria are never marked satisfied solely because a planned activity exists.

## 6. Result vocabulary

Recommended result values are `PASS`, `FAIL`, `INCONCLUSIVE`, `NOT_RUN`, `NOT_APPLICABLE` and `ERROR`.

- `PASS` means the stated criterion was met for the recorded configuration.
- `FAIL` means it was not met.
- `INCONCLUSIVE` means the evidence cannot support a conclusion.
- `NOT_RUN` means no execution occurred.
- `NOT_APPLICABLE` requires an approved applicability rationale.
- `ERROR` means execution or evidence production was invalid.

An execution error is not a failed engineering criterion unless the criterion explicitly concerns execution reliability. It produces its own finding and may require rerun or repair.

## 7. Findings, anomalies, waivers and limitations

A finding records observation, affected scope, severity, owner, evidence, required action, due condition and disposition. An anomaly describes unexpected behavior or data and remains distinct from its eventual disposition.

A waiver is an authorized, bounded exception. It records rationale, risk, compensating controls, authority, validity period and reopening condition. A waiver does not convert a failed result into a pass.

A limitation records what cannot be concluded. It is linked to affected evidence, claims, decisions and releases and remains visible in derived views.

## 8. Provenance and derivation

Provenance identifies who or what produced an item, from which inputs, using which method and configuration, and when. Derived evidence records the transformation and source identities.

Manual transcription, conversion, filtering, aggregation and redaction are derivations. Each shall preserve a route to the controlled source and disclose any information loss relevant to interpretation.

## 9. Integrity, validity and reproducibility

Integrity controls may include cryptographic hashes, immutable storage, signatures, controlled access and configuration records. Integrity shows that content is unchanged relative to an identity; it does not establish semantic validity.

Validity assessment checks relevance, method suitability, configuration match, calibration where applicable, independence and unresolved anomalies. Reproducibility records the inputs, environment, procedure and expected tolerance needed to repeat the activity.

## 10. Classification and publication boundary

Classification determines who may access an item. Publication is a separate authorized release decision. A public surrogate may replace a restricted source only when it preserves the permitted claim boundary and identifies what has been withheld or abstracted.

Rights, licences, consent, personal data, export restrictions and third-party obligations are assessed before release. Redaction creates a controlled derivative and does not alter the source package.

## 11. Completeness and missing items

Package completeness is evaluated against an expected-content model for the stated scope and tailoring level. Each expected item is `PRESENT`, `MISSING`, `NOT_APPLICABLE`, `WAIVED` or `SUPERSEDED`.

Critical missing evidence cannot be hidden by an aggregate percentage. The package reports missing items, open findings, failed or inconclusive results, limitations and unavailable sources alongside positive evidence.

## 12. States and controlled reopening

Recommended package states are `PLANNED`, `ASSEMBLING`, `IN_REVIEW`, `ACCEPTED`, `ACCEPTED_WITH_CONDITIONS`, `REJECTED`, `SUPERSEDED`, `ARCHIVED` and `WITHDRAWN`.

Reopening is triggered by relevant change, new counter-evidence, an expired waiver, invalidated configuration, material error, rights change or an affected decision reopening. Reopening creates a controlled state transition and preserves prior assessment history.

## 13. Retention, supersession and archiving

An accepted package is never silently overwritten. Corrections create a new version or erratum linked to the original. Supersession identifies the replacement and reason. Withdrawal preserves identity and records why the package should no longer be relied upon.

Retention covers content, metadata, integrity records, access constraints and disposition authority. Archiving is a lifecycle state, not evidence deletion.

## 14. Traceability interfaces

The package uses the public traceability model. Evidence supports claims through TRL-15; actual results are evidenced through TRL-14; limitations bind evidence and claims through TRL-16; baselines contain selected versions through TRL-18.

Within the logical architecture, LC-04 represents the Evidence and Assurance domain and IF-04 represents the Evidence Package interface. These references define public semantics rather than a specific tool implementation.

## 15. Minimum views

Recommended views are:

- package identity and baseline summary;
- content index and expected-item status;
- requirement–criterion–method–result–evidence matrix;
- claim–support–counter-evidence–limitation matrix;
- findings, waivers and actions register;
- provenance and derivation chain;
- classification and release view;
- supersession and retention history.

Views are generated from controlled content and never become an alternative source of truth.

## 16. Tailoring

- **T1** permits a compact package with essential identities, results, evidence, findings, limitations and decision.
- **T2** adds structured completeness, provenance, reviews and lifecycle records.
- **T3** adds greater independence, integrity assurance, reproducibility and retention rigor.

No tailoring level removes evidence provenance, actual-result visibility, Critical missing-item disclosure, claim limitations, decision authority or controlled supersession.

## 17. Conceptual POC applicability

The model can support a provisional Emergency Stop Button reference, a Door Interlock Safety System alternative and an Overtemperature Protection System alternative. Typical evidence differs by candidate, but the package contract remains stable.

This applicability is conceptual and non-implementing. It does not select a POC, authorize work, demonstrate a result or admit a Pattern.

## 18. Roles and authority

The package owner assembles and maintains the package. Evidence producers remain accountable for source items. Reviewers assess relevance, sufficiency and validity. Classification and publication authorities control access and release. Acceptance authority issues the package decision and conditions.

Role combination may be proportionate to scale, but accountability, conflicts and decisions remain explicit.

## 19. Maturity and limitations

This model defines a public logical contract. It is not a claim that a complete evidence repository, automated integrity service, qualified toolchain or assurance case has been deployed. Maturity is demonstrated package by package against an identified scope and baseline.
