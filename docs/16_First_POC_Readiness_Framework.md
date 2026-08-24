# First POC Readiness Framework

## 1. Purpose

This document defines the minimum framework used by MBSA Lab to determine
whether a first proof of concept (POC) is ready to enter controlled execution.
It provides a repeatable basis for comparing candidate POCs, identifying
missing prerequisites, recording conditions, and making an explicit readiness
decision.

The framework separates four questions that must not be conflated:

1. Is the candidate useful as a demonstration?
2. Is its intended scope sufficiently bounded?
3. Are the engineering and assurance prerequisites available?
4. Has an authorized decision been made to start execution?

A positive readiness assessment answers the first three questions. It does not,
by itself, answer the fourth.

## 2. Scope

The framework covers:

- candidate definition and comparison;
- problem statement and demonstrative value;
- scope, boundary, assumptions, constraints, and dependencies;
- stakeholder, requirement, architecture, analysis, verification, and evidence
  prerequisites;
- traceability and configuration expectations;
- risk, uncertainty, limitation, and stop-trigger management;
- readiness decision rules and permitted decision states;
- proportionate tailoring for POCs of different complexity;
- conceptual application to three initial candidates:
  - Emergency Stop Button;
  - Door Interlock Safety System;
  - Overtemperature Protection System.

## 3. Exclusions

This framework does not:

- authorize or start a POC;
- select a candidate irreversibly;
- define a detailed product architecture;
- prescribe a technology stack or tool vendor;
- implement software, hardware, models, tests, or automation;
- claim that verification or safety evidence already exists;
- replace project governance, engineering review, or safety judgment;
- treat a communication asset as engineering evidence;
- approve a reusable pattern merely because it was used by a POC.

## 4. Normative Language

The terms **shall**, **should**, and **may** express mandatory, recommended, and
permitted provisions respectively. A provision marked **shall** may be tailored
only through an explicit, justified, reviewed, and traceable decision.

## 5. Core Principles

### 5.1 Readiness is evidence-based

A readiness decision shall reference inspectable information. Intent,
repository presence, document existence, or tool output alone is insufficient.

### 5.2 Readiness is not execution authorization

`READY` and `READY_WITH_CONDITIONS` describe prerequisite maturity. A separate
authorized decision is required before resources are committed or execution
begins.

### 5.3 Demonstrative value is necessary but insufficient

A candidate should make the MBSE and MBSA value chain visible, but an attractive
demonstration shall not compensate for an uncontrolled boundary, unavailable
evidence, or unacceptable risk.

### 5.4 Claims remain proportional to evidence

No candidate may claim more maturity, safety, verification, reuse, or
operational relevance than its available evidence supports.

### 5.5 Traceability is established before evidence accumulates

Identifiers, relationships, configuration references, and evidence locations
shall be defined early enough to prevent retrospective reconstruction.

### 5.6 Reversibility is preserved

The first POC shall be small enough to stop, revise, defer, or replace without
creating disproportionate sunk cost or architectural lock-in.

### 5.7 Public information is deliberately bounded

Public engineering content shall contain only information useful to understand,
assess, reproduce, or reuse the published approach. Internal orchestration,
working procedures, unpublished review records, and operational administration
shall remain outside public deliverables.

## 6. Key Definitions

| Term | Definition |
| --- | --- |
| Candidate POC | A bounded concept being considered for controlled execution. |
| POC charter | The authoritative statement of purpose, boundary, objectives, constraints, expected outputs, and decision authority. |
| Readiness criterion | A testable condition required before execution may be considered. |
| Readiness record | The configuration-controlled assessment of criteria, evidence, gaps, conditions, and decision. |
| Condition | A bounded obligation that must be satisfied by a stated owner and due point. |
| Stop trigger | An observable condition requiring work not to start or to stop pending review. |
| Evidence | Inspectable information supporting or challenging a claim. |
| Finding | A recorded observation, nonconformity, uncertainty, or unresolved question. |
| Tailoring | Controlled adaptation of required activities or artefacts to the POC context. |
| Public surrogate | Sanitized information that preserves demonstrative meaning without exposing restricted source material. |

## 7. Readiness Dimensions

Readiness is assessed across ten dimensions. No single aggregate score may hide
a failed mandatory criterion.

### 7.1 Purpose and value

The candidate shall have:

- a concise problem statement;
- an identified audience and decision need;
- an explicit MBSE and MBSA learning objective;
- a demonstrable end-to-end value proposition;
- success measures that can be observed within the POC boundary.

### 7.2 Scope and boundary

The candidate shall identify:

- system of interest and external actors;
- operational context;
- included and excluded behavior;
- normal, degraded, and relevant abnormal conditions;
- interfaces crossing the boundary;
- the maximum scope permitted for the first increment.

### 7.3 Stakeholders and governance

The readiness record shall name, at minimum:

- the POC owner;
- engineering authority;
- assurance or safety review authority;
- verification reviewer;
- configuration and publication authority where applicable;
- the authority allowed to authorize, condition, defer, stop, or reopen work.

The same person may hold multiple roles for a small POC, but the resulting lack
of independence shall be declared.

### 7.4 Requirements and claims

The candidate shall define:

- stakeholder need or use case;
- functional intent;
- safety-relevant intent where applicable;
- requirement identifiers and acceptance logic;
- initial claims to be evaluated;
- prohibited claims that available evidence cannot support.

### 7.5 Architecture and interfaces

Readiness requires enough architectural definition to establish feasibility and
verification boundaries, without prematurely freezing implementation detail.
The minimum includes:

- logical functions;
- responsible logical components;
- key interfaces and exchanged information;
- external dependencies;
- relevant failure propagation paths;
- explicit architectural unknowns.

### 7.6 MBSA analysis basis

The candidate shall identify:

- hazardous or undesirable behavior within scope;
- initiating faults or failure conditions considered;
- expected safety mechanisms or constraints;
- the analysis method proposed;
- assumptions and limitations affecting interpretation;
- the planned relationship between analysis results and engineering decisions.

No analysis result shall be presumed before the analysis is executed and
reviewed.

### 7.7 Verification and validation basis

The candidate shall have a testable verification concept covering:

- what will be verified or validated;
- which requirements, claims, interfaces, and scenarios are covered;
- method and expected result;
- required environment, data, and instrumentation;
- pass, fail, inconclusive, and blocked outcomes;
- treatment of anomalies and reruns.

### 7.8 Traceability and evidence

The candidate shall define how it will maintain links among:

- stakeholder need and use case;
- requirements;
- architecture elements and interfaces;
- failure analysis elements;
- verification cases and results;
- claims, evidence, findings, and decisions;
- configuration and version identifiers.

Evidence shall remain distinguishable from narrative explanation. Missing,
superseded, rejected, or withdrawn evidence shall remain visible through its
lifecycle status.

### 7.9 Resources and feasibility

Readiness shall account for:

- skills and review capacity;
- model, software, hardware, or simulation availability;
- data rights and confidentiality constraints;
- tool availability without turning tools into architectural dependencies;
- estimated effort and elapsed time;
- integration and environment constraints;
- credible fallback options.

### 7.10 Communication and publication

If the POC is intended for public demonstration, readiness shall establish:

- what may be published;
- which sources require a public surrogate;
- ownership, licensing, consent, and classification checks;
- the relationship between published material and authoritative evidence;
- correction, supersession, withdrawal, and retention rules.

A video, screenshot, diagram, or narrative is a projection of engineering work;
it is not a substitute for source artefacts or evidence.

## 8. Criterion Classification

Each criterion shall be classified as one of the following:

| Class | Meaning | Decision effect |
| --- | --- | --- |
| Critical | Protects boundary, safety, authority, evidence integrity, or legal constraints. | Any failure prevents `READY` and `READY_WITH_CONDITIONS`. |
| Mandatory | Required for controlled execution, but a bounded gap may be converted into an explicit pre-start condition. | Failure normally produces `NOT_READY`; narrowly bounded gaps may produce `READY_WITH_CONDITIONS`. |
| Supporting | Improves effectiveness or reuse but is not essential to begin safely and coherently. | Gap is recorded and prioritized but does not independently prevent readiness. |

Criticality shall be assigned before the assessment result is known.

## 9. Readiness States

### 9.1 READY

`READY` means:

- all Critical and Mandatory criteria pass;
- evidence is available and configuration-identifiable;
- no open condition is required before starting;
- residual uncertainties and risks are accepted by the proper authority;
- execution may be considered through a separate authorization decision.

### 9.2 READY_WITH_CONDITIONS

`READY_WITH_CONDITIONS` means:

- all Critical criteria pass;
- no condition undermines safety, scope integrity, evidence integrity, or legal
  compliance;
- every remaining condition has an owner, objective evidence, due point, and
  escalation path;
- conditions designated pre-start are closed before execution begins;
- a separate authorization decision is still required.

### 9.3 NOT_READY

`NOT_READY` means that one or more Critical criteria fail, Mandatory gaps are
not acceptably bounded, evidence is insufficient, or a stop trigger is active.
Required remediation and reassessment shall be recorded.

### 9.4 DEFERRED

`DEFERRED` means that assessment or execution is intentionally postponed because
of priority, dependency, timing, resource, or strategic considerations. It does
not imply technical failure or future authorization.

## 10. Mandatory Stop Triggers

The decision shall be `NOT_READY`, or an active assessment shall stop, when any
of the following is observed:

- the system boundary is materially ambiguous;
- the POC would require uncontrolled access to restricted information;
- a safety-relevant claim lacks an identified verification or analysis path;
- evidence provenance or configuration cannot be established;
- required decision authority is absent or conflicted;
- expected behavior depends on a fabricated or unverified result;
- the candidate cannot be reduced to a reversible first increment;
- a legal, licensing, consent, export, or publication constraint is unresolved;
- an external dependency has no viable fallback and invalidates the schedule;
- scope growth changes the problem, risk class, or assurance needs;
- a condition previously accepted as bounded becomes open-ended;
- the proposed demonstration would overstate maturity or safety.

## 11. Minimum Input Set

The following inputs shall be available or explicitly recorded as gaps:

| Input | Minimum content |
| --- | --- |
| Candidate statement | Name, problem, audience, value, expected learning. |
| Context and boundary | Actors, external systems, inclusions, exclusions, interfaces. |
| POC charter | Objectives, maximum scope, outputs, constraints, owners, decision authority. |
| Requirement basis | Needs, requirements, acceptance intent, identifiers. |
| Architecture basis | Functions, logical components, interfaces, key failure paths. |
| MBSA basis | Undesired behavior, faults, mechanisms, method, assumptions. |
| Verification concept | Cases, methods, environments, expected results, verdict rules. |
| Traceability plan | Required relationships and lifecycle states. |
| Evidence plan | Evidence types, provenance, storage, review, retention. |
| Risk register | Risks, likelihood or exposure rationale, controls, owners, triggers. |
| Resource estimate | Skills, assets, dependencies, effort range, fallback. |
| Publication boundary | Classification, rights, licenses, surrogates, review authority. |

## 12. Readiness Record

Each assessment shall use a configuration-identifiable readiness record. For
every criterion, the record shall contain:

- criterion identifier and classification;
- applicability and tailoring decision;
- result: `PASS`, `FAIL`, `PARTIAL`, `NOT_ASSESSED`, or `NOT_APPLICABLE`;
- objective rationale;
- evidence or source reference;
- open finding or condition identifier;
- owner and due point;
- reviewer and review date;
- effect on the overall decision.

The record shall also contain:

- assessed candidate and version;
- assessment boundary;
- assumptions and limitations;
- open risks and dependencies;
- aggregate decision and decision authority;
- conditions, stop triggers, and reopening criteria;
- next permitted action.

## 13. Decision Logic

The following precedence applies:

1. An active stop trigger results in `NOT_READY`.
2. Any failed Critical criterion results in `NOT_READY`.
3. An unbounded Mandatory gap results in `NOT_READY`.
4. A bounded Mandatory gap may result in `READY_WITH_CONDITIONS` only when the
   condition cannot invalidate the assessment and is assigned appropriately.
5. `READY` requires all Critical and Mandatory criteria to pass.
6. A strategic postponement may result in `DEFERRED`, regardless of technical
   readiness, provided the technical assessment is not misrepresented.
7. No state authorizes execution automatically.

Numerical scoring may support comparison, but it shall not override this
precedence or average away a blocking failure.

## 14. Assessment Workflow

The minimum workflow is:

1. register the candidate and intended decision;
2. establish the assessment boundary;
3. confirm roles and decision authority;
4. classify criteria before evaluating results;
5. collect or reference the minimum inputs;
6. assess each readiness dimension;
7. record evidence, gaps, findings, risks, and conditions;
8. perform engineering, assurance, evidence, and publication reviews as
   applicable;
9. apply stop triggers and decision precedence;
10. issue the readiness state with rationale;
11. authorize, condition, defer, or reject the next action separately;
12. retain the record and reopen it when a trigger occurs.

## 15. Review Separation

The following review concerns shall remain distinguishable, even when performed
by a small team:

| Review concern | Primary question |
| --- | --- |
| Engineering | Is the problem, boundary, architecture basis, and feasibility coherent? |
| Safety and assurance | Are hazards, failure assumptions, claims, and assurance needs adequately framed? |
| Verification | Are success, failure, and inconclusive outcomes testable? |
| Evidence and traceability | Can each material claim and decision be reconstructed from controlled sources? |
| Publication | Can the intended public material be released without overclaim, rights, or confidentiality issues? |
| Decision authority | Is the residual risk and uncertainty acceptable for the next action? |

A pass in one concern shall not be interpreted as a pass in another.

## 16. Conditions Management

A condition is valid only when it includes:

- a unique identifier;
- the criterion or risk that created it;
- a precise closure statement;
- required evidence;
- an accountable owner;
- a due point expressed as a date or lifecycle event;
- escalation and stop behavior if overdue;
- a reviewer authorized to close it.

Conditions shall not be used to bypass failed Critical criteria or to defer an
unbounded portion of the candidate scope.

## 17. Reassessment and Reopening

The readiness decision shall be reopened when:

- the candidate boundary changes materially;
- a new interface or dependency is introduced;
- a requirement, hazard, assumption, or claim changes materially;
- evidence is invalidated, withdrawn, or superseded;
- a condition is missed or becomes unbounded;
- the implementation strategy changes the verification or assurance basis;
- a significant finding or external constraint emerges;
- the planned publication scope changes;
- the readiness record is no longer aligned with the candidate configuration.

Reassessment may be limited to affected criteria only when impact analysis shows
that the remaining decision basis is unchanged.

## 18. Tailoring

Tailoring provides proportionality without removing essential objectives.

### 18.1 T1 — Compact

Suitable for a small, self-contained candidate with few interfaces and no
specialized execution environment. Artefacts may be consolidated, but boundary,
requirements, analysis basis, verification, evidence, risks, and authority
remain explicit.

### 18.2 T2 — Standard

Suitable for a candidate with several logical elements, meaningful failure
behavior, and multiple verification scenarios. Separate engineering,
traceability, evidence, and review records are normally expected.

### 18.3 T3 — Extended

Suitable for a candidate with complex interfaces, specialized hardware or data,
significant external dependencies, or stronger assurance and publication needs.
Additional independence, configuration, evidence, and review provisions may be
required.

### 18.4 Tailoring rules

Every tailoring decision shall:

- identify the affected provision;
- preserve its objective or explain why it is not applicable;
- state the compensating control where needed;
- identify the approving authority;
- remain traceable to the readiness record.

## 19. Conceptual Candidate Assessment Method

The three initial candidates are compared conceptually against the following
characteristics:

- clarity of observable behavior;
- ability to expose MBSE-to-MBSA traceability;
- boundary controllability;
- safety mechanism visibility;
- verification feasibility;
- evidence diversity;
- dependency and environment burden;
- demonstrative clarity for a public audience;
- extensibility without first-increment scope growth;
- reversibility and fallback options.

This comparison is not a readiness verdict. Actual readiness requires the input
set and evidence defined above.

## 20. Candidate A — Emergency Stop Button

### 20.1 Concept

The candidate demonstrates how an emergency stop request is detected,
validated, propagated, acted upon, monitored, and evidenced within a bounded
system context.

### 20.2 Demonstrative strengths

- direct and easily observable trigger-to-response chain;
- clear distinction between command, acknowledgement, achieved safe behavior,
  and reset authorization;
- strong fit for requirement-to-architecture-to-analysis-to-test traceability;
- natural failure modes such as missed detection, unintended activation,
  delayed response, stuck signal, broken communication, and invalid reset;
- feasible staged growth from a logical simulation to richer implementations;
- understandable public narrative without requiring proprietary data.

### 20.3 Principal readiness questions

- What exactly is stopped, inhibited, or brought to a safe condition?
- Which behaviors are immediate and which require controlled sequencing?
- How are activation, acknowledgement, safe-state achievement, and reset kept
  distinct?
- What prevents unauthorized or premature restart?
- Which faults are detected, tolerated, or exposed?
- What timing assumptions and observability are required?
- Can a public surrogate represent the relevant behavior faithfully?

### 20.4 Principal risks

- oversimplifying the difference between a command and achieved safe state;
- implying compliance with industrial emergency-stop standards without an
  applicable product context and evidence;
- hiding reset and restart hazards;
- reducing the POC to a trivial button demonstration without an assurance chain.

### 20.5 Conceptual position

This candidate is the provisional reference candidate for a first detailed
readiness assessment because it combines a compact boundary, visible safety
logic, broad traceability opportunities, and manageable dependencies. This is a
conditional recommendation, not an execution authorization or final selection.

## 21. Candidate B — Door Interlock Safety System

### 21.1 Concept

The candidate demonstrates controlled access or operation based on door state,
locking state, authorization, operating mode, and detected inconsistencies.

### 21.2 Demonstrative strengths

- rich state and transition behavior;
- visible interaction between sensing, command, physical state, and operating
  permission;
- meaningful degraded scenarios and diagnostic coverage;
- strong basis for state-machine, interface, and failure-analysis views.

### 21.3 Principal readiness questions

- Is the protected equipment or zone boundary explicit?
- How are door position, lock position, and command state distinguished?
- Which transitions are allowed in each operating mode?
- What occurs on sensor disagreement, loss of power, or failed locking?
- Is escape, override, or maintenance access in scope?
- Can physical behavior be represented without specialized hardware?

### 21.4 Principal risks

- rapid scope growth through modes, bypasses, human factors, and physical
  mechanisms;
- ambiguity between monitored state and actual physical containment;
- hardware dependencies that may delay a first increment;
- context-specific safety expectations being presented as universal.

### 21.5 Conceptual position

This candidate remains a strong alternative when state-machine richness and
sensor-actuator consistency are prioritized. A compact first increment would
require strict control of modes, overrides, and physical assumptions.

## 22. Candidate C — Overtemperature Protection System

### 22.1 Concept

The candidate demonstrates temperature acquisition, plausibility assessment,
threshold or model-based detection, protective action, recovery, and evidence
under normal and faulted conditions.

### 22.2 Demonstrative strengths

- quantitative inputs and time-dependent behavior;
- opportunities for threshold, hysteresis, rate-of-rise, filtering, and sensor
  plausibility analysis;
- clear links among physical assumptions, requirements, algorithms, failure
  modes, and test data;
- natural support for simulated scenarios and reproducible datasets.

### 22.3 Principal readiness questions

- What asset and thermal boundary are protected?
- Which temperature range, dynamics, accuracy, and sampling assumptions apply?
- Are thresholds illustrative or derived from an authoritative source?
- How are sensor faults distinguished from real overheating?
- What protective action is required and when may recovery occur?
- Which thermal behavior must be simulated rather than claimed as physical?

### 22.4 Principal risks

- requiring a credible thermal model or hardware environment too early;
- presenting illustrative thresholds as validated engineering limits;
- overlooking latency, calibration, hysteresis, and sensor-placement effects;
- conflating detection performance with complete system protection.

### 22.5 Conceptual position

This candidate remains a strong alternative when quantitative analysis and
data-driven verification are prioritized. Its readiness depends more heavily on
the credibility and provenance of the thermal assumptions and data.

## 23. Conceptual Comparison

| Characteristic | Emergency Stop Button | Door Interlock | Overtemperature Protection |
| --- | --- | --- | --- |
| Boundary compactness | High | Medium | Medium |
| Observable safety response | High | High | High |
| State-machine richness | Medium | High | Medium |
| Quantitative analysis potential | Medium | Medium | High |
| Specialized environment dependency | Low to medium | Medium to high | Medium to high |
| Public demonstrative clarity | High | High | High |
| Risk of uncontrolled first-increment growth | Medium | High | Medium |
| Natural MBSE–MBSA traceability | High | High | High |
| Reversibility of a logical first increment | High | Medium | Medium to high |

The qualitative values express conceptual tendencies only. They shall be
replaced by evidence-based assessment results before a readiness verdict.

## 24. Recommended Candidate Sequence

Subject to evidence-based readiness assessment, the default sequence is:

1. Emergency Stop Button as the reference candidate;
2. Door Interlock Safety System as the state-rich alternative;
3. Overtemperature Protection System as the quantitative alternative.

The sequence may change when resource availability, evidence provenance,
strategic learning objectives, or risk analysis supports a different choice.
All three candidates remain legitimate until an authorized selection decision
is recorded.

## 25. Minimum Success Measures for the First POC

The first POC should demonstrate, at minimum:

- a controlled system boundary and use case;
- uniquely identified requirements and architecture elements;
- at least one safety-relevant claim and its analysis basis;
- representative nominal, faulted, and recovery behavior;
- traceability from intent through architecture and analysis to verification;
- reproducible verification evidence with explicit verdicts;
- visible findings, assumptions, limitations, and decisions;
- a configuration-identifiable evidence package;
- a public explanation that does not exceed the authoritative evidence;
- an explicit decision on what should be retained, improved, generalized, or
  rejected after completion.

Success does not require production-grade implementation, exhaustive safety
assessment, certification, or universal reuse.

## 26. Evidence Expectations

The evidence plan should distinguish:

| Evidence category | Examples |
| --- | --- |
| Context | Boundary model, actor description, operational scenarios. |
| Requirements | Identified needs, functional and safety-related requirements, acceptance logic. |
| Architecture | Logical views, interfaces, state behavior, allocation rationale. |
| Analysis | Failure scenarios, assumptions, analysis configuration, reviewed results. |
| Verification | Test specification, environment configuration, execution record, verdict, anomaly. |
| Traceability | Relationship export, coverage report, unresolved-link report. |
| Decision | Review record, finding disposition, accepted limitation, readiness decision. |
| Communication | Approved public surrogate, publication review, correction or withdrawal record. |

Each evidence item shall identify its source, configuration, producer, review
status, and relationship to the claim or decision it supports.

## 27. Risk Model

At least the following risk classes shall be considered:

- scope and boundary ambiguity;
- requirements volatility;
- architecture feasibility;
- safety-analysis incompleteness;
- verification environment unavailability;
- evidence loss or provenance weakness;
- traceability gaps;
- skills or review-capacity constraints;
- schedule and dependency uncertainty;
- confidentiality, licensing, consent, and publication constraints;
- overclaim and audience misinterpretation;
- tool lock-in or non-reproducibility.

Risk handling shall identify prevention, detection, mitigation, fallback, owner,
review point, and stop trigger where applicable.

## 28. Tool and Technology Neutrality

The framework is independent of a specific modeling, analysis, requirements,
test, repository, recording, or publication tool. A selected tool may be used
when it supports the required objectives, but tool availability alone shall not
be treated as readiness.

Where a tool is replaced, the integrity of identifiers, relationships,
configuration, evidence, and decisions shall be preserved.

## 29. Pattern and Reuse Relationship

A POC may apply an existing pattern or produce observations relevant to a future
pattern. POC success does not automatically prove that the solution is reusable,
admissible, generalized, or mature.

Any reusable-pattern claim requires separate evidence concerning:

- repeated applicability;
- explicit context and variability;
- known limitations and counterexamples;
- verification and evidence expectations;
- lifecycle ownership and change control.

## 30. Communication Relationship

Communication preparation may begin only when a stable, inspectable engineering
baseline exists. Publication readiness is distinct from technical quality,
semantic quality, evidence sufficiency, and execution readiness.

Any public release shall remain traceable to its authoritative sources and
shall identify material assumptions and limitations. Corrections, errata,
supersession, withdrawal, and retention shall be controlled without silently
overwriting prior releases.

## 31. Readiness Review Questions

Before issuing a decision, reviewers should be able to answer:

1. What exact decision is requested?
2. What is the smallest valid first increment?
3. Which claims will the POC attempt to support or challenge?
4. Which claims are expressly prohibited?
5. What evidence is required for each material claim?
6. What could invalidate the boundary or assessment?
7. Which dependencies lack a fallback?
8. Which uncertainties affect safety or interpretability?
9. Can results be reproduced from controlled configuration and data?
10. Can the work stop cleanly if a trigger occurs?
11. Can public material be produced without exposing restricted information?
12. Who is authorized to accept the residual risks and conditions?

An unanswered material question shall be recorded as a finding, not converted
into an implicit assumption.

## 32. Readiness Decision Record Template

A decision record should contain the following fields:

| Field | Required content |
| --- | --- |
| Candidate | Name and configuration identifier. |
| Decision requested | Readiness question and next contemplated action. |
| Boundary | Included and excluded scope. |
| Tailoring level | T1, T2, or T3 with rationale. |
| Criteria results | Critical, Mandatory, and Supporting results with evidence. |
| Findings | Open, accepted, resolved, superseded, and rejected findings. |
| Conditions | Owner, closure evidence, due point, escalation. |
| Risks | Residual exposure, controls, owner, acceptance authority. |
| Limitations | Known limits on interpretation and reuse. |
| Decision | `READY`, `READY_WITH_CONDITIONS`, `NOT_READY`, or `DEFERRED`. |
| Authority | Decision maker and date. |
| Next action | Separately authorized action or explicit stop. |
| Reopening triggers | Events that invalidate or require review of the decision. |

## 33. Framework Maturity and Limitations

This framework establishes a minimum readiness model. Its effectiveness must be
demonstrated through controlled application and retrospective review.

Current limitations include:

- no completed POC evidence is asserted by this document;
- the qualitative candidate comparison is conceptual;
- tailoring thresholds require calibration through use;
- domain-specific regulatory or standards obligations must be added when an
  actual application context is selected;
- independence and assurance depth depend on the real risk and claim context;
- readiness status can change when inputs, evidence, configuration, or external
  constraints change.

The framework should be revised when application evidence shows that criteria,
decision rules, tailoring, or stop triggers are insufficient or
disproportionate.
