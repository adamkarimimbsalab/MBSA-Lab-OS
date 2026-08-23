# MBSA Lab OS — Traceability Model

## 1. Purpose and Status

This document defines the logical and semantic traceability model applicable to
MBSA Lab OS proofs of concept (POCs). It establishes how engineering elements,
decisions, configurations, results, evidence, claims, changes and reuse
candidates are related, reviewed, baselined and kept navigable.

The model is technology-independent. It is not a database schema, an exchange
format, a tool configuration, an API, an evidence package, or a compliance
claim.

Document state at controlled installation: `CANDIDATE — US015`. Acceptance and
baselining require completion of the US015 verification and Git workflow.

## 2. Scope and Intended Use

### 2.1 In scope

- traceable-element types and their minimum logical envelope;
- canonical relations, inverse relations and allowed endpoints;
- applicability, obligation, cardinality and responsibility rules;
- link creation, review, validity, invalidation and supersession;
- upstream, downstream, V&V, claim–evidence and change-impact coverage;
- missing, broken, obsolete, ambiguous and conflicting links;
- minimum matrices and navigable views;
- baseline, configuration, provenance and historical integrity;
- proportional tailoring at T1, T2 and T3;
- alignment with the MEF and POC Lifecycle;
- conceptual applicability to the three candidate POC classes.

### 2.2 Out of scope

- selecting, designing or implementing a POC;
- populating a complete real POC trace dataset;
- physical graph, database or repository schemas;
- Codebeamer, DOORS, Jira, GitHub or other tool configuration;
- APIs, plugins, pipelines and automation;
- the detailed Evidence Package defined by US016;
- the integrated Gate model defined by US017;
- pattern admission and the full Pattern Lifecycle defined by US018;
- physical or organizational architecture;
- normative compliance claims;
- publication of private information or modification of the private Master Plan.

### 2.3 Intended users

The model supports POC owners, engineering contributors, reviewers, governance
authorities, evidence custodians and publication or reuse decision makers.

## 3. Authoritative Inputs and Precedence

The controlled entry baseline is:

`3f869217a93d3e0853a4b3e4f11de6f8c66fde98`

Precedence is:

1. verified Git state and formally accepted governance decisions;
2. `docs/10_POC_Lifecycle_and_Minimal_POC_Factory.md`;
3. `docs/09_Minimal_Engineering_Framework.md`;
4. `docs/08_MBSA_Lab_OS_Capability_and_Logical_Architecture.md`;
5. `docs/07_MBSA_Lab_OS_System_Context_and_Boundaries.md`;
6. governance and repository conventions in `docs/03` through `docs/06`;
7. the controlled Sprint 2 backlog;
8. the public strategic foundation.

A conflict affecting authority, scope, meaning, confidentiality, maturity or
acceptance requires a controlled stop and explicit disposition. No lower source
silently overrides a higher source.

## 4. Inherited Constraints

- MBSA Lab OS remains the System of Interest.
- `MBSA-Lab-OS` is the public repository; private strategic control remains
  outside it.
- Governance owns decisions and baselines. Engineering owns source work
  products. Evidence & Traceability maintains references and assurance status,
  but does not take ownership of source artefacts.
- Governance, production, evidence, publication and reuse remain distinct.
- Traceability is progressive, proportionate, navigable and mandatory.
- Missing links are visible; they are never inferred as present.
- The POC Lifecycle orchestrates the MEF and does not replace it.
- Evidence precedes claims, publication and reuse decisions.
- A POC acceptance is not product readiness or normative compliance.
- A Pattern Candidate is not an admitted pattern.
- CAP-04, the Evidence & Traceability Core and the Engineering Framework Core
  remain `PARTIAL`; POC Factory Logic and Pattern & Reuse Core remain
  `STRATEGIC ONLY`.

## 5. Terminology and Normative Language

`MUST`, `MUST NOT`, `SHOULD`, `SHOULD NOT` and `MAY` express binding,
recommended and optional model rules respectively.

| Term | Meaning |
|---|---|
| Traceable element | Identified, versioned logical item that may participate in a relation. |
| Trace link | Typed, directed and reviewable relation between two element versions. |
| Canonical direction | Authoritative stored or expressed direction used by this model. |
| Inverse | Navigable semantic view of the same relation; it is not a second independent fact. |
| Link obligation | Expected link instance derived from an applicable rule. |
| Valid link | Active link whose endpoints, semantics, versions, authority and applicability pass validation. |
| Baseline | Authorized, immutable identification of a coherent set of element versions and links. |
| Provenance | Information identifying origin, authorship, derivation and governing baseline. |
| Supersession | Controlled replacement that preserves historical identity and navigation. |
| Waiver | Authorized, bounded and time- or baseline-limited exception to an obligation. |

## 6. Traceability Principles

1. **Identity before relation.** An endpoint MUST have a stable identifier and
   version before a link can be accepted.
2. **One fact, two directions.** A canonical relation and its inverse MUST
   expose one semantic fact, not duplicate records with independent states.
3. **Explicit applicability.** Obligations are evaluated only after their
   applicability is established and justified.
4. **Evidence before claim.** Evidence canonically `supports` a Claim; the Claim
   is navigable through `is_supported_by`.
5. **Separate verification and validation.** Requirements are verified; needs
   are validated. Neither relation substitutes for the other.
6. **Historical integrity.** Invalidated and superseded links remain
   reconstructable and are excluded from current valid coverage.
7. **No silent private crossing.** Public traces MUST NOT expose private content;
   an authorized public surrogate or opaque reference is required.
8. **Proportional rigor.** Tailoring may reduce ceremony, never the essential
   objectives for applicable accepted scope.
9. **Change is graph-aware.** Impact analysis traverses relevant upstream and
   downstream relations, then records disposition for each candidate impact.
10. **Percentages are not assurance.** Coverage metrics complement but do not
    replace semantic review, evidence quality or acceptance decisions.

## 7. Conceptual Metamodel

The model contains five logical concepts:

- `TraceableElement` — a stable, typed and versioned engineering or governance item;
- `TraceLink` — a typed directed relation between two specific element versions;
- `LinkRule` — allowed endpoints, meaning, inverse, applicability and obligation;
- `LinkAssessment` — review, validity, finding, waiver and disposition data;
- `Baseline` — an authorized set of element and link versions.

A relation is valid only when its source and target exist, match the permitted
types, resolve to controlled versions, satisfy the LinkRule, have compatible
classification and have passed the required review.

## 8. Traceable-Element Envelope

Every traceable element MUST expose the following logical fields. A physical
implementation may distribute them across systems provided their meaning and
navigability are preserved.

| Field | Rule |
|---|---|
| `element_id` | Stable, unique and never reassigned. |
| `element_type` | One controlled type from Section 9. |
| `title` | Human-readable, concise and non-empty. |
| `lifecycle_state` | `PROPOSED`, `IN_REVIEW`, `ACCEPTED`, `BASELINED`, `REOPENED` or `REJECTED`. |
| `version` | Identifies the content version addressed by links. |
| `logical_owner` | Role accountable for source content. |
| `classification` | `PUBLIC`, `PRIVATE` or `BOUNDARY_SHARED`. |
| `provenance` | Source, author or derivation, and creation context. |
| `baseline_id` | Governing baseline when baselined; otherwise explicitly unset. |
| `created_at` | Creation timestamp with timezone or equivalent ordered record. |
| `modified_at` | Last controlled modification timestamp. |
| `incoming_links` | Navigable set or resolvable query. |
| `outgoing_links` | Navigable set or resolvable query. |
| `validity_status` | Current semantic and configuration validity. |

Optional fields include rationale, tags, external reference and authorized
public surrogate. Their absence MUST NOT prevent stable identity.

## 9. Traceable-Element Type Catalogue

| Code | Type | Logical content |
|---|---|---|
| `SRC` | Source | Stakeholder input, observation, reference or authorized directive. |
| `PRB` | Problem | Bounded condition or gap to address. |
| `NED` | Need | Stakeholder or operational outcome sought. |
| `REQ` | Requirement | Verifiable constraint or capability statement. |
| `ACC` | Acceptance Criterion | Observable condition for acceptance. |
| `ARC` | Architecture Element | Logical structure, behavior, interface or allocation. |
| `SAF` | Safety Assessment | Hazard-oriented assessment, concern, assumption or analysis. |
| `CTL` | Safety Control | Risk-control requirement, constraint or measure. |
| `IMP` | Implementation Item | Controlled realization or configuration. |
| `VFC` | Verification Case | Method, case or procedure for requirement verification. |
| `VFR` | Verification Result | Recorded outcome and verdict of verification. |
| `VAC` | Validation Case | Method, scenario or procedure for need validation. |
| `VAR` | Validation Result | Recorded outcome and conclusion of validation. |
| `EVI` | Evidence Item | Controlled information used to support an assertion. |
| `CLM` | Claim | Explicit proposition requiring support and review. |
| `LIM` | Limitation | Constraint on interpretation, validity or applicability. |
| `DEC` | Decision | Authorized choice and rationale. |
| `FND` | Finding | Review or assurance observation requiring disposition. |
| `ANO` | Anomaly | Deviation or unexpected behavior requiring control. |
| `CHG` | Change Record | Controlled request and disposition of change. |
| `BLN` | Baseline | Authorized set of element and link versions. |
| `POC` | POC | Controlled POC identity and lifecycle record. |
| `WPR` | Work Product | MEF or POC Lifecycle output. |
| `PAT` | Pattern Candidate | Reuse candidate not yet admitted as a pattern. |
| `RUA` | Reuse Applicability | Context, evidence, limitations and decision for reuse. |
| `DSP` | Disposition | Resolution of an impact, finding, anomaly or candidate. |

## 10. Common Trace-Link Contract

Every accepted TraceLink MUST contain:

- stable `link_id` and controlled `link_type_id`;
- source element identifier and version;
- target element identifier and version;
- canonical meaning and inverse name;
- obligation class: `MANDATORY`, `CONDITIONAL` or `OPTIONAL`;
- applicability result: `APPLICABLE` or `NOT_APPLICABLE`;
- applicability rationale and authority when conditional or not applicable;
- link state and validity status;
- creator, reviewer and maintainer roles;
- creation and review phase or work product;
- provenance and governing baseline;
- creation, review and last-assessment timestamps;
- findings, waiver, expiration and supersession references when applicable.

The source/target versions and rule version MUST be recoverable. Free-text links
without controlled type and endpoints do not satisfy this contract.

## 11. Canonical Relation Vocabulary

Cardinality is expressed from one source to target instances. `1..*` applies to
accepted scope when the rule is applicable. An unrestricted maximum is used
unless a justified domain constraint requires otherwise.

| ID | Canonical relation | Allowed source → target | Inverse | Obligation / cardinality |
|---|---|---|---|---|
| `TRL-01` | `informs` | `SRC → PRB` | `is_informed_by` | Conditional; applicable accepted PRB: `1..*` sources. |
| `TRL-02` | `justifies` | `PRB → NED` | `is_justified_by` | Mandatory; accepted NED: `1..*` problems. |
| `TRL-03` | `is_refined_by` | `NED → REQ` | `refines` | Mandatory; accepted NED: `1..*` requirements unless explicitly validation-only. |
| `TRL-04` | `has_acceptance_criterion` | `REQ/NED → ACC` | `accepts` | Conditional; `1..*` where explicit criteria apply. |
| `TRL-05` | `is_allocated_to` | `REQ → ARC` | `realizes_requirement` | Mandatory for allocated accepted requirements; `1..*`. |
| `TRL-06` | `is_assessed_by` | `REQ/ARC → SAF` | `assesses` | Conditional on safety applicability; `1..*`. |
| `TRL-07` | `results_in_control` | `SAF → CTL` | `controls_assessed_concern` | Conditional when control is required; `1..*`. |
| `TRL-08` | `is_realized_by` | `ARC → IMP` | `realizes_architecture` | Mandatory for implemented accepted architecture; `1..*`. |
| `TRL-09` | `is_implemented_by` | `CTL → IMP` | `implements_control` | Mandatory for implemented applicable controls; `1..*`. |
| `TRL-10` | `is_verified_by` | `REQ → VFC` | `verifies` | Mandatory for accepted verifiable requirements; `1..*`. |
| `TRL-11` | `produces_verification_result` | `VFC → VFR` | `results_from_verification` | Mandatory for executed verification cases; `1..*` over executions. |
| `TRL-12` | `is_validated_by` | `NED → VAC` | `validates` | Mandatory for accepted needs; `1..*`. |
| `TRL-13` | `produces_validation_result` | `VAC → VAR` | `results_from_validation` | Mandatory for executed validation cases; `1..*` over executions. |
| `TRL-14` | `is_evidenced_by` | `VFR/VAR/DEC/FND/DSP → EVI` | `evidences` | Mandatory for accepted conclusions or dispositions; `1..*`. |
| `TRL-15` | `supports` | `EVI → CLM` | `is_supported_by` | Mandatory for accepted claims; `1..*` evidence items per claim. |
| `TRL-16` | `is_limited_by` | `EVI/CLM/RUA/PAT → LIM` | `limits` | Conditional; mandatory when a known limitation exists. |
| `TRL-17` | `governs` | `DEC → TraceableElement` | `is_governed_by` | Mandatory for decisions with effect; `1..*` governed elements. |
| `TRL-18` | `contains_version` | `BLN → TraceableElement/TraceLink` | `is_contained_in` | Mandatory for baseline members; `1..*`. |
| `TRL-19` | `requests_change_to` | `CHG → TraceableElement` | `is_change_target_of` | Mandatory for each change; `1..*`. |
| `TRL-20` | `potentially_impacts` | `CHG → TraceableElement` | `is_potentially_impacted_by` | Mandatory for candidate impact set; `1..*`. |
| `TRL-21` | `is_disposed_by` | `CHG/ANO/FND → DSP` | `disposes` | Mandatory before closure; `1..*`. |
| `TRL-22` | `affects` | `ANO/FND → TraceableElement` | `is_affected_by` | Mandatory for actionable anomaly/finding; `1..*`. |
| `TRL-23` | `supersedes` | `TraceableElement → same type` | `is_superseded_by` | Conditional; `0..*`, acyclic for a version lineage. |
| `TRL-24` | `produces_candidate` | `POC → PAT` | `is_candidate_from` | Conditional on extraction; `0..*`; never implies admission. |
| `TRL-25` | `supports_applicability` | `EVI → RUA` | `is_supported_by_evidence` | Mandatory for an accepted reuse-applicability decision; `1..*`. |
| `TRL-26` | `assesses_candidate` | `RUA → PAT` | `has_applicability_assessment` | Mandatory for evaluated candidates; `1..*` across contexts. |
| `TRL-27` | `produces` | `POC/MEF stage/PLC phase → WPR` | `is_produced_by` | Mandatory for required work products; `1..*`. |
| `TRL-28` | `traces_to` | `WPR → TraceableElement` | `is_represented_in` | Conditional bridge; MUST use a more specific link when one applies. |

`TRL-28` is not a semantic escape hatch. It is permitted only for work-product
packaging or legacy references where no more precise relation is defined, and
its rationale MUST be recorded.

## 12. Source–Problem–Need–Requirement Semantics

The chain `SRC informs PRB`, `PRB justifies NED`, and `NED is_refined_by REQ`
MUST be navigable in both directions. A source is not itself a need, and a need
is not rewritten as a requirement. Many-to-many refinement is permitted when
scope and rationale remain explicit. Orphan accepted needs and requirements are
invalid unless an authorized, bounded waiver exists.

## 13. Architecture–Safety–Implementation Semantics

Allocation relates requirements to architecture. Realization relates
architecture to implementation. Safety assessment is distinct from the control
it may produce; a control is separately traced to its implementation. Safety
applicability MUST be recorded even when the outcome is `NOT_APPLICABLE`.

No link in this section asserts safety compliance. It records engineering
reasoning, allocation and controlled realization only.

## 14. Verification–Validation–Result–Evidence Semantics

Verification determines whether a requirement is satisfied by its realization.
Validation determines whether the solution and its behavior satisfy the need in
the intended context. Each executed case produces a versioned result. A result
links to one or more evidence items; an evidence item may support several
claims when its scope and limitations are compatible.

A `PASS` result without accessible evidence, configuration, procedure and
provenance does not satisfy an accepted trace obligation.

## 15. Claim–Evidence–Limitation Semantics

The canonical direction is `EVI supports CLM`; `CLM is_supported_by EVI` is its
inverse navigation. Support MUST state scope and strength without overstating
what the evidence demonstrates. Known limitations link to evidence, claims,
reuse assessments or candidates and remain visible in publication decisions.

A claim with no valid supporting evidence is `UNSUPPORTED`. Conflicting
evidence creates a finding and prevents silent acceptance until disposition.

## 16. Decision and Baseline Relations

A Decision links to every element it governs. A Baseline contains explicit
element and link versions; membership is immutable for that baseline. A later
baseline may supersede versions while preserving navigation to prior content.

Baseline identifiers, approval authority, timestamp and scope MUST be recorded.
Branch names, working-tree state or mutable file paths alone are not baselines.

## 17. Change–Impact–Disposition Relations

Every Change Record MUST identify its trigger and target elements. Impact
analysis traverses relevant incoming and outgoing links to establish a candidate
set covering needs, requirements, architecture, safety, implementation, V&V,
evidence, claims, decisions, publications and reuse candidates.

Each candidate impact is classified as:

- `POTENTIAL` — discovered but not yet assessed;
- `CONFIRMED` — requires change, re-verification or renewed decision;
- `NOT_APPLICABLE` — excluded with rationale and authority.

Closure requires a Disposition for confirmed impacts and applicable anomalies
or findings. Reopening follows MEF and POC Lifecycle rules. Obsolete links are
invalidated, not erased.

## 18. POC–Pattern Candidate–Applicability Relations

A POC MAY `produce_candidate` after the applicable POC Lifecycle phase. This
creates a Pattern Candidate only. Reuse Applicability assesses that candidate
for a stated context and MUST be supported by evidence and constrained by known
limitations. Admission to a pattern library is outside US015.

## 19. Link States, Validity and Supersession

| Link state | Meaning | Included in valid coverage |
|---|---|---|
| `PROPOSED` | Created but not reviewed. | No |
| `IN_REVIEW` | Under semantic and configuration review. | No |
| `ACTIVE` | Reviewed and valid for the addressed versions. | Yes |
| `INVALID` | Endpoint, type, meaning, classification or evidence rule fails. | No |
| `OBSOLETE` | No longer current but retained historically. | No |
| `SUPERSEDED` | Replaced by an identified successor link. | No |
| `WAIVED` | Obligation excepted by bounded authorization; the absent link is not counted as valid. | No |

A link becomes invalid when an endpoint is unavailable, the endpoint version
changes without confirmed applicability, the type rule is violated, review
expires, classification is incompatible, or supporting context is withdrawn.
Invalidation MUST record reason, assessor and time. Supersession MUST identify
the successor and preserve the prior link.

## 20. Creation, Review and Maintenance Responsibilities

| Activity | Accountable role | Required participation |
|---|---|---|
| Create source-to-engineering links | Source work-product owner | Downstream owner consulted. |
| Create allocation/realization links | Engineering owner | Architecture and implementation owners. |
| Create safety links | Safety-assessment owner | Requirement, architecture and control owners. |
| Create V&V links | V&V owner | Requirement or need owner. |
| Register evidence and claim support | Evidence custodian | Claim owner and independent reviewer as tailored. |
| Review link semantics | Owning-domain reviewer | Evidence & Traceability Core maintains status. |
| Approve waivers and baselines | Governance authority | Affected owners and evidence custodian. |
| Maintain links after change | Change owner coordinates | All confirmed impacted owners. |

Creation occurs with the source or target work product as soon as both stable
identities exist. Review occurs no later than the checkpoint that accepts the
downstream work product. Maintenance continues until closure and through any
reopening or supersession.

## 21. Coverage Rules and Formulas

An `applicable obligation` is one expected link instance after population,
scope, tailoring and applicability have been resolved. A `valid present link`
is an `ACTIVE` link satisfying Section 10.

For any coverage view:

`Coverage (%) = 100 × valid present mandatory obligations / applicable mandatory obligations`

The result is bounded to `[0%, 100%]`. Report numerator, denominator, unit,
scope, baseline and exclusions. If the denominator is zero, report
`NOT_APPLICABLE` rather than `100%` or `0%`.

Required measures are:

| Measure | Population / obligation |
|---|---|
| Upstream coverage | Accepted elements requiring at least one valid upstream justification link. |
| Downstream coverage | Accepted elements requiring at least one valid downstream realization or assessment link. |
| Requirement-verification coverage | Applicable accepted requirements with valid `TRL-10` links. |
| Need-validation coverage | Accepted needs with valid `TRL-12` links. |
| Claim-evidence coverage | Accepted claims with at least one valid inverse of `TRL-15`. |
| Change-impact coverage | Candidate impacts with an assessed classification and confirmed impacts with disposition. |

Additionally report counts of missing, broken, invalid, obsolete, ambiguous,
conflicting, waived and not-applicable obligations. `NOT_APPLICABLE` requires
rationale and authorized assessor. Acceptance requires zero missing mandatory
links in the accepted perimeter unless each exception has a valid, bounded and
traceable waiver. A high percentage never overrides an invalid critical link.

## 22. Required Views and Matrices

| View | Inputs | Owner | Required output | Limitation |
|---|---|---|---|---|
| Problem–Need–Requirement | `SRC/PRB/NED/REQ`, `TRL-01..03` | Engineering owner | Justification and refinement gaps. | Does not prove requirement quality. |
| Requirement–Architecture–Safety | `REQ/ARC/SAF/CTL`, `TRL-05..07` | Architecture owner | Allocation and safety-analysis coverage. | Does not assert compliance. |
| Requirement–Verification–Result | `REQ/VFC/VFR/EVI`, `TRL-10/11/14` | V&V owner | Planned/executed verification and evidence status. | PASS still requires evidence review. |
| Need–Validation–Result | `NED/VAC/VAR/EVI`, `TRL-12..14` | Validation owner | Need-validation coverage and conclusions. | Distinct from verification. |
| Claim–Evidence–Limitation | `CLM/EVI/LIM`, `TRL-15/16` | Evidence custodian | Supported, unsupported and limited claims. | Support strength remains reviewed judgment. |
| Change–Impact–Disposition | `CHG/ANO/FND/DSP`, `TRL-19..22` | Change owner | Potential, confirmed and disposed impacts. | Traversal identifies candidates, not certainty. |
| POC–Candidate–Applicability | `POC/PAT/RUA/EVI/LIM`, `TRL-24..26` | Reuse owner | Candidate context, support and limitations. | Does not admit a pattern. |
| Coverage and Invalid Links | Obligations, link assessments | Evidence & Traceability Core | Formulas, counts and gap lists. | Percentages do not replace review. |
| Baseline and Modified Elements | `BLN`, versions, `TRL-18/23` | Governance | Membership, supersession and deltas. | Only valid for identified baselines. |

Every view MUST state its baseline, scope, filters, generation time and excluded
classes. A matrix is a projection of the model, not the model itself.

## 23. Baseline, Configuration and Provenance

Links address element versions, not only stable element identifiers. A baseline
records the exact versions of elements, links and governing rules. Comparing
baselines identifies added, modified, superseded and removed-from-current-scope
items without destroying history.

Evidence provenance MUST identify acquisition or generation context,
configuration, responsible role and integrity reference sufficient for later
assessment. A public artefact referencing private evidence MUST use an approved
surrogate that exposes no private content and makes the access limitation clear.

## 24. Tailoring T1/T2/T3

| Level | Permitted proportionality | Minimum retained control |
|---|---|---|
| `T1 — Lightweight` | Combined registers and manual matrices. | Stable IDs, essential chain, V&V distinction, evidence–claim support, change impact and visible gaps. |
| `T2 — Standard` | Separate work products, formal reviews and complete required views. | All applicable mandatory relations, coverage measures and baseline control. |
| `T3 — Enhanced` | Additional independence, review depth, attributes and checks. | T2 controls plus risk-justified assurance rigor. |

Tailoring MUST record level, rationale, authority, scope and review trigger. It
MUST NOT remove identity, PUBLIC/PRIVATE control, mandatory applicable links,
evidence-before-claim, V&V distinction, change impact, historical integrity or
acceptance visibility.

## 25. Alignment with the Minimal Engineering Framework

| MEF work product | Primary trace contribution | Checkpoint expectation |
|---|---|---|
| `WP-MEF-01` Problem | `SRC→PRB` | Problem provenance accepted. |
| `WP-MEF-02` Need | `PRB→NED` | Need justified. |
| `WP-MEF-03` Requirement | `NED→REQ`, criteria | Requirements have upstream rationale. |
| `WP-MEF-04` Architecture | `REQ→ARC` | Allocation reviewed. |
| `WP-MEF-05` Safety Assessment | `REQ/ARC→SAF→CTL` | Applicability and controls reviewed. |
| `WP-MEF-06` Implementation | `ARC/CTL→IMP` | Realization and configuration identified. |
| `WP-MEF-07` V&V | `REQ→VFC→VFR`, `NED→VAC→VAR` | Verification and validation independently visible. |
| `WP-MEF-08` Evidence | `Result/Decision→EVI→CLM` | Evidence validity and limitations assessed. |
| `WP-MEF-09` Reuse | `EVI→RUA→PAT` | Applicability bounded; no automatic admission. |

The corresponding `CP-MEF-01` through `CP-MEF-09` validate the applicable
relations before accepting each work product. A failed link check prevents
silent progression and may reopen an upstream stage.

## 26. Alignment with the POC Lifecycle

| POC Lifecycle phase | Traceability focus |
|---|---|
| `PLC-01 Proposal` | POC identity, source and initial problem. |
| `PLC-02 Qualification` | Problem, need, constraints and candidate applicability. |
| `PLC-03 Selection` | Decision, rationale and affected proposal. |
| `PLC-04 Framing` | Scope, acceptance criteria, tailoring and baseline. |
| `PLC-05 Design` | Requirements, architecture, safety and allocations. |
| `PLC-06 Safety Assessment` | Concerns, assessments, controls and applicability. |
| `PLC-07 Implementation` | Realization and configuration links. |
| `PLC-08 Verification and Validation` | Separate requirement verification and need validation chains. |
| `PLC-09 Evidence and Acceptance` | Results, evidence, claims, limitations and decision. |
| `PLC-10 Publication Readiness` | Classification, approved public surrogate and publication decision. |
| `PLC-11 Lessons Learned` | Findings, dispositions and affected elements. |
| `PLC-12 Pattern-Candidate Extraction` | POC-to-candidate and reuse-applicability links. |
| `PLC-13 Closure` | Final baseline, open limitations and historical integrity. |

`CP-POC-01` through `CP-POC-13` review the trace status applicable to their
phase. The POC Lifecycle remains the orchestration authority; US015 supplies
the trace semantics.

## 27. Interfaces to US016–US018

- **US016 — Evidence Package:** consumes element and link identities, validity,
  provenance and Claim–Evidence semantics; it defines detailed packaging.
- **US017 — Integrated Gates:** consumes checkpoint obligations, metrics and
  findings; it defines the integrated Gate catalogue and final numbering.
- **US018 — Pattern Lifecycle:** consumes Pattern Candidates, reuse assessments,
  evidence and limitations; it owns admission and lifecycle decisions.

US015 does not pre-implement these deliverables. `IF-US012-03` carries
engineering work-product references; `IF-US012-04` carries evidence and trace
link information without transferring source ownership.

## 28. Multi-POC Conceptual Assessment

| Candidate | Example trace path | Applicability observation |
|---|---|---|
| Emergency Stop Button | Hazardous motion problem → immediate-stop need → stop requirement → safety control → implementation → verification result → evidence → claim. | Supports discrete safety control, reaction-time verification and explicit limitations. |
| Door Interlock Safety System | Access hazard → prevention need → interlock requirement → architecture/safety allocation → implementation → verification and validation → evidence. | Supports state-dependent control and multiple architecture elements. |
| Overtemperature Protection System | Thermal hazard source → protection need → threshold requirement → sensing/control architecture → implementation → test result → evidence → claim. | Supports quantitative thresholds, configurations and environment limitations. |

All three candidates can use the same element envelope, relation contract,
coverage rules and change-impact semantics. This is a conceptual genericity
check only; it selects, designs and implements no POC.

## 29. Governance and Maturity Limitations

Governance approves baselines, waivers and acceptance. Engineering owns source
content. Evidence & Traceability Core maintains reference integrity, link
status, coverage and findings. Publication and reuse authorities consume those
results but retain their distinct decisions.

This document completes a logical definition, not operational demonstration.
No populated POC graph, automated checker, tool readiness, product readiness or
normative compliance has been demonstrated. Current inherited maturity labels
therefore remain unchanged.

## 30. Assumptions, Risks and Deferred Points

### 30.1 Assumptions

- Every accepted work product can expose a stable identifier and version.
- Logical owners and review authorities are designated by the applicable POC.
- Baseline and classification decisions are available to trace review.

### 30.2 Risks and mitigations

| Risk | Consequence | Mitigation |
|---|---|---|
| Generic links hide semantics | False coverage | Prefer `TRL-01..27`; constrain `TRL-28`. |
| Duplicate inverse records diverge | Conflicting status | Treat inverse as navigation over one fact. |
| Metrics incentivize link quantity | Weak assurance | Validate semantics and evidence; expose invalid counts. |
| Version drift breaks links | Stale conclusions | Address versions and re-assess after change. |
| Private content crosses boundary | Confidentiality breach | Classification check and approved public surrogate. |
| Tailoring removes essential control | Unsupported acceptance | Preserve non-tailorable objectives and authorization. |
| Candidate treated as admitted pattern | Premature reuse | Keep admission exclusively in US018. |

### 30.3 Deliberately deferred

Physical storage, serialization, automation, evidence-package structure,
integrated Gate numbering and Pattern Lifecycle admission are deferred to their
authorized future scopes.

## 31. Acceptance Criteria Compliance Matrix

| AC | Coverage | Candidate verdict |
|---|---|---|
| `AC-US015-01` | Sections 3–4 | PASS subject to Git verification |
| `AC-US015-02` | Sections 3–4, 20, 27 | PASS subject to Git verification |
| `AC-US015-03` | Sections 4, 25 | PASS |
| `AC-US015-04` | Sections 4, 26 | PASS |
| `AC-US015-05` | Sections 1–2 | PASS |
| `AC-US015-06` | Section 9 | PASS |
| `AC-US015-07` | Section 8 | PASS |
| `AC-US015-08` | `TRL-01/02`, Section 12 | PASS |
| `AC-US015-09` | `TRL-03`, Section 12 | PASS |
| `AC-US015-10` | `TRL-05`, Section 13 | PASS |
| `AC-US015-11` | `TRL-06/07`, Section 13 | PASS |
| `AC-US015-12` | `TRL-08/09`, Section 13 | PASS |
| `AC-US015-13` | `TRL-10..13`, Section 14 | PASS |
| `AC-US015-14` | `TRL-14`, Section 14 | PASS |
| `AC-US015-15` | `TRL-15`, Section 15 | PASS |
| `AC-US015-16` | `TRL-24`, Section 18 | PASS |
| `AC-US015-17` | Sections 10–11 | PASS |
| `AC-US015-18` | Sections 6, 11 | PASS |
| `AC-US015-19` | Sections 10–11 | PASS |
| `AC-US015-20` | Sections 10–11 | PASS |
| `AC-US015-21` | Section 20 | PASS |
| `AC-US015-22` | Section 19 | PASS |
| `AC-US015-23` | Section 21 | PASS |
| `AC-US015-24` | Sections 19, 21–22 | PASS |
| `AC-US015-25` | Section 22 | PASS |
| `AC-US015-26` | Section 17 | PASS |
| `AC-US015-27` | Sections 16, 19, 23 | PASS |
| `AC-US015-28` | Section 24 | PASS |
| `AC-US015-29` | Section 27 | PASS |
| `AC-US015-30` | Sections 1–2, 7 | PASS |
| `AC-US015-31` | Sections 4, 6, 23 | PASS |
| `AC-US015-32` | Section 28 | PASS |
| `AC-US015-33` | Sections 29–30 | PASS |
| `AC-US015-34` | Sections 3, 32 | PENDING GIT VERIFICATION |

## 32. Verification Strategy and Document Governance

### 32.1 Content verification

- confirm every controlled element and relation identifier is unique;
- confirm every canonical relation has allowed endpoints, inverse, obligation
  and cardinality semantics;
- verify the 34 AC mappings and absence of scope leakage;
- inspect V&V separation, evidence direction, PUBLIC/PRIVATE control and
  multi-POC genericity;
- confirm formulas specify numerator, denominator, unit, exclusions and the
  zero-denominator case.

### 32.2 Repository verification

- install only `docs/11_Traceability_Model.md` on the authorized feature branch;
- require UTF-8 without BOM or NUL, LF endings and no trailing whitespace;
- run `git diff --check` and `git diff --cached --check` at their authorized Gates;
- verify staged and committed scope is limited to this file;
- capture real blob, functional, merge and remote SHAs rather than predicting them.

### 32.3 Change control

Changes to identifiers, canonical direction, endpoint rules, non-tailorable
objectives or authority boundaries require impact analysis across US011–US018.
Editorial changes still follow repository governance and preserve stable IDs.

### 32.4 Acceptance rule

This candidate becomes the US015 accepted baseline only after all AC and DoD
checks pass, the controlled Git workflow completes, the functional commit is
merged with `--no-ff`, synchronization is proven and closure evidence is issued.

## 33. Conclusion

The model defines a stable, navigable and technology-independent semantic
contract from source and problem through need, requirement, architecture,
safety, implementation, V&V, evidence, claim, change and reuse candidacy. It
keeps missing or invalid links visible, preserves provenance and history, and
supports proportional POC governance without claiming operational maturity.
