# MBSA Lab OS — Evidence Package Model

## 1. Purpose and Document Status

This document defines the logical and documentary model for an MBSA Lab OS
Evidence Package. It specifies the minimum controlled information required to
assemble, review, accept, publish under authorization, retain and retrieve the
evidence position of a proof of concept (POC).

The model binds evidence to an identified POC scope, configuration, baseline,
set of claims, actual results and explicit limitations. It preserves negative,
contradictory and inconclusive results and keeps missing or invalid information
visible.

The model is technology-independent. It is not a physical archive, database,
graph, serialization format, tool configuration, API, pipeline, certification
package or normative-compliance claim.

Document state at controlled installation: `CANDIDATE — US016`. Acceptance and
baselining require completion of the US016 review and Git workflow.

## 2. Scope and Exclusions

### 2.1 In scope

- the logical contract, identity, scope and lifecycle of an Evidence Package;
- the minimum content index and inclusion rules;
- the minimum metadata of an Evidence Item;
- Claim, Evidence, Result, Finding and Limitation semantics;
- need-validation and requirement-verification evidence chains;
- applicable architecture, decision and Safety Assessment references;
- POC realization, configuration, environment and baseline identity;
- evidence provenance, derivation, validity and integrity information;
- reproducibility information and declared reproducibility limits;
- negative, contradictory, blocked, not-executed and inconclusive results;
- anomalies, findings, changes, waivers and dispositions;
- completeness, missing-item detection and acceptance conditions;
- `PUBLIC`, `PRIVATE` and `BOUNDARY_SHARED` classification;
- controlled public surrogates for non-public source evidence;
- tailoring at `T1`, `T2` and `T3` without loss of essential objectives;
- retention, supersession, logical archiving and controlled reopening;
- minimum views and matrices;
- conceptual applicability to three candidate POC classes.

### 2.2 Out of scope

- selection, design, implementation or testing of a real POC;
- creation of a complete Evidence Package instance;
- creation of fictitious evidence or results;
- physical storage, archive, database or graph schemas;
- tool-specific configuration for Codebeamer, DOORS, Jira, GitHub or others;
- APIs, plugins, pipelines, automation or proprietary exchange formats;
- the integrated Gate catalogue, decisions and numbering reserved for US017;
- pattern admission and Pattern Lifecycle decisions reserved for US018;
- redefinition of the US015 Traceability Model;
- product readiness, certification, safety-integrity or compliance claims;
- publication of private information;
- modification of the private Master Plan;
- authorization or start of US017.

### 2.3 Intended users

The model supports POC owners, engineering contributors, configuration owners,
V&V contributors, safety contributors, evidence custodians, independent
reviewers as tailored, governance authorities, publication authorities and
future reuse reviewers.

## 3. Sources of Authority

The controlled public entry baseline is:

`5dcbadb99c4587f96f7c0f45c8437aeeaefacfe5`

Precedence is:

1. verified Git state and formally accepted governance decisions;
2. `docs/11_Traceability_Model.md` for identity, trace semantics, provenance,
   validity, baselines and Claim–Evidence relations;
3. `docs/10_POC_Lifecycle_and_Minimal_POC_Factory.md` for the POC Lifecycle,
   work products, decisions and acceptance;
4. `docs/09_Minimal_Engineering_Framework.md` for the MEF, V&V, Evidence and
   Reuse contracts;
5. `docs/08_MBSA_Lab_OS_Capability_and_Logical_Architecture.md` for CAP-04,
   `LC-US012-04` and `IF-US012-04`;
6. `docs/07_MBSA_Lab_OS_System_Context_and_Boundaries.md` for the System of
   Interest and trust boundaries;
7. governance and repository conventions in `docs/03` through `docs/06`;
8. the controlled Sprint 2 backlog;
9. the public strategic foundation for general context.

A conflict affecting authority, baseline, scope, semantics, classification,
maturity or acceptance requires a controlled stop and explicit disposition. A
lower-authority source MUST NOT silently override a higher-authority source.

The private Master Plan may inform sequencing but MUST NOT be copied into the
public repository.

## 4. Inherited Architecture and Governance

US016 preserves the following contracts:

- MBSA Lab OS remains the System of Interest.
- `MBSA-Lab-OS` remains public; private Strategic Control remains outside it.
- Governance owns decisions, waivers, acceptance and baselines.
- Engineering owns the source engineering work products.
- Evidence & Traceability maintains evidence references, trace links,
  assessments, gaps and assurance status without taking ownership of sources.
- The POC Lifecycle orchestrates the MEF and does not replace it.
- Governance, engineering production, evidence, publication and reuse remain
  distinguishable responsibilities.
- Traceability is progressive, proportionate, navigable and mandatory.
- Missing, invalid, obsolete, superseded or conflicting information remains
  visible and is not inferred as valid.
- Evidence canonically `supports` a Claim; the inverse is `is_supported_by`.
- Requirement verification remains distinct from need validation.
- Stable identity, version, provenance, classification, baseline and validity
  are required for accepted traceable content.
- POC acceptance does not imply product readiness or normative compliance.
- A Pattern Candidate is not an admitted pattern.

The Evidence & Traceability Core and Engineering Framework Core remain
`PARTIAL`. POC Factory Logic and Pattern & Reuse Core remain `STRATEGIC ONLY`.
This document improves definition maturity only.

## 5. Concepts and Terminology

`MUST`, `MUST NOT`, `SHOULD`, `SHOULD NOT` and `MAY` express mandatory,
prohibited, recommended, discouraged and optional model rules.

| Term | Controlled meaning |
|---|---|
| Evidence Package | Identified and baselined logical collection that presents the evidence position for a bounded POC scope and configuration. |
| Evidence Item | Controlled information used to support, challenge or contextualize an assertion, result, decision or disposition. |
| Claim | Explicit proposition whose acceptance requires compatible valid Evidence. |
| Result | Actual recorded outcome of an executed review, analysis, verification or validation activity. |
| Limitation | Constraint on interpretation, validity, applicability, reproducibility, publication or reuse. |
| Finding | Review or assurance observation requiring an explicit disposition. |
| Anomaly | Unexpected behavior or deviation requiring control. |
| Waiver | Authorized, bounded and traceable exception; it does not alter an observed result. |
| Provenance | Origin, authorship, acquisition or generation context and derivation history. |
| Integrity reference | Proportionate means of detecting unintended or unauthorized content change. |
| Reproducibility | Declared degree to which a result can be recreated or reevaluated in a compatible context. |
| Public surrogate | Authorized public representation of restricted source evidence that preserves no prohibited content and states its access limitation. |
| Package baseline | Immutable identification of the package version, content references, trace links and governing decisions accepted together. |

### 5.1 Foundational principles

1. **Identity before inclusion.** A package or item MUST have a stable identity
   and version before acceptance.
2. **Evidence before claim.** A Claim MUST NOT be accepted without applicable,
   valid and reviewable Evidence.
3. **Actual result before conclusion.** Planned or expected results MUST NOT be
   represented as observed results.
4. **Configuration bounds meaning.** Evidence is interpreted only for the POC,
   realization, environment and baseline it addresses.
5. **Limitations travel with claims.** A Claim MUST retain the limitations that
   bound its supporting Evidence.
6. **Negative evidence remains visible.** Failure, contradiction and
   inconclusive outcomes MUST NOT be deleted or hidden.
7. **A view is not a source.** Matrices and summaries project controlled source
   items; they do not replace them.
8. **Public access is not assumed.** Classification and release authority are
   evaluated separately from technical validity.
9. **Completeness is explicit.** Missing mandatory items and unresolved gaps
   are reported, not inferred away.
10. **Definition is not demonstration.** A documentary model does not establish
    operational readiness.

## 6. Evidence Package Logical Contract

Every Evidence Package MUST expose the following logical envelope:

| Field | Rule |
|---|---|
| `package_id` | Stable, unique and never reassigned. |
| `package_title` | Human-readable, concise and non-empty. |
| `package_version` | Identifies the package content version. |
| `package_state` | One controlled state from Section 19. |
| `poc_id` | Stable identity of the addressed POC. |
| `scope_statement` | Included and excluded claims, activities, configurations and periods. |
| `applicability` | Context, assumptions and conditions under which the package may be interpreted. |
| `tailoring_level` | `T1`, `T2` or `T3`, with decision reference. |
| `logical_owner` | Role accountable for package assembly and maintenance. |
| `review_authority` | Role accountable for evidence-position review. |
| `acceptance_authority` | Governance role authorized to accept or reject the package. |
| `classification` | `PUBLIC`, `PRIVATE` or `BOUNDARY_SHARED`. |
| `baseline_id` | Governing immutable package baseline when accepted. |
| `content_index` | Versioned list of expected and included logical items. |
| `open_findings` | Navigable set of unresolved findings and dispositions. |
| `limitations` | Package-level interpretation and applicability limits. |
| `created_at` | Creation timestamp with timezone or equivalent ordered record. |
| `reviewed_at` | Last completed controlled review time, or explicitly unset. |
| `accepted_at` | Acceptance time, or explicitly unset. |
| `supersedes` | Prior package version or baseline replaced, when applicable. |
| `retention_disposition` | Retention, archive and access decision. |

### 6.1 Package membership

Package membership is expressed by controlled references to identified source
items. A physical copy MAY be retained when authorized, but copying a file does
not by itself establish identity, provenance, context, validity or meaning.

The package MUST identify the applicable `TRL-10` through `TRL-18` and `TRL-25`
relations from US015. Other `TRL-01` through `TRL-28` relations remain
navigable when needed to justify scope, decisions, change or reuse.

### 6.2 Inclusion classes

| Class | Meaning |
|---|---|
| `MANDATORY` | Required for the accepted package scope when applicable. |
| `CONDITIONAL` | Required when a stated applicability condition is true. |
| `OPTIONAL` | Useful but not required for minimum acceptance. |

### 6.3 Expected-item status

| Status | Meaning | Counts as valid present content |
|---|---|---|
| `PRESENT` | Identified item is available, applicable and passes required checks. | Yes |
| `MISSING` | Applicable expected item has no recoverable valid reference. | No |
| `NOT_APPLICABLE` | Applicability was assessed as false with rationale and authority. | Excluded from applicable denominator |
| `INVALID` | Item exists but fails identity, provenance, configuration, integrity, classification or semantic checks. | No |
| `SUPERSEDED` | Historical item has an identified successor. | No for current coverage |

`MISSING`, `INVALID` and `SUPERSEDED` remain visible. `NOT_APPLICABLE` requires
an assessor, rationale, decision time and governing baseline.

## 7. Package Identity, Scope and Baseline

The package identity MUST resolve to exactly one POC identity and a bounded
evaluation scope. The scope MUST state:

- POC objective and learning questions;
- addressed Claims and acceptance criteria;
- included and excluded engineering work products;
- applicable POC Lifecycle phases and MEF stages;
- POC realization and configuration identifiers;
- environment, period and external dependencies;
- assumptions, constraints and applicable limitations;
- tailoring level and deviations;
- classification and authorized access boundary;
- applicable source and package baselines.

A package baseline MUST record the exact versions of its index, Evidence Items,
Claims, limitations, trace links, findings, decisions and governing rules.
Mutable branch names, working-tree state or file paths alone are not baselines.

Acceptance applies only to the identified scope and baseline. A later change
MUST trigger impact assessment and may require a new package version, renewed
review or reopening.

## 8. Evidence Item Metadata Model

Every Evidence Item MUST expose the following minimum metadata. A physical
implementation may distribute the fields across systems if their meanings and
navigability remain intact.

| Field | Minimum rule |
|---|---|
| `evidence_id` | Stable, unique and never reassigned. |
| `evidence_type` | Controlled logical type from Section 8.1. |
| `title` | Human-readable and non-empty. |
| `version` | Exact addressed content version. |
| `validity_status` | Current semantic, configuration and review validity. |
| `producer` | Person, role, system or external source that produced the information. |
| `logical_owner` | Role accountable for source content. |
| `custodian` | Role maintaining the evidence reference and status. |
| `reviewer` | Required reviewer or explicitly unset when not yet reviewed. |
| `created_at` | Acquisition or generation time with timezone or equivalent ordering. |
| `reviewed_at` | Review time or explicitly unset. |
| `source_reference` | Recoverable location or authorized surrogate reference. |
| `provenance` | Origin, acquisition/generation method and derivation context. |
| `poc_id` | Addressed POC identity. |
| `configuration_id` | Evaluated realization and configuration. |
| `environment_id` | Applicable execution or review environment. |
| `baseline_id` | Governing baseline. |
| `activity_reference` | Procedure, case, analysis, review or decision producing the item. |
| `observed_result` | Actual observation and verdict where relevant. |
| `claim_links` | Applicable `supports` relations to Claims. |
| `engineering_links` | Related needs, requirements, architecture, controls and decisions. |
| `limitations` | Known bounds on interpretation and use. |
| `classification` | `PUBLIC`, `PRIVATE` or `BOUNDARY_SHARED`. |
| `access_boundary` | Authorized audience or access constraint. |
| `integrity_reference` | Proportionate integrity mechanism and value/reference. |
| `findings` | Contradictions, anomalies or review findings. |
| `supersession` | Prior/successor identity where applicable. |
| `retention` | Retention period, trigger or disposition. |
| `interpretation_conditions` | Conditions required to use the item correctly. |

### 8.1 Evidence types

| Type | Meaning |
|---|---|
| `PRIMARY` | Direct record of an observation, execution, review or decision. |
| `DERIVED` | Information calculated, transformed or summarized from identified sources. |
| `SYNTHETIC` | Controlled aggregate constructed from multiple identified sources. |
| `EXTERNAL_REFERENCE` | Evidence maintained by an external authority or provider. |
| `PUBLIC_SURROGATE` | Authorized bounded public representation of a restricted source. |

A `DERIVED`, `SYNTHETIC` or `PUBLIC_SURROGATE` item MUST identify its source
chain and transformation or omission rules. `SYNTHETIC` means aggregated; it
does not authorize invented observations.

## 9. Claims and Acceptance Criteria

Claim and Evidence are distinct traceable concepts. A Claim MUST contain:

- stable Claim identity and version;
- proposition stated in testable or reviewable terms;
- Claim owner and review authority;
- addressed POC scope, configuration and baseline;
- applicable acceptance criterion or decision objective;
- support-strength expectation;
- linked supporting and challenging Evidence;
- limitations and assumptions;
- status and acceptance disposition.

An accepted Claim MUST be linked through `TRL-15 — supports` to at least one
valid Evidence Item compatible with its scope, configuration, baseline and
limitations. The strength of the Claim MUST NOT exceed what the Evidence
demonstrates.

| Claim support state | Meaning |
|---|---|
| `SUPPORTED` | Applicable valid Evidence supports the bounded proposition. |
| `PARTIALLY_SUPPORTED` | Evidence supports only an explicitly limited portion. |
| `UNSUPPORTED` | No applicable valid supporting Evidence exists. |
| `CHALLENGED` | Applicable Evidence contradicts or materially weakens the Claim. |
| `NOT_ASSESSED` | Required review has not been completed. |

`PARTIALLY_SUPPORTED` requires explicit Claim reduction or an acceptance with
limitations. `CHALLENGED` creates a Finding and prevents silent acceptance.

## 10. Requirements, Needs, V&V and Evidence

The package MUST keep the following chains separately navigable:

- Requirement `is_verified_by` Verification Case (`TRL-10`);
- Verification Case `produces_verification_result` Verification Result
  (`TRL-11`);
- Need `is_validated_by` Validation Case (`TRL-12`);
- Validation Case `produces_validation_result` Validation Result (`TRL-13`);
- Result `is_evidenced_by` Evidence Item (`TRL-14`);
- Evidence Item `supports` Claim (`TRL-15`).

Verification confirms satisfaction of specified requirements. Validation
confirms that the result addresses the intended need in its context of use. A
verification result MUST NOT substitute for a required validation conclusion,
and a validation observation MUST NOT silently satisfy a requirement-verification
obligation.

For each executed case, the package MUST identify the procedure, expected
result, actual result, verdict, configuration, environment, executor, execution
time, anomalies and Evidence Item references.

### 10.1 Result vocabulary

| Verdict | Meaning |
|---|---|
| `PASS` | Observed result satisfies the stated criterion for the addressed configuration. |
| `FAIL` | Observed result does not satisfy the stated criterion. |
| `BLOCKED` | Execution or conclusion could not proceed due to an identified blocker. |
| `NOT_EXECUTED` | Planned activity was not performed. |
| `INCONCLUSIVE` | Available observations do not support a defensible pass/fail conclusion. |

The package MUST preserve all applicable verdicts. Useful learning from a
failed experiment does not convert a failed requirement into `PASS`.

## 11. Architecture, Decisions and Safety Evidence

The package MUST identify the architecture elements, interfaces, allocations,
implementation items and decisions applicable to the evaluated configuration.
It MUST preserve the relevant `TRL-05` through `TRL-09` and `TRL-17` relations
when they affect Claims, V&V, safety controls or limitations.

The Safety Evidence & Control View MUST reference:

- the applicable Safety Assessment and its method;
- identified hazards, concerns or harmful outcomes;
- assumptions and operating boundaries;
- derived controls and their requirement/architecture allocation;
- implementation references for applicable controls;
- verification and validation evidence;
- residual uncertainty and limitations;
- findings, waivers and acceptance authority.

The Evidence Package records a proportionate safety position only. It MUST NOT
claim normative compliance, certification or safety integrity unless a
separately authorized and demonstrated compliance basis exists.

## 12. Results, Findings, Waivers and Limitations

### 12.1 Results

Actual results MUST be retained with their original verdict and context.
Negative, contradictory or inconclusive results MUST NOT be removed because a
different result supports an acceptance decision.

### 12.2 Findings and anomalies

Every material contradiction, evidence gap, invalid item or unexplained
deviation MUST create or reference a Finding or Anomaly. The record MUST state:

- identity, description and discovery source;
- affected items, Claims, criteria, baselines and classifications;
- severity or decision relevance using the approved project method;
- owner, review authority and due trigger;
- disposition and supporting Evidence;
- residual limitation and closure or reopening condition.

### 12.3 Waivers

A waiver MUST identify its authority, rationale, scope, affected obligation,
baseline, expiration or review trigger and compensating controls. A waiver:

- does not create missing Evidence;
- does not make an invalid TraceLink valid;
- does not change a `FAIL` into `PASS`;
- does not erase the associated gap or limitation;
- does not apply outside its stated scope and baseline.

### 12.4 Limitations

A Limitation is mandatory whenever interpretation, validity, applicability,
reproducibility, publication or reuse is bounded. It MUST link through `TRL-16`
to the affected Evidence, Claim, Reuse Applicability or Pattern Candidate.

## 13. Provenance and Derivation

Evidence provenance MUST make the following recoverable:

- original source and source authority;
- producer and responsible owner;
- acquisition or generation method;
- date, environment and configuration;
- source baseline and version;
- transformation, calculation, filtering or aggregation steps;
- intermediate sources for derived or synthetic Evidence;
- access constraints and external dependencies;
- supersession history.

Each derivation step MUST identify its inputs, rule or method, output and
responsible producer. A derived item becomes invalid when a required source is
unavailable, superseded without reassessment or outside the declared
applicability context.

An external reference MUST record the external authority, stable reference,
retrieval or observation date, applicable version and access limitation. A
source unavailable to a reviewer MUST be classified as an access gap unless an
authorized review or surrogate provides sufficient bounded assurance.

## 14. Integrity and Validity

Integrity control is proportional to risk, change frequency, publication and
reuse ambition. The model does not mandate an algorithm or implementation.

An integrity reference SHOULD identify:

- protected logical item and version;
- mechanism type, such as controlled baseline identifier, immutable record or
  cryptographic digest;
- value or recoverable reference;
- calculation or registration time;
- responsible authority;
- verification result and time.

Evidence validity requires all of the following:

1. stable identity and resolvable version;
2. recoverable source or authorized surrogate;
3. sufficient provenance;
4. compatible POC scope, configuration, environment and baseline;
5. applicable trace semantics;
6. required review completed;
7. classification and access rules satisfied;
8. integrity check proportionate to the Claim;
9. limitations and contradictions visible;
10. no unassessed supersession or invalidating change.

Failure of a mandatory validity condition sets the item status to `INVALID`
for current coverage while preserving its historical record.

## 15. Reproducibility

Reproducibility is declared and bounded; it is not a universal guarantee. The
package MUST state the level supported by available information:

| Level | Meaning |
|---|---|
| `R0 — NOT_REPRODUCIBLE` | Required information or dependencies are unavailable. |
| `R1 — REVIEWABLE` | Reasoning and result can be reviewed, but execution cannot be recreated. |
| `R2 — REPEATABLE` | Same controlled configuration and method can reasonably repeat the activity. |
| `R3 — REPRODUCIBLE` | A compatible independent environment can reasonably recreate and evaluate the result. |

These levels are Evidence Package properties and are unrelated to the US016
workflow Gates `R0–R7`.

The Reproducibility Information View MUST identify, as applicable:

- realization and configuration references;
- environment, dependencies and versions;
- inputs, datasets, stimuli and preconditions;
- procedure, sequence and expected observations;
- build, setup and calibration information;
- random seeds, timing or nondeterminism controls when relevant;
- actual outputs and evaluation method;
- unavailable private or external dependencies;
- permitted substitutions and their limitations;
- known variability and expected tolerance;
- responsible owner and support horizon.

## 16. Classification and Publication Boundary

Every package and Evidence Item MUST have one classification:

| Classification | Meaning |
|---|---|
| `PUBLIC` | Authorized for public disclosure within the recorded release scope. |
| `PRIVATE` | Restricted source content that MUST NOT enter the public repository. |
| `BOUNDARY_SHARED` | Controlled information crossing a defined trust boundary under explicit authorization. |

Technical validity does not authorize publication. The Publication Governance
Gateway separately decides what may be released.

When a required source remains private, a public package MAY reference an
authorized `PUBLIC_SURROGATE`. The surrogate MUST:

- have its own stable identity, version, provenance and approval;
- identify the class and purpose of the restricted source without revealing it;
- state which Claim or decision it may support publicly;
- state omissions, review method and access limitation;
- remain linked to the restricted source through an authorized boundary record;
- avoid credentials, personal data, private strategy and restricted supplier
  or partner information.

A surrogate does not automatically provide the same assurance as its source.
The difference MUST be recorded as a limitation.

## 17. Completeness and Missing Items

Completeness is assessed over applicable expected items, not raw file count.

For mandatory items:

`Completeness (%) = 100 × valid PRESENT mandatory items / applicable mandatory items`

The result is bounded to `[0%, 100%]`. Reports MUST state numerator,
denominator, unit, scope, baseline and exclusions. If the denominator is zero,
report `NOT_APPLICABLE`, not `100%` or `0%`.

The package MUST report counts and identities for:

- `PRESENT` mandatory, conditional and optional items;
- `MISSING` items;
- `INVALID` items;
- `SUPERSEDED` current-scope references;
- `NOT_APPLICABLE` items and their rationales;
- unsupported or challenged Claims;
- open Findings and Anomalies;
- expired or soon-to-expire waivers;
- unassessed change impacts;
- inaccessible private or external sources.

Acceptance requires zero unresolved missing mandatory items in the accepted
scope unless every exception has a valid bounded waiver and the resulting
limitation is explicitly accepted. A high completeness percentage MUST NOT
override invalid critical Evidence or a challenged critical Claim.

## 18. Tailoring T1/T2/T3

| Level | Permitted proportionality | Expected evidence-package control |
|---|---|---|
| `T1 — Lightweight` | Combined registers, compact index and peer review for low-complexity, low-consequence scope. | Stable identities, configuration, essential Claim–Evidence chains, V&V distinction, negative results, limitations, provenance, classification and visible gaps. |
| `T2 — Standard` | Separate key views, formal review and complete applicable index. | All applicable mandatory content, coverage measures, baseline, integrity and acceptance records. |
| `T3 — Enhanced` | Additional independence, review depth, integrity controls and reproducibility detail. | T2 controls plus risk-justified assurance, stronger configuration control and broader challenge evidence. |

Tailoring MUST record level, rationale, scope, deviations, combined views,
omitted optional detail, compensating controls, authority and escalation or
review triggers.

Tailoring MUST NOT remove:

- POC and package identity;
- configuration and baseline identity;
- Claim–Evidence semantics;
- separate verification and validation;
- actual and negative results;
- limitations and contradictions;
- provenance and proportional integrity;
- classification and publication boundary;
- acceptance authority;
- visible missing mandatory content.

## 19. Package States and Controlled Reopening

| State | Meaning | Acceptance status |
|---|---|---|
| `DRAFT` | Package definition or content is being prepared. | Not accepted |
| `ASSEMBLED` | Expected content has been indexed for review. | Not accepted |
| `IN_REVIEW` | Assigned reviewers are evaluating validity, completeness and coherence. | Not accepted |
| `INCOMPLETE` | Applicable mandatory gaps prevent acceptance. | Not accepted |
| `ACCEPTED` | Applicable acceptance conditions pass without unresolved limiting condition. | Accepted for stated scope/baseline |
| `ACCEPTED_WITH_LIMITATIONS` | Acceptance authority explicitly accepts bounded limitations or waivers. | Accepted only within stated limits |
| `REJECTED` | Evidence position does not support the proposed acceptance. | Not accepted |
| `RESTRICTED` | Access or publication is limited by classification or rights. | Technical acceptance tracked separately |
| `SUPERSEDED` | A later identified package version replaces current use. | Historical only |
| `ARCHIVED` | Active use ended and retention disposition was applied. | Historical only |

### 19.1 Transition rules

- `DRAFT → ASSEMBLED` requires an indexed scope and expected-item population.
- `ASSEMBLED → IN_REVIEW` requires identified reviewers and a stable candidate
  version.
- `IN_REVIEW → ACCEPTED` requires valid, complete and coherent mandatory
  content and authorized disposition.
- `IN_REVIEW → ACCEPTED_WITH_LIMITATIONS` requires explicit limitations,
  authority and review triggers.
- `IN_REVIEW → INCOMPLETE` or `REJECTED` records blocking gaps or an unsupported
  evidence position.
- An accepted package becomes `SUPERSEDED` only after its successor is
  identified and historical navigation is preserved.
- `ARCHIVED` requires a retention, ownership and access disposition.

### 19.2 Reopening triggers

An accepted or archived position MUST be considered for reopening when:

- a Claim, criterion, requirement, need or POC objective changes;
- configuration, environment or baseline applicability changes;
- new Evidence contradicts an accepted Claim;
- an Evidence Item becomes invalid or unavailable;
- a Finding, Anomaly or change invalidates a conclusion;
- a waiver expires or its conditions fail;
- classification or publication authorization changes;
- a new reuse context exceeds recorded applicability.

Governance records whether the package is reopened, superseded or retained with
an added limitation. The decision MUST identify trigger, affected scope,
baseline, impact assessment, authority and required renewed review.

## 20. Retention, Supersession and Archiving

Retention decisions MUST identify:

- retained package and Evidence Item identities and versions;
- retention purpose, period or event-based trigger;
- logical owner and custodian;
- authorized access and classification;
- external dependency and availability risks;
- integrity-verification expectations;
- supersession lineage;
- disposal or archive authority;
- reopening and retrieval conditions.

Supersession does not delete the historical evidence position. A successor MUST
identify what it replaces and why, while the prior package remains recoverable
subject to authorization and retention constraints.

Logical archiving changes active-use state; it does not imply a specific
storage technology. Destructive disposal is governed separately and MUST NOT
occur while a package supports an active baseline, open Finding, published
Claim, unresolved change or reuse decision.

## 21. Minimal Views and Matrices

Every view MUST state its objective, inputs, owner, filters, outputs,
limitations, baseline and completeness status. A view is a projection and does
not replace its source items.

| View | Minimum inputs | Owner | Required output | Primary limitation |
|---|---|---|---|---|
| Package Identity & Scope View | Package, POC, charter, tailoring, baseline | Package owner | Identity, boundary, configuration and applicability | Does not assess evidence sufficiency |
| Claim–Evidence–Limitation Matrix | `CLM/EVI/LIM`, `TRL-15/16` | Evidence custodian | Supported, partial, unsupported and challenged Claims | Support strength remains reviewed judgment |
| Requirement/Need–V&V–Evidence Coverage View | `REQ/NED/VFC/VAC/VFR/VAR/EVI`, `TRL-10..15` | V&V and evidence owners | Separate verification and validation chains and gaps | Coverage does not prove method quality |
| Configuration & Baseline View | POC, realization, environment, `BLN`, `TRL-18` | Configuration owner | Applicable versions and baseline membership | Valid only for identified baseline |
| Safety Evidence & Control View | `SAF/CTL/IMP/V&V/EVI/LIM` | Safety owner | Concerns, controls, results and residual limitations | Does not assert compliance |
| Anomaly/Finding–Disposition View | `ANO/FND/DSP/CHG`, `TRL-19..22` | Change or finding owner | Open/closed items, impacts and disposition | Closure quality requires review |
| Negative/Contradictory Results Register | Results, Evidence, Findings, Claims | Evidence custodian | Preserved non-positive results and affected Claims | Presence does not determine disposition alone |
| Provenance & Integrity View | Evidence metadata, sources, derivations, integrity references | Evidence custodian | Source chain, validity and integrity status | External access may be constrained |
| Acceptance & Authority Record | Claims, criteria, findings, limitations, decisions | Governance | Disposition, authority, scope and conditions | Acceptance is baseline-bounded |
| Publication/Access Boundary View | Classification, rights, source/surrogate pairs, release decision | Publication authority | Authorized public subset and restrictions | Technical validity does not authorize release |
| Completeness and Missing Items View | Expected index, inclusion classes, item status | Package owner | Formula, counts and actionable gaps | Percentages do not replace semantic review |
| Reproducibility Information View | Configuration, environment, inputs, method, outputs, dependencies | Engineering and V&V owners | Declared reproducibility level and missing information | External or private dependencies may prevent replay |

## 22. Multi-POC Conceptual Applicability

This section tests model genericity only. It does not select, design, implement
or test a POC and does not create actual Evidence.

### 22.1 Emergency Stop Button

| Dimension | Conceptual Evidence Package application |
|---|---|
| Claims | Bounded response behavior and observable safe-state behavior for an identified configuration |
| Evidence emphasis | Requirement verification, response-time observations, state-transition results, safety-control implementation and limitations |
| Configuration | Input device, decision logic, actuation surrogate, timing source and test environment |
| Negative results | Missed activation, delayed response, unintended activation and indeterminate state |
| Reproducibility | Controlled stimulus, timing method, initial state and response evaluation |
| Boundary | No product-safety or normative-compliance claim |

### 22.2 Door Interlock Safety System

| Dimension | Conceptual Evidence Package application |
|---|---|
| Claims | Bounded prohibited-transition and permitted-operation behavior for identified door and operating states |
| Evidence emphasis | State matrix, requirements, architecture allocation, scenario-based V&V, anomaly dispositions and validation context |
| Configuration | Door-state source, operating-state source, interlock logic, actuation surrogate and scenario set |
| Negative results | Incorrect transition, stale state, bypass, sensor disagreement and indeterminate input |
| Reproducibility | Initial states, event sequences, timing, fault injection assumptions and expected state transitions |
| Boundary | No physical-vehicle integration or homologation claim |

### 22.3 Overtemperature Protection System

| Dimension | Conceptual Evidence Package application |
|---|---|
| Claims | Bounded threshold detection and protective-response behavior under controlled stimuli |
| Evidence emphasis | Calibration/configuration, quantitative threshold cases, persistence, hysteresis, recovery and fault behavior |
| Configuration | Sensor model, stimulus source, thresholds, filter, timing, protection output and environment |
| Negative results | Missed threshold, delayed action, nuisance activation, sensor bias and failed recovery |
| Reproducibility | Stimulus profile, calibration, sampling, initial thermal state, tolerance and output evaluation |
| Boundary | Simulated or otherwise controlled scope; no product thermal-safety claim |

### 22.4 Genericity conclusion

The three candidates use the same package identity, Evidence Item envelope,
Claim–Evidence–Limitation contract, configuration control, result vocabulary,
provenance rules, completeness assessment and acceptance semantics. Evidence
types, configurations, hazards, cases and reproducibility details vary by POC.
This demonstrates conceptual genericity only.

## 23. Roles, Ownership and Acceptance Authority

| Activity | Accountable logical role | Required participation |
|---|---|---|
| Define package scope and acceptance intent | Governance Core | POC owner, engineering and evidence contributors |
| Produce engineering source items | Engineering source owner | Applicable domain reviewers |
| Produce V&V results | V&V owner | Engineering, configuration, safety and validation stakeholders |
| Register Evidence metadata and trace links | Evidence custodian | Source owner and Claim owner |
| Maintain configuration and baseline references | Configuration owner | Engineering and evidence custodians |
| Review Evidence validity and sufficiency | Evidence review authority | Claim owner and independent reviewer as tailored |
| Accept or reject Claims/package | Governance acceptance authority | Evidence, engineering, V&V and safety participants |
| Authorize public release | Publication Governance Gateway | Governance, evidence and content owners |
| Maintain retention and supersession | Package custodian | Governance and source owners |
| Reopen or supersede an accepted package | Governance Core | All confirmed impacted owners |

One person MAY perform several roles for a small POC, but logical ownership,
review and decision records remain distinguishable. Combining participants does
not collapse engineering truth, evidence assessment and governance acceptance.

## 24. Risks, Limitations and Maturity

### 24.1 Assumptions

- accepted work products can expose stable identifiers and versions;
- POC realization, configuration and environment can be identified;
- Claims and acceptance criteria are defined before final evidence review;
- source owners and decision authorities are designated;
- restricted sources can be handled outside the public repository;
- tooling may implement this model without changing its semantics.

### 24.2 Risks and mitigations

| Risk | Consequence | Mitigation |
|---|---|---|
| File collection mistaken for Evidence | Unsupported Claim acceptance | Require identity, provenance, context, validity and Claim relation |
| PASS result detached from configuration | False applicability | Require POC, realization, environment and baseline metadata |
| Claim exceeds Evidence | Maturity or safety inflation | Record support strength, limitations and review authority |
| Negative result is hidden | Biased acceptance | Mandatory negative/contradictory register and Findings |
| Derived Evidence loses its source chain | Unreviewable conclusion | Require derivation inputs, method and supersession assessment |
| Private source leaks publicly | Confidentiality breach | Classification, public surrogate and publication authority |
| Completeness percentage replaces judgment | False assurance | Report gaps and validity; prohibit metric-only acceptance |
| Waiver treated as proof | Invalid acceptance | Preserve gap, limitation and bounded waiver semantics |
| Tailoring removes essential evidence | Unsupported lightweight package | Preserve non-tailorable objectives in Section 18 |
| Reproducibility overstated | Unrepeatable or misleading result | Declare bounded level, dependencies and unavailable information |
| Package state confused with US017 Gate | Downstream semantic conflict | Keep state vocabulary package-specific and defer integrated Gates |
| Candidate package implies operational maturity | Misleading architecture status | Preserve explicit maturity statement |

### 24.3 Current maturity and limitations

| Element | Position after US016 definition | Evidence still required |
|---|---|---|
| Evidence Package logical model | Defined, pending repository acceptance | Instantiation on a real POC |
| Evidence Item metadata contract | Defined logically | Tool-independent operational use |
| Evidence & Traceability Core | `PARTIAL` | Populated package, review metrics and repeated execution |
| Engineering Framework Core | `PARTIAL` | Real MEF execution and accepted V&V results |
| POC Factory Logic | `STRATEGIC ONLY` | Selected and executed POC lifecycle |
| Pattern & Reuse Core | `STRATEGIC ONLY` | US018 governance and admitted patterns |

No populated Evidence Package, automated checker, tool readiness, product
readiness, safety integrity, certification or normative compliance is
demonstrated by this document.

## 25. Interfaces with US017 and US018

### 25.1 US017 — Integrated Gates

US017 consumes:

- package identity, state, baseline and completeness;
- applicable mandatory obligations and missing-item status;
- Claim support and V&V coverage;
- Findings, Anomalies, waivers and limitations;
- acceptance authority and disposition;
- reproducibility and publication readiness information.

US017 owns the integrated Gate catalogue, final Gate identifiers, entry/exit
criteria, decision sequencing and Gate authorities. US016 does not define or
number those Gates.

### 25.2 US018 — Pattern Lifecycle

US018 consumes:

- Pattern Candidates and Reuse Applicability records;
- supporting Evidence through `TRL-25`;
- source configuration and context;
- limitations, negative results and applicability boundaries;
- provenance, validity, supersession and retention information.

US018 owns admission, rejection, lifecycle states and governance of reusable
patterns. An accepted Evidence Package does not admit a pattern or authorize
reuse in a different context.

## 26. Acceptance Criteria Compliance Matrix

| AC | Coverage | Candidate verdict |
|---|---|---|
| `AC-US016-01` | Sections 3–4 | PASS subject to Git verification |
| `AC-US016-02` | Sections 3–4, 23, 25 | PASS subject to Git verification |
| `AC-US016-03` | Sections 4–5, 10, 18 | PASS |
| `AC-US016-04` | Sections 4, 7, 19, 23 | PASS |
| `AC-US016-05` | Sections 4, 6, 9–14 | PASS |
| `AC-US016-06` | Sections 1–2 | PASS |
| `AC-US016-07` | Sections 6–7 | PASS |
| `AC-US016-08` | Sections 6–8 | PASS |
| `AC-US016-09` | Sections 5 and 9 | PASS |
| `AC-US016-10` | Section 9 | PASS |
| `AC-US016-11` | Sections 6 and 8 | PASS |
| `AC-US016-12` | Sections 9–10 | PASS |
| `AC-US016-13` | Section 11 | PASS |
| `AC-US016-14` | Section 11 | PASS |
| `AC-US016-15` | Sections 7–8 and 10–11 | PASS |
| `AC-US016-16` | Sections 5 and 10 | PASS |
| `AC-US016-17` | Sections 10 and 12 | PASS |
| `AC-US016-18` | Section 12 | PASS |
| `AC-US016-19` | Sections 9 and 12 | PASS |
| `AC-US016-20` | Sections 8 and 13 | PASS |
| `AC-US016-21` | Sections 8 and 14 | PASS |
| `AC-US016-22` | Sections 13–14 | PASS |
| `AC-US016-23` | Section 15 | PASS |
| `AC-US016-24` | Section 16 | PASS |
| `AC-US016-25` | Sections 8 and 16 | PASS |
| `AC-US016-26` | Sections 6 and 17 | PASS |
| `AC-US016-27` | Section 6 | PASS |
| `AC-US016-28` | Section 18 | PASS |
| `AC-US016-29` | Section 21 | PASS |
| `AC-US016-30` | Sections 9, 12 and 19 | PASS |
| `AC-US016-31` | Sections 19–20 | PASS |
| `AC-US016-32` | Sections 2 and 25 | PASS |
| `AC-US016-33` | Sections 1–2, 8, 14–15 and 20 | PASS |
| `AC-US016-34` | Sections 3, 22, 24 and 27 | PENDING GIT VERIFICATION |

The matrix records content coverage. No criterion is finally accepted solely
because it references a section. Final verdicts require semantic review,
document controls and real Git evidence.

## 27. Definition of Done and Closure Conditions

### 27.1 Content verification

Review MUST confirm:

- all 27 approved sections are present and coherent;
- all 34 Acceptance Criteria have credible evidence locations;
- package identity, membership, inclusion and item-status rules are complete;
- every Evidence Item field has an unambiguous minimum rule;
- Claim and Evidence remain distinct and `EVI supports CLM` is preserved;
- Requirement verification and need validation remain separate;
- actual, negative, contradictory and inconclusive results remain visible;
- Findings, Anomalies, changes, waivers and limitations have dispositions;
- provenance, derivation, integrity and validity are reviewable;
- reproducibility is bounded and not confused with workflow Gates;
- classification and public-surrogate rules prevent private disclosure;
- completeness exposes missing and invalid mandatory items;
- tailoring preserves every non-tailorable objective;
- package acceptance, supersession, retention and reopening are controlled;
- all twelve minimum views are defined;
- the three conceptual POC applications remain non-implementing;
- US017 and US018 boundaries remain intact;
- maturity and limitations remain explicit.

### 27.2 Document verification

Repository controls MUST confirm:

- Markdown is readable and structurally coherent;
- identifiers and controlled vocabulary are consistent;
- repository-relative references are valid;
- no private source, credential, personal datum or restricted content exists;
- encoding is UTF-8 without BOM or NUL characters;
- line endings are LF;
- no trailing whitespace exists;
- `git diff --check` and `git diff --cached --check` pass;
- staged and committed scope is limited to
  `docs/12_Evidence_Package_Model.md`.

### 27.3 Git and closure verification

US016 may be declared `DONE` only after the controlled workflow:

1. verifies the approved entry baseline and clean repository;
2. creates only the authorized feature branch;
3. installs and reviews only `docs/12_Evidence_Package_Model.md`;
4. stages the sole deliverable after successful review;
5. captures the real functional commit and feature tracking;
6. revalidates `main` and the live remote before merge;
7. merges with `--no-ff` and captures the real merge SHA;
8. proves local, tracking and live-remote synchronization;
9. proves functional-commit reachability before feature cleanup;
10. verifies final clean state and absence of feature residue;
11. issues the controlled US016 report and handoff;
12. keeps US017 `NOT STARTED` until a separate explicit GO.

### 27.4 Acceptance rule

This candidate becomes the accepted US016 baseline only when all 34 Acceptance
Criteria and the complete Definition of Done are demonstrated. Any unresolved
mandatory criterion prevents closure and MUST be classified as `DEBUG`, `FAIL`
or an explicitly accepted non-blocking reservation that does not contradict an
Acceptance Criterion.

### 27.5 Conclusion

The Evidence Package Model defines a stable, technology-independent contract
for presenting the evidence position of a bounded POC. It connects Claims to
actual, configuration-aware and provenance-controlled Evidence; preserves
failures, contradictions and limitations; makes completeness and access
boundaries explicit; and supports proportionate review, publication and future
reuse decisions without claiming operational maturity.
