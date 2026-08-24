# MBSA Lab — Engineering Governance

## 1. Purpose

This document defines the public engineering-governance principles used by MBSA Lab. It establishes how problems, evidence, decisions, changes, and publications are handled across the project.

Governance provides decision structure. It does not replace engineering judgment, safety authority, verification, validation, or legal obligations.

## 2. Scope

This governance applies to public engineering artefacts, including requirements, architecture, POCs, tests, evidence packages, patterns, tools, and communication releases.

Private administration may use additional controls, but those controls do not redefine the public engineering model unless deliberately incorporated into the public baseline.

## 3. Governance principles

### 3.1 Practicality

Engineering effort should be proportional to the decision, risk, complexity, and maturity involved.

### 3.2 Simplicity

Use the smallest process and artefact set that can still produce credible, reviewable evidence.

### 3.3 Engineering rigor

Important assumptions, interfaces, criteria, results, and limitations must be explicit.

### 3.4 Reproducibility

Another competent reviewer should be able to understand the configuration, method, inputs, and results sufficiently to assess or repeat the work.

### 3.5 Incremental development

Capabilities evolve through bounded increments and controlled baselines. Planned maturity must not be reported as achieved maturity.

### 3.6 Transparency

Negative findings, failed criteria, uncertainty, and residual risk remain visible.

### 3.7 Tool independence

Governance objectives are defined independently of a specific modelling, coding, test, or publication tool.

### 3.8 Public by deliberate curation

Material is public only after its engineering value, confidentiality, rights, and publication suitability have been reviewed.

## 4. Engineering decision rules

### DR-01 — Define the problem before the solution

State the need, context, stakeholders, intended use, boundary, and exclusions before selecting an implementation.

### DR-02 — State assumptions explicitly

Assumptions must be identifiable, testable where possible, and revisited when evidence changes.

### DR-03 — Separate facts, assumptions, inferences, claims, and decisions

These categories must not be presented as interchangeable.

### DR-04 — Consider alternatives

Material decisions should identify credible alternatives and the criteria used to compare them.

### DR-05 — Record rationale

A decision record should explain what was decided, by whom, on which evidence, within which scope, and with which limitations.

### DR-06 — Prefer evidence over assertion

The strength of a claim cannot exceed the strength and relevance of its evidence.

### DR-07 — Use proportional traceability

Traceability depth depends on risk and decision importance, but critical claims must not become disconnected from requirements, evidence, findings, or authority.

### DR-08 — Verify before declaring completion

Artefact presence is not proof of correctness. Completion requires objective checks against explicit criteria.

### DR-09 — Validate against intended use

Conformance to a specification does not by itself prove stakeholder suitability.

### DR-10 — Make limitations explicit

Known limitations, unresolved findings, environmental constraints, and excluded behaviours remain attached to the result.

### DR-11 — Prefer the smallest credible demonstration

Reduce unnecessary scope while preserving enough fidelity to answer the engineering question.

### DR-12 — Preserve reuse conditions

Reusable material retains applicability, dependencies, configuration, evidence, and limitations.

## 5. Engineering evidence

Evidence is an identifiable artefact or observation used to support or challenge a claim. Evidence may include:

- reviewed requirements or architecture;
- configuration records;
- test procedures and results;
- analysis outputs;
- logs, measurements, or generated reports;
- review findings and decisions.

Evidence must have sufficient identity, provenance, integrity, and context for its intended use. Communication material is not a substitute for source evidence.

## 6. Traceability

Traceability should connect, where applicable:

- stakeholder needs to requirements;
- requirements to architecture and implementation;
- risks and safety concerns to controls;
- verification and validation criteria to results;
- results to claims and findings;
- claims and findings to decisions;
- public releases to their approved sources.

Trace links express a relationship, not proof of adequacy. Their semantic meaning must be clear.

## 7. Verification, validation, and quality gates

Verification, validation, evidence review, and publication review are separate concerns.

MBSA Lab uses the integrated quality-gate model defined in [Integrated Quality Gates Model](13_Integrated_Quality_Gates_Model.md). That model is the authoritative public definition of gate families, objectives, outcomes, tailoring, and decision authority.

Legacy or project-specific checkpoint names must not create a competing public gate taxonomy.

## 8. Change governance

Changes are classified by their impact on meaning, interfaces, evidence, risk, and released claims.

- Minor changes preserve behaviour and engineering meaning.
- Significant changes affect requirements, architecture, interfaces, evidence, limitations, or decisions.
- Corrective changes repair an identified defect and retain traceability to the superseded state.

Released artefacts must not be silently overwritten. Correction, supersession, withdrawal, retention, and reopening require explicit disposition.

## 9. Publication and confidentiality

Before public release, material is reviewed for:

- engineering coherence and bounded claims;
- absence of confidential, personal, contractual, or security-sensitive data;
- intellectual-property, licence, consent, and attribution obligations;
- separation from private administration and development orchestration;
- suitability for the intended audience.

Generic engineering terms are not private by themselves. Confidentiality review is semantic and contextual.

When a real industrial example cannot be published, an explicitly identified public surrogate may be used. The surrogate must not imply equivalence beyond what is demonstrated.

## 10. Governance boundaries

The following authorities remain distinct even when one person performs several roles:

- engineering authority;
- safety or assurance authority;
- verification and validation authority;
- evidence and traceability authority;
- publication authority;
- configuration and change authority.

Separation of concerns prevents a technical PASS from being interpreted automatically as acceptance, reuse approval, or publication authorization.

## 11. Compliance checklist

Before an engineering result is accepted or released, confirm that:

- the problem, scope, and exclusions are explicit;
- assumptions and alternatives are recorded;
- requirements, architecture, and configuration are identifiable;
- verification and validation criteria are distinct;
- evidence supports the stated claims;
- findings, limitations, and residual risks are visible;
- traceability is sufficient for the decision;
- change and version identity are controlled;
- confidentiality and rights have been reviewed;
- the competent authority has made the relevant decision.

## 12. Limitations

This governance is a minimal public framework. It does not replace applicable organisational processes, standards, regulation, certification schemes, contractual obligations, or independent assurance.
