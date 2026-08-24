# MBSA Lab OS — Integrated Quality Gates Model

## 1. Purpose

This document defines a single integrated, tool-neutral model for controlled engineering decisions. Gates establish explicit entry criteria, evidence expectations, review authority, decisions, conditions and reopening rules.

A Gate is a decision boundary. It is not a meeting name, checklist alone, software command or guarantee of product quality.

## 2. Gate logical metamodel

A Gate record includes:

- stable Gate identity and family;
- purpose, scope and tailoring level;
- accountable owner and decision authority;
- entry and exit criteria;
- required Evidence Package content;
- review participants and independence needs;
- findings, waivers, limitations and conditions;
- decision, rationale and timestamp;
- configuration and baseline;
- actions, due conditions and reopening triggers;
- supersession, closure and retention information.

Criteria, evidence items, findings, decisions and actions retain their own identities. A Gate view aggregates them without replacing them.

## 3. Identification and taxonomy

Gate identities follow `GATE-<FAMILY>-<NUMBER>`. The integrated families are:

| Family | Purpose |
|---|---|
| GATE-GOV | Governance, authority and scope |
| GATE-ENG | Engineering definition and coherence |
| GATE-EVI | Evidence sufficiency and integrity |
| GATE-POC | POC lifecycle decisions |
| GATE-PUB | Publication and communication |
| GATE-REP | Reproducibility, configuration and repository integrity |
| GATE-CLS | Classification, rights and access |

Checkpoints may prepare or inform a Gate. A checkpoint never creates a competing Gate family and cannot issue a decision reserved to the integrated authority.

## 4. Integrated Gate catalogue

### 4.1 Governance

| ID | Decision focus |
|---|---|
| GATE-GOV-01 | Authority, scope and governing sources |
| GATE-GOV-02 | Tailoring, responsibilities and independence |
| GATE-GOV-03 | Baseline, change and release authority |

### 4.2 Engineering

| ID | Decision focus |
|---|---|
| GATE-ENG-01 | Problem and need definition |
| GATE-ENG-02 | Requirements and acceptance criteria |
| GATE-ENG-03 | Architecture and interface coherence |
| GATE-ENG-04 | Safety and assurance analysis |
| GATE-ENG-05 | Implementation readiness |
| GATE-ENG-06 | Verification readiness |
| GATE-ENG-07 | Validation readiness |
| GATE-ENG-08 | Engineering result review |
| GATE-ENG-09 | Reuse and Pattern readiness |

### 4.3 Evidence

| ID | Decision focus |
|---|---|
| GATE-EVI-01 | Evidence plan and expected content |
| GATE-EVI-02 | Provenance, integrity and configuration |
| GATE-EVI-03 | Claim support, findings and limitations |
| GATE-EVI-04 | Package completeness and acceptance |

### 4.4 POC lifecycle

| ID | Decision focus |
|---|---|
| GATE-POC-01 | Candidate qualification |
| GATE-POC-02 | Readiness assessment |
| GATE-POC-03 | Selection |
| GATE-POC-04 | Start authorization |
| GATE-POC-05 | Execution readiness |
| GATE-POC-06 | Interim review |
| GATE-POC-07 | Verification and validation review |
| GATE-POC-08 | POC acceptance or termination |
| GATE-POC-09 | Pattern-candidate disposition |

### 4.5 Publication

| ID | Decision focus |
|---|---|
| GATE-PUB-01 | Semantic, evidence and audience readiness |
| GATE-PUB-02 | Authorized public release and lifecycle control |

### 4.6 Reproducibility and configuration

| ID | Decision focus |
|---|---|
| GATE-REP-01 | Configuration identity |
| GATE-REP-02 | Reproducibility package sufficiency |
| GATE-REP-03 | Baseline and integrity verification |
| GATE-REP-04 | Retention, restoration and supersession |

### 4.7 Classification and rights

| ID | Decision focus |
|---|---|
| GATE-CLS-01 | Classification, rights and consent assessment |
| GATE-CLS-02 | Access, redaction and release boundary |

## 5. Entry and exit criteria

Entry criteria establish whether a review can produce a valid decision. They cover scope, authority, required inputs, configuration, known findings and participant readiness.

Exit criteria establish whether the Gate objective has been met. Every mandatory criterion receives a result, supporting evidence and reviewer assessment. Missing Critical evidence prevents a positive decision unless the Gate definition explicitly permits a bounded conditional result and the Critical objective remains protected.

## 6. States and transitions

Recommended Gate states are `PLANNED`, `READY_FOR_REVIEW`, `IN_REVIEW`, `DECIDED`, `REOPENED`, `SUPERSEDED` and `CLOSED`.

A Gate moves to `DECIDED` only after authority records a permitted decision. Relevant change, new counter-evidence, expired conditions or invalidated configuration may move it to `REOPENED`. Supersession identifies the replacement Gate decision and retains the earlier record.

## 7. Decision vocabulary

Permitted decisions are:

- `GO` — proceed within the stated scope;
- `GO_WITH_CONDITIONS` — proceed while bounded conditions are controlled;
- `NO_GO` — do not proceed;
- `DEFER` — decision postponed pending identified inputs;
- `ACCEPT` — reviewed outcome accepted;
- `ACCEPT_WITH_CONDITIONS` — accepted with bounded obligations;
- `REJECT` — reviewed outcome not accepted;
- `WITHDRAW` — prior authorization or release withdrawn.

Where a status vocabulary is needed, `PASSED`, `PASSED_WITH_CONDITIONS`, `FAILED` and `NOT_EVALUATED` may summarize criterion outcomes. Status never replaces the decision record.

## 8. Evaluation rules

Reviewers assess criterion result, evidence sufficiency, trace validity, configuration match, unresolved findings, limitations and authority. Aggregate scoring may support prioritization but shall not hide a failed Critical criterion.

An execution or tooling anomaly creates a finding and evidence about the affected activity. It cannot be reinterpreted as successful engineering evidence. The validity of the intended activity must be established by a controlled rerun or other accepted evidence.

## 9. Findings, waivers and conditions

Findings record severity, affected criteria, evidence, owner, required action and disposition. Negative and inconclusive results remain visible.

A waiver is authorized, bounded and time-limited or event-limited. It records risk and compensating controls. Conditions specify owner, due condition, verification method and stop trigger. A vague promise is not a condition.

## 10. Traceability and Evidence Packages

Gate criteria trace to needs, requirements, architecture, controls and lifecycle objectives. Results trace to actual evidence. Claims and limitations use the Traceability Model, and the accepted configuration is identified in the Evidence Package.

A Gate register or dashboard is a view. It cannot replace the underlying evidence, findings, decisions or baselines.

## 11. Engineering framework and POC lifecycle

The engineering Gates map problem definition through requirements, architecture, safety, implementation, verification, validation and reuse. The POC Gates preserve distinct decisions for readiness, selection, start authorization, execution and acceptance.

`READY`, `READY_WITH_CONDITIONS`, `NOT_READY` and `DEFERRED` may describe readiness assessment. They do not imply selection or start authorization. POC success does not imply Pattern admission.

## 12. Change, reopening and supersession

Change impact review identifies affected criteria, evidence, claims, decisions, releases and Patterns. Material impact reopens the relevant Gate. A replacement decision identifies what it supersedes and whether earlier use remains valid.

Gate closure requires conditions and actions to be resolved or transferred under authority, retention to be defined and reopening triggers to remain discoverable.

## 13. Classification and publication

Engineering acceptance and publication authorization are separate. Publication review checks classification, rights, consent, audience, semantic accuracy, evidence traceability, limitations and release identity.

Technical quality is necessary where applicable but never sufficient by itself for publication. A public surrogate remains traceable to its controlled source and discloses its abstraction boundary.

## 14. Tailoring

- **T1** uses compact records and role combinations appropriate to low-complexity work.
- **T2** uses structured criteria, evidence matrices and formal reviews.
- **T3** adds stronger independence, assurance, integrity and retention controls.

Tailoring changes depth and independence, not essential objectives, Critical criteria, evidence provenance, authority, negative-result visibility or change control.

## 15. Minimum decision views

The model supports a Gate register, criteria-and-evidence matrix, decision-and-action log, findings-and-waivers register, reopening-and-supersession view and publication-boundary view.

An end-to-end decision sequence should expose scope and authority, engineering definition, readiness, authorized execution, actual results, evidence review, acceptance, reuse disposition and any public release.

## 16. Roles and authority

The Gate owner prepares the review. Criterion owners provide assessable results. Evidence owners maintain sources and provenance. Reviewers assess sufficiency. Decision authority issues the decision. Classification and publication authorities control access and release.

Roles may be combined proportionately, but accountability and conflicts remain visible.

## 17. Conceptual POC application

The model can assess an Emergency Stop Button as a provisional reference and compare Door Interlock Safety System and Overtemperature Protection System alternatives. This is conceptual only: no candidate is finally selected, authorized to start or accepted by this document.

## 18. Maturity and limitations

This document defines the public decision architecture. It does not demonstrate populated Gate records, independent assurance, tool implementation or completed POC decisions. Checkpoints and Gate outcomes are credible only when supported by real evidence for an identified configuration.
