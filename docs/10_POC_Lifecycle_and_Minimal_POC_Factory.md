# MBSA Lab OS — POC Lifecycle and Minimal POC Factory

## 1. Purpose

This document defines the thirteen-phase lifecycle and minimal logical factory used to govern proofs of concept (POCs) from proposal through closure.

A POC is a bounded engineering experiment intended to reduce uncertainty or demonstrate learning. It is not a production product, certification package, admitted pattern, or publication authorization.

## 2. Scope

The model covers:

- candidate intake, qualification, selection, and framing;
- design, safety assessment, implementation, and V&V;
- evidence, acceptance, publication readiness, learning, reuse, and closure;
- lifecycle states and decision vocabulary;
- logical POC Factory responsibilities and interfaces;
- configuration, change, anomaly, suspension, and reopening controls;
- proportional tailoring and conceptual applicability.

It does not select or start a POC, prescribe technology, or claim that the POC Factory is operational.

## 3. Relationship to the Minimal Engineering Framework

The MEF structures engineering content from problem through reuse. The POC lifecycle governs the investment, authorization, execution, disposition, and retention of one bounded POC.

The two models are complementary:

- MEF answers what engineering work must be credible;
- PLC answers how a POC moves through controlled decisions;
- Evidence and Traceability controls what results support;
- Governance controls authority and configuration.

## 4. Lifecycle overview

| Phase | Name | Objective | Principal state or disposition |
| --- | --- | --- | --- |
| PLC-01 | Proposal | Record the candidate and uncertainty | PROPOSED |
| PLC-02 | Qualification | Establish relevance and assessability | QUALIFIED |
| PLC-03 | Selection | Decide whether to invest | SELECTED, REJECTED, or DEFERRED |
| PLC-04 | Framing | Accept charter, boundary, criteria, and tailoring | FRAMED |
| PLC-05 | Design | Define an accepted solution position | ACTIVE |
| PLC-06 | Safety Assessment | Establish a proportionate safety position | ACTIVE or BLOCKED |
| PLC-07 | Implementation | Realize the controlled POC configuration | IN_REVIEW |
| PLC-08 | Verification and Validation | Evaluate conformance and usefulness separately | IN_REVIEW |
| PLC-09 | Evidence and Acceptance | Decide the claim-evidence disposition | ACCEPTED, REWORK, or ABANDONED |
| PLC-10 | Publication Readiness | Decide what may be released | PUBLICATION_READY or RESTRICTED |
| PLC-11 | Lessons Learned | Retain validated learning and limitations | ACCEPTED |
| PLC-12 | Pattern-Candidate Extraction | Identify reusable knowledge without admission | ACCEPTED |
| PLC-13 | Closure | Complete disposition, retention, and accountability | CLOSED |

## 5. Controlled states

| State | Meaning |
| --- | --- |
| PROPOSED | Candidate exists; no commitment is implied |
| QUALIFIED | Relevance, assessability, and initial constraints are understood |
| SELECTED | Framing is authorized; technical success is not implied |
| FRAMED | Charter and controlled boundary are accepted |
| ACTIVE | Authorized engineering work is in progress |
| IN_REVIEW | Work products await a bounded decision |
| BLOCKED | A defined condition prevents progress |
| DEFERRED | Work is paused with a review trigger |
| ABANDONED | Work ended without intended acceptance |
| ACCEPTED | POC objectives have an accepted evidence position |
| PUBLICATION_READY | A bounded release is authorized |
| RESTRICTED | Publication is prohibited or limited |
| CLOSED | Lifecycle and retention obligations are complete |
| REOPENED | New evidence or change invalidates or extends an earlier decision |

`ACCEPTED` does not mean production readiness, standards compliance, pattern admission, or unrestricted publication.

## 6. Decision vocabulary

| Decision | Effect |
| --- | --- |
| GO | Authorize the next bounded phase |
| NO-GO | Refuse progression |
| GO_WITH_CONDITIONS | Progress under owned, verifiable conditions and stop triggers |
| REWORK | Return defined work for correction |
| DEFER | Pause pending a documented trigger |
| ABANDON | End the POC while retaining evidence and learning |
| RESUME | Reactivate after conditions and baseline are revalidated |
| CLOSE | Finalize lifecycle obligations |
| REOPEN | Reassess an accepted or closed position |

A decision record identifies subject, authority, rationale, evidence, conditions, limitations, configuration, and affected lifecycle state.

## 7. Common phase contract

Every phase has:

- explicit entry criteria;
- identified inputs and outputs;
- accountable authority and participants;
- visible assumptions, risks, findings, and limitations;
- evidence-based acceptance criteria;
- a checkpoint and disposition;
- change and reopening rules;
- controlled public/private classification.

## 8. Phase definitions

### PLC-01 — Proposal

Capture the candidate, source, problem, expected learning, preliminary boundary, stakeholders, assumptions, and exclusions without implying selection.

- Output: `WP-POC-01 POC Proposal`.
- Checkpoint: `CP-POC-01 Proposal Admitted for Qualification`.

### PLC-02 — Qualification

Assess strategic relevance, distinct uncertainty, observability, feasibility, evidence potential, confidentiality, dependencies, and rough tailoring.

- Output: `WP-POC-02 Qualification Record`.
- Checkpoint: `CP-POC-02 Qualification Accepted`.

### PLC-03 — Selection

Compare qualified candidates and make an explicit investment decision. Selection authorizes framing but accepts no technical result.

- Output: `WP-POC-03 Selection Decision`.
- Checkpoint: `CP-POC-03 Selection Disposition`.

### PLC-04 — Framing

Define the POC Charter: objectives, learning questions, IN/OUT boundary, success and stop criteria, assumptions, tailoring, configuration, evidence strategy, and closure conditions.

- Outputs: `WP-POC-04 POC Charter` and `WP-POC-04A Tailoring Record`.
- Checkpoint: `CP-POC-04 Charter Accepted`.

### PLC-05 — Design

Develop requirements, architecture, allocations, interfaces, decisions, implementation boundary, and verification needs consistent with the charter.

- Output: accepted `WP-MEF-04 Architecture Definition` and design decisions.
- Checkpoint: `CP-POC-05 Design Position Accepted`.

### PLC-06 — Safety Assessment

Establish a proportionate safety position, derived controls, assumptions, residual uncertainty, and safety-related V&V needs without unsupported compliance claims.

- Output: `WP-MEF-05 Safety Assessment`.
- Checkpoint: `CP-POC-06 Safety Position Accepted for POC Scope`.

### PLC-07 — Implementation

Realize and identify the configuration needed for the approved experiment. Record dependencies, setup, deviations, and anomalies.

- Output: `WP-MEF-06 Implementation Realization` and configuration record.
- Checkpoint: `CP-POC-07 Implementation Ready for V&V`.

### PLC-08 — Verification and Validation

Execute controlled cases against the identified implementation. Keep verification of requirements separate from validation of intended learning or use.

- Output: `WP-MEF-07 V&V Results` and anomaly records.
- Checkpoint: `CP-POC-08 V&V Conclusion Reviewed`.

### PLC-09 — Evidence and Acceptance

Map Claims to Evidence, Findings, limitations, and residual uncertainty. Decide whether the POC objective is accepted, conditional, reworked, or abandoned.

- Outputs: applicable Evidence Package and `WP-POC-09 Acceptance Record`.
- Checkpoint: `CP-POC-09 POC Evidence and Acceptance Disposition`.

### PLC-10 — Publication Readiness

Review technical accuracy, semantic clarity, evidence, traceability, confidentiality, rights, consent, attribution, and channel suitability separately.

- Output: `WP-POC-10 Publication Readiness Decision`.
- Checkpoint: `CP-POC-10 Publication Disposition`.

Technical Quality PASS does not authorize publication.

### PLC-11 — Lessons Learned

Capture evidence-linked learning, failed assumptions, causal factors, process observations, recommendations, and applicability limits.

- Output: `WP-POC-11 Lessons-Learned Record`.
- Checkpoint: `CP-POC-11 Learning Accepted`.

### PLC-12 — Pattern-Candidate Extraction

Identify potentially reusable knowledge, context, variability, dependencies, evidence, safety implications, and limitations without declaring an admitted pattern.

- Outputs: `WP-MEF-09 Reuse Assessment` and `WP-POC-12 Pattern Candidate`.
- Checkpoint: `CP-POC-12 Reuse Disposition`.

POC success does not equal Pattern admission.

### PLC-13 — Closure

Reconcile final state, open items, retained configuration, evidence, publication disposition, reuse disposition, ownership, access, and reopening triggers.

- Output: `WP-POC-13 Closure Record`.
- Checkpoint: `CP-POC-13 POC Closed`.

## 9. Lifecycle-to-MEF mapping

| POC phase group | Principal MEF relationship |
| --- | --- |
| PLC-01 to PLC-04 | MEF-01 Problem, MEF-02 Need, and framing of MEF-03 Requirement |
| PLC-05 | MEF-03 Requirement and MEF-04 Architecture |
| PLC-06 | MEF-05 Safety Assessment |
| PLC-07 | MEF-06 Implementation |
| PLC-08 | MEF-07 Verification and Validation |
| PLC-09 | MEF-08 Evidence |
| PLC-11 and PLC-12 | Feedback to all MEF stages and MEF-09 Reuse |
| PLC-10 and PLC-13 | Governance overlays; not additional MEF stages |

## 10. Minimal POC Factory responsibilities

The logical POC Factory provides:

- candidate intake and register control;
- qualification and comparison support;
- charter, tailoring, and configuration control;
- phase-entry and checkpoint coordination;
- integration of engineering, safety, V&V, and evidence work;
- anomaly, condition, suspension, and reopening control;
- publication and reuse handoffs;
- closure and retention coordination.

These responsibilities may initially be manual. A documented factory is `PARTIAL` until repeated controlled execution is demonstrated.

## 11. Interfaces and control flows

- Governance Decision and Baseline — authority, scope, conditions, and accepted configuration.
- Engineering Work-Product Exchange — needs, requirements, architecture, implementation, and V&V inputs.
- Evidence and Trace-Link Exchange — identities, Claims, Evidence, Findings, limitations, and decisions.
- Publication Handoff — bounded release source and authorization.
- Reuse Handoff — candidate knowledge with context and evidence.

No handoff transfers authority silently. The receiving lifecycle applies its own criteria and decision.

## 12. Tailoring and proportionality

Tailoring levels T1, T2, and T3 may vary document depth, review independence, coverage, and formalism. Tailoring must retain:

- bounded objective and system context;
- measurable success and stop criteria;
- configuration identity;
- proportionate safety reasoning;
- separate verification and validation;
- evidence-linked acceptance;
- findings and limitations;
- publication and reuse authority where applicable;
- closure and reopening controls.

## 13. Configuration, change, and anomalies

A POC configuration identifies relevant source, requirements, architecture, implementation, environment, data, procedures, and dependencies.

A material change triggers impact analysis across affected phases, evidence, claims, safety controls, publication, and reuse. An anomaly records observation, expected behaviour, configuration, severity, disposition, and affected evidence.

Accepted or published results are not silently overwritten. Correction, erratum, supersession, withdrawal, retention, and reopening are controlled.

## 14. Suspension, deferral, abandonment, and resumption

- Suspension addresses a temporary blocker during active work.
- Deferral pauses investment pending a stated trigger.
- Abandonment ends the intended path while retaining learning and evidence.
- Resumption requires revalidation of conditions, configuration, dependencies, and authority.

## 15. Evidence, publication, and reuse boundaries

- POC acceptance means the bounded objective has an accepted evidence position.
- Publication readiness means a specific release boundary is authorized.
- Pattern candidacy means reusable potential has been identified.
- Pattern admission requires a separate Pattern decision.
- Communication material never replaces engineering evidence.

## 16. Conceptual multi-POC assessment

### 16.1 Emergency Stop Button

Provisional reference candidate for readiness analysis. It is not finally selected and is not authorized to start.

### 16.2 Door Interlock Safety System

Retained alternative testing state-dependent access, sensor plausibility, actuation, and unsafe-open behaviour.

### 16.3 Overtemperature Protection System

Retained alternative testing continuous sensing, thresholds, degraded states, protective action, and environmental assumptions.

Application to all three candidates remains conceptual and non-implementing.

## 17. Limitations

The lifecycle and factory are public engineering definitions. They do not prove that a POC has been selected, authorized, implemented, verified, accepted, published, or converted into an admitted pattern.

POC Factory maturity remains `PARTIAL` until repeated controlled execution provides operational evidence.
