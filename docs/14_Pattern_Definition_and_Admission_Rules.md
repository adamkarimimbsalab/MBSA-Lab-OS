# MBSA Lab OS — Pattern Definition and Admission Rules

## 1. Purpose

This document defines what constitutes a reusable engineering Pattern and the controlled process by which a Pattern candidate may be admitted, conditioned, rejected, superseded, deprecated or retired.

A Pattern captures reusable engineering knowledge. It is neither a copied project artefact nor a claim that one successful POC is universally applicable.

## 2. Core concepts

- **Pattern candidate** — a proposed reusable solution not yet admitted.
- **Pattern** — an admitted, configured and governed reusable asset.
- **Applicability assessment** — analysis of contexts in which reuse is valid, conditional or invalid.
- **Adaptation** — controlled modification required for a target context.
- **Pattern instance** — application of a Pattern to a specific system and configuration.
- **Admission decision** — authorized determination of reuse status.

POC success, Pattern candidacy, admission and use in a target system are separate events.

## 3. Identification and configuration

Each candidate and admitted Pattern has a stable `pattern_id`, title, version, state, owner, source, configuration, applicability boundary, tailoring class, Evidence Package reference, classification and supersession information.

A changed applicability boundary, safety assumption, interface contract or mandatory control requires impact assessment and normally a new version. An admitted version is not silently overwritten.

## 4. Minimum Pattern contract

An admitted Pattern shall define:

1. intent and problem addressed;
2. context and applicability boundary;
3. forces, constraints and assumptions;
4. solution structure and responsibilities;
5. interfaces and dependencies;
6. safety and assurance considerations;
7. required controls and verification obligations;
8. known variants and permitted adaptations;
9. evidence, claims, findings and limitations;
10. misuse cases and non-applicable contexts;
11. implementation and validation guidance;
12. lifecycle, change and retention rules;
13. ownership and decision authority;
14. classification, rights and publication constraints.

## 5. Lifecycle

Recommended states are `PROPOSED`, `CANDIDATE`, `IN_ASSESSMENT`, `ADMITTED`, `ADMITTED_WITH_CONDITIONS`, `REJECTED`, `DEPRECATED`, `SUPERSEDED`, `RETIRED` and `WITHDRAWN`.

Only `ADMITTED` and, within explicit conditions, `ADMITTED_WITH_CONDITIONS` are available for governed reuse. `DEPRECATED` discourages new use while preserving existing traceability. `RETIRED` ends normal availability; `WITHDRAWN` records that the asset should no longer be relied upon.

## 6. Admission process

Admission proceeds through proposal, identity and scope definition, source assessment, applicability analysis, evidence assembly, independent or proportionate review, finding disposition, authorized decision, publication-boundary review and controlled release.

The process may iterate. Iteration does not erase prior findings, evidence or decisions.

## 7. Admission obligations

| ID | Obligation |
|---|---|
| PAO-01 | Stable identity, version and owner exist. |
| PAO-02 | Problem, intent and public value are clear. |
| PAO-03 | Applicability and non-applicability boundaries are explicit. |
| PAO-04 | Assumptions, dependencies and environmental constraints are identified. |
| PAO-05 | Architecture, interfaces and required controls are coherent. |
| PAO-06 | Safety and assurance implications are assessed. |
| PAO-07 | Verification and validation obligations are defined. |
| PAO-08 | Evidence supports the stated claims for identified configurations. |
| PAO-09 | Findings, negative results, waivers and limitations remain visible. |
| PAO-10 | Variants and permitted adaptation rules are bounded. |
| PAO-11 | Misuse, failure modes and stop conditions are addressed. |
| PAO-12 | Change, supersession, deprecation, retirement and retention are controlled. |
| PAO-13 | Classification, rights, consent and publication constraints are satisfied. |
| PAO-14 | Authorized admission and reuse decisions are recorded. |

No numerical score may compensate for a failed Critical obligation.

## 8. Gate mapping and decisions

Pattern readiness is reviewed through the integrated engineering, evidence, classification and publication Gates. GATE-ENG-09 addresses reuse readiness; Pattern disposition remains an explicit authority decision.

Permitted admission decisions include `ADMIT`, `ADMIT_WITH_CONDITIONS`, `APPLY_WITH_ADAPTATION`, `DEFER`, `REJECT`, `DEPRECATE`, `SUPERSEDE`, `RETIRE` and `WITHDRAW`.

`APPLY_WITH_ADAPTATION` authorizes only the bounded target-context adaptation described in the decision. It does not alter the source Pattern or waive target-system verification.

## 9. Evidence and Claim rules

Claims are no broader than their supporting evidence and applicable configurations. Evidence Package identity, provenance, actual results, findings and limitations remain linked to the candidate and admitted Pattern.

Communication material, demonstrations and summaries may explain a Pattern but do not replace engineering sources, V&V results, Evidence Packages or admission decisions.

## 10. Findings, waivers and limitations

Findings are classified, assigned and disposed under authority. Open Critical findings prevent admission. Conditional admission requires bounded conditions, owners, verification methods, due events and stop triggers.

Waivers identify risk and compensating controls and expire or reopen under defined conditions. Limitations travel with the Pattern and every public or target-specific view.

## 11. Reuse applicability

Each intended reuse evaluates target context, needs, architecture, interfaces, environment, hazards, controls, configuration, evidence relevance and organizational authority. Applicability results are `APPLICABLE`, `APPLICABLE_WITH_ADAPTATION`, `NOT_APPLICABLE` or `INCONCLUSIVE`.

An applicability assessment is evidence for a reuse decision, not a substitute for that decision. Target-system verification and validation remain necessary.

## 12. Change and reopening

Changes to sources, requirements, interfaces, assumptions, controls, evidence, rights or target environments trigger impact assessment. Material impact may reopen admission, restrict applicability, require a new version or withdraw the Pattern.

Supersession identifies replacement versions and migration guidance. Deprecation states why new use is discouraged. Retirement and withdrawal preserve history, affected instances and notification obligations.

## 13. Classification, rights and publication

Admission and public release are separate. Rights, licences, consent, restricted information and third-party obligations are assessed before publication. A public Pattern may use a controlled surrogate where necessary, but the surrogate states its abstraction and applicability limits.

Private development administration is not part of the public Pattern contract. Public engineering concepts, evidence boundaries and decision semantics remain visible where useful.

## 14. Tailoring

- **T1** permits a compact candidate package and combined roles for low-complexity reuse.
- **T2** requires structured applicability, evidence and review records.
- **T3** adds stronger independence, assurance, integrity and lifecycle controls.

Tailoring shall not remove stable identity, applicability boundaries, Critical obligations, evidence provenance, limitations, authority or controlled change.

## 15. Required views and companion template

Required views include Pattern summary, applicability matrix, assumptions and dependencies, architecture and interfaces, evidence-and-claim matrix, findings and limitations, variants and adaptations, lifecycle history and reuse decisions.

A companion template may guide authors, but conformance is semantic. Empty headings, copied boilerplate or an unchecked form do not satisfy the contract.

## 16. Conceptual POC application

An Emergency Stop Button may serve as the provisional reference candidate. Door Interlock Safety System and Overtemperature Protection System remain alternatives for testing generality.

The three applications are conceptual and non-implementing. They do not establish final POC selection, start authorization, successful execution, Pattern admission or target-system fitness.

## 17. Roles and authority

Candidate owners maintain content. Evidence owners maintain sources and provenance. Applicability assessors evaluate reuse contexts. Reviewers assess obligations. Admission authority issues the decision. Classification and publication authorities control release.

Role combinations are proportionate, but accountability and conflicts remain explicit.

## 18. Maturity and limitations

This document defines the public admission model. It does not claim a populated Pattern library, admitted Pattern inventory, completed POC, certified solution or automated governance implementation. Maturity is demonstrated per Pattern through actual evidence and authorized decisions.
