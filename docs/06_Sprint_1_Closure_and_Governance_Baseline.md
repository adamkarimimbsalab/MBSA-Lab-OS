# MBSA Lab — Foundational Governance Baseline

## 1. Purpose

This document records the public engineering foundation established during the initial repository-development phase. It describes the resulting governance baseline independently of non-public execution and administration records.

## 2. Baseline scope

The foundational baseline includes:

- a public project entry point and overview;
- Vision and Mission;
- Engineering Governance;
- Git Workflow and Versioning;
- repository and documentation conventions;
- issue and pull-request contribution templates.

These artefacts establish how later architecture, POCs, evidence, patterns, and communication material are governed.

## 3. Foundational outcomes

### 3.1 Strategic foundation

The project purpose, target identity, audiences, scope, and limitations are defined publicly.

### 3.2 Engineering governance

Decision rules distinguish facts, assumptions, inferences, claims, evidence, findings, and decisions. Verification, validation, safety, traceability, change, and publication concerns remain explicit.

### 3.3 Configuration governance

The public repository uses controlled branches, coherent commits, reviewed integration, stable baselines, and explicit release identity.

### 3.4 Contribution governance

Issue and pull-request templates provide a consistent public interface for proposing, assessing, and reviewing changes.

### 3.5 Documentation governance

Public documents follow stable structure, naming, encoding, line-ending, traceability, and public/private-separation rules.

## 4. Public artefact set

The foundational artefacts are:

| Artefact | Public purpose |
| --- | --- |
| `README.md` | Repository entry point |
| `docs/00_Project_Overview.md` | Project scope and capability overview |
| `docs/01_Vision.md` | Long-term direction |
| `docs/02_Mission.md` | Recurring engineering mission |
| `docs/03_Engineering_Governance.md` | Engineering decision and evidence rules |
| `docs/04_Git_Workflow_and_Versioning.md` | Controlled change and version policy |
| `docs/05_Repository_and_Documentation_Conventions.md` | Repository and documentation rules |
| `.github/ISSUE_TEMPLATE/` | Structured public work intake |
| `.github/PULL_REQUEST_TEMPLATE.md` | Structured change review |

The table identifies public functions, not historical completion evidence.

## 5. Governance relationships

The foundational documents form one coherent policy set:

1. Vision defines the intended future state.
2. Mission defines the recurring work used to approach that state.
3. Engineering Governance defines decision, evidence, change, and publication principles.
4. Git Workflow defines how accepted public configurations evolve.
5. Repository Conventions define how artefacts are structured and maintained.
6. Contribution templates apply these principles to proposed changes.

Later domain documents refine this foundation and should reference it rather than create competing definitions.

## 6. Baseline acceptance principles

A public governance baseline is credible when:

- its artefacts are present and mutually coherent;
- scope and authority are explicit;
- important terms are used consistently;
- encoding, structure, and repository hygiene are controlled;
- public/private separation is demonstrated;
- limitations and incomplete capabilities remain visible;
- the accepted repository state is identifiable.

Specific Git object identifiers are configuration evidence and may be retained in release records; they are not required in this public conceptual baseline.

## 7. Non-regression rules

### NR-01 — Preserve engineering meaning

Editorial improvement must not silently change an engineering requirement or decision.

### NR-02 — Preserve public/private separation

Public artefacts exclude private administration, internal orchestration, local paths, credentials, personal data, and unpublished records.

### NR-03 — Preserve evidence-based status

Planned, conceptual, implemented, verified, accepted, reusable, and published states remain distinct.

### NR-04 — Preserve repository text policy

Public text remains UTF-8 without BOM, LF, final LF, and free of NUL and trailing whitespace.

### NR-05 — Preserve traceability

Material changes retain sufficient identity, rationale, evidence, and review context.

### NR-06 — Preserve competent authority

Technical verification does not automatically grant safety acceptance, reuse admission, release approval, or publication authorization.

### NR-07 — Avoid silent contradiction

When a later authoritative document refines an earlier concept, cross-references and affected statements are reviewed for coherence.

## 8. Known limitations

The foundational baseline defines governance but does not itself provide:

- a completed production architecture;
- a certified safety lifecycle;
- a validated production implementation;
- an admitted pattern library;
- operational proof for every target capability.

Those claims require their own artefacts, evidence, gates, and authority.

## 9. Evolution rule

The baseline evolves through explicit maintenance or feature changes. Each evolution should:

1. define scope and acceptance criteria;
2. preserve public engineering value;
3. remove or prevent inappropriate public information;
4. verify semantic coherence and text quality;
5. integrate through the controlled Git workflow;
6. establish a new identifiable baseline.

## 10. Baseline decision

The foundational governance set is the public starting point for subsequent MBSA Lab architecture and engineering work. Its role is to constrain and guide later artefacts, not to claim maturity that has not been demonstrated.
