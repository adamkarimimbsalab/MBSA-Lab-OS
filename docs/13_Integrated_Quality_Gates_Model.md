# MBSA Lab OS — Integrated Quality Gates Model

## 1. Purpose and Document Status

This document defines the integrated quality-gate model for MBSA Lab OS. It
connects governance decisions, Minimal Engineering Framework (MEF) checkpoints,
POC lifecycle decisions, traceability controls, Evidence Packages, repository
baselines, publication boundaries and closure controls through one coherent and
tool-independent contract.

The model answers five questions for every Gate:

1. what bounded object and baseline are being reviewed;
2. what measurable criteria and applicable evidence are required;
3. who prepares, reviews and decides;
4. what decision is permitted by the observed results;
5. what actions, limitations and reopening triggers remain after the decision.

Document status: **candidate architectural definition for US017**. Installation,
review, version control and US017 closure evidence remain governed by the US017
Controlled PING-PONG workflow. The presence of this document does not prove that
any project or POC Gate has been executed or passed.

## 2. Scope and Exclusions

### 2.1 In scope

This model defines:

- a common Gate contract and stable identification scheme;
- Gate families, levels, states, transitions and decision vocabulary;
- entry and exit criteria, evidence obligations and evaluation rules;
- ownership, review participation and decision authority;
- mappings to MEF stages, POC lifecycle phases, trace links and Evidence Packages;
- findings, limitations, waivers, DEBUG records and compensating controls;
- post-baseline change, reopening, supersession, closure and retention;
- the relationship between Gate decisions and Git evidence;
- classification and publication-boundary controls;
- proportional tailoring for T1, T2 and T3;
- minimal decision views and conceptual application to three POC candidates.

### 2.2 Out of scope

This document does not:

- select, design, implement, verify or validate a real POC;
- execute a Gate or manufacture evidence for a POC;
- implement a workflow engine, API, plugin, pipeline or proprietary tool;
- claim universal normative status, certification, regulatory compliance or
  safety integrity;
- redefine the MEF, POC lifecycle, Traceability Model or Evidence Package Model;
- define pattern admission or pattern lifecycle, which remain owned by US018;
- start Video Factory US019, readiness US020, freeze US021 or closure US022;
- publish or modify the private Master Plan or MBSA-Lab-Control content.

### 2.3 Intended use

The model is intended for an individual engineering project first. It is also
scalable to collaborative work by separating responsibilities even when one
person performs several roles. A user may implement the model with Markdown,
Git, issue tracking, requirements tools or automation, but the semantics do not
depend on a particular tool.

## 3. Sources of Authority and Precedence

The following precedence applies when interpreting this document:

1. controlled Git evidence and the applicable approved baseline;
2. `docs/12_Evidence_Package_Model.md` for evidence, Claims, completeness,
   Findings, limitations and acceptance;
3. `docs/11_Traceability_Model.md` for identities, relations, baselines, impact
   analysis and Claim–Evidence semantics;
4. `docs/10_POC_Lifecycle_and_Minimal_POC_Factory.md` for POC phases, decisions,
   abandonment, resumption and closure;
5. `docs/09_Minimal_Engineering_Framework.md` for stages, work products,
   checkpoints and V&V;
6. `docs/08_MBSA_Lab_OS_Capability_and_Logical_Architecture.md` for logical
   responsibilities and interfaces;
7. `docs/07_MBSA_Lab_OS_System_Context_and_Boundaries.md` for the System of
   Interest and trust boundaries;
8. `docs/03` to `docs/06` for governance, Git workflow and repository rules.

A lower-precedence source shall not silently override a higher-precedence
contract. A material contradiction creates a Finding and blocks an unqualified
PASS until the contradiction is resolved or dispositioned by the competent
authority.

## 4. Inherited Architecture and Governance Invariants

The model preserves the following invariants:

- MBSA Lab OS is the System of Interest and MBSA-Lab-OS remains public.
- MBSA-Lab-Control and the private Master Plan remain outside the public repository.
- Governance decides, approves baselines and accepts bounded deviations.
- Engineering owns engineering sources and generated work products.
- Evidence & Traceability references, evaluates and packages evidence without
  transferring source ownership.
- The POC Lifecycle orchestrates the MEF; it does not replace MEF-01 to MEF-09.
- Requirement Verification and Need Validation remain distinct activities.
- Evidence supports Claims; a Claim cannot be stronger than its supporting evidence.
- Negative, missing, invalid, superseded and inconclusive results remain visible.
- A waiver neither creates evidence nor changes an observed FAIL into PASS.
- Technical validity, governance acceptance, publication and reuse are distinct decisions.
- Tailoring never removes essential Gate objectives or auditability.
- POC Factory Logic and Pattern & Reuse Core remain `STRATEGIC ONLY`.
- Engineering Framework Core and Evidence & Traceability Core remain `PARTIAL`.

## 5. Normative Language and Core Terms

`SHALL` denotes a mandatory rule of this model. `SHOULD` denotes a recommended
rule requiring justification when not followed. `MAY` denotes a permitted choice.

| Term | Definition |
|---|---|
| Gate | A bounded review-and-decision control over an identified object, scope, configuration and baseline. |
| Gate instance | One application of a Gate definition to one governed object and decision context. |
| Criterion | A measurable, observable or explicitly reviewable condition. |
| Evidence obligation | A MANDATORY, CONDITIONAL or OPTIONAL expectation for an Evidence Item. |
| Decision authority | The role authorized to issue the decision for the bounded Gate instance. |
| Decision record | The immutable record of authority, date, scope, baseline, evidence, result, conditions and next action. |
| Finding | A recorded gap, contradiction, anomaly or unmet expectation requiring disposition. |
| Limitation | A known bound on evidence, applicability, confidence or interpretation. |
| Waiver | A bounded and authorized acceptance of a deviation; it does not modify observed evidence. |
| DEBUG | An investigation/correction status; it is not an acceptance decision. |
| Reopening | A controlled transition from a previously decided state to renewed evaluation. |
| Supersession | Replacement of a controlled Gate decision by an identified later decision without deleting history. |

## 6. Gate Logical Metamodel

A Gate definition SHALL expose the following attributes:

| Attribute group | Required content |
|---|---|
| Identity | stable Gate ID, title, version and purpose |
| Applicability | family, level, governed object type and applicability rule |
| Control boundary | scope, configuration, baseline and tailoring profile |
| Responsibilities | owner, contributors, reviewer and decision authority |
| Entry | measurable prerequisites and their recorded state |
| Evidence | obligations, Evidence Package reference and validity requirements |
| Evaluation | review method, independence rule and criterion logic |
| Decision | permitted outcomes and decision constraints |
| Exit | required actions, owner and due date or trigger |
| Exceptions | waiver authority, risk, compensating controls and expiration |
| Traceability | Claims, Evidence, Findings, Decisions, baselines and impacts |
| Lifecycle | state, reopening triggers, closure and supersession rules |
| Boundary | PUBLIC, PRIVATE or BOUNDARY_SHARED classification |
| Repository | optional Git events used as evidence, never as semantic substitutes |

A Gate instance SHALL additionally identify:

- `gate_instance_id`;
- governed object identity and version;
- configuration and baseline identifiers;
- applicable criteria and evidence obligations;
- review participants and declared conflicts of interest;
- review date and decision date;
- decision, conditions, limitations and open actions;
- links to the decision record and Evidence Package baseline.

No Gate may be satisfied solely by its title, a meeting, a checkbox, a commit,
a branch, a pull request or a tool status.

## 7. Identification Scheme

Gate definitions use `GATE-<FAMILY>-<NN>`. Gate instances use
`GI-<GATE-ID>-<OBJECT>-<SEQUENCE>`. Examples are illustrative, not evidence:

- `GATE-GOV-01` — Scope and Authorization;
- `GI-GATE-GOV-01-US017-001` — the first scope review instance for US017;
- `GATE-ENG-07` — V&V Readiness and Results;
- `GATE-REP-03` — Main Integration and Remote Synchronization.

Identifiers SHALL remain stable after publication. Renaming a title does not
change identity. A materially changed contract requires a new version; an
incompatible replacement requires a new Gate definition or explicit supersession.

## 8. Integrated Gate Taxonomy

### 8.1 Gate families

| Family | Prefix | Primary purpose | Primary authority |
|---|---|---|---|
| Governance and framing | `GOV` | authorization, scope, tailoring, risk and baseline | Governance |
| Engineering and V&V | `ENG` | MEF readiness, work-product quality and V&V | Governance on Engineering recommendation |
| POC lifecycle | `POC` | phase transitions and operational POC decisions | POC decision authority |
| Evidence and traceability | `EVI` | evidence validity, coverage, Claims and Findings | Acceptance authority |
| Configuration and repository | `REP` | version, scope, lineage, merge and synchronization evidence | Repository authority |
| Publication and reuse | `PUB` | public boundary, release, lessons and reuse readiness | Publication/reuse authority |
| Closure and retention | `CLS` | action closure, archive, supersession and final status | Governance |

Each Gate has one primary family and one primary decision authority. It MAY
consume views owned by other families. Cross-family consumption does not create
duplicate Gates or transfer ownership.

### 8.2 Gate levels

| Level | Meaning | Typical object |
|---|---|---|
| `L0` | project/sprint governance control | roadmap, sprint, architecture baseline |
| `L1` | POC or engineering lifecycle control | POC phase, MEF stage set |
| `L2` | work-product or Evidence Package control | requirement set, architecture, test result package |
| `L3` | repository/publication transaction control | branch, commit, merge, release artifact |

Level expresses the controlled object, not importance. A lower-level Gate may
block a higher-level decision when its evidence is mandatory.

## 9. Integrated Gate Catalogue

| Gate ID | Gate | Level | Principal inputs | Permitted principal outcomes |
|---|---|---:|---|---|
| `GATE-GOV-01` | Scope and authorization | L0/L1 | objective, boundaries, dependencies | GO, NO-GO, REWORK, DEFER |
| `GATE-GOV-02` | Acceptance contract and tailoring | L0/L1 | AC, DoD, tailoring record | GO, GO_WITH_CONDITIONS, REWORK |
| `GATE-GOV-03` | Baseline authorization | L0–L2 | reviewed configuration, decision package | GO, NO-GO, DEFER |
| `GATE-ENG-01` | Problem readiness | L1/L2 | MEF-01 work products | GO, REWORK, DEFER |
| `GATE-ENG-02` | Need readiness | L1/L2 | MEF-02 work products | GO, REWORK, DEFER |
| `GATE-ENG-03` | Requirement readiness | L1/L2 | MEF-03 work products | GO, REWORK, DEFER |
| `GATE-ENG-04` | Architecture readiness | L1/L2 | MEF-04 work products | GO, REWORK, DEFER |
| `GATE-ENG-05` | Safety-assessment readiness | L1/L2 | MEF-05 work products | GO, REWORK, DEFER |
| `GATE-ENG-06` | Implementation readiness/results | L1/L2 | MEF-06 baseline and build evidence | GO, REWORK, DEFER |
| `GATE-ENG-07` | V&V readiness/results | L1/L2 | MEF-07 plans, procedures and results | GO, NO-GO, REWORK |
| `GATE-ENG-08` | Evidence readiness | L1/L2 | MEF-08 package | GO, GO_WITH_CONDITIONS, REWORK |
| `GATE-ENG-09` | Reuse readiness | L1/L2 | MEF-09 applicability evidence | GO, NO-GO, DEFER |
| `GATE-POC-01` | Proposal qualification | L1 | PLC-01/02 records | GO, NO-GO, DEFER, ABANDON |
| `GATE-POC-02` | Selection | L1 | qualified candidates and rationale | GO, NO-GO, DEFER |
| `GATE-POC-03` | Framing approval | L1 | PLC-04 scope and plan | GO, GO_WITH_CONDITIONS, REWORK |
| `GATE-POC-04` | Design/safety approval | L1 | PLC-05/06 outputs | GO, NO-GO, REWORK |
| `GATE-POC-05` | Implementation/V&V authorization | L1 | PLC-07/08 readiness | GO, NO-GO, REWORK |
| `GATE-POC-06` | Evidence and acceptance | L1 | PLC-09 Evidence Package | GO, GO_WITH_CONDITIONS, NO-GO |
| `GATE-POC-07` | Publication readiness | L1 | PLC-10 public surrogate and boundary review | GO, NO-GO, DEFER |
| `GATE-POC-08` | Lessons/pattern-candidate handoff | L1 | PLC-11/12 records | GO, REWORK, DEFER |
| `GATE-POC-09` | POC closure | L1 | PLC-13 closure package | CLOSE, REWORK, DEFER |
| `GATE-EVI-01` | Traceability coverage | L2 | required links, coverage and gaps | GO, GO_WITH_CONDITIONS, REWORK |
| `GATE-EVI-02` | Evidence validity and integrity | L2 | provenance, validity and checksums | GO, NO-GO, REWORK |
| `GATE-EVI-03` | Claim and acceptance review | L1/L2 | Claims, criteria, results and limitations | GO, GO_WITH_CONDITIONS, NO-GO |
| `GATE-EVI-04` | Finding and waiver disposition | L1/L2 | Findings, waivers and controls | GO, GO_WITH_CONDITIONS, REWORK |
| `GATE-REP-01` | Entry baseline and branch authorization | L3 | main/remote baseline and clean tree | GO, NO-GO, REWORK |
| `GATE-REP-02` | Candidate scope and commit readiness | L3 | diff, staging, content checks | GO, NO-GO, REWORK |
| `GATE-REP-03` | Integration and synchronization | L3 | merge ancestry, remote state and scope | GO, NO-GO, REWORK |
| `GATE-REP-04` | Reachability and feature cleanup | L3 | main reachability and branch state | CLOSE, REOPEN, REWORK |
| `GATE-PUB-01` | Classification and publication boundary | L1/L2 | classification matrix and public surrogate | GO, NO-GO, REWORK |
| `GATE-PUB-02` | Reuse handoff readiness | L1/L2 | applicability and limitations | GO, NO-GO, DEFER |
| `GATE-CLS-01` | Decision/action closure | L0–L2 | action register and final evidence | CLOSE, REOPEN, DEFER |
| `GATE-CLS-02` | Retention and supersession | L0–L2 | archive index and replacement decision | CLOSE, REWORK |

The catalogue is architectural. A project SHALL instantiate only applicable
Gates and SHALL record non-applicability rather than silently omitting expected
controls.

A repository anomaly enters the DEBUG investigation workflow defined in
Section 20. DEBUG may block evaluation or require retest, but it is not a
permitted Gate decision or lifecycle state.

## 10. Mapping to MEF Checkpoints

| MEF stage | Integrated Gate | Gate consumes | Gate does not replace |
|---|---|---|---|
| MEF-01 Problem | `GATE-ENG-01` | problem definition, context and rationale | engineering production/review activities |
| MEF-02 Need | `GATE-ENG-02` | stakeholder need and validation intent | Need Validation |
| MEF-03 Requirement | `GATE-ENG-03` | requirement quality and traceability | requirement authorship |
| MEF-04 Architecture | `GATE-ENG-04` | architecture views, allocations and decisions | architecture development |
| MEF-05 Safety Assessment | `GATE-ENG-05` | hazards, safety reasoning and limitations | safety-analysis method |
| MEF-06 Implementation | `GATE-ENG-06` | configured implementation and build evidence | implementation activity |
| MEF-07 V&V | `GATE-ENG-07` | plan, procedure, environment and results | Verification or Validation execution |
| MEF-08 Evidence | `GATE-ENG-08`, `GATE-EVI-*` | Evidence Package, Claims and Findings | evidence-source ownership |
| MEF-09 Reuse | `GATE-ENG-09`, `GATE-PUB-02` | applicability and reuse limitations | US018 pattern admission |

MEF checkpoints remain the engineering control points defined by US013. This
model supplies a uniform decision envelope and cross-family integration.

## 11. Mapping to the POC Lifecycle

| POC phases | Integrated decision control | Required coordination |
|---|---|---|
| PLC-01 Proposal / PLC-02 Qualification | `GATE-POC-01` | governance scope and candidate evidence |
| PLC-03 Selection | `GATE-POC-02` | comparative rationale; no candidate is preselected here |
| PLC-04 Framing | `GATE-POC-03` | `GATE-GOV-01/02` and MEF applicability |
| PLC-05 Design / PLC-06 Safety Assessment | `GATE-POC-04` | `GATE-ENG-04/05` and traceability coverage |
| PLC-07 Implementation / PLC-08 V&V | `GATE-POC-05` | `GATE-ENG-06/07` and configured baseline |
| PLC-09 Evidence and Acceptance | `GATE-POC-06` | `GATE-EVI-01..04` and acceptance authority |
| PLC-10 Publication | `GATE-POC-07` | `GATE-PUB-01`; technical validity is not publication approval |
| PLC-11 Lessons / PLC-12 Pattern Candidate | `GATE-POC-08` | evidence-backed lessons and bounded candidate handoff |
| PLC-13 Closure | `GATE-POC-09`, `GATE-CLS-01/02` | open-action disposition, retention and final status |

POC phase completion and Gate decision are linked but not synonymous. A phase
may be operationally complete while its Gate is blocked by missing or invalid
evidence.

## 12. Traceability and Evidence Integration

Each Gate instance SHALL link at minimum:

```text
Gate Definition -> APPLIES_TO -> Governed Object
Gate Instance -> BASELINED_AS -> Reviewed Baseline
Gate Instance -> REQUIRES -> Acceptance Criterion
Evidence Item -> SUPPORTS -> Claim
Result -> VERIFIES -> Requirement
Validation Result -> VALIDATES -> Need
Finding -> CHALLENGES -> Claim or Decision
Decision -> DECIDES -> Gate Instance
Decision -> BASED_ON -> Evidence Package Baseline
Change -> IMPACTS -> Gate Instance or Decision
Decision -> SUPERSEDES -> Earlier Decision
```

Links SHALL preserve identity, source, target, relation type, status, baseline
and provenance as defined by the Traceability Model. Invalid, missing,
superseded and not-applicable links remain visible in coverage views.

An Evidence Package used at a Gate SHALL identify:

- package ID, version, scope, configuration and baseline;
- applicable MANDATORY, CONDITIONAL and OPTIONAL obligations;
- item status: `PRESENT`, `MISSING`, `NOT_APPLICABLE`, `INVALID` or `SUPERSEDED`;
- result vocabulary: `PASS`, `FAIL`, `BLOCKED`, `NOT_EXECUTED` or `INCONCLUSIVE`;
- Claims, Findings, limitations, waivers and acceptance references;
- provenance, integrity, validity and publication classification.

Package completeness is evaluated against applicable obligations, not file
count. A complete package can still contain a FAIL; completeness is not
acceptance.

## 13. Gate States and Lifecycle

### 13.1 States

| State | Meaning |
|---|---|
| `PLANNED` | Gate instance identified but not yet evaluated for readiness |
| `READY` | entry criteria and minimum review package available |
| `IN_REVIEW` | controlled evaluation in progress |
| `PASSED` | authorized decision issued with all mandatory conditions satisfied |
| `PASSED_WITH_CONDITIONS` | bounded authorization with tracked conditions |
| `FAILED` | decision criteria prohibit progression |
| `DEFERRED` | decision postponed with reason and trigger |
| `REOPENED` | earlier decision invalidated or challenged by a reopening trigger |
| `CLOSED` | decision and required follow-up are completed and retained |
| `SUPERSEDED` | replaced by an identified later controlled decision |

`DEBUG` is not a Gate lifecycle state. It is an investigation status applied to
the execution or evidence-generation workflow while the Gate remains in its
current controlled state.

### 13.2 Permitted transitions

```text
PLANNED -> READY -> IN_REVIEW
IN_REVIEW -> PASSED | PASSED_WITH_CONDITIONS | FAILED | DEFERRED
PASSED | PASSED_WITH_CONDITIONS | FAILED | DEFERRED -> REOPENED
REOPENED -> READY | IN_REVIEW
PASSED | PASSED_WITH_CONDITIONS -> CLOSED
FAILED | DEFERRED -> CLOSED only after explicit abandonment or terminal disposition
any decided state -> SUPERSEDED through an identified replacement decision
```

Every transition SHALL record actor, authority, timestamp, source state,
destination state, reason, baseline and supporting evidence.

## 14. Entry Criteria

Entry criteria SHALL be measurable, observable or explicitly reviewable. A Gate
may enter `READY` only when:

- the governed object, scope, configuration and baseline are identified;
- the Gate contract and applicable tailoring profile are known;
- prerequisite decisions have valid states;
- required reviewers and decision authority are identified and available;
- the Evidence Package index exists and mandatory review inputs are available;
- known Findings, limitations, waivers and conflicts are disclosed;
- classification and access constraints permit the planned review;
- the review method and independence needs are recorded.

A missing mandatory prerequisite records the prerequisite readiness status
`NOT_READY` and prevents the transition to `READY`. `NOT_READY` is not an
Evidence Item status and shall not be hidden by scheduling the review meeting.

## 15. Exit Criteria

A Gate may leave `IN_REVIEW` only when:

- every applicable criterion has an explicit result and evidence reference;
- contradictions and Findings are recorded and dispositioned to the extent
  required by the selected decision;
- the decision authority has reviewed the applicable package baseline;
- the selected outcome is permitted by the rule set in Section 17;
- conditions, limitations and compensating controls are explicit;
- each follow-up action has an owner and due date or event trigger;
- the decision record is baselined, linked and classified;
- reopening and expiration triggers are recorded.

Exit from review does not necessarily authorize forward progression. `FAILED`,
`DEFERRED`, `REWORK` and `ABANDON` are legitimate visible outcomes.

## 16. Review and Evaluation Rules

For each criterion the review record SHALL state:

- criterion ID and applicability;
- evaluation method: test, analysis, inspection, demonstration or review;
- expected observation or threshold;
- actual result and result status;
- evidence identity, version and validity;
- reviewer and review date;
- Finding, limitation or waiver reference where applicable.

Independence SHALL be adapted to risk and tailoring:

- T1 MAY use self-review with an explicit checklist and retained evidence;
- T2 SHOULD separate author and reviewer for key Gates;
- T3 SHALL define independence needs based on risk, criticality and applicable
  governance obligations.

Independence is a property of the review arrangement, not merely a job title.
When one person holds several roles, the decision record shall make the role
switch explicit and identify any limitation.

## 17. Decision Vocabulary and Logic

### 17.1 Permitted decisions

| Decision | Meaning |
|---|---|
| `GO` | authorized progression within the recorded scope and baseline |
| `NO-GO` | progression prohibited |
| `GO_WITH_CONDITIONS` | bounded progression authorized with enforceable conditions |
| `REWORK` | correction required before renewed review |
| `DEFER` | decision postponed pending an identified event or evidence |
| `ABANDON` | controlled termination of the governed activity |
| `REOPEN` | previous decision returned to active evaluation |
| `CLOSE` | controlled completion and retention |

### 17.2 Decision rules

`GO` requires all applicable mandatory criteria satisfied, all mandatory
evidence present and valid, no unresolved material contradiction, and no open
Finding whose severity prohibits progression.

`GO_WITH_CONDITIONS` is permitted only when:

- the unmet item is compatible with bounded progression;
- authority to accept the condition is explicit;
- risk, scope and affected Claims are recorded;
- compensating controls are active where needed;
- owners and due dates or triggers are assigned;
- expiration and automatic reopening conditions are defined.

An applicable mandatory criterion with `FAIL`, `BLOCKED`, `NOT_EXECUTED` or
`INCONCLUSIVE` prohibits an unqualified `GO`. A waiver may affect the authorized
decision but does not change the observed result.

`NO-GO`, `REWORK`, `DEFER` and `ABANDON` SHALL preserve the failed or missing
evidence and state the permitted next action.

### 17.3 Decision-to-state mapping

| Decision | Resulting Gate state | Rule |
|---|---|---|
| `GO` | `PASSED` | all mandatory progression conditions are satisfied |
| `GO_WITH_CONDITIONS` | `PASSED_WITH_CONDITIONS` | bounded conditions and reopening triggers are recorded |
| `NO-GO` | `FAILED` | progression is prohibited for the reviewed scope and baseline |
| `REWORK` | `FAILED` or `REOPENED` | `FAILED` after an initial review; `REOPENED` when an earlier decision is challenged |
| `DEFER` | `DEFERRED` | a review date or event trigger and retention conditions are recorded |
| `ABANDON` | `FAILED`, then `CLOSED` | terminal disposition is retained; closure follows only after closure criteria are met |
| `REOPEN` | `REOPENED` | the earlier decision remains in history and renewed evaluation is required |
| `CLOSE` | `CLOSED` | all applicable closure and retention conditions are satisfied |

The decision and resulting state SHALL be recorded together. DEBUG never maps
to a Gate decision or state; it temporarily blocks or investigates the
evaluation workflow until retest evidence is available.

### 17.4 Decision record

Every decision SHALL contain decision ID, Gate instance, authority, date,
governed object, scope, configuration, baseline, evidence package baseline,
criteria results, Findings, waivers, outcome, conditions, limitations, next
action and reopening triggers.

## 18. Findings, Limitations and Negative Results

Findings SHALL be classified by identity, type, severity, affected object,
baseline, related criterion, owner, due date or trigger, status and disposition.

The model prohibits:

- deletion of failed results from the decision view;
- conversion of `INCONCLUSIVE` to PASS without new evidence;
- treating `NOT_EXECUTED` as `NOT_APPLICABLE`;
- treating a limitation statement as a waiver;
- closing a material contradiction through narrative consensus alone.

A Claim's confidence and scope SHALL be reduced when its evidence is limited,
invalid, superseded or contradicted.

## 19. Waivers and Compensating Controls

A waiver SHALL identify:

- waiver ID and competent authority;
- governed object, deviation and affected criterion;
- scope, configuration and baseline;
- justification and accepted risk;
- affected Claims and decisions;
- compensating controls and their evidence;
- start, expiration date or event trigger;
- review, revocation and reopening conditions.

Waivers SHALL be visible in the Gate decision view. An expired or invalidated
waiver triggers reopening when it was necessary for the earlier decision.

## 20. DEBUG and Command-Incident Control

Any investigation or correction of an execution anomaly SHALL start with
`DEBUG`. The DEBUG record SHALL preserve:

- symptom and exact operational context;
- command or mechanism involved;
- root cause or current hypothesis;
- impact on repository, evidence and Gate status;
- bounded correction;
- retest evidence;
- preventive rule and propagation target.

DEBUG is never evidence of acceptance. A corrected command must be retested,
and the affected Gate remains blocked until the intended postcondition is
proved.

For interactive PowerShell/Git controls:

- commands SHOULD be single-line, tagged and fail-fast when grouping is safe;
- `Set-Location` SHALL be supplied separately;
- interactive commands SHALL NOT use `exit`, `exit 1` or process termination;
- failures SHALL emit `[DEBUG]` and `[STOP]` while preserving the console;
- native Git success/failure SHALL be decided using `$LASTEXITCODE`;
- the wrapper SHALL temporarily avoid terminating treatment of native `stderr`;
- Git success messages on `stderr` SHALL NOT be treated as failures;
- variable native output SHALL return `0..N` lines without forced array nesting;
- wrappers SHALL NOT use `return ,$o` when an empty native output is valid;
- exactly-one-line output SHALL be checked before scalar conversion;
- after an interruption following mutation, a read-only postcheck SHALL precede
  retry, rollback or further mutation.

## 21. Change, Impact and Post-Baseline Control

A post-baseline change SHALL create a new version or commit and SHALL NOT
rewrite controlled history. Its record includes:

- change identity, rationale and authority;
- source and target baselines;
- impacted requirements, architecture, safety analysis, implementation, V&V,
  Evidence Items, Claims, Gate decisions and publication artifacts;
- evidence to renew or invalidate;
- selected disposition: maintain, reopen, supersede or retire;
- decision and completion evidence.

Impact analysis depth is proportional to the change, but the existence of an
impact decision is not tailorable.

## 22. Reopening, Supersession and Closure

Reopening triggers include:

- changed scope, configuration or baseline;
- new contradictory evidence or invalidated evidence;
- material Finding or previously hidden negative result;
- expired waiver or failed compensating control;
- changed classification or publication boundary;
- unavailable dependency or changed external assumption;
- reuse outside the recorded applicability envelope;
- correction that changes a criterion result or Claim.

Reopening SHALL preserve the earlier decision. A new decision either confirms,
changes or supersedes it. Supersession links both decisions and states why the
earlier decision is no longer current.

Closure requires disposition of required actions, retention of the decision
and evidence index, recorded residual limitations, final classification and
identified reopening conditions. Abandonment may close work but does not erase
the engineering or decision history.

## 23. Classification and Publication Boundary

Each Gate artifact SHALL be classified as:

- `PUBLIC` — approved for the public MBSA-Lab-OS boundary;
- `PRIVATE` — retained in the private control boundary;
- `BOUNDARY_SHARED` — exchanged through an explicitly controlled interface.

A public repository SHALL contain neither private Strategic Control content nor
credentials, personal data or restricted supplier information. When public
evidence is required for a private source, a controlled public surrogate MAY
describe the decision, scope and limitations without exposing restricted content.

Technical Gate PASS does not grant publication permission. `GATE-PUB-01` must
evaluate classification, redaction, public surrogate validity, licensing and
publication authority independently.

## 24. Relationship with Git Evidence

Git can prove version, scope, integrity, ancestry and publication state. It
cannot alone prove semantic correctness, safety adequacy or acceptance.

| Git event or evidence | What it may prove | What it cannot prove alone |
|---|---|---|
| clean entry baseline | absence of local uncommitted change | semantic validity of the baseline |
| authorized feature branch | isolated change origin | authorization beyond its recorded Gate |
| diff/staging scope | candidate file scope | content correctness |
| functional commit | immutable candidate version | acceptance |
| merge `--no-ff` and parents | integration lineage | semantic review quality |
| push and remote-live SHA | publication/synchronization state | release or Gate acceptance |
| reachability | commit retained from main | correctness of the commit |
| feature cleanup | branch lifecycle completion | evidence completeness |

Repository Gates SHALL distinguish entry baseline, feature branch, candidate
diff, staged scope, functional commit, merge commit, remote synchronization,
reachability and cleanup. No SHA may be invented or anticipated.

## 25. Tailoring and Proportionality

### 25.1 T1 — lightweight controlled application

T1 MAY combine related reviews and use compact registers. It still SHALL retain
Gate identity, scope, baseline, mandatory criteria, Evidence references,
negative results, Findings, authority, decision, limitations, classification,
change/reopening rules and audit trail.

### 25.2 T2 — structured application

T2 SHOULD separate key Gates, authors and reviewers, maintain explicit coverage
and action matrices, and baseline decision packages at significant transitions.

### 25.3 T3 — increased assurance

T3 SHALL increase review depth, independence where justified, evidence
challenge, configuration control and formal action/waiver monitoring according
to risk and applicable obligations.

Tailoring is recorded before application. It SHALL state profile, rationale,
combined or omitted non-essential activities, preserved objectives, authorities
and approval. Tailoring never creates a claim of external compliance.

## 26. Minimal Decision Views

### 26.1 Gate register

| Gate instance | Object/baseline | State | Owner | Authority | Decision | Conditions | Reopen trigger |
|---|---|---|---|---|---|---|---|

### 26.2 Criteria and evidence matrix

| Gate instance | Criterion | Applicability | Result | Evidence item/version | Validity | Finding/waiver |
|---|---|---|---|---|---|---|

### 26.3 Decision and action log

| Decision ID | Gate instance | Outcome | Baseline | Authority/date | Action | Owner | Due/trigger | Status |
|---|---|---|---|---|---|---|---|---|

### 26.4 Reopening and supersession view

| Earlier decision | Trigger | Impacted claims/evidence | New Gate instance | New decision | Supersession link |
|---|---|---|---|---|---|

### 26.5 Publication-boundary view

| Artifact/evidence | Classification | Source owner | Public surrogate | Publication authority | Status |
|---|---|---|---|---|---|

These views SHALL remain navigable from stable identities. Empty templates are
not proof; populated and baselined records are required for an executed Gate.

## 27. End-to-End Decision Sequence

The generic sequence is:

1. Governance authorizes scope and tailoring through `GATE-GOV-01/02`.
2. Engineering produces MEF work products under source ownership.
3. Applicable `GATE-ENG-*` instances evaluate stage readiness and results.
4. POC lifecycle Gates consume, coordinate and decide operational transitions.
5. `GATE-EVI-*` evaluates traceability, Evidence Package validity, Claims and Findings.
6. Governance issues bounded acceptance and baseline decisions.
7. `GATE-REP-*` proves repository transactions when Git is applicable.
8. `GATE-PUB-*` separately controls publication and reuse handoffs.
9. `GATE-CLS-*` closes actions, retention and supersession.

Any step may generate a backward impact, `REWORK`, `DEFER`, `NO-GO`, `ABANDON`
or reopening. The sequence is controlled but not artificially linear.

## 28. Conceptual Application to Three POC Candidates

The following examples test genericity only. They do not select, design,
implement or evaluate a real POC and contain no fabricated Gate result.

### 28.1 Emergency Stop Button

Potential Gate emphasis includes clear problem/need separation, safety-related
requirements, architecture and failure-response reasoning, configured hardware
and software interfaces, response-time Verification, Need Validation, evidence
integrity and explicit limitations. A publication decision would separately
assess whether diagrams, code and evidence are public.

The same Gate contract can govern the candidate without pre-assigning PASS,
safety integrity or fitness for use.

### 28.2 Door Interlock Safety System

Potential Gate emphasis includes operating modes, boundary conditions,
prevention and detection behavior, interface allocation, fault and misuse
analysis, state-based Verification, Validation scenarios, Findings and reopening
after configuration changes.

The model supports traceability from Need through Requirement, Architecture,
V&V Result, Evidence and Claim while keeping Requirement Verification distinct
from Need Validation.

### 28.3 Overtemperature Protection System

Potential Gate emphasis includes sensing assumptions, thresholds, timing,
diagnostics, mitigation behavior, degraded modes, environmental conditions,
test/analysis evidence and explicit applicability limits.

A changed sensor, threshold, environment or control strategy would trigger
impact analysis and may reopen earlier architecture, V&V and acceptance Gates.

### 28.4 Genericity conclusion

All three candidates can use the same identities, states, criteria/evidence
contract, authority model, decision vocabulary, Git relationship and reopening
rules. Their evidence content and assurance depth differ. This supports
genericity without asserting execution or equivalence of risk.

## 29. Responsibility and Authority Model

| Responsibility | Owns | Shall not silently assume |
|---|---|---|
| Governance | scope, tailoring, baseline, deviation and acceptance decisions | engineering-source ownership |
| Engineering | work products, technical rationale and corrections | final acceptance authority |
| Evidence & Traceability | link integrity, evidence index, coverage and Finding visibility | source authorship or waiver authority |
| Reviewer | evaluation and challenge record | decision authority unless explicitly assigned |
| POC Factory Logic | lifecycle orchestration and handoffs | existence of an operational team or tool |
| Repository authority | Git transaction evidence | semantic acceptance |
| Publication authority | boundary and release decision | technical Claim creation |
| Reuse authority | applicability and reuse handoff | US018 pattern admission before authorization |

Role accumulation is permitted for an individual project, but the record SHALL
state which role is acting at each decision and any resulting independence
limitation.

## 30. Risks, Limitations and Maturity

### 30.1 Principal risks and controls

| Risk | Control |
|---|---|
| Gate proliferation | one primary family/authority; tailoring and mapping instead of duplication |
| checkbox compliance | measurable criteria and evidence-linked results |
| commit treated as acceptance | explicit Git/Gate separation |
| hidden negative evidence | mandatory visibility of FAIL/BLOCKED/INCONCLUSIVE and Findings |
| waiver misuse | bounded authority, expiration and unchanged observed result |
| stale decision after change | impact analysis and reopening triggers |
| private content leakage | classification and public-surrogate control |
| false operational maturity | explicit candidate/documentary status |
| individual role concentration | role declaration and independence limitation |

### 30.2 Maturity statement

This document establishes an architectural and documentary Gate model.

- Engineering Framework Core remains `PARTIAL`.
- Evidence & Traceability Core remains `PARTIAL`.
- POC Factory Logic remains `STRATEGIC ONLY`.
- Pattern & Reuse Core remains `STRATEGIC ONLY`.

No executed Gate, workflow automation, tool readiness, POC readiness, product
readiness, safety integrity, certification or compliance is demonstrated.

## 31. Acceptance Criteria Compliance Matrix

The following matrix records candidate-document coverage. Formal US017 AC
verdicts require the controlled review and Git evidence defined by the US017
workflow.

| AC | Candidate coverage | Status before formal review |
|---|---|---|
| AC-US017-01 | Sections 2–4, 23 | COVERED — PENDING REVIEW |
| AC-US017-02 | Sections 3–4, 29 | COVERED — PENDING REVIEW |
| AC-US017-03 | Sections 4, 10, 27 | COVERED — PENDING REVIEW |
| AC-US017-04 | Sections 4, 11, 27 | COVERED — PENDING REVIEW |
| AC-US017-05 | Sections 3, 7, 12, 21–22 | COVERED — PENDING REVIEW |
| AC-US017-06 | Sections 3, 12, 17–19 | COVERED — PENDING REVIEW |
| AC-US017-07 | Sections 1–2 | COVERED — PENDING REVIEW |
| AC-US017-08 | Sections 5–7 | COVERED — PENDING REVIEW |
| AC-US017-09 | Sections 8–11 | COVERED — PENDING REVIEW |
| AC-US017-10 | Section 8 | COVERED — PENDING REVIEW |
| AC-US017-11 | Section 13 | COVERED — PENDING REVIEW |
| AC-US017-12 | Section 14 | COVERED — PENDING REVIEW |
| AC-US017-13 | Section 15 | COVERED — PENDING REVIEW |
| AC-US017-14 | Sections 12, 14–17 | COVERED — PENDING REVIEW |
| AC-US017-15 | Sections 6, 26 | COVERED — PENDING REVIEW |
| AC-US017-16 | Sections 6, 16, 29 | COVERED — PENDING REVIEW |
| AC-US017-17 | Section 17 | COVERED — PENDING REVIEW |
| AC-US017-18 | Section 17.2 | COVERED — PENDING REVIEW |
| AC-US017-19 | Sections 12, 17–18 | COVERED — PENDING REVIEW |
| AC-US017-20 | Sections 13, 20 | COVERED — PENDING REVIEW |
| AC-US017-21 | Section 19 | COVERED — PENDING REVIEW |
| AC-US017-22 | Section 21 | COVERED — PENDING REVIEW |
| AC-US017-23 | Section 22 | COVERED — PENDING REVIEW |
| AC-US017-24 | Section 22 | COVERED — PENDING REVIEW |
| AC-US017-25 | Section 24 | COVERED — PENDING REVIEW |
| AC-US017-26 | Sections 20, 24 | COVERED — PENDING REVIEW |
| AC-US017-27 | Section 23 | COVERED — PENDING REVIEW |
| AC-US017-28 | Section 25 | COVERED — PENDING REVIEW |
| AC-US017-29 | Sections 2.3, 16, 25, 29 | COVERED — PENDING REVIEW |
| AC-US017-30 | Sections 4, 29 | COVERED — PENDING REVIEW |
| AC-US017-31 | Sections 9, 26 | COVERED — PENDING REVIEW |
| AC-US017-32 | Section 28 | COVERED — PENDING REVIEW |
| AC-US017-33 | Sections 1, 2, 28, 30 | COVERED — PENDING REVIEW |
| AC-US017-34 | Sections 2.2, 10, 30, 33 | COVERED — PENDING REVIEW |

## 32. Verification and Closure Strategy

### 32.1 Content verification

Formal review SHALL verify:

- consistency with `docs/07` to `docs/12`;
- presence and internal consistency of the Gate contract, catalogue, states,
  criteria, evidence rules, authorities, decisions and reopening logic;
- explicit preservation of negative results, Findings and limitations;
- conceptual genericity across the three candidates;
- absence of fabricated evidence or operational claims;
- complete traceability to all 34 frozen AC.

### 32.2 Document verification

The controlled workflow SHALL verify UTF-8 without BOM or NUL, LF line endings,
absence of trailing whitespace, valid Markdown structure, stable identifiers,
references, SHA-256 and Git blob identity.

### 32.3 Repository verification

Only `docs/13_Integrated_Quality_Gates_Model.md` may be staged and committed for
the functional scope. The workflow SHALL prove diff scope, functional commit,
merge `--no-ff`, merge parents and subject, push, main/origin/remote-live
alignment, reachability, clean working tree and local/remote feature cleanup.

### 32.4 Acceptance rule

US017 may be declared DONE only when all frozen AC have evidence-based PASS
verdicts, the Definition of Done is satisfied, all macro-Gates are closed, no
blocking or contradictory reservation remains, and US018 remains
`NOT STARTED / REQUIRES EXPLICIT GO`.

## 33. Interfaces with US018 and Later Work

US017 supplies US018 with Gate semantics that may govern future pattern
admission and lifecycle decisions. It does not define the pattern admission
criteria, admit a candidate or authorize US018.

US019–US022 remain outside this document. Their future Gates may instantiate
this model only after their own explicit authorization and controlled scope
decisions.

## 34. Document Status

This candidate defines the Integrated Quality Gates Model requested by US017.
It is suitable for controlled installation and review, subject to the US017
workflow. It does not itself constitute a Gate decision, a repository baseline,
a POC result, a certification claim or authorization to start US018.
