# MBSA Lab OS — Video Factory Minimal Interface

## 1. Document Control

| Field | Value |
|---|---|
| Document | `docs/15_Video_Factory_Minimal_Interface.md` |
| User Story | US019 — Video Factory Minimal Interface |
| Version | 0.1 |
| Date | 2026-08-24 |
| Status | CANDIDATE — US019 |
| System of Interest | MBSA Lab OS |
| Repository classification | PUBLIC |
| Logical owner | Video Factory Core under Governance control |
| Acceptance authority | Governance Core |
| Publication authority | Publication Governance Gateway |

This document is a normative architecture model for a future controlled video
production capability. It defines an interface and its control semantics. It
does not demonstrate that a Video Factory, a production pipeline, a studio, a
POC, or any video release is operational.

## 2. Purpose and Scope

### 2.1 Purpose

The purpose is to define the minimum controlled interface between MBSA Lab OS
engineering assets and a future video production workflow. The interface makes
the demonstrated configuration, supporting evidence, permitted message,
production lineage, reviews, publication decision, and post-release history
identifiable and navigable.

The interface SHALL prevent audiovisual quality, repository presence, or a
successful recording from being interpreted as engineering acceptance,
publication authorization, product readiness, certification, conformity, or
safety integrity.

### 2.2 In scope

This document defines:

- video request, work-item, release, and erratum identities;
- a minimum input and readiness contract;
- a technology-independent video-type taxonomy;
- roles, ownership, reviews, and decision authorities;
- a fourteen-step workflow from request to retention;
- storyboard, script, capture, editing, and configuration controls;
- technical, semantic, evidence, traceability, and publication reviews;
- traceability from a video release to its request, POC, configuration,
  engineering sources, Git baseline, Evidence Package, Claims, and limitations;
- release, correction, erratum, supersession, withdrawal, and reopening rules;
- proportional tailoring at T1, T2, and T3;
- conceptual applicability to the three strategic candidate POCs;
- failure modes, stop conditions, maturity limits, and non-claims.

### 2.3 Out of scope

The following are explicitly outside US019:

- producing, recording, editing, or publishing a real video;
- selecting, designing, implementing, executing, or accepting a POC;
- implementing a studio, pipeline, CI/CD workflow, API, plugin, platform, or
  automation;
- mandating OBS, x264, a codec, container, hosting service, or channel;
- defining a campaign, series, channel, or marketing strategy;
- creating fictitious evidence, results, readiness, or publication decisions;
- correcting inherited documentary deviations `E-HER-01` through `E-HER-03`;
- copying or modifying the private Master Plan or MBSA-Lab-Control content;
- defining the detailed First POC Readiness Framework owned by US020;
- starting US020 or any later User Story.

## 3. Authority and Source Hierarchy

When sources conflict, the following precedence applies:

1. verified Git evidence and an applicable controlled baseline;
2. the Integrated Quality Gates Model in `docs/13`;
3. the Evidence Package Model in `docs/12`;
4. the Traceability Model in `docs/11`;
5. the POC Lifecycle in `docs/10`;
6. the Minimal Engineering Framework in `docs/09`;
7. Pattern admission rules and template in `docs/14` and `templates/`;
8. capability and logical architecture in `docs/08`;
9. system boundary and governance sources in `docs/03` through `docs/07`;
10. the controlled Sprint 2 backlog for the original US019 intent.

The backlog records US019 as `Should`. The controlled Sprint 2 decision records
US019 as `Must`. This version difference is preserved; the backlog source is not
silently rewritten.

The private Master Plan may govern sequencing through an authorized boundary,
but its content SHALL NOT be reproduced in the public repository.

## 4. Definitions and Normative Language

`SHALL` and `MUST` denote mandatory obligations. `SHOULD` denotes a recommended
practice requiring rationale when omitted. `MAY` denotes an option.

| Term | Definition |
|---|---|
| Video request | Controlled statement of audience, purpose, type, scope, sources, intended message, and requested channel. |
| Video work item | Versioned production record joining a request to brief, storyboard, script, capture, edit, and review artefacts. |
| Video candidate | Rendered output awaiting all applicable reviews and a publication decision. |
| Video release | Immutable identity for the exact audiovisual content authorized for a stated channel and boundary. |
| Video erratum | Controlled post-release notice that qualifies or corrects a bounded aspect without silently replacing the release. |
| Exploitable baseline | Identified and sufficiently stable POC configuration, engineering-source set, result set, evidence position, rights position, and authorized message suitable for the proposed video purpose. |
| Technical Quality Review | Review of audio, image, synchronization, legibility, render integrity, and related audiovisual properties. |
| Semantic/Engineering Review | Review of fidelity to engineering sources, configuration, terminology, results, limitations, and permitted Claims. |
| Evidence/Traceability Review | Review of identities, links, Evidence Packages, Claims, Findings, gaps, provenance, and version consistency. |
| Publication Review | Independent decision on classification, rights, consent, public surrogate, channel, audience, and authorized message. |
| Primary evidence | Controlled information generated or retained as direct support for a Claim or result. A video is not primary evidence by default. |
| Public surrogate | Authorized public representation of a restricted source that does not disclose protected content or imply unsupported equivalence. |

## 5. System Boundary and Invariants

### 5.1 Boundary

MBSA Lab OS is the System of Interest. `MBSA-Lab-OS` remains public.
MBSA-Lab-Control, the private Master Plan, credentials, personal data, and
restricted strategic-control content remain outside the public repository.

The interface consumes controlled references to engineering and evidence
assets. It does not transfer their logical ownership to the Video Factory Core.

### 5.2 Invariants

1. Governance owns scope, tailoring, waivers, acceptance, baselines, and final
   authority allocation.
2. Engineering owns engineering source work products.
3. Evidence & Traceability maintains references and assurance status without
   taking ownership of source artefacts.
4. Publication Governance Gateway controls the release boundary.
5. A video is a communication projection and SHALL NOT replace an engineering
   source, V&V result, Evidence Package, Claim, Finding, or Gate decision.
6. Evidence precedes accepted Claims, publication, and reuse decisions.
7. Negative, failed, invalid, contradictory, inconclusive, and not-executed
   results remain visible when material to interpretation.
8. Technical quality, semantic acceptance, evidence sufficiency, and
   publication authorization are separate decisions.
9. Git establishes repository identity, transaction, and filiation; it does
   not establish semantic truth or audiovisual quality.
10. Pattern Candidate, Pattern admission, video communication, and target reuse
    remain separate concepts and decisions.
11. Tailoring SHALL NOT remove an essential control objective.
12. Maturity SHALL NOT be inferred from an interface definition.

## 6. Video Factory Minimal Interface

### 6.1 Logical exchange

The interface accepts a controlled **Video Source Package** and returns a
controlled **Video Release Package** or an explicit non-release disposition.

The Video Source Package SHALL contain or reference:

- the video request and intended type;
- POC identity, scope, configuration, and lifecycle position;
- Git commit, release, tree, and applicable blob identities when relevant;
- engineering work products and authoritative versions;
- Evidence Package baseline, Claims, Findings, limitations, and dispositions;
- audience, purpose, permitted message, and prohibited overclaims;
- source owners, classification, rights, licences, consent, and provenance;
- proposed storyboard, script, capture plan, and environment constraints;
- applicable tailoring and review obligations.

The Video Release Package SHALL contain or reference:

- exact `VIDREL` identity and immutable content checksum;
- predecessor work item and request;
- rendered file identity, duration, technical attributes, and language;
- review records and their separate outcomes;
- publication decision, authority, channel, date, and classification;
- demonstrated POC, configuration, source, Evidence, and Claim links;
- mandatory limitations, disclosures, errata, and retention status;
- successor or withdrawal links when applicable.

### 6.2 Interface status

| Status | Meaning |
|---|---|
| `PROPOSED` | Request recorded but not qualified. |
| `QUALIFIED` | Purpose, type, scope, audience, and source owners are identified. |
| `NOT_READY` | At least one mandatory readiness condition is absent, invalid, contradictory, or unauthorized. |
| `READY` | Input contract is complete enough to authorize bounded production work. |
| `IN_PRODUCTION` | Authorized capture or editing work is active. |
| `IN_REVIEW` | Candidate content is undergoing one or more independent reviews. |
| `REWORK` | Defined correction is required before reconsideration. |
| `DEFERRED` | Work is paused with a trigger or review date. |
| `RELEASE_AUTHORIZED` | Exact candidate and release boundary are approved. |
| `RELEASED` | Authorized content is available on the approved channel. |
| `SUPERSEDED` | A successor release replaces the release for stated uses. |
| `WITHDRAWN` | Availability is revoked under a controlled decision. |
| `RETAINED` | Historical artefacts and decisions are preserved under retention rules. |

These interface statuses do not replace Gate-instance states defined in
`docs/13`.

## 7. Interface Entities and Stable Identities

### 7.1 Required identities

| Prefix | Entity | Minimum identity content |
|---|---|---|
| `VIDREQ` | Video Request | stable ID, version, owner, audience, purpose, type, scope, classification, status |
| `VIDWORK` | Video Work Item | stable ID, version, request, producer, brief/script/capture/edit versions, candidate checksum, status |
| `VIDREL` | Video Release | stable ID, version, exact checksum, decision, channel, classification, release date, status |
| `VIDERR` | Video Erratum | stable ID, version, affected release, issue, impact, correction, authority, status |

An implementation MAY choose another syntax, but identities SHALL be unique,
stable, versioned, and resolvable within the governed scope.

### 7.2 Common metadata

Every entity SHALL record:

- identity and version;
- title and concise purpose;
- logical owner and accountable authority;
- creation and last-decision dates;
- lifecycle status;
- classification: `PUBLIC`, `PRIVATE`, or `BOUNDARY_SHARED`;
- provenance and source references;
- applicable baseline identifier;
- predecessor, successor, and invalidation status where applicable;
- limitations and open Findings;
- retention and access position.

## 8. Video Type Taxonomy

| Type | Admissible source position | Permitted message | Mandatory reviewers | Mandatory limitation |
|---|---|---|---|---|
| Architecture/concept walkthrough | Controlled architecture baseline or clearly marked candidate | Explain structure, boundary, responsibilities, and rationale | Engineering; semantic; publication | Architecture maturity and unimplemented elements |
| Engineering work-product walkthrough | Identified work-product version and owner authorization | Explain content and engineering use | Source owner; semantic; publication | Review/acceptance status and scope |
| POC demonstration | Identified POC configuration and exploitable baseline | Show observed behaviour within the recorded scenario | POC owner; V&V; evidence; publication | Configuration, scenario, result limits, and non-product status |
| V&V method/result explanation | Executed cases and controlled results | Explain method, result, coverage, and conclusions | V&V; evidence; semantic; publication | Verification/validation distinction and coverage gaps |
| Evidence-package summary | Identified Evidence Package baseline | Summarize Claims, support, Findings, and limitations | Evidence; Claim owners; publication | Summary is not the Evidence Package itself |
| Lesson learned or Pattern-Candidate explanation | Accepted lesson or identified Pattern Candidate | Explain source-bounded learning or candidate rationale | Engineering; evidence; pattern/reuse; publication | Candidate is not an admitted Pattern or reusable authorization |
| Corrective update or erratum | Existing `VIDREL` and controlled issue | Qualify or correct an earlier communication | Affected source owners; semantic; publication | Exact affected release and residual impact |

A demonstration video SHALL NOT be treated as a source test record or primary
evidence unless a separately authorized capture contract defines that role,
configuration, integrity, provenance, and retention. The default rule is that
the video references primary evidence.

## 9. Roles, Ownership, and Authorities

| Role | Responsibility | Prohibited inference |
|---|---|---|
| Requester/Sponsor | States audience, purpose, need, expected use, and requested timing | Request does not authorize production or publication |
| POC owner | Identifies POC scope, configuration, status, and relevant results | POC ownership does not authorize public release |
| Engineering source owner | Confirms source identity, version, meaning, and permitted representation | Review does not transfer source ownership |
| Video producer | Controls work-item lineage, capture, editing, and candidate integrity | Production does not authorize Claims |
| Technical reviewer | Evaluates audiovisual fitness and render integrity | Technical PASS does not imply semantic PASS |
| Semantic/Engineering reviewer | Evaluates fidelity, terminology, configuration, results, and limitations | Semantic PASS does not authorize publication |
| Evidence reviewer | Evaluates links, support, Findings, gaps, and Claim strength | Completeness does not imply positive results |
| Rights/privacy reviewer | Evaluates licences, attribution, consent, personal data, and restricted material | Rights PASS does not imply engineering validity |
| Publication authority | Decides exact release boundary, channel, classification, and message | Publication does not imply product readiness or Pattern admission |
| Governance Core | Owns scope, tailoring, conditions, waivers, baselines, and final escalation | Governance decision does not manufacture missing evidence |

A person MAY fulfil several roles for a low-complexity item, but logical review
outcomes and authorities SHALL remain separately recorded. Independence SHALL
be increased with risk, novelty, irreversibility, Claim breadth, safety
significance, or external exposure.

## 10. Input and Readiness Contract

### 10.1 Mandatory input record

The following fields are mandatory before status `READY`:

| Field | Required content |
|---|---|
| Request | `VIDREQ` identity, version, owner, type, purpose, audience, and requested channel |
| POC or engineering subject | Stable identity, scope, configuration, maturity, and owner |
| Baseline | Commit/release and authoritative source versions actually addressed |
| Scenario | Demonstrated or explained scenario, assumptions, preconditions, and expected boundary |
| Results | Available V&V results, execution state, coverage, anomalies, and conclusions |
| Evidence | Evidence Package identity/version, relevant Evidence Items, Claims, Findings, and limitations |
| Message | Authorized statements, required disclosures, and prohibited Claims |
| Sources | Exact source artefacts, versions, owners, provenance, and access position |
| Rights | Classification, licences, attribution, consent, personal-data review, and surrogate decisions |
| Production | Proposed storyboard/script/capture plan and environment constraints |
| Reviews | Applicable reviewers, decision authorities, criteria, and tailoring record |
| Retention | Proposed retention, channel persistence, and withdrawal mechanism |

### 10.2 Obligation status

Each input obligation SHALL be classified `MANDATORY`, `CONDITIONAL`, or
`OPTIONAL`, and evaluated as `PRESENT`, `MISSING`, `NOT_APPLICABLE`, `INVALID`,
or `SUPERSEDED`. `NOT_APPLICABLE` requires rationale and authority.

Any mandatory field that is missing, invalid, contradictory, superseded without
a successor, or unauthorized produces `NOT_READY`. A waiver does not create
evidence, make a source valid, or convert a failed result into `PASS`.

## 11. Exploitable Baseline Model

### 11.1 Minimum conditions

An exploitable baseline exists for a proposed purpose only when all applicable
conditions below are satisfied:

1. POC or engineering subject, configuration, and scope are unambiguous.
2. Commit, release, and demonstrated source versions are identified.
3. The intended scenario is stable enough to capture or explain consistently.
4. Actual V&V results and execution status are identifiable.
5. Evidence Package and applicable Claims are mutually compatible.
6. Findings, limitations, gaps, and negative results are visible.
7. Source ownership, classification, rights, licences, and consent are decided.
8. Public/private boundaries and required public surrogates are decided.
9. The permitted message and prohibited overclaims are explicit.
10. Required reviewers and publication authority are allocated.
11. Open changes do not invalidate the proposed representation.
12. Reproduction limitations and environmental dependencies are stated.

### 11.2 Readiness decision

Readiness is purpose-specific. A baseline suitable for an internal architecture
walkthrough may be unsuitable for a public POC-result demonstration.

The readiness disposition SHALL be one of:

- `GO`: authorize the next bounded production step;
- `GO_WITH_CONDITIONS`: authorize it with owned conditions, due points, and stop
  triggers;
- `NO-GO`: refuse progression;
- `REWORK`: return a defined input for correction;
- `DEFER`: pause until a stated trigger or review date.

These decisions reuse the vocabulary and authority rules of `docs/13`. They do
not create a parallel family of video Gates.

## 12. Minimal End-to-End Workflow

The named `CP-VID-*` elements below are checkpoints, not new Gate families.
Their decisions SHALL be recorded through applicable Gate instances from
`docs/13`.

| Step | Objective and principal activity | Inputs | Outputs | Owner/review | Applicable control and exit |
|---|---|---|---|---|---|
| 1. Request/proposal | Record purpose, audience, type, scope, expected use, and requested channel | Sponsor need | Versioned `VIDREQ` | Requester; Governance intake | `GATE-GOV-01`; intelligible and bounded request |
| 2. Qualification | Confirm type, relevance, source owners, exposure, and major constraints | `VIDREQ` | Qualification record | Video coordinator; Engineering | `CP-VID-01`; qualify, rework, defer, or reject |
| 3. Baseline/readiness | Evaluate the exploitable-baseline contract | Qualification; POC/source/evidence records | Readiness record | Governance; POC; Evidence | `GATE-GOV-02` plus applicable engineering/evidence Gates; `READY` or `NOT_READY` |
| 4. Source and rights package | Assemble exact sources, classifications, licences, consent, and surrogates | Ready baseline | Video Source Package | Source owners; rights/privacy | `GATE-PUB-01` input review; all mandatory sources authorized |
| 5. Brief/storyboard/script | Define narrative, visual sequence, Claims, disclosures, and prohibited messages | Source Package | Versioned brief, storyboard, script | Producer; semantic reviewers | `CP-VID-02`; source-aligned script accepted for capture planning |
| 6. Capture plan/environment | Identify scene, commands, configuration, tools, versions, parameters, and recovery | Accepted script | Capture plan and environment record | Producer; POC/Engineering | Applicable `GATE-ENG-*`; reproducible-enough plan |
| 7. Recording/capture | Capture only the authorized scenario and sources | Capture plan | Raw captures and capture log | Producer | `CP-VID-03`; raw assets identified and intact |
| 8. Editing | Produce a candidate while retaining source lineage and disclosures | Raw assets; script | Versioned candidate and edit-decision list | Producer | `CP-VID-04`; candidate checksum and lineage complete |
| 9. Technical review | Evaluate audio, image, synchronization, legibility, and render integrity | Candidate | Technical review record | Technical reviewer | `PASS`, `REWORK`, or `BLOCKED`; no semantic inference |
| 10. Semantic review | Verify fidelity to sources, configuration, results, terminology, and limitations | Candidate; sources | Semantic review record | Engineering/POC reviewers | Applicable `GATE-ENG-*`; `PASS`, `REWORK`, or `BLOCKED` |
| 11. Evidence/trace review | Verify release links, Evidence, Claims, Findings, gaps, and versions | Candidate; Evidence Package; trace view | Evidence/trace review record | Evidence reviewer | `GATE-EVI-01..04`; gaps dispositioned |
| 12. Publication decision | Decide classification, rights, surrogate, exact message, channel, and conditions | Candidate and all reviews | Publication decision | Publication authority | `GATE-PUB-01`; `GO`, `GO_WITH_CONDITIONS`, `NO-GO`, `REWORK`, or `DEFER` |
| 13. Controlled release | Bind immutable content to release identity and authorized channel | Authorized candidate | `VIDREL` and release record | Release custodian | Exact checksum/channel match; otherwise stop |
| 14. Feedback and lifecycle | Monitor, correct, issue errata, supersede, withdraw, retain, or reopen | Released content; feedback; changes | `VIDERR`, successor, withdrawal, or retention record | Governance; affected authorities | `GATE-CLS-01/02` and publication controls |

No downstream step may infer completion of an upstream control merely from the
existence of a file or a repository commit.

## 13. Storyboard, Script, and Capture Controls

### 13.1 Storyboard and script

Each storyboard or script SHALL identify:

- version, author, reviewers, and status;
- intended audience, learning objective, and duration range;
- scene sequence and source references;
- spoken and on-screen Claims;
- required limitations, disclosures, attribution, and safety statements;
- permitted terminology and prohibited overclaims;
- displayed POC/configuration/baseline identity;
- treatment of failed, negative, incomplete, or inconclusive results;
- planned redaction or public surrogate;
- differences from predecessor versions.

### 13.2 Capture plan

The capture plan SHALL identify:

- scenario, preconditions, steps, expected observations, and stop conditions;
- POC configuration, software/hardware versions, commit/release, and data set;
- operating environment and material dependencies;
- screen, camera, audio, terminal, model, or diagram sources;
- recording tool and version when relevant;
- resolution, frame rate, audio format, colour, and synchronization settings as
  production parameters, not architectural dependencies;
- sensitive fields, credentials, personal data, and prohibited views;
- time/reference synchronization and capture-log method;
- recovery, retake, and invalid-capture rules.

### 13.3 Environment statement

OBS and x264 MAY be recorded as an available environment. They SHALL NOT be
mandated by this interface, treated as logical architecture elements, or used
as evidence that a Video Factory exists.

## 14. Technical Quality Review

The Technical Quality Review SHALL evaluate at least:

- file readability and absence of corruption;
- audio intelligibility, clipping, unwanted noise, and channel consistency;
- image resolution, focus, exposure, frame stability, and artefacts;
- audio/video synchronization;
- readability of diagrams, models, code, terminals, captions, and identifiers;
- timing of overlays, transitions, and annotations;
- absence of unintended blank, frozen, or duplicated sequences;
- consistency between candidate checksum, review target, and release candidate;
- accessibility requirements activated for the audience and channel.

Result values are `PASS`, `FAIL`, `BLOCKED`, `NOT_EXECUTED`, or
`INCONCLUSIVE`. Only `PASS` on the exact candidate satisfies technical review.
It does not satisfy semantic, evidence, rights, or publication review.

## 15. Semantic and Engineering Review

The Semantic/Engineering Review SHALL verify:

- the exact POC, configuration, commit, baseline, and source versions shown;
- consistency between narration, captions, diagrams, behaviour, and sources;
- correct distinction between need, requirement, architecture, implementation,
  verification, validation, Evidence, Claim, Finding, and decision;
- faithful reporting of actual results and execution state;
- visibility of material limitations, assumptions, negative results, and gaps;
- absence of claims beyond the demonstrated scope or evidence strength;
- absence of product-readiness, certification, conformity, or safety-integrity
  implications unless separately and validly authorized;
- correct maturity statement for MBSA Lab OS capabilities;
- absence of unauthorized private or restricted information;
- consistency of terminology with the controlled architecture corpus.

A montage SHALL NOT remove a material failure, contradiction, or limitation in
a manner that changes the meaning of the underlying engineering record.

## 16. Evidence and Traceability Review

### 16.1 Review obligations

The review SHALL establish that:

- every accepted video Claim identifies scope, subject, configuration, and
  supporting Evidence;
- Claim strength does not exceed Evidence strength;
- the Evidence Package baseline and relevant items are identifiable;
- `PASS`, `FAIL`, `BLOCKED`, `NOT_EXECUTED`, and `INCONCLUSIVE` remain distinct;
- missing, invalid, contradictory, and superseded evidence remains visible;
- Findings, limitations, waivers, and dispositions are linked;
- every displayed result maps to its executed configuration and procedure;
- public surrogates are authorized and do not imply source equivalence;
- the release trace view is navigable in both directions.

### 16.2 Minimum relations

| Source | Relation | Target | Obligation |
|---|---|---|---|
| `VIDREQ` | `authorizes_scope_for` | `VIDWORK` | Mandatory |
| `VIDWORK` | `uses_source` | Engineering work product/version | Mandatory for every represented source |
| `VIDWORK` | `demonstrates_configuration` | POC/configuration/baseline | Conditional; mandatory for demonstrations |
| `VIDWORK` | `references` | Evidence Package baseline | Mandatory for evidence- or result-bearing content |
| `VIDWORK` | `communicates` | Claim | Conditional; mandatory for every asserted engineering proposition |
| Claim | `is_supported_by` | Evidence Item | Mandatory for accepted Claims |
| Claim/Evidence/Release | `is_limited_by` | Limitation | Mandatory when a known limitation exists |
| Finding | `affects` | Source, Claim, work item, or release | Mandatory for actionable Findings |
| Decision | `governs` | `VIDREQ`, `VIDWORK`, or `VIDREL` | Mandatory for decisions with effect |
| `VIDREL` | `releases_candidate_from` | `VIDWORK` version/checksum | Mandatory |
| `VIDREL` | `published_under` | Publication decision/channel | Mandatory |
| `VIDERR` | `qualifies` | `VIDREL` | Mandatory |
| Successor `VIDREL` | `supersedes` | Predecessor `VIDREL` | Mandatory for supersession |

Relations SHALL preserve identity, version, provenance, status, and applicable
baseline. Invalidated and superseded links remain reconstructable.

## 17. Publication Boundary and Decision Model

### 17.1 Publication review

Publication Review SHALL independently evaluate:

- `PUBLIC`, `PRIVATE`, or `BOUNDARY_SHARED` classification;
- repository and channel compatibility;
- copyright, licence, attribution, brand, and redistribution rights;
- personal data, voice/image consent, credentials, and confidential material;
- exact public surrogate and redaction decisions;
- permitted audience, territory, channel, and persistence;
- Claim wording, required limitations, and callouts;
- release checksum and reviewed candidate identity;
- withdrawal mechanism and responsible authority.

### 17.2 Decisions

| Decision | Effect |
|---|---|
| `GO` | Authorizes release of the exact candidate to the exact channel and boundary. |
| `GO_WITH_CONDITIONS` | Authorizes release only when explicit owned conditions and verification points are satisfied. |
| `NO-GO` | Refuses release. |
| `REWORK` | Returns defined content or metadata for correction. |
| `DEFER` | Pauses the decision until a stated trigger or review date. |
| `WITHDRAW` | Revokes availability under a controlled post-release decision. |
| `SUPERSEDE` | Authorizes a successor relationship and predecessor disposition. |

The decisions reuse `docs/13` semantics. Publication authorization is bound to
the exact content checksum, message, classification, channel, and conditions.
A change to any bound element requires impact analysis and, where material, a
new decision.

## 18. Release Identity and Traceability

Each `VIDREL` SHALL record:

- release ID and version;
- exact audiovisual checksum and technical metadata;
- predecessor `VIDREQ` and `VIDWORK` versions;
- POC identity, configuration, scenario, and baseline;
- Git commit/release and represented source versions;
- Evidence Package, Claims, Findings, and limitations;
- storyboard, script, capture-plan, raw-capture, and edit versions;
- Technical, Semantic, Evidence/Traceability, and Publication review results;
- decision identity, authority, date, conditions, and rationale;
- channel, audience, classification, release date, and retention rule;
- errata, withdrawal status, and predecessor/successor relations.

A published file SHALL NOT be overwritten silently. A byte change produces a
new candidate identity and, if authorized, a new `VIDREL` version.

## 19. Corrections, Errata, Supersession, and Withdrawal

### 19.1 Before publication

A correction before publication creates a new `VIDWORK` candidate version.
Affected reviews SHALL be repeated according to impact. The rejected or
superseded candidate remains identifiable until the retention decision.

### 19.2 After publication

| Situation | Required control |
|---|---|
| Bounded non-material clarification | Create `VIDERR`; link the affected release, issue, interpretation impact, and authority. |
| Material semantic or audiovisual correction | Create a new candidate and new `VIDREL`; repeat affected reviews and publication decision. |
| Preferred successor | Record `SUPERSEDE`, predecessor/successor links, migration message, and predecessor availability. |
| Unauthorized, unsafe, misleading, or rights-invalid content | Record `WITHDRAW`, reason, authority, channel actions, consumer notification, and retained history. |
| Changed source, POC, baseline, Evidence, Claim, rights, classification, or channel | Perform impact analysis and reopen affected readiness, review, and publication decisions. |

Withdrawal SHALL NOT erase the historical decision record. Known consumers
SHOULD be notified proportionately when the change affects interpretation,
safety, rights, or reliance.

## 20. Tailoring T1/T2/T3

| Level | Typical complexity | Permitted simplification | Controls that remain mandatory |
|---|---|---|---|
| T1 | Short, low-exposure internal explanation with no substantive result Claim | One person may fulfil several logical roles; brief and storyboard may be combined | Identity, scope, sources, classification, rights, semantic accuracy, limitations, exact candidate, decision, retention |
| T2 | Public walkthrough or bounded demonstration with normal engineering Claims | Review records may use compact templates; selected workflow checkpoints may be combined | Exploitable baseline, source lineage, separate technical/semantic/evidence/publication outcomes, Claim support, release identity |
| T3 | High-exposure, safety-significant, multi-source, third-party, or broad-Claim content | No default simplification; additional independence and assurance may be required | All applicable obligations, explicit independence, detailed evidence and rights review, controlled release and withdrawal readiness |

Tailoring changes ceremony, not objectives. Omitted activities SHALL have a
rationale, authority, impact assessment, and retained coverage of the essential
control objective.

## 21. Conceptual Application to the Three Strategic POCs

This section demonstrates model applicability only. It does not select, start,
implement, test, accept, or authorize a POC or video.

| Candidate POC | Possible video purpose | Mandatory baseline emphasis | Mandatory limitations |
|---|---|---|---|
| Emergency Stop Button — priority candidate | Architecture walkthrough or controlled POC demonstration | Exact control logic, configuration, test scenario, safety-related assumptions, executed results, and Evidence Package | Prototype scope; no product or safety-integrity Claim; negative and boundary results visible |
| Door Interlock Safety System — fallback | Engineering-work-product walkthrough or V&V method explanation | State/transition baseline, interlock conditions, fault cases, verification/validation distinction | Conceptual/fallback status; no operational-readiness implication |
| Overtemperature Protection System — fallback | Architecture or result explanation | Threshold assumptions, sensing/control configuration, cases, environment, results, and limitations | No certification/conformity Claim; environmental and modelling limits explicit |

No row constitutes readiness. US020 owns the detailed framework used to decide
whether a first POC may begin in Sprint 3.

## 22. Failure Modes and Stop Conditions

| Failure mode | Required response |
|---|---|
| POC, configuration, commit, or source version is ambiguous | `NOT_READY`; resolve identity before capture |
| Evidence Package or material result is absent/invalid | Stop the affected Claim or content; do not infer support |
| Script exceeds authorized Claims | `REWORK`; align message and limitations |
| Candidate differs from reviewed checksum | Invalidate review applicability and repeat affected reviews |
| Technical PASS is presented as engineering or publication acceptance | Correct the decision record and block release |
| Private/restricted content crosses the public boundary | Stop, classify, remove or authorize a surrogate through Publication Governance |
| Rights, licence, consent, or attribution is unresolved | `NO-GO` or `DEFER` publication |
| Negative result or material limitation is removed by editing | Block release and restore faithful representation |
| Tool or codec is presented as an architectural dependency | Correct the interface statement |
| Video is treated as primary evidence without an authorized capture contract | Reclassify it as communication or establish a separate controlled evidence contract |
| Published content requires material correction | Create successor release or withdraw; never overwrite silently |
| Baseline, Evidence, Claim, rights, classification, or channel changes | Perform impact analysis and reopen affected decisions |
| Gate authority or review independence is unclear | Stop and request Governance disposition |
| US020 activity is introduced | Stop; US020 requires a separate explicit GO |

Every DEBUG record SHALL preserve symptom, cause, impact, correction, retest,
prevention, and final status. A failed control SHALL NOT be hidden by rerunning
an altered command without retaining the failed variant in the DEBUG register.

## 23. Inherited Documentary Deviations

The following pre-existing deviations are acknowledged and remain outside the
functional scope of US019:

| ID | Controlled status | Description | Disposition |
|---|---|---|---|
| `E-HER-01` | OPEN / BOUNDED / NON-BLOCKING | Final LF absent in `README.md` and `docs/00_Project_Overview.md` | Governance maintenance Gate required |
| `E-HER-02` | OPEN / BOUNDED / NON-BLOCKING | Trailing whitespace in canonical blobs of `docs/01`, `docs/02`, and `docs/03` | Governance maintenance Gate required |
| `E-HER-03` | OPEN / BOUNDED / NON-BLOCKING | Physical CRLF in the Windows checkout of `docs/02` and `docs/03`, with no canonical Git divergence after filters | Treat canonical blob and checkout representation separately |

These deviations SHALL NOT be corrected opportunistically in the US019
functional commit and SHALL NOT be propagated into this document. Their
controlled correction is due before US021 and before baseline v0.2.

## 24. Compliance and Acceptance Mapping

The following matrix maps every frozen US019 Acceptance Criterion to an
inspectable section of this document. Final `PASS` requires Gate evidence; the
mapping alone is not acceptance.

| AC | Coverage | Candidate assessment |
|---|---|---|
| AC-US019-01 | Sections 3 and 5 | Covered |
| AC-US019-02 | Sections 5 and 6 | Covered |
| AC-US019-03 | Sections 3, 5, 9, and 10 | Covered |
| AC-US019-04 | Sections 3, 11, 12, and 17–19 | Covered |
| AC-US019-05 | Sections 7, 16, and 18 | Covered |
| AC-US019-06 | Sections 6, 10, 11, and 16 | Covered |
| AC-US019-07 | Sections 3, 11, 12, 17, and 22 | Covered |
| AC-US019-08 | Sections 5, 8, and 21 | Covered |
| AC-US019-09 | Section 2 | Covered |
| AC-US019-10 | Sections 6, 7, and 10 | Covered |
| AC-US019-11 | Section 8 | Covered |
| AC-US019-12 | Sections 10 and 11 | Covered |
| AC-US019-13 | Sections 7, 10, 11, and 18 | Covered |
| AC-US019-14 | Sections 5, 6, 9, and 16 | Covered |
| AC-US019-15 | Sections 4, 5, 8, and 16 | Covered |
| AC-US019-16 | Section 12 | Covered |
| AC-US019-17 | Section 12 | Covered |
| AC-US019-18 | Section 13 | Covered |
| AC-US019-19 | Sections 13 and 18 | Covered |
| AC-US019-20 | Sections 14–17 | Covered |
| AC-US019-21 | Sections 5, 9, 14, and 17 | Covered |
| AC-US019-22 | Sections 16 and 18 | Covered |
| AC-US019-23 | Sections 5, 9, 10, and 17 | Covered |
| AC-US019-24 | Sections 5, 8, 13, 15, and 16 | Covered |
| AC-US019-25 | Section 19 | Covered |
| AC-US019-26 | Sections 18 and 19 | Covered |
| AC-US019-27 | Sections 17 and 19 | Covered |
| AC-US019-28 | Sections 11, 12, and 17 | Covered |
| AC-US019-29 | Section 20 | Covered |
| AC-US019-30 | Section 13.3 | Covered |
| AC-US019-31 | Sections 2, 6, and 13 | Covered |
| AC-US019-32 | Section 21 | Covered |
| AC-US019-33 | Sections 1, 5, and 25 | Covered |
| AC-US019-34 | Section 23 | Covered |
| AC-US019-35 | Process evidence and final catalogue | Pending Gate evidence |
| AC-US019-36 | R5–R7 evidence and closure deliverables | Pending Gate evidence |
| AC-US019-37 | Autonomous R7D return prompt | Pending Gate evidence |
| AC-US019-38 | Sections 2.3, 21, and 26 | Covered |

## 25. Limitations, Maturity, and Non-Claims

### 25.1 Current maturity

This document defines a logical and semantic interface only. Consequently:

- Video Factory Core remains `PARTIAL` or at the lower maturity established by
  the applicable architecture baseline;
- no production workflow has been executed;
- no capture, render, review, release, withdrawal, or retention capability has
  been operationally demonstrated;
- no real POC has been declared ready for video production;
- no toolchain, performance, staffing, cost, or scalability property is proven;
- conceptual application to candidate POCs is not implementation evidence.

### 25.2 Prohibited claims

This document SHALL NOT be cited as proof of:

- product readiness or production readiness;
- certification, conformity, regulatory approval, or safety integrity;
- a validated or operational Video Factory;
- a verified or validated POC;
- complete Evidence, traceability, security, privacy, or rights clearance;
- automatic publication or reuse authorization;
- universal applicability of a Pattern, workflow, tool, or video format.

## 26. Document Status and Next Controlled Step

At installation, this document is a US019 candidate. Repository presence,
staging, commit, merge, or publication alone does not prove semantic acceptance.

US019 may be declared `DONE` only after all 38 frozen Acceptance Criteria and
the complete Definition of Done have evidence-based `PASS` results, including:

- semantic and human review;
- documentary, structural, encoding, confidentiality, and overclaim controls;
- minimal staging and cached-scope verification;
- functional commit, no-fast-forward merge, remote synchronization, and
  independent final Git verification;
- controlled feature-branch cleanup;
- separate final report, handoff, incremented command catalogue, and autonomous
  `PROMPT_MISE_A_JOUR_DISCUSSION_GENERALE_APRES_US019_v1.0.txt`;
- continued visibility of `E-HER-01` through `E-HER-03` until a separately
  governed correction is proven.

US020 remains `NOT STARTED / REQUIRES EXPLICIT GO`. Completion, merge, or
closure of US019 SHALL NOT start it automatically.
