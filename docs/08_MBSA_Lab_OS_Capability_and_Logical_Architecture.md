# MBSA Lab OS — Capability and Logical Architecture

## 1. Purpose

This document defines the stable public capability model, logical components, interfaces, dependencies, and end-to-end flows of MBSA Lab OS.

The architecture allocates responsibility without prescribing a specific tool, deployment, or implementation technology.

## 2. Scope and modelling rules

The document covers:

- ten capabilities identified as `CAP-01` through `CAP-10`;
- seven logical components identified as `LC-01` through `LC-07`;
- ten logical interfaces identified as `IF-01` through `IF-10`;
- seven end-to-end flows identified as `FL-01` through `FL-07`;
- maturity, ownership, trust, and dependency rules.

A capability describes an ability and outcome. A logical component groups responsibilities. An interface describes an exchange contract. A flow describes an ordered value or information path. None of these proves physical implementation.

## 3. Architecture principles

- AP-01 — Preserve the system context and public/private boundary.
- AP-02 — Evidence precedes maturity claims.
- AP-03 — Governance constrains every capability.
- AP-04 — Traceability is proportional but mandatory for material claims.
- AP-05 — Public/private separation is invariant.
- AP-06 — Logical architecture remains technology-independent.
- AP-07 — Reuse follows verified applicability and admission.
- AP-08 — Publication follows stable sources and explicit authority.
- AP-09 — Capability realization is progressive.
- AP-10 — Architecture remains independent of one POC candidate.

## 4. Maturity vocabulary

| Level | Meaning |
| --- | --- |
| `STRATEGIC ONLY` | Intent and boundary exist; operating model is not established |
| `PARTIAL` | Some authoritative structure or repeatable behaviour exists; capability is incomplete |
| `BASELINED` | A reviewed public definition is established for the stated scope |
| `OPERATIONAL` | Repeated execution with controlled evidence is demonstrated |

Maturity applies to a bounded capability claim, not automatically to the whole project.

## 5. Capability catalogue

| ID | Capability | Outcome | Boundary | Current maturity |
| --- | --- | --- | --- | --- |
| CAP-01 | Strategic Direction and Control | Convert approved intent into governed public direction | Shared | PARTIAL |
| CAP-02 | Governance and Change Control | Control decisions, changes, authorities, and baselines | Inside | BASELINED |
| CAP-03 | Engineering Lifecycle Enablement | Structure coherent engineering work | Inside | PARTIAL |
| CAP-04 | Evidence, Assurance, and Traceability | Connect claims, evidence, findings, limitations, and decisions | Inside | PARTIAL |
| CAP-05 | POC Production Enablement | Govern candidate readiness and the POC lifecycle | Inside | PARTIAL |
| CAP-06 | Knowledge and Pattern Reuse | Assess and admit reusable engineering knowledge | Inside | PARTIAL |
| CAP-07 | Publication and Visibility Governance | Authorize bounded public releases | Inside/shared | PARTIAL |
| CAP-08 | Contribution and Feedback Integration | Convert external input into controlled change | Boundary | PARTIAL |
| CAP-09 | Learning Interface Enablement | Supply stable assets to learning capabilities | Future interface | STRATEGIC ONLY |
| CAP-10 | Tooling Evolution Enablement | Derive tools from recurring demonstrated needs | Future interface | STRATEGIC ONLY |

CAP-05 is `PARTIAL` because lifecycle and readiness models exist, but no first POC has been selected, authorized, executed, or accepted.

## 6. Logical component catalogue

| ID | Logical component | Primary responsibility |
| --- | --- | --- |
| LC-01 | Strategic Control Bridge | Classify and mediate approved direction across the public/private boundary |
| LC-02 | Governance Core | Own rules, authority, decisions, change, and baseline control |
| LC-03 | Engineering Framework Core | Structure problems, needs, requirements, architecture, safety, implementation, and V&V |
| LC-04 | Evidence and Traceability Core | Maintain identities, trace relationships, evidence, claims, findings, and limitations |
| LC-05 | POC Factory Logic | Govern readiness, lifecycle execution, configuration, and closure of POCs |
| LC-06 | Pattern and Reuse Core | Assess pattern candidates and control admission, reuse, and withdrawal |
| LC-07 | Publication Governance Gateway | Separate technical, evidence, confidentiality, rights, and release decisions |

Logical components may be realized by documents, roles, services, tools, or combinations of these. The model does not impose physical centralization.

## 7. Capability-to-component allocation

`A` means accountable logical owner; `C` means contributor.

| Capability | LC-01 | LC-02 | LC-03 | LC-04 | LC-05 | LC-06 | LC-07 |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| CAP-01 | A | C |  | C |  |  |  |
| CAP-02 |  | A |  | C |  |  |  |
| CAP-03 |  | C | A | C |  |  |  |
| CAP-04 |  | C | C | A | C | C | C |
| CAP-05 |  | C | C | C | A |  |  |
| CAP-06 |  | C | C | C | C | A |  |
| CAP-07 |  | C |  | C |  | C | A |
| CAP-08 |  | A | C | C |  |  | C |
| CAP-09 |  | C |  | C |  | C | A |
| CAP-10 |  | C | A | C |  | C |  |

## 8. Logical interfaces

| ID | Interface | Participants | Principal content |
| --- | --- | --- | --- |
| IF-01 | Strategic Direction Exchange | LC-01 and external strategic authority | Approved direction and public evidence feedback |
| IF-02 | Governance Decision and Baseline | LC-02 and governed components | Scope, decisions, conditions, authority, and accepted configuration |
| IF-03 | Engineering Work-Product Exchange | LC-03 with LC-04, LC-05, and LC-06 | Needs, requirements, architecture, implementation, and V&V inputs |
| IF-04 | Evidence and Trace-Link Exchange | LC-04 and evidence producers/consumers | Evidence identity, trace links, claims, findings, and limitations |
| IF-05 | Contribution and Review | LC-02/LC-03 with contributors | Proposals, changes, findings, and dispositions |
| IF-06 | Publication Release | LC-07 and external channels | Authorized release package and publication state |
| IF-07 | Video Production Handoff | LC-07 and Video Factory | Approved sources, release requirements, and feedback |
| IF-08 | Learning Asset Handoff | LC-06/LC-07 and future Academy | Stable learning assets and source traceability |
| IF-09 | Tooling Need and Result Exchange | LC-03/LC-06 and future tools | Governed needs, experiments, results, and evidence |
| IF-10 | Feedback and Controlled Change | Audiences with LC-02/LC-03 | Questions, defects, feedback, and decisions |

## 9. Artefact ownership

| Artefact family | Logical owner | Governing condition |
| --- | --- | --- |
| Approved public direction | LC-01 | Classified and governed |
| Governance rules and decisions | LC-02 | Authority and change identity retained |
| Engineering work products | LC-03 | Accepted scope and configuration visible |
| Evidence and trace links | LC-04 | Provenance, integrity, and limitations retained |
| POC packages | LC-05 | Lifecycle state and authority explicit |
| Pattern candidates and admitted patterns | LC-06 | Candidate and admitted states remain distinct |
| Publication readiness and releases | LC-07 | Technical PASS does not imply publication |

Private strategic and administrative records remain outside the public architecture repository.

## 10. Logical dependency model

- LC-01 depends on LC-02 to govern public direction.
- LC-02 depends on LC-04 for evidence-based decisions.
- LC-03 depends on LC-02 and LC-04 for controlled scope and evidence.
- LC-05 depends on LC-03 and LC-04 for POC engineering and acceptance.
- LC-06 depends on LC-04 and LC-05 for evidence-backed reuse.
- LC-07 depends on LC-02 and LC-04 for authorization and supported claims.

Dependency expresses required responsibility, not implementation sequence.

## 11. End-to-end logical flows

### FL-01 — Strategic direction to public baseline

Approved direction → classification → governance decision → evidence record → public baseline.

### FL-02 — Engineering problem to verified evidence

Governed problem → needs → requirements → architecture → safety and implementation → V&V → evidence → acceptance decision.

### FL-03 — Verified evidence to reusable pattern

Evidence → recurring structure → pattern candidate → applicability review → admission decision → controlled pattern.

### FL-04 — Stable artefact to authorized publication

Stable source → technical review → evidence review → confidentiality and rights review → publication decision → external release.

### FL-05 — Stable asset to video or learning capability

Approved source → release or learning package → external production → quality review → controlled feedback.

### FL-06 — Proven need to tooling requirement

Recurring limitation → evidence of value → governed requirement → experiment → result and evidence feedback.

### FL-07 — Contribution or feedback to controlled change

Input → classification → impact assessment → decision → controlled change or rejection → verification → feedback.

## 12. Public/private trust points

Trust decisions occur at:

- LC-01 when direction crosses the strategic boundary;
- LC-02 when scope, authority, or baseline is accepted;
- LC-04 when evidence supports a public claim;
- LC-07 when a release crosses to an external channel.

Prohibited crossings include private records copied without public value, unclassified evidence, unsupported claims, credentials, personal data, and material without suitable rights.

## 13. POC independence

Emergency Stop Button is the provisional reference candidate only. Door Interlock Safety System and Overtemperature Protection System remain alternatives. No candidate is finally selected or authorized to start.

CAP, LC, IF, and FL definitions must remain applicable to all three conceptual candidates.

## 14. Risks and limitations

| Risk | Architectural control |
| --- | --- |
| Capability confused with implementation | Maintain explicit maturity and evidence |
| Component interpreted as one physical service | Preserve logical allocation |
| Private data crosses a public interface | Enforce trust-point classification |
| POC success treated as pattern admission | Keep LC-05 and LC-06 decisions separate |
| Technical PASS treated as publication | Keep LC-07 authority separate |
| Tooling defines the architecture | Derive tools through IF-09 from governed needs |

This document does not define deployment, select tools, authorize POC work, or demonstrate operational maturity.
