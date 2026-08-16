# MBSA Lab — Engineering Governance

**Document:** `docs/03_Engineering_Governance.md`  
**User Story:** US005 — Engineering Governance  
**Version:** v0.1  
**Status:** Working — validation pending  
**Repository:** `MBSA-Lab-OS`  
**Sprint:** Sprint 1 — Documentary Foundation  

---

## 1. Purpose

This document defines the engineering governance framework for MBSA Lab.

Its purpose is to establish the principles and decision rules used to design,
build, verify, validate, document and publish engineering artefacts within
MBSA Lab.

Engineering governance exists to ensure that MBSA Lab remains:

- technically coherent;
- practical;
- reproducible;
- traceable;
- progressively developed;
- transparent about assumptions and evidence;
- independent from unnecessary tool lock-in;
- suitable for public engineering learning;
- protected against disclosure of confidential information.

This document governs engineering decisions and engineering evidence.

Detailed Git branch, commit, versioning and release mechanisms are defined
separately under **US006 — Git Workflow & Versioning**.

---

## 2. Scope

This governance applies to engineering artefacts produced within
`MBSA-Lab-OS`, including where applicable:

- system definitions;
- requirements;
- architectures;
- MBSE models;
- MBSA analyses;
- safety concepts;
- safety requirements;
- design decisions;
- implementations;
- tests;
- verification results;
- validation results;
- POCs;
- reusable patterns;
- engineering documentation;
- technical examples;
- public educational artefacts derived from engineering work.

It also establishes the interface between engineering work and publication.

It does not define:

- the detailed Git branching strategy;
- commit message conventions;
- version numbering mechanics;
- release mechanics;
- GitHub Issue templates;
- Pull Request templates.

Those subjects belong to later Sprint 1 User Stories.

---

## 3. Governance Principles

### 3.1 Practicality

Engineering work must solve a concrete problem or demonstrate a concrete
engineering concept.

A solution should not be made unnecessarily complex when a simpler solution
can demonstrate the intended concept adequately.

**Decision implication:** prefer the smallest technically credible solution
that provides sufficient evidence for the objective.

### 3.2 Simplicity

Complexity must be justified by an engineering need.

MBSA Lab should start with simple systems and progressively increase
complexity.

**Decision implication:** do not introduce architecture, tooling or analysis
complexity merely because it is available.

### 3.3 Engineering Rigor

Engineering claims must be supported by explicit reasoning and evidence.

Where relevant, distinguish:

- requirement;
- assumption;
- definition;
- design decision;
- calculation/result;
- test;
- verification;
- validation.

**Decision implication:** a statement presented as an engineering conclusion
must be supported by an appropriate artefact or evidence.

### 3.4 Reproducibility

A technically significant result should be reproducible from the published
artefacts to a reasonable extent.

Relevant inputs, assumptions, configuration, implementation and validation
evidence should be documented.

**Decision implication:** avoid undocumented manual steps when they materially
affect the result.

### 3.5 Incremental Development

MBSA Lab evolves through small validated increments.

A subsystem is not considered complete merely because its directory exists.
Its maturity must be demonstrated through documented purpose, implementation
where applicable, examples, validation where applicable, version information,
traceability and a known next extension.

**Decision implication:** deliver a small validated increment before expanding
scope.

### 3.6 Transparency

Limitations, assumptions, incomplete areas and deferred work must be made
explicit.

**Decision implication:** do not present a POC as an industrially complete
solution when it is only a concept demonstration.

### 3.7 Open Learning

Engineering artefacts should be understandable enough to support learning,
without removing the engineering rigor required for credible results.

**Decision implication:** explain the problem, system, concept, theory,
implementation and validation rather than publishing isolated results.

### 3.8 Industrial Relevance

Examples should reflect realistic engineering problems and system concerns.

The first POC is intentionally simple, but it must preserve a credible
engineering structure.

**Decision implication:** simplicity of implementation must not eliminate the
engineering reasoning that makes the example useful.

### 3.9 Tool Independence

Tools are selected because they support the engineering workflow, not
because they are fashionable or because the method is intrinsically tied to
one commercial product.

**Decision implication:** distinguish the engineering method from the tool
used to demonstrate it.

### 3.10 Long-Term Product Thinking

Reusable patterns, methods and tooling are strategic assets.

Engineering work should be structured so that useful elements can later
become:

- reusable patterns;
- POC templates;
- Academy material;
- tooling requirements;
- Safety DSL concepts;
- MBSA Plugin capabilities.

**Decision implication:** avoid one-off solutions when a reusable abstraction
can be created without disproportionate effort.

---

## 4. Engineering Decision Rules

### 4.1 Rule DR-01 — Define the Problem Before the Solution

Before selecting an architecture, model, tool or implementation, define:

- the engineering problem;
- the system or context;
- the intended outcome;
- the scope;
- the relevant constraints.

A solution must not be justified solely by tool availability.

### 4.2 Rule DR-02 — State Assumptions Explicitly

Assumptions that materially affect an engineering conclusion must be
documented.

Examples include:

- system boundaries;
- operating conditions;
- environmental assumptions;
- simplified component behaviour;
- unavailable data;
- modelling abstractions;
- validation limitations.

### 4.3 Rule DR-03 — Separate Facts, Assumptions and Inferences

Engineering documentation must distinguish:

- observed or established facts;
- assumptions introduced by the model;
- derived results;
- engineering interpretations or inferences.

This prevents an assumption from being presented as a validated fact.

### 4.4 Rule DR-04 — Consider Alternatives

For significant architectural or engineering decisions, identify the
reasonable alternatives considered.

The decision record should explain why the selected solution is appropriate.

For small decisions, lightweight justification is sufficient.

### 4.5 Rule DR-05 — Record Decision Rationale

A significant decision should answer:

1. What problem does the decision solve?
2. What alternatives were considered?
3. Why was the selected option chosen?
4. What trade-offs were accepted?
5. What evidence supports the decision?
6. What limitations remain?

### 4.6 Rule DR-06 — Prefer Evidence Over Claims

A major engineering claim should be supported by one or more appropriate
artefacts:

- model;
- architecture;
- calculation;
- implementation;
- test;
- verification result;
- validation result;
- reproducible demonstration;
- documented engineering rationale.

### 4.7 Rule DR-07 — Use Progressive Traceability

Traceability must be developed progressively according to the maturity and
complexity of the engineering work.

The target MBSA Lab traceability chain is:

```text
Problem
  ↓
Stakeholder Need
  ↓
Requirement
  ↓
Function
  ↓
Architecture
  ↓
Safety Concept
  ↓
Safety Requirement
  ↓
Design Element
  ↓
Implementation
  ↓
Test
  ↓
Verification
  ↓
Validation
  ↓
Evidence
  ↓
Documentation
  ↓
Video
```

The first POC does not need maximum traceability complexity, but it must
demonstrate the principle.

### 4.8 Rule DR-08 — Verify Before Declaring Success

A result must not be declared verified without a defined verification
activity and evidence.

Verification asks whether the implementation or artefact satisfies its
specified criteria.

### 4.9 Rule DR-09 — Validate Against Intended Behaviour

Validation must establish whether the demonstrated result is appropriate for
the intended use, objective or system behaviour.

Verification and validation must not be treated as interchangeable terms.

### 4.10 Rule DR-10 — Make Limitations Explicit

If an engineering activity cannot establish a conclusion because of missing
data, simplified assumptions or scope limitations, the limitation must be
recorded.

An absence of evidence must not be represented as evidence of correctness.

### 4.11 Rule DR-11 — Prefer the Smallest Credible Demonstration

When several implementation approaches can demonstrate the same engineering
concept, prefer the smallest approach that:

- preserves the engineering reasoning;
- can be implemented;
- can be verified;
- can be validated;
- can be documented;
- can be reproduced.

### 4.12 Rule DR-12 — Preserve Reusability

Where practical, significant engineering work should produce artefacts that
can be reused in later POCs, patterns, Academy material or tooling.

---

## 5. Engineering Evidence Rules

MBSA Lab follows an evidence-first approach.

The preferred evidence progression is:

```text
Claim
 ↓
Engineering artefact
 ↓
Verification
 ↓
Validation
 ↓
Documented evidence
```

Evidence must be proportional to the claim.

A conceptual claim may require a model and rationale.

An implementation claim should normally require executable or inspectable
implementation evidence.

A behavioural claim should normally require a test or demonstration.

A safety-related claim requires explicit safety reasoning and appropriate
verification/validation evidence for the scope being claimed.

### Evidence classification

Engineering artefacts should be understood as one or more of:

| Evidence type | Purpose |
|---|---|
| Requirement | Defines what is expected |
| Model | Represents system/behaviour/architecture |
| Analysis | Provides engineering reasoning |
| Implementation | Demonstrates realization |
| Test | Exercises defined behaviour |
| Verification | Demonstrates conformity to specified criteria |
| Validation | Demonstrates suitability for intended objective |
| Documentation | Makes reasoning and evidence understandable |
| Video | Communicates the engineering result |

---

## 6. Traceability Rules

Traceability is required where it materially improves engineering confidence,
understanding or reuse.

The minimum useful traceability for a POC should normally connect:

```text
Problem
  ↓
Requirement / Engineering objective
  ↓
Architecture / Model
  ↓
Safety concept or mechanism
  ↓
Implementation
  ↓
Test
  ↓
Verification
  ↓
Validation
  ↓
Evidence
```

Traceability should be:

- explicit where feasible;
- consistent;
- maintained when relevant artefacts change;
- understandable by another engineer.

Traceability must not become documentation overhead without engineering
value.

---

## 7. Verification and Validation Rules

### 7.1 Verification

Verification checks whether an artefact or implementation meets defined
requirements or acceptance criteria.

Examples:

- requirement-to-design consistency;
- model consistency;
- implementation behaviour against a defined test;
- expected state transition;
- expected safety mechanism activation.

### 7.2 Validation

Validation checks whether the demonstrated solution is appropriate for its
intended objective or use.

For MBSA Lab POCs, validation should explicitly state:

- what is being validated;
- under which assumptions;
- using which scenario;
- what constitutes an acceptable result;
- what the validation does not establish.

### 7.3 Quality Gates

MBSA Lab adopts the following project-level quality gates:

**Gate 1 — Concept**  
Can a beginner understand the problem?

**Gate 2 — Engineering**  
Is the system definition technically coherent?

**Gate 3 — MBSE**  
Is the model consistent with the system?

**Gate 4 — MBSA**  
Is the safety reasoning explicit?

**Gate 5 — Implementation**  
Can the result be demonstrated?

**Gate 6 — Validation**  
Is there evidence that the intended behaviour works?

**Gate 7 — Communication**  
Can the concept be explained in a short video?

**Gate 8 — Reuse**  
Can the result become a reusable pattern?

A gate may be explicitly marked not applicable where justified.

---

## 8. Change Governance

Engineering changes should be controlled according to their impact.

### 8.1 Minor change

A minor change does not materially alter:

- architecture;
- engineering conclusion;
- safety reasoning;
- public meaning;
- traceability.

It may be implemented directly with appropriate documentation.

### 8.2 Significant change

A significant change materially affects an engineering artefact or
conclusion.

It should document:

- reason for change;
- affected artefacts;
- impact;
- validation required;
- resulting decision.

### 8.3 Change principle

When a change invalidates an existing engineering conclusion, the conclusion
must be re-evaluated rather than silently retained.

### 8.4 Historical traceability

Previous validated states should remain recoverable through the project's
version-control history.

Detailed branch, commit and release mechanics are intentionally delegated
to US006.

---

## 9. Publication and Confidentiality Rules

MBSA Lab is a public engineering reference, but public visibility must not
override confidentiality.

### 9.1 Public by default only when deliberately curated

An artefact may be published when it is:

- technically appropriate for public release;
- free of confidential information;
- free of private personal information;
- free of secrets or credentials;
- appropriately abstracted or anonymized where necessary.

### 9.2 Confidential material

The following must not be published in `MBSA-Lab-OS`:

- industrial confidential information;
- customer confidential information;
- private contacts;
- credentials or secrets;
- private CV variants;
- unreleased commercial plans;
- private project-control information.

Private control material belongs in `MBSA-Lab-Control`.

### 9.3 Industrial examples

Industrial relevance should be preserved without exposing proprietary
information.

Where necessary:

```text
Real industrial context
        ↓
Abstraction / anonymization
        ↓
Generic engineering case
        ↓
Public MBSA Lab artefact
```

### 9.4 Publication decision

Before publication, verify:

1. Is the technical content correct for its stated scope?
2. Are assumptions and limitations explicit?
3. Is the evidence sufficient for the claim?
4. Is confidential information excluded?
5. Is the artefact understandable and reproducible enough for its intended
   audience?
6. Is the relationship to the source engineering work clear?

---

## 10. Governance Boundaries

US005 defines engineering governance.

The following boundaries apply:

| Subject | Owner |
|---|---|
| Engineering principles | US005 |
| Engineering decision rules | US005 |
| Evidence principles | US005 |
| Traceability principles | US005 |
| Verification / validation principles | US005 |
| Change governance principles | US005 |
| Publication / confidentiality principles | US005 |
| Git branch strategy | US006 |
| Commit convention | US006 |
| Versioning | US006 |
| Release rules | US006 |
| GitHub Issue templates | US007 |
| Pull Request template / review rules | US008 |
| Repository/documentation conventions | US009 |
| Sprint closure / final baseline | US010 |

This boundary prevents duplication between Sprint 1 User Stories.

---

## 11. Relationship with MBSA Lab Engineering Workflow

The governance framework supports the MBSA Lab master pattern:

```text
Industrial Problem
        ↓
System
        ↓
Concept
        ↓
Definition
        ↓
Theory
        ↓
MBSE
        ↓
MBSA
        ↓
Implementation
        ↓
Validation
        ↓
Conclusion
        ↓
GitHub
        ↓
Video
        ↓
LinkedIn
        ↓
PDF / reusable learning artefact
```

It also supports the V-cycle used as the engineering and learning backbone:

```text
Stakeholder / Operational Need
        ↓
System Requirements
        ↓
Functional Architecture
        ↓
Logical / Technical Architecture
        ↓
Implementation
        ↓
Unit / Component Verification
        ↓
Integration Verification
        ↓
System Verification
        ↓
Validation
```

Governance therefore acts as the control layer connecting engineering work,
evidence and publication.

---

## 12. Relationship with Git Workflow

Git is the mechanism used to preserve engineering history, but Git workflow
is not itself the engineering governance framework.

US006 will define:

- branch strategy;
- commit convention;
- versioning;
- release rules.

US005 only requires that significant engineering changes remain traceable
and that validated states remain recoverable.

---

## 13. Governance Compliance Checklist

Before an engineering artefact is considered governed, check the following:

### Scope
- [ ] Problem or objective is defined.
- [ ] System/context is defined.
- [ ] Scope and boundaries are explicit.

### Engineering reasoning
- [ ] Assumptions are documented.
- [ ] Facts and inferences are distinguished.
- [ ] Relevant alternatives were considered.
- [ ] Decision rationale is documented for significant decisions.
- [ ] Trade-offs are known.

### Evidence
- [ ] Relevant engineering artefacts exist.
- [ ] Verification criteria are defined where applicable.
- [ ] Verification evidence exists where applicable.
- [ ] Validation criteria are defined where applicable.
- [ ] Validation evidence exists where applicable.
- [ ] Limitations are explicit.

### Traceability
- [ ] Relevant links between requirements, architecture, implementation and
      verification/validation are available.
- [ ] Traceability is proportional to complexity.

### Publication
- [ ] Confidential information is excluded.
- [ ] Secrets and private information are excluded.
- [ ] Public scope is clear.
- [ ] Reproducibility is sufficient for the intended claim.

### Reuse
- [ ] Reusable elements have been identified where appropriate.
- [ ] Next extension is known.

