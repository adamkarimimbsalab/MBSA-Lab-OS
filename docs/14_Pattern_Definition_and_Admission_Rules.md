# MBSA Lab OS — Pattern Definition and Admission Rules

## 1. Purpose and document status

This document defines the controlled contract, admission rules and lifecycle of
an MBSA Lab Pattern. It establishes how a Pattern Candidate may be evaluated,
challenged, admitted with or without limitations, rejected, changed,
superseded, retired and archived.

This document is a normative model for future work. It does not admit a real
pattern, validate a candidate, select a POC, authorize reuse in a target
context, or demonstrate that the Pattern & Reuse Core is operational.

Status: proposed public Sprint 2 baseline deliverable for US018.

## 2. Scope

### 2.1 In scope

- definition of Pattern, Pattern Candidate, Pattern Version and Pattern Family;
- minimum content contract for a Pattern;
- admission obligations, reviews, authorities, decisions and records;
- Pattern lifecycle states and permitted transitions;
- evidence, traceability, classification and publication obligations;
- deprecation, supersession, retirement, retention and reopening;
- target-context reuse applicability assessment;
- tailoring levels `T1`, `T2` and `T3` without removal of essential objectives;
- controlled views and matrices supported by the companion template.

### 2.2 Out of scope

- admission or validation of a real Pattern Candidate;
- selection, design, implementation or test of a POC;
- creation of a populated operational Pattern Library;
- implementation of a database, API, plugin, workflow or pipeline;
- publication of private or restricted evidence;
- automatic authorization of reuse;
- claims of product readiness, certification, conformity, safety integrity or
  universal applicability;
- redefinition of the MEF, POC Lifecycle, Traceability Model, Evidence Package
  Model or Integrated Quality Gates Model;
- Video Factory work owned by US019 and later Sprint 2 work.

## 3. Sources of authority and precedence

The following precedence applies when interpreting this document:

1. actual Git evidence and the applicable controlled baseline;
2. `docs/13_Integrated_Quality_Gates_Model.md` for Gate semantics, authorities,
   decisions, DEBUG and closure;
3. `docs/12_Evidence_Package_Model.md` for Evidence Packages, Claims, Findings,
   limitations and evidence validity;
4. `docs/11_Traceability_Model.md` for identities, provenance, relations,
   baselines, change and impact;
5. `docs/10_POC_Lifecycle_and_Minimal_POC_Factory.md` for Pattern Candidate
   handoff, lessons and POC closure;
6. `docs/09_Minimal_Engineering_Framework.md` for `MEF-09 Reuse` and applicable
   work products;
7. `docs/08_MBSA_Lab_OS_Capability_and_Logical_Architecture.md` for Pattern
   Library responsibilities and logical interfaces;
8. `docs/07_MBSA_Lab_OS_System_Context_and_Boundaries.md` for the System of
   Interest and public/private boundaries;
9. `docs/03` through `docs/06` for governance, Git and documentation rules.

A lower-precedence artefact shall not silently override a higher-precedence
decision. A material contradiction requires a Finding and an explicit
disposition.

## 4. Inherited invariants

- MBSA Lab OS is the System of Interest.
- MBSA-Lab-OS remains public; MBSA-Lab-Control and its Master Plan remain
  private.
- Governance owns scope, tailoring, acceptance, waivers and baselines.
- Engineering owns engineering source artefacts.
- Evidence & Traceability references and evaluates sources without receiving
  their ownership.
- The POC Lifecycle orchestrates `MEF-01` through `MEF-09`; it does not replace
  them.
- `PLC-12` may submit a Pattern Candidate; submission is not admission.
- Evidence supports a Claim; a Claim shall not exceed its supporting Evidence.
- Requirement Verification and Need Validation remain distinct.
- Negative, invalid, contradictory, missing and inconclusive results remain
  visible.
- A waiver creates neither evidence nor a PASS.
- Technical PASS, acceptance, publication, Pattern admission and target reuse
  are separate decisions.
- Git proves transaction and filiation, not semantic quality.
- Pattern & Reuse Core remains `STRATEGIC ONLY` until operational evidence
  supports a later maturity decision.

## 5. Normative language

`SHALL` and `MUST` identify mandatory obligations. `SHOULD` identifies a
recommended practice requiring rationale when omitted. `MAY` identifies an
allowed option. `CONDITIONAL` identifies an obligation activated by recorded
applicability criteria.

The words admitted, accepted, published, reusable and validated shall not be
used as synonyms.

## 6. Core concepts

| Concept | Controlled meaning |
|---|---|
| Pattern | A governed, versioned and evidence-bounded reusable solution structure for a recurring problem in an explicit context. |
| Pattern Candidate | A proposal submitted for evaluation; it is neither admitted nor authorized for reuse. |
| Pattern Version | An immutable identified configuration of Pattern content and its admission record. |
| Pattern Family | A controlled grouping of related Patterns; family membership does not transfer admission. |
| Example | An illustrative instance that may explain a Pattern but does not prove it. |
| Rule | A normative constraint applicable within a stated scope. |
| Template | A controlled structure used to capture required information; completion is not evidence of admission. |
| Artefact | An identified information item with owner, configuration and provenance. |
| Lesson Learned | A bounded observation from work performed; it may motivate a candidate but is not a Pattern. |
| Admission Record | The immutable decision record linking criteria, Evidence, Findings, authority, limitations and resulting state. |
| Review Record | Evidence of a review activity; it is not the admission decision unless the reviewer also holds recorded authority. |
| Reuse Applicability | A target-specific evaluation of whether and how an admitted Pattern may be applied. |
| Source POC | A configured POC that generated relevant results or lessons. |
| Evidence Package | The controlled aggregation defined by US016; completeness does not imply positive results. |
| Claim | A bounded proposition supported by identified Evidence. |
| Finding | A recorded issue, gap, contradiction, invalidity or observation requiring disposition. |
| Limitation | A boundary restricting interpretation, admission or reuse. |
| Alternative | A credible solution option assessed against explicit criteria. |
| Consequence | A positive, negative or conditional effect of applying the solution structure. |
| Constraint | A mandatory restriction on solution or applicability. |
| Supersession | A governed relation identifying a replacement without erasing historical records. |

## 7. Identification and configuration

Recommended identifiers are:

- `PAT-<domain>-<sequence>` for a Pattern identity;
- `PATVER-<pattern-id>-<version>` for an immutable Pattern Version;
- `PATFAM-<domain>-<sequence>` for a Pattern Family;
- `PADM-<pattern-version>-<sequence>` for an Admission Record;
- `PREV-<pattern-version>-<sequence>` for a Review Record;
- `PRA-<pattern-version>-<target>-<sequence>` for a Reuse Applicability record.

Every identifier shall be unique in its authority domain. A Pattern Version
shall identify its source revision, configuration baseline, owner, status,
classification and supersession relations. Changing normative content requires
a new Pattern Version and impact analysis.

## 8. Minimum Pattern contract

Every candidate submitted for admission shall expose, as applicable:

1. stable identifier, name, version, owner and status;
2. Pattern Family and related Pattern relations;
3. classification, publication authority, provenance and rights;
4. context and recurring problem;
5. forces, tensions and decision drivers;
6. generic solution and essential structure;
7. invariants that tailoring shall not alter;
8. allowed variation and tailoring guidance;
9. positive, negative and conditional consequences;
10. trade-offs and risks;
11. assumptions, preconditions and constraints;
12. limitations and counter-indications;
13. alternatives considered and selection rationale;
14. source POC identities, configurations and baselines;
15. Claims and supporting Evidence Packages;
16. negative results, contradictions, Findings and dispositions;
17. known applicability and non-applicability domains;
18. verification and validation obligations for target reuse;
19. lifecycle history and admission records;
20. change, reopening, deprecation, supersession, retirement and retention
    rules.

A blank or fully populated template is not proof. A generic solution with no
bounded context, source, limitations or decision record is not admissible.

## 9. Distinctions that shall remain explicit

| Objects or decisions | Required distinction |
|---|---|
| Candidate vs Pattern | A candidate awaits admission; a Pattern has an applicable admission decision. |
| Pattern vs Example | The Pattern is generic and governed; an Example is illustrative and contextual. |
| Pattern vs Rule | A Pattern proposes a reusable solution structure; a Rule constrains behaviour. |
| Pattern vs Template | A Template captures information; it is not the reusable solution. |
| Claim vs Evidence | A Claim is a proposition; Evidence is the supporting information. |
| Review vs Decision | A review informs authority; authority records the decision. |
| Admission vs publication | Admission evaluates the Pattern; publication controls release boundary. |
| Admission vs reuse | Admission is source-bounded; reuse is evaluated for each target context. |
| Pattern state vs Gate state | Pattern lifecycle and Gate lifecycle use separate vocabularies. |
| DEBUG vs decision | DEBUG investigates an anomaly; it cannot decide admission. |

## 10. Pattern lifecycle

### 10.1 States

| State | Meaning |
|---|---|
| `DRAFT` | Content is being prepared and has not been submitted. |
| `CANDIDATE` | Minimum submission package exists; no admission review is complete. |
| `IN_REVIEW` | Applicable admission controls are active. |
| `ADMITTED` | Authority accepted the identified Pattern Version within its recorded envelope. |
| `ADMITTED_WITH_LIMITATIONS` | Authority accepted the version subject to explicit, enforceable limitations. |
| `REJECTED` | Authority determined that admission criteria were not met. |
| `DEPRECATED` | New use is discouraged while controlled existing references remain. |
| `SUPERSEDED` | A recorded successor replaces this version for stated uses. |
| `RETIRED` | The version is no longer available for new reuse decisions. |
| `ARCHIVED` | The retained record is read-only except for archival metadata and links. |

`VALIDATED` is not a default Pattern state. If a future governance decision
introduces it, the decision shall define independent evidence across distinct
contexts, authority, applicability envelope and exclusions. It shall not imply
universal applicability.

### 10.2 Permitted transitions

| From | To | Minimum trigger and decision |
|---|---|---|
| `DRAFT` | `CANDIDATE` | Submission owner declares the minimum package ready. |
| `CANDIDATE` | `IN_REVIEW` | Scope, reviewers, authority and criteria are authorized. |
| `IN_REVIEW` | `ADMITTED` | All mandatory criteria pass and no unresolved blocking Finding remains. |
| `IN_REVIEW` | `ADMITTED_WITH_LIMITATIONS` | Criteria support bounded admission and limitations are explicit and enforceable. |
| `IN_REVIEW` | `REJECTED` | Mandatory criteria fail or evidence is insufficient for admission. |
| `REJECTED` | `CANDIDATE` | Reopening trigger and new or corrected evidence are accepted for re-review. |
| `ADMITTED*` | `IN_REVIEW` | Material change, contradiction, invalidated evidence or changed boundary triggers reopening. |
| `ADMITTED*` | `DEPRECATED` | Risk, obsolescence or preferred successor discourages new use. |
| `ADMITTED*` or `DEPRECATED` | `SUPERSEDED` | Successor identity and migration scope are approved. |
| `ADMITTED*`, `DEPRECATED` or `SUPERSEDED` | `RETIRED` | Authority ends new-use eligibility and disposes active references. |
| Any terminal operational state | `ARCHIVED` | Retention, index and access controls pass `GATE-CLS-02`. |

`ADMITTED*` means `ADMITTED` or `ADMITTED_WITH_LIMITATIONS` only in this table.
Every transition shall have criteria, Evidence, reviewer, decision authority,
decision, limitations, actions, timestamp, baseline and reopening triggers.

## 11. Admission process

The controlled sequence is:

1. propose a Draft;
2. qualify the submission as a Candidate;
3. authorize scope, tailoring, reviewers and decision authority;
4. evaluate identity, provenance, Evidence, Claims and Findings;
5. challenge genericity, alternatives, consequences and applicability;
6. determine publication boundary independently;
7. decide `ADMIT`, `ADMIT_WITH_LIMITATIONS`, `REJECT`, `REWORK` or `DEFER`;
8. record the resulting Pattern state and immutable Admission Record;
9. baseline the admitted configuration if authorized;
10. retain limitations, negative results and reopening triggers.

No step may be inferred from repository presence, template completion, a POC
PASS, publication, reviewer consensus or Git merge alone.

## 12. Admission obligations

### 12.1 Classification

| Class | Meaning |
|---|---|
| `MANDATORY` | Always required for the admission decision. |
| `CONDITIONAL` | Required when its applicability condition is true. |
| `OPTIONAL` | Useful but not required; omission does not weaken mandatory evidence. |

### 12.2 Mandatory obligations

| ID | Obligation | Minimum evidence |
|---|---|---|
| `PAO-01` | Stable candidate identity and version | Candidate record and immutable revision |
| `PAO-02` | Owner, reviewers and authority | Responsibility and authority record |
| `PAO-03` | Recurring problem and bounded context | Problem/context statement with sources |
| `PAO-04` | Generic solution separated from implementation detail | Solution structure and variation points |
| `PAO-05` | Forces, alternatives and rationale | Alternatives and trade-off analysis |
| `PAO-06` | Consequences and counter-indications | Positive/negative consequence record |
| `PAO-07` | Source POC and configuration | Navigable source, revision and baseline links |
| `PAO-08` | Evidence Package and Claims | Identified Evidence Package and Claim matrix |
| `PAO-09` | Negative results and Findings | Visible register and dispositions |
| `PAO-10` | Applicability and non-applicability | Bounded domain matrix |
| `PAO-11` | Tailoring invariants | Non-tailorable objectives and allowed variation |
| `PAO-12` | Classification, rights and publication position | Boundary and rights decision |
| `PAO-13` | Change and lifecycle controls | Reopening, supersession, retirement and retention rules |
| `PAO-14` | Admission decision record | Criteria, authority, decision and limitations |

### 12.3 Conditional obligations

- safety-related content activates applicable Safety Assessment and independent
  review obligations;
- external or third-party material activates rights and redistribution review;
- restricted sources activate a controlled public-surrogate decision;
- admission across multiple contexts activates cross-context comparison;
- an open waiver activates compensating controls and expiry/review dates;
- a successor activates migration, compatibility and supersession analysis.

Optional examples, diagrams or tooling references shall not substitute for an
applicable mandatory or conditional obligation.

## 13. Integrated Gate mapping

US018 reuses the existing Gate catalogue and does not create a competing Gate
family.

| Admission concern | Applicable Gates | Expected decision focus |
|---|---|---|
| Scope and authorization | `GATE-GOV-01` | Candidate, boundaries, reviewers and authority |
| Contract and tailoring | `GATE-GOV-02` | Obligations, AC, tailoring and conditions |
| Reuse readiness | `GATE-ENG-09` | Source-bounded reuse information and applicability |
| Traceability coverage | `GATE-EVI-01` | Required links, gaps and navigability |
| Evidence validity | `GATE-EVI-02` | Provenance, configuration, integrity and validity |
| Claims and acceptance | `GATE-EVI-03` | Claim strength, criteria, results and limitations |
| Findings and waivers | `GATE-EVI-04` | Disposition, compensating controls and open risks |
| Publication boundary | `GATE-PUB-01` | `PUBLIC`, `PRIVATE`, `BOUNDARY_SHARED` and surrogate |
| Reuse handoff | `GATE-PUB-02` | Applicability, limitations and target obligations |
| Action closure | `GATE-CLS-01` | Open actions and final decision completeness |
| Retention/supersession | `GATE-CLS-02` | Archive, successor and retained navigation |
| Repository evidence | applicable `GATE-REP-*` | Transaction, filiation and configured paths only |

A Gate PASS supports only the object, scope, configuration and baseline stated
by its Gate Instance. Gate PASS does not automatically produce Pattern
admission.

## 14. Roles and decision authority

| Role | Responsibility | Prohibited inference |
|---|---|---|
| Candidate owner | Prepare and maintain candidate content | Ownership is not admission authority |
| Source POC owner | Identify source configuration and results | POC success is not admission |
| Engineering reviewer | Review problem, solution, constraints and alternatives | Review is not the final decision |
| Evidence reviewer | Review Evidence Packages, Claims, Findings and limitations | Evidence completeness is not admission |
| Safety reviewer | Review activated safety obligations | Safety review is not publication approval |
| Publication authority | Decide release boundary and surrogate | Publication is not admission or reuse |
| Pattern admission authority | Decide admission and resulting Pattern state | Admission is not target reuse authorization |
| Target reuse authority | Decide applicability in a named target context | A target decision does not change source admission |
| Governance | Authorize scope, tailoring, waivers and baselines | Governance shall not invent evidence |

Independence requirements shall be proportional to tailoring level, risk,
novelty, reversibility, safety significance and breadth of Claims.

## 15. Admission decisions

Permitted decisions are:

- `ADMIT`;
- `ADMIT_WITH_LIMITATIONS`;
- `REJECT`;
- `REWORK`;
- `DEFER`.

An Admission Record shall contain candidate and version identifiers, decision
scope, configuration, applicable criteria, Evidence references, Findings,
waivers, reviewer positions, authority, decision, rationale, limitations,
actions, resulting state, effective date and reopening triggers.

`ADMIT_WITH_LIMITATIONS` requires every limitation to be explicit, testable or
inspectable, allocated to an owner and preserved in publication and reuse
handoffs. A limitation cannot conceal a failed mandatory criterion.

`REJECT` preserves the candidate, evidence and rationale. Rejection does not
delete negative results. Re-review requires an explicit trigger and new or
corrected information.

## 16. Evidence and Claim rules

- Each Claim shall identify its scope, subject, configuration and supporting
  Evidence.
- Evidence validity, completeness and strength shall be assessed separately.
- A complete Evidence Package may include FAIL, INVALID, INCONCLUSIVE,
  NOT_EXECUTED or missing results.
- Claim strength shall not exceed Evidence strength.
- Conflicting evidence shall be visible and dispositioned.
- Evidence from one configuration or environment shall not be generalized
  without an applicability argument.
- Evidence and source ownership remain with their authoritative producers.
- Checksums and Git identities support integrity; they do not prove truth or
  engineering adequacy.

## 17. Findings, waivers and limitations

Findings shall identify severity, affected object, baseline, evidence,
disposition owner, due condition and impact on admission. Blocking Findings
prevent `ADMIT`. A non-blocking Finding shall still be visible and justified.

A waiver shall identify scope, rationale, authority, compensating controls,
expiry or review trigger and residual risk. A waiver does not create evidence,
change FAIL to PASS or authorize reuse beyond its scope.

Limitations shall propagate to the Pattern Version, Admission Record,
publication artefact and every Reuse Applicability record.

## 18. Reuse applicability

Admission and reuse applicability are independent decisions. For each target
context, a Reuse Applicability Assessment shall compare:

- target context, problem and forces;
- compatible and incompatible assumptions;
- constraints, architecture, interfaces and configurations;
- transferable and non-transferable Evidence;
- requirements, Safety Assessment, Verification and Validation to renew;
- limitations, counter-indications and residual risks;
- changes and tailoring needed;
- target decision authority and baseline.

Permitted target decisions are:

| Decision | Meaning |
|---|---|
| `APPLY` | Applicable within the recorded target envelope without structural adaptation. |
| `APPLY_WITH_ADAPTATION` | Applicable only with identified changes and renewed assurance activities. |
| `DO_NOT_APPLY` | Material incompatibility or unacceptable risk prevents application. |
| `DEFER` | Information is insufficient or a prerequisite is unresolved. |

No decision transfers product certification, safety integrity, compliance or
readiness from source to target.

## 19. Change, impact and reopening

Material changes include modification of context, problem, essential solution,
invariants, evidence, Claims, limitations, rights, classification, source
baseline or applicability envelope. A material change requires:

1. a new Pattern Version or explicit correction record;
2. impact analysis over admission and active reuse assessments;
3. affected-link navigation using the Traceability Model;
4. reopening of applicable Gates and Findings;
5. a new or amended authority decision;
6. communication to known consumers.

Reopening triggers include invalidated evidence, newly discovered negative
results, changed constraints, safety impact, expired waiver, rights change,
contradiction, successor availability and reuse outside the recorded envelope.

## 20. Deprecation, supersession, retirement and retention

- `DEPRECATED` discourages new use and identifies migration guidance.
- `SUPERSEDED` identifies the successor and exact replacement scope; history is
  preserved.
- `RETIRED` prevents new reuse decisions and disposes known active references.
- `ARCHIVED` retains identity, provenance, decisions, limitations, successors
  and access rules.
- Retention shall preserve negative results, rejected versions and Findings
  required to understand decisions.

Deletion shall not be used to simulate supersession or erase adverse evidence.

## 21. Classification, publication and rights

Every Pattern component and Evidence reference shall be classified:

- `PUBLIC` — authorized for MBSA-Lab-OS publication;
- `PRIVATE` — retained outside the public repository;
- `BOUNDARY_SHARED` — exchanged only through a controlled interface.

When private evidence is necessary to support a public Pattern, Governance and
publication authority shall decide whether a public surrogate is adequate.
The surrogate shall preserve the claim boundary and disclose limitations
without exposing restricted content.

Admission does not grant publication rights. Publication does not prove
admission or target applicability.

## 22. Tailoring and proportionality

| Level | Typical use | Required control |
|---|---|---|
| `T1` | Low-risk, reversible and narrow candidate | Lightweight records with all essential objectives preserved |
| `T2` | Structured candidate or broader reuse intent | Formal reviews, matrices and configuration control |
| `T3` | Safety-significant, high-impact or hard-to-reverse use | Increased independence, evidence depth and change control |

Tailoring may reduce ceremony or combine records. It shall not remove stable
identity, context/problem, solution, alternatives, limitations, Evidence,
negative results, authority, admission decision, target applicability,
publication boundary, change control or retention.

## 23. Required views

The companion template provides these controlled projections:

1. Pattern Register;
2. Candidate Admission Checklist;
3. Claim–Evidence–Limitation Matrix;
4. Source POC and Baseline View;
5. Alternatives and Trade-offs View;
6. Applicability/Non-Applicability Matrix;
7. Negative Results and Findings Register;
8. Admission Decision Record;
9. Version/Supersession/Retention View;
10. Publication and Rights View;
11. Reuse Applicability Assessment.

A view is a projection and shall retain navigable references to authoritative
sources.

## 24. Companion template rules

`templates/MBSA_Lab_Pattern_Template.md` implements the information structure
defined here. Template headings may be combined under approved tailoring, but
mandatory information and its provenance shall remain accessible. Placeholder
text shall be removed or explicitly marked `NOT_APPLICABLE` with rationale
before review.

Template completion cannot change a Pattern state. Only an authorized and
recorded admission decision can do so.

## 25. Conceptual application to the three candidate POCs

### 25.1 Emergency Stop Button

The model could capture a candidate concerning stop-request handling or
state-management. Admission would require configured source evidence,
failure-response limits, alternatives and explicit non-applicability. No such
candidate is admitted here.

### 25.2 Door Interlock Safety System

The model could capture a candidate concerning interlock state or diagnostic
structure. Differences in sensors, actuation, timing, hazards and operating
context would require target-specific assessment. No such candidate is
admitted here.

### 25.3 Overtemperature Protection System

The model could capture a monitoring or protective-action candidate. Threshold
semantics, thermal dynamics, detection coverage and safe-state assumptions
would bound admission and reuse. No such candidate is admitted here.

### 25.4 Genericity conclusion

The same contract can evaluate all three conceptual candidates without
selecting them, asserting common evidence or claiming they are reusable. This
demonstrates model genericity only.

## 26. Risks and controls

| Risk | Consequence | Control |
|---|---|---|
| Candidate mistaken for admitted Pattern | Unsupported reuse | Explicit lifecycle and admission record |
| Admission mistaken for universal validation | Overclaim | Bounded context and prohibition of default `VALIDATED` |
| Positive-result bias | Hidden failure modes | Mandatory negative-results register |
| Template-driven bureaucracy | Fields without engineering value | Tailoring with essential objectives preserved |
| Evidence copied without provenance | Invalid Claims | Evidence Package and Traceability controls |
| Private material published | Confidentiality breach | Classification, rights and public-surrogate decision |
| Old version reused | Inconsistent solution | Version, supersession and consumer notification |
| Source evidence transferred to target | False assurance | Separate Reuse Applicability Assessment |

## 27. Maturity and limitations

This document establishes a documentary and conceptual model. It does not
demonstrate operational Pattern Library capability, tool support, automated
workflow, cross-project reuse, product readiness or safety assurance.

Current maturity remains:

- Pattern & Reuse Core: `STRATEGIC ONLY`;
- Engineering Framework Core: `PARTIAL`;
- Evidence & Traceability Core: `PARTIAL`;
- POC Factory Logic: `STRATEGIC ONLY`.

Maturity may change only through evidence-backed governance decisions.

## 28. Acceptance Criteria compliance matrix

| Acceptance Criterion | Coverage |
|---|---|
| `AC-US018-01` | Sections 2–4 preserve the System of Interest and boundaries. |
| `AC-US018-02` | Sections 3–4 preserve Pattern Library responsibilities. |
| `AC-US018-03` | Sections 3–4, 13 and 18 preserve `MEF-09` and V&V separation. |
| `AC-US018-04` | Sections 3–4 and 11 preserve `PLC-11/12` candidate handoff. |
| `AC-US018-05` | Sections 3, 7, 19 and 20 preserve identity, provenance and baselines. |
| `AC-US018-06` | Sections 6, 12, 16 and 17 consume Evidence Package concepts. |
| `AC-US018-07` | Sections 3, 10, 13 and 15 consume integrated Gate semantics. |
| `AC-US018-08` | Sections 1–2 define purpose, scope and exclusions. |
| `AC-US018-09` | Sections 6 and 9 distinguish Pattern-related concepts. |
| `AC-US018-10` | Section 8 defines the tool-independent minimum contract. |
| `AC-US018-11` | Sections 7–10 define identity, owner, classification and lifecycle. |
| `AC-US018-12` | Section 8 defines context, problem, forces and solution. |
| `AC-US018-13` | Sections 8 and 12 define consequences, alternatives and limits. |
| `AC-US018-14` | Sections 8, 12 and 16 preserve source POC navigation. |
| `AC-US018-15` | Sections 6, 9 and 16 distinguish Claim, Evidence and Pattern. |
| `AC-US018-16` | Sections 12, 16 and 17 preserve negative results and Findings. |
| `AC-US018-17` | Section 12 classifies testable admission obligations. |
| `AC-US018-18` | Sections 8, 11 and 16 separate completeness, validity and admission. |
| `AC-US018-19` | Section 14 distinguishes reviewers and authorities. |
| `AC-US018-20` | Sections 9–10 and 15 link decision and Pattern state. |
| `AC-US018-21` | Sections 10, 15 and 17 bound admission with limitations. |
| `AC-US018-22` | Sections 10, 15 and 19 control rejection and re-review. |
| `AC-US018-23` | Sections 1 and 10 prohibit fictitious `VALIDATED` status. |
| `AC-US018-24` | Sections 9 and 18 separate admission and reuse. |
| `AC-US018-25` | Section 18 defines target assessment and renewed V&V. |
| `AC-US018-26` | Section 19 defines change, impact and reopening. |
| `AC-US018-27` | Section 20 controls deprecation, supersession and retention. |
| `AC-US018-28` | Section 21 defines classification, publication and rights. |
| `AC-US018-29` | Section 22 preserves essential objectives under `T1/T2/T3`. |
| `AC-US018-30` | Sections 23–24 and the companion template cover required views. |
| `AC-US018-31` | Sections 1, 24 and 30 identify the two controlled deliverables. |
| `AC-US018-32` | Section 25 applies the model conceptually without implementation. |
| `AC-US018-33` | Sections 1 and 27 exclude fictitious maturity Claims. |
| `AC-US018-34` | Sections 3 and 13 reuse US017 without a competing Gate family. |
| `AC-US018-35` | Section 30 defines closure evidence obligations. |
| `AC-US018-36` | Sections 2 and 30 preserve the autonomous prompt and US019 boundary. |

## 29. Verification strategy

Verification shall include:

- semantic review against `docs/09–13`;
- consistency between this document and the companion template;
- coverage review of `AC-US018-01` through `AC-US018-36`;
- checks for prohibited overclaims and accidental admission;
- checks for public/private boundary and rights;
- UTF-8 without BOM or NUL, LF endings, final LF and no trailing whitespace;
- `git diff --check` and `git diff --cached --check`;
- minimal two-path staging and blob/hash evidence;
- human decision before commit and merge.

## 30. Closure and interfaces

US018 may close only when both deliverables pass the frozen AC and DoD, Git
evidence is complete, Findings and inherited process observations are recorded,
and the following separate artefacts are delivered:

1. final US018 report;
2. handoff to the general discussion;
3. incremented and deduplicated command catalogue;
4. autonomous `PROMPT_MISE_A_JOUR_DISCUSSION_GENERALE_APRES_US018_v1.0.txt`.

The autonomous prompt shall also be presented directly to the user. Its absence
makes documentary closure incomplete. US019 remains `NOT STARTED / REQUIRES
EXPLICIT GO`.

## 31. Document status

The document defines a controlled Pattern admission and lifecycle model. It
does not establish that any candidate is admitted, validated, published or
reusable. All future applications remain subject to evidence, authority,
configuration, limitations and target-specific decisions.
