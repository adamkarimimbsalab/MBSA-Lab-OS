# MBSA Lab OS — System Context and Boundaries

## 1. Purpose

This document defines the controlled system context and system boundaries of **MBSA Lab OS** for Sprint 2 — MBSA Lab OS Architecture v0.1.

It establishes, at system-context level:

- what MBSA Lab OS is;
- what belongs within the system of interest;
- what remains outside the system;
- which responsibilities are shared across the boundary;
- which human actors, repositories, platforms, tools and future capabilities interact with the system;
- how public and private responsibilities are separated;
- how Strategic Control is distributed logically across public and private artefacts;
- which high-level information, governance, contribution, validation and publication flows cross the system boundary;
- which assumptions, constraints, dependencies, risks and open decisions govern the context.

This document intentionally stops at the **system-context and boundary level**. It does not define the internal logical architecture in detail. Detailed capability decomposition and logical architecture belong to subsequent Sprint 2 work, including US012.

---

## 2. Scope

### 2.1 In scope

US011 covers:

- the identity of MBSA Lab OS as the system of interest;
- system purpose and delivered value;
- stakeholders and external actors;
- system environment;
- system boundary;
- elements considered inside, outside or shared across the boundary;
- high-level system responsibilities and non-responsibilities;
- the public/private boundary;
- the logical role of Strategic Control;
- the relationship between MBSA Lab OS and MBSA-Lab-Control;
- the position of the Governance Core;
- the contextual position of the Engineering Framework;
- the contextual position of the POC Factory, Pattern Library and Video Factory;
- future interfaces toward Academy, Eclipse Platform, Safety DSL and MBSA Plugin;
- publication and visibility interfaces;
- high-level information and artefact flows;
- assumptions, constraints, dependencies, risks, limitations and open decisions;
- traceability to the Sprint 1 baseline and Sprint 2 acceptance criteria.

### 2.2 Out of scope

US011 does not:

- define detailed internal components;
- define a detailed logical architecture;
- allocate all internal responsibilities;
- design detailed APIs;
- select implementation technologies unless strictly needed to define a boundary;
- implement software;
- implement a POC;
- design the Emergency Stop Button POC;
- design the Door Interlock Safety System;
- design the Overtemperature Protection System;
- create a validated reusable pattern;
- implement the POC Factory;
- implement the Pattern Library;
- implement the Video Factory;
- implement MBSA Academy;
- implement an Eclipse Platform;
- implement a Safety DSL;
- implement an MBSA Plugin;
- create additional repositories without a separately approved need;
- change GitHub visibility;
- modify the private Master Plan;
- expose private project-control information;
- reopen or rewrite the Sprint 1 baseline without a proven anomaly and explicit decision;
- start or implement US012 or later User Stories.

---

## 3. Source Baseline and Authority

### 3.1 Controlled entry baseline

The controlled Sprint 2 entry baseline for US011 is:

- repository: `MBSA-Lab-OS`;
- visibility: `PUBLIC`;
- branch at entry verification: `main`;
- working tree at entry verification: `CLEAN`;
- `HEAD = main = origin/main`;
- baseline SHA:
  `2b9b35c746a0a30bd35ae6b045efed052d07c5ed`;
- associated commit:
  `Merge US010 - Sprint 1 Closure & Governance Baseline`.

### 3.2 Primary authoritative sources

This document is derived from the following controlled sources:

1. `README.md`
2. `docs/00_Project_Overview.md`
3. `docs/01_Vision.md`
4. `docs/02_Mission.md`
5. `docs/03_Engineering_Governance.md`
6. `docs/04_Git_Workflow_and_Versioning.md`
7. `docs/05_Repository_and_Documentation_Conventions.md`
8. `docs/06_Sprint_1_Closure_and_Governance_Baseline.md`
9. the controlled post-Sprint-1 Master Plan rebaseline;
10. the controlled transition/rebaselining Gates;
11. the approved Sprint 2 backlog and US011 launch prompt;
12. the validated operational evidence collected during Sprint 1.

### 3.3 Conflict-handling rule

If two sources appear inconsistent:

1. the inconsistency must be made explicit;
2. historical intent must not silently override a more recent controlled decision;
3. implementation maturity must never be inferred from roadmap intent alone;
4. public/private separation must remain conservative;
5. any conflict affecting scope, governance, baseline or acceptance must be escalated through a controlled decision before implementation.

---

## 4. Terminology

### 4.1 MBSA Lab

**MBSA Lab** is the overall initiative and ecosystem.

It encompasses engineering, education, publication, future tooling, professional visibility and longer-term ecosystem development.

MBSA Lab is broader than MBSA Lab OS.

### 4.2 MBSA Lab OS

**MBSA Lab OS** is the system of interest of US011.

It is the public, living, governed operating foundation that turns MBSA Lab strategy into reproducible engineering structure, governed artefacts, reusable methods, evidence-oriented workflows and progressively implementable capabilities.

MBSA Lab OS is not an operating system in the computer-platform sense.

It is also not a single software product or a single repository folder.

### 4.3 MBSA-Lab-OS

`MBSA-Lab-OS` is the principal public Git repository used to host the public engineering baseline and related publishable artefacts of MBSA Lab OS.

The repository is an implementation and publication container for the system, not the full definition of the system itself.

### 4.4 MBSA-Lab-Control

`MBSA-Lab-Control` is the private project-control environment.

It holds private control artefacts, including the private Master Plan, and must remain separated from the public repository.

It is outside the public MBSA Lab OS repository boundary while participating in the distributed Strategic Control relationship.

### 4.5 Strategic Control

**Strategic Control** is a logical responsibility covering items such as:

- identity;
- vision;
- mission;
- strategic decisions;
- roadmap;
- version-control decisions;
- architecture freeze decisions;
- arbitration of public/private classification.

Strategic Control is **not** represented as a single physical repository.

Its public artefacts may live in `MBSA-Lab-OS`, while sensitive project-control artefacts remain in `MBSA-Lab-Control`.

### 4.6 Governance Core

The **Governance Core** is the set of baselined rules and artefacts established during Sprint 1 for controlled engineering work, including:

- Engineering Governance;
- Git Workflow and Versioning;
- Issue Templates;
- Pull Request Template;
- Repository and Documentation Conventions;
- Sprint closure and baseline discipline;
- evidence, traceability, review, publication and confidentiality rules.

### 4.7 Engineering Framework

The **Engineering Framework** is the target reusable engineering structure connecting:

`Problem → Need → Requirement → Architecture → Safety Assessment → Implementation → V&V → Evidence → Reuse`

At US011 entry, this capability is not considered fully baselined as an operational framework.

### 4.8 MBSE and MBSA

Within this project:

- **MBSE** means **Model-Based Systems Engineering**;
- **MBSA** refers to **Model-Based Safety Assessment** activities.

Engineering may include Safety Assessment, but the two terms must not be conflated.

### 4.9 Boundary classifications

This document uses three primary boundary classes:

- **IN** — belongs to the system of interest at the contextual responsibility/capability level;
- **OUT** — remains external to the system of interest;
- **BOUNDARY / SHARED** — crosses, spans or depends on the boundary and requires explicit interaction rules.

An `IN` classification does not imply that a detailed internal component architecture has already been defined.

---

## 5. System of Interest

The System of Interest is:

> **MBSA Lab OS**

MBSA Lab OS is the governed public operating foundation of MBSA Lab. Its role is to transform strategic intent into a coherent, reproducible and evidence-oriented engineering system that can progressively support POCs, reusable patterns, publication, education and future tooling.

MBSA Lab OS therefore provides continuity between:

- strategic intent;
- governance;
- engineering methods;
- controlled artefacts;
- evidence;
- reusable knowledge;
- publication;
- later capability growth.

It must remain progressive and incremental.

Capabilities that are only strategic or partially prepared must not be represented as operationally implemented.

---

## 6. System Purpose and Value

### 6.1 Purpose

The purpose of MBSA Lab OS is to provide a controlled framework through which MBSA Lab can produce, validate, publish and reuse engineering assets.

### 6.2 Value delivered

MBSA Lab OS is intended to deliver:

- a stable engineering governance foundation;
- reproducible engineering workflows;
- traceable architecture and modelling practices;
- explicit evidence expectations;
- controlled publication rules;
- reusable structures for future POCs;
- a basis for pattern extraction;
- a basis for educational reuse;
- a basis for future tooling;
- professional public evidence of engineering capability.

### 6.3 Value principle

The system is evidence-oriented.

A major result is not considered mature because it is described in a roadmap. It becomes mature only when appropriate artefacts, verification, validation and baseline evidence exist.

---

## 7. Stakeholders and External Actors

### 7.1 Primary engineering stakeholders

Primary stakeholders include:

- MBSE professionals;
- MBSA and safety engineers;
- systems engineers;
- systems architects;
- software and system architects;
- automotive engineering professionals;
- aerospace engineering professionals;
- engineering managers;
- reviewers and contributors.

### 7.2 Professional stakeholders

Professional stakeholders include:

- recruiters;
- hiring managers;
- engineering organizations;
- potential collaborators;
- potential consulting or training customers in later phases.

### 7.3 Educational stakeholders

Educational stakeholders include:

- engineering students;
- PhD students;
- junior engineers;
- universities;
- training organizations;
- future Academy learners.

### 7.4 Maintainer / project-control actor

The project maintainer is responsible for:

- controlled decisions;
- acceptance;
- publication decisions;
- baseline transitions;
- confidentiality decisions;
- approval of architecture freeze and future lifecycle transitions.

The maintainer interacts with MBSA Lab OS but is not treated as an internal software component.

### 7.5 Contributors

Contributors interact with MBSA Lab OS through controlled work-intake and change-review mechanisms.

Contribution is governed by repository rules, Issue Templates, Pull Request review, acceptance criteria and evidence expectations.

---

## 8. System Environment

The environment of MBSA Lab OS contains:

- the broader MBSA Lab initiative;
- the private `MBSA-Lab-Control` environment;
- GitHub infrastructure;
- local Git working environments;
- engineering tools;
- modelling tools;
- development environments;
- future POC execution environments;
- publication channels;
- learning and dissemination channels;
- external contributors;
- engineering audiences;
- future collaboration partners.

External technologies and services may support MBSA Lab OS but do not become part of the system merely because they are used.

---

## 9. System Boundary

### 9.1 Inside the boundary

The following are considered **IN** at the US011 context level.

#### 9.1.1 Governance Core

Status: **BASELINED**

Includes the controlled governance responsibilities implemented through Sprint 1 artefacts.

#### 9.1.2 Engineering Framework responsibility

Status: **PARTIAL**

The responsibility to define and operate a reusable engineering lifecycle belongs to MBSA Lab OS.

The detailed capability architecture is deferred.

#### 9.1.3 POC Factory responsibility

Status: **STRATEGIC ONLY**

The target responsibility to provide a repeatable mechanism for creating controlled POCs belongs to MBSA Lab OS.

No operational POC Factory is claimed at US011.

#### 9.1.4 Pattern Library responsibility

Status: **STRATEGIC ONLY**

The target responsibility to capture reusable patterns from verified engineering work belongs to MBSA Lab OS.

No validated pattern library is claimed at US011.

#### 9.1.5 Publication-governance responsibility

The rules that determine whether artefacts are suitable for public release are part of MBSA Lab OS governance.

External publication platforms themselves remain outside.

#### 9.1.6 Evidence and traceability responsibility

The requirement to maintain traceable engineering evidence, acceptance criteria and baselines belongs to MBSA Lab OS.

### 9.2 Outside the boundary

The following are **OUT** unless future architecture work explicitly reclassifies them.

#### 9.2.1 MBSA-Lab-Control repository

The private repository is external to the public MBSA Lab OS repository and holds private project-control information.

#### 9.2.2 GitHub platform infrastructure

GitHub is an external hosting, collaboration and publication platform.

#### 9.2.3 YouTube

YouTube is an external publication and explanation channel.

#### 9.2.4 LinkedIn

LinkedIn is an external professional-distribution channel.

#### 9.2.5 Website

The future website is currently external and not implemented.

#### 9.2.6 MBSA Academy

Academy is treated at US011 as a future consuming / adjacent capability rather than as an already implemented internal capability.

Status: **STRATEGIC ONLY**

#### 9.2.7 Eclipse Platform

Future tooling environment.

Status: **STRATEGIC ONLY**

#### 9.2.8 Safety DSL

Future domain/tooling capability.

Status: **STRATEGIC ONLY**

#### 9.2.9 MBSA Plugin

Future tooling/product capability.

Status: **STRATEGIC ONLY**

#### 9.2.10 Community and business ecosystem

Community, consulting, training business, conferences and future productization remain outside the current MBSA Lab OS system boundary.

### 9.3 Boundary / shared responsibilities

The following are classified **BOUNDARY / SHARED**.

#### 9.3.1 Strategic Control

Strategic Control spans the public/private boundary.

The logical responsibility is shared across:

- public strategic artefacts in `MBSA-Lab-OS`;
- private control artefacts in `MBSA-Lab-Control`.

#### 9.3.2 Video Factory interface

The Video Factory is currently **PARTIAL**.

The responsibility to provide structured reuse of stable engineering assets for video production is adjacent to MBSA Lab OS.

Its detailed ownership and internal allocation remain outside US011.

#### 9.3.3 Contribution interface

Contribution crosses the boundary between external contributors and the governed public repository.

#### 9.3.4 Publication interface

Publication crosses the boundary between governed public artefacts and external distribution channels.

#### 9.3.5 Engineering-tool interface

Engineering and modelling tools support the lifecycle but remain external technologies unless later architecture explicitly allocates them as system components.

### 9.4 Explicit non-responsibilities

MBSA Lab OS is not responsible for:

- GitHub service availability;
- YouTube service availability;
- LinkedIn service availability;
- third-party tool licensing;
- external platform security;
- external cloud infrastructure;
- private personal data management outside approved project-control needs;
- guaranteeing business outcomes;
- guaranteeing audience growth;
- implementing future tooling before needs are proven;
- claiming validation that has not been demonstrated.

---

## 10. High-Level Context Interactions

MBSA Lab OS interacts with its environment through five primary interaction families.

### 10.1 Strategic interaction

Inputs:

- Vision;
- Mission;
- roadmap;
- architecture decisions;
- controlled priorities.

Outputs:

- public strategic artefacts;
- architecture direction;
- controlled constraints;
- baselines.

### 10.2 Engineering interaction

Inputs:

- engineering problems;
- stakeholder needs;
- requirements;
- modelling concepts;
- safety concerns;
- implementation evidence;
- V&V results.

Outputs:

- governed engineering artefacts;
- architecture material;
- traceability;
- evidence;
- reusable knowledge.

### 10.3 Contribution interaction

Inputs:

- Issues;
- engineering tasks;
- change proposals;
- Pull Requests;
- review feedback.

Outputs:

- accepted changes;
- rejection rationale;
- recorded evidence;
- traceable baselines.

### 10.4 Publication interaction

Inputs:

- verified public artefacts;
- publication decisions;
- confidentiality review.

Outputs:

- GitHub documentation and source assets;
- future videos;
- professional summaries;
- future educational reuse.

### 10.5 Feedback interaction

Inputs:

- reviewer feedback;
- contributor feedback;
- user observations;
- lessons from future POCs;
- defects;
- limitations.

Outputs:

- controlled changes;
- revised assumptions;
- new Issues;
- new decisions;
- future patterns;
- architecture evolution.

---

## 11. Public / Private Boundary

### 11.1 Public repository

`MBSA-Lab-OS` is public.

Public content may include:

- public engineering documentation;
- public architecture material;
- public governance;
- approved POCs;
- reusable patterns;
- public educational material;
- approved tooling;
- public evidence.

### 11.2 Private control environment

Private control information belongs outside the public repository.

Examples include:

- private Master Plan content;
- private CV variants;
- private contacts;
- non-public business plans;
- sensitive project-control information;
- any private material not explicitly approved for publication.

### 11.3 Publication rule

Content is not public merely because it is strategically relevant.

Every artefact must be classified according to:

- sensitivity;
- purpose;
- intellectual-property constraints;
- third-party restrictions;
- personal-data exposure;
- publication value.

### 11.4 Boundary invariant

A future change must not copy private control artefacts into `MBSA-Lab-OS` merely to centralize documentation.

Public/private separation is an architectural and governance invariant.

---

## 12. Strategic Control Relationship

### 12.1 Logical distribution

Strategic Control is represented as a logical responsibility distributed across two physical environments.

Public side:

- README;
- Project Overview;
- Vision;
- Mission;
- public architecture;
- public governance;
- public roadmap information where approved.

Private side:

- private Master Plan;
- private arbitration;
- sensitive roadmap/control information;
- private decision material.

### 12.2 Direction of flow

Private control may authorize or influence public artefacts.

Public artefacts may provide evidence that informs private strategic decisions.

The relationship is therefore bidirectional in information terms but constrained by publication policy.

### 12.3 Prohibited interpretation

The following interpretation is explicitly rejected:

> `MBSA-Lab-Control` contains the entire Strategic Control system and `MBSA-Lab-OS` contains none of it.

Strategic Control is logical and distributed.

---

## 13. Governance Core Relationship

The Governance Core is the most mature internal responsibility of MBSA Lab OS.

It provides:

- work-entry rules;
- scope control;
- Acceptance Criteria;
- Definition of Done;
- verification and validation discipline;
- evidence expectations;
- Git workflow;
- branch and merge conventions;
- repository conventions;
- publication/confidentiality rules;
- baseline discipline;
- closure discipline.

The Governance Core constrains all later capabilities.

No future factory, POC, pattern, Academy content or tooling capability may bypass it.

---

## 14. Engineering and Production Capability Context

### 14.1 Engineering Framework

Current maturity: **PARTIAL**

Contextual responsibility:

- organize the engineering lifecycle;
- support traceability;
- define evidence expectations;
- prepare later POC execution;
- remain technology-independent where possible.

### 14.2 POC Factory

Current maturity: **STRATEGIC ONLY**

Contextual responsibility:

- transform an engineering concept into a controlled, understandable and publishable demonstration;
- apply a repeatable lifecycle;
- produce evidence suitable for reuse.

No operational factory is claimed.

### 14.3 Pattern Library

Current maturity: **STRATEGIC ONLY**

Contextual responsibility:

- capture verified, reusable engineering patterns from real work;
- avoid declaring patterns reusable before they have been tested in practice.

### 14.4 Video Factory

Current maturity: **PARTIAL**

Contextual responsibility:

- turn stable engineering assets into repeatable explanatory content;
- preserve traceability between technical evidence and communication.

Availability of recording tools does not prove a mature Video Factory.

---

## 15. Visibility and Publication Context

### 15.1 GitHub

GitHub is the principal public engineering-evidence channel.

Primary roles:

- source hosting;
- version history;
- issue intake;
- change review;
- public documentation;
- reproducibility support.

GitHub is external infrastructure.

### 15.2 YouTube

YouTube is an explanatory and demonstration channel.

It must reuse verified engineering work rather than precede it.

### 15.3 LinkedIn

LinkedIn is a professional distribution channel.

It should summarize validated work rather than substitute for engineering evidence.

### 15.4 Website

A future website may become an identity hub.

At US011, it is not an implemented dependency of MBSA Lab OS.

### 15.5 Publication ordering principle

The preferred direction is:

`Engineering Work → Evidence → Public Artefact → Explanation → Professional Distribution`

Communication must not be treated as evidence of engineering completion.

---

## 16. Future Capability Interfaces

### 16.1 MBSA Academy

Academy is expected to reuse stable engineering artefacts.

Potential future inputs:

- POCs;
- patterns;
- models;
- explanations;
- evidence packages.

At US011, no operational Academy capability is claimed.

### 16.2 Eclipse Platform

Future tooling may consume stabilized engineering needs.

It must not drive architecture before recurring needs are demonstrated.

### 16.3 Safety DSL

The Safety DSL is a future capability that depends on a sufficiently stable domain model and recurring modelling needs.

### 16.4 MBSA Plugin

The MBSA Plugin is a future tooling/product capability.

It depends on proven patterns, domain knowledge and tooling needs.

### 16.5 Future integration rule

Future capabilities must integrate through explicit interfaces and governed artefacts.

They must not be silently assumed to be internal components of MBSA Lab OS before a controlled architecture decision.

---

## 17. POC Context and Constraints

### 17.1 Priority POC candidate

Priority 1:

- **Emergency Stop Button**

Current state:

- selected as the first POC candidate under controlled conditions;
- not implemented;
- detailed scope deferred until architecture freeze and subsequent work.

### 17.2 Retained alternatives

Priority 2:

- **Door Interlock Safety System**

Priority 3:

- **Overtemperature Protection System**

These remain controlled fallback/future candidates.

### 17.3 US011 constraint

US011 must preserve these candidates as context without designing or implementing them.

### 17.4 Architectural expectation

MBSA Lab OS should eventually support a lifecycle applicable to more than one POC candidate.

This prevents the Engineering Framework from becoming specific to a single demonstration.

---

## 18. Information and Artefact Flows

### 18.1 Strategic flow

`Private/Public Strategic Control → Governed Architecture Direction`

### 18.2 Engineering flow

`Problem → Need → Requirement → Architecture → Safety Assessment → Implementation → V&V → Evidence`

### 18.3 Reuse flow

`Verified Evidence → Pattern Candidate → Review → Reusable Knowledge`

### 18.4 Publication flow

`Verified Public Artefact → GitHub → Video/Professional Distribution`

### 18.5 Education flow

`Stable Engineering Asset → Future Academy Material`

### 18.6 Tooling flow

`Recurring Proven Need → Domain Understanding → Future Tooling Requirement → Eclipse/DSL/Plugin Work`

### 18.7 Feedback flow

`Review / POC Result / User Feedback → Issue or Decision → Controlled Change`

### 18.8 Baseline flow

`Approved Change → Commit → Integration → Baseline Verification → Closure Evidence`

---

## 19. System Context Diagram

### 19.1 Notation

This document uses a repository-native text diagram.

Rules:

- the central box is the System of Interest;
- external entities are outside the box;
- arrows indicate high-level information, governance, contribution or publication flows;
- the diagram does not imply detailed internal component architecture;
- maturity labels are described in the accompanying matrices.

### 19.2 Diagram

```text
                                   MBSA LAB
                            broader initiative / ecosystem
                                       |
                              strategic intent / goals
                                       v
          +------------------------------------------------------+
          |                    MBSA LAB OS                       |
          |                 SYSTEM OF INTEREST                   |
          |                                                      |
          |  +------------------+                                |
          |  | Governance Core  |  BASELINED                     |
          |  +------------------+                                |
          |                                                      |
          |  Engineering Framework responsibility     PARTIAL    |
          |  POC Factory responsibility              STRATEGIC   |
          |  Pattern Library responsibility           STRATEGIC   |
          |  Evidence / Traceability / Publication Governance    |
          |                                                      |
          +------------------------------------------------------+
             ^                 ^                    |
             |                 |                    |
             |                 |                    | governed public artefacts
             |                 |                    v
             |                 |             +-------------+
             |                 |             |   GitHub    |
             |                 |             |  EXTERNAL   |
             |                 |             +-------------+
             |                 |                    |
             |                 |              publication / access
             |                 |                    |
             |                 |          +---------+---------+
             |                 |          |                   |
             |                 |          v                   v
             |                 |      +---------+         +----------+
             |                 |      | YouTube |         | LinkedIn |
             |                 |      |   OUT   |         |   OUT    |
             |                 |      +---------+         +----------+
             |                 |
             |      contribution / review / engineering inputs
             |                 |
             |        +------------------------+
             |        | Contributors / Users   |
             |        | Engineers / Reviewers  |
             |        +------------------------+
             |
     strategic decisions / control
             |
    +-------------------------+
    |    MBSA-Lab-Control     |
    |      PRIVATE / OUT      |
    | private Master Plan and |
    | sensitive control data  |
    +-------------------------+

          Adjacent / future interfaces:
          -----------------------------------------------
          MBSA Academy            STRATEGIC ONLY
          Video Factory           PARTIAL / BOUNDARY
          Eclipse Platform        STRATEGIC ONLY
          Safety DSL              STRATEGIC ONLY
          MBSA Plugin             STRATEGIC ONLY
          Website                 NOT IMPLEMENTED / FUTURE
          Community / Business    FUTURE
```

### 19.3 Reading rule

The diagram does not state that all target responsibilities already exist as implemented subsystems.

It only states their contextual relationship to MBSA Lab OS.

---

## 20. Boundary Classification Matrix

| Element | Classification | Maturity | Rationale |
|---|---|---|---|
| MBSA Lab OS | SYSTEM OF INTEREST | Architecture under construction | Central system defined by US011 |
| Governance Core | IN | BASELINED | Established by Sprint 1 |
| Engineering Framework responsibility | IN | PARTIAL | Core target responsibility, not fully baselined |
| POC Factory responsibility | IN | STRATEGIC ONLY | Target MBSA Lab OS capability |
| Pattern Library responsibility | IN | STRATEGIC ONLY | Reuse responsibility belongs to target OS |
| Evidence & Traceability governance | IN | BASELINED / evolving | Core engineering responsibility |
| Publication governance | IN | BASELINED / evolving | Public-release control is internal governance |
| Strategic Control | BOUNDARY / SHARED | PARTIAL / BASELINED by artefact | Logical responsibility spans public/private |
| MBSA-Lab-Control | OUT | AVAILABLE | Private control environment |
| GitHub platform | OUT / INTERFACE | AVAILABLE | External hosting and collaboration platform |
| Contributors | OUT / ACTOR | AVAILABLE | External human actors |
| Engineering audiences | OUT / ACTOR | AVAILABLE | Consumers / reviewers |
| Video Factory | BOUNDARY / SHARED | PARTIAL | Adjacent production capability |
| YouTube | OUT | External platform | Explanation/publication channel |
| LinkedIn | OUT | External platform | Professional distribution |
| MBSA Academy | OUT / FUTURE INTERFACE | STRATEGIC ONLY | Future consumer of stable engineering assets |
| Eclipse Platform | OUT / FUTURE INTERFACE | STRATEGIC ONLY | Future tooling capability |
| Safety DSL | OUT / FUTURE INTERFACE | STRATEGIC ONLY | Future domain/tooling capability |
| MBSA Plugin | OUT / FUTURE INTERFACE | STRATEGIC ONLY | Future tooling/product capability |
| Website | OUT | NOT IMPLEMENTED | Future identity/publication channel |
| Community | OUT | NOT IMPLEMENTED | Future ecosystem capability |
| Business / Consulting / Training | OUT | FUTURE | Professional/business ecosystem |

---

## 21. Interface / Interaction Matrix

| ID | External Entity | Direction | Information / Artefact | Governing Concern |
|---|---|---|---|---|
| INT-01 | MBSA-Lab-Control | Bidirectional | strategic decisions, approved public direction, evidence feedback | confidentiality, authority |
| INT-02 | Contributors | Inbound | Issues, proposals, changes, review input | governance, scope, traceability |
| INT-03 | Contributors | Outbound | decisions, review results, accepted baseline | transparency, evidence |
| INT-04 | GitHub | Outbound | source, documentation, issues, PR artefacts | publication, integrity |
| INT-05 | GitHub | Inbound | contribution events, review context, repository state | workflow, traceability |
| INT-06 | YouTube | Outbound | explanations derived from stable engineering assets | evidence-before-communication |
| INT-07 | LinkedIn | Outbound | professional summaries and visibility content | claim discipline |
| INT-08 | Engineering tools | Bidirectional | models, implementation artefacts, test evidence | reproducibility |
| INT-09 | Future Academy | Outbound | reusable learning-ready engineering assets | maturity and reuse |
| INT-10 | Future Tooling | Bidirectional | stable domain needs, models, automation opportunities | deferred architecture |
| INT-11 | Future POCs | Bidirectional | requirements, models, evidence, lessons learned | controlled lifecycle |
| INT-12 | Reviewers / Audiences | Inbound | feedback, defects, clarification needs | change governance |

---

## 22. Assumptions

### A-US011-01

MBSA Lab OS remains the principal system of interest for Sprint 2 architecture work.

### A-US011-02

The public repository remains `MBSA-Lab-OS`.

### A-US011-03

The private control repository remains logically separate from the public engineering repository.

### A-US011-04

No external platform is assumed to be permanently available.

### A-US011-05

Future architecture will refine internal allocation without invalidating the high-level public/private boundary defined here.

### A-US011-06

Engineering and modelling tools may change over time and therefore should not become unnecessary structural dependencies.

### A-US011-07

Future POCs will provide evidence used to refine factories, patterns and tooling.

---

## 23. Constraints

### C-US011-01 — Public/private separation

Private control information must not be committed to the public repository.

### C-US011-02 — No premature implementation claims

`PARTIAL`, `STRATEGIC ONLY`, `NOT IMPLEMENTED` and similar maturity states must remain explicit.

### C-US011-03 — Architecture before POC implementation

Sprint 2 architecture must establish sufficient structure before the first POC is implemented.

### C-US011-04 — Progressive architecture

The architecture must remain incremental and evidence-driven.

### C-US011-05 — Technology independence

No unnecessary dependency on a specific commercial tool or vendor should be introduced.

### C-US011-06 — Git governance

Changes must follow the approved Git workflow and repository conventions.

### C-US011-07 — Repository-native documentation

Markdown is the primary documentation source.

### C-US011-08 — Canonical text handling

Repository text must remain compatible with the approved UTF-8 and LF conventions.

### C-US011-09 — Traceability

Normative claims must be supported by controlled sources, decisions or evidence.

### C-US011-10 — US011 / US012 separation

US011 must not absorb detailed logical architecture work intended for US012.

---

## 24. Dependencies

### D-US011-01 — Sprint 1 Governance Core

US011 depends on the Governance Core established by US005–US010.

### D-US011-02 — Vision and Mission

System purpose and context depend on the baselined Vision and Mission.

### D-US011-03 — Repository conventions

The document depends on US009 conventions for placement, naming, Markdown and text handling.

### D-US011-04 — Strategic rebaseline

System context depends on the controlled post-Sprint-1 rebaseline.

### D-US011-05 — Future US012

Detailed capability and logical architecture depends on this context definition.

### D-US011-06 — Future POC preparation

Future POC work depends on the architecture being sufficiently clear and frozen.

---

## 25. Risks and Limitations

### R-US011-01 — MBSA Lab vs MBSA Lab OS confusion

Risk:

The broader MBSA Lab ecosystem may be incorrectly represented as entirely internal to MBSA Lab OS.

Mitigation:

Use explicit `IN`, `OUT` and `BOUNDARY / SHARED` classifications.

### R-US011-02 — Repository vs system confusion

Risk:

`MBSA-Lab-OS` may be treated as identical to MBSA Lab OS.

Mitigation:

Maintain the distinction between system and hosting repository.

### R-US011-03 — Strategic Control physical-location confusion

Risk:

Strategic Control may be represented as belonging exclusively to `MBSA-Lab-Control`.

Mitigation:

Represent it as a distributed logical responsibility.

### R-US011-04 — Maturity inflation

Risk:

Strategic or partial capabilities may be described as implemented.

Mitigation:

Keep maturity labels visible and traceable.

### R-US011-05 — US012 scope leakage

Risk:

US011 may prematurely define detailed internal architecture.

Mitigation:

Keep this document contextual and defer internal decomposition.

### R-US011-06 — Confidentiality leakage

Risk:

Private control details may be copied into the public document.

Mitigation:

Describe the private boundary without exposing private content.

### R-US011-07 — Communication-before-evidence

Risk:

Publication channels may create claims stronger than the engineering evidence.

Mitigation:

Preserve evidence-before-communication ordering.

### R-US011-08 — Tool-driven architecture

Risk:

Eclipse, DSL or Plugin ambitions may bias architecture prematurely.

Mitigation:

Treat future tooling as external/future interfaces until recurring needs are proven.

### R-US011-09 — POC-specific architecture

Risk:

The architecture may become tailored only to Emergency Stop Button.

Mitigation:

Preserve the other controlled POC candidates and design later framework capabilities for more than one case.

### R-US011-10 — Historical-view inconsistency

Risk:

Older documents sometimes list MBSA Lab OS, Academy, factories and tooling as parallel elements, while other documents describe MBSA Lab OS as the operating framework connecting them.

Mitigation:

Treat those historical structures as different abstraction views and avoid forcing a detailed ownership interpretation in US011.

---

## 26. Open Decisions

### O-US011-01 — Detailed internal allocation

Which detailed logical components own each internal responsibility?

Owner:

- US012 and later architecture work.

### O-US011-02 — Video Factory allocation

Should Video Factory become a fully internal MBSA Lab OS capability or remain an adjacent production service?

Owner:

- later Sprint 2 architecture work.

### O-US011-03 — Academy integration model

Should Academy remain an external consumer or eventually become a direct MBSA Lab OS capability?

Owner:

- later architecture / Academy work.

### O-US011-04 — Tooling repository strategy

Whether Eclipse Platform, Safety DSL or MBSA Plugin require separate repositories remains conditional on demonstrated need.

### O-US011-05 — Website architecture

The role and hosting architecture of a future website remain open.

### O-US011-06 — Community / business interfaces

Detailed interfaces toward community, consulting, training and business activities remain outside Sprint 2 architecture unless separately authorized.

---

## 27. Traceability to Sprint 1 Baseline

| US011 Topic | Sprint 1 / Controlled Source |
|---|---|
| Project identity | `README.md`, `docs/00_Project_Overview.md` |
| Vision relationship | `docs/01_Vision.md` |
| Mission and audiences | `docs/02_Mission.md` |
| Governance Core | `docs/03_Engineering_Governance.md` |
| Git and versioning boundary | `docs/04_Git_Workflow_and_Versioning.md` |
| Placement, naming and Markdown rules | `docs/05_Repository_and_Documentation_Conventions.md` |
| Sprint 1 baseline and public/private invariants | `docs/06_Sprint_1_Closure_and_Governance_Baseline.md` |
| Strategic architecture and roadmap | controlled transition/rebaseline Gates |
| Sprint 2 scope | controlled Sprint 2 definition and backlog |
| US011 scope and closure rules | controlled US011 launch prompt |

---

## 28. Acceptance Criteria Traceability

| ID | Acceptance Criterion | Evidence in this document |
|---|---|---|
| AC-US011-01 | MBSA Lab OS identified as System of Interest | Sections 4, 5 |
| AC-US011-02 | Purpose and value defined | Section 6 |
| AC-US011-03 | MBSA Lab / MBSA Lab OS / repositories distinguished | Section 4 |
| AC-US011-04 | Boundary explicit | Sections 9, 19 |
| AC-US011-05 | IN / OUT / SHARED documented | Sections 9, 20 |
| AC-US011-06 | Responsibilities and non-responsibilities defined | Sections 9, 13, 14 |
| AC-US011-07 | Human actors identified | Section 7 |
| AC-US011-08 | External systems and platforms identified | Sections 8, 20 |
| AC-US011-09 | Boundary interactions described | Sections 10, 21 |
| AC-US011-10 | Structuring domains positioned by maturity | Sections 13–16, 20 |
| AC-US011-11 | Strategic Control correctly represented | Sections 11, 12, 19 |
| AC-US011-12 | Public/private separation explicit | Section 11 |
| AC-US011-13 | Private artefacts excluded from public repository | Section 11 |
| AC-US011-14 | Governance/information/contribution/publication flows defined | Sections 10, 18, 21 |
| AC-US011-15 | Context diagram provided | Section 19 |
| AC-US011-16 | Diagram/text/matrices consistent | Sections 19–21 |
| AC-US011-17 | Assumptions, constraints, dependencies explicit | Sections 22–24 |
| AC-US011-18 | Risks and open decisions explicit | Sections 25–26 |
| AC-US011-19 | Claims traceable to controlled sources | Sections 3, 27 |
| AC-US011-20 | No maturity inflation | Sections 9, 14, 16, 20 |
| AC-US011-21 | No POC/API/component design introduced | Sections 2, 17 |
| AC-US011-22 | Repository conventions respected | Sections 3, 23 |
| AC-US011-23 | Quality controls defined and reproducible | Section 29 |
| AC-US011-24 | Final Git evidence required for closure | Section 29 |

---

## 29. US011 Verification Strategy

Before US011 can be declared DONE, verification must demonstrate at least:

### 29.1 Content verification

- system of interest is unambiguous;
- purpose and value are present;
- actors are identified;
- boundary classifications are complete;
- public/private separation is explicit;
- Strategic Control is correctly represented;
- maturity labels are preserved;
- no private information is disclosed;
- no detailed US012 architecture is introduced;
- no POC is designed or implemented;
- assumptions, risks and decisions are recorded;
- diagram, text and matrices are consistent.

### 29.2 Repository verification

Verify:

- expected filename;
- expected directory;
- Markdown readability;
- heading consistency;
- whitespace;
- UTF-8 text handling;
- LF normalization;
- absence of accidental unrelated changes;
- absence of private or sensitive material.

### 29.3 Git verification

The controlled workflow must include:

1. verify branch and baseline;
2. inspect the unstaged diff;
3. run `git diff --check`;
4. confirm scope;
5. stage only the US011 artefact;
6. inspect the staged diff;
7. run `git diff --cached --check`;
8. commit and capture the real SHA;
9. publish the feature branch according to governance;
10. verify feature/main delta;
11. merge using the approved workflow;
12. capture the merge SHA;
13. push main;
14. verify `main = origin/main`;
15. process the completed feature branch according to governance;
16. verify the final working tree;
17. produce the US011 status report and handoff.

No predicted commit or merge SHA is permitted.

---

## 30. Relationship to Subsequent Sprint 2 Architecture Work

This document establishes the contextual contract for subsequent architecture work.

US011 answers:

- What is MBSA Lab OS?
- Why does it exist?
- Who interacts with it?
- What is inside?
- What is outside?
- What crosses the boundary?
- What is private?
- What is public?
- Which capabilities are mature, partial or strategic?
- Which decisions remain open?

Subsequent work may answer:

- Which logical capabilities exist internally?
- How are responsibilities decomposed?
- Which interfaces exist between internal capabilities?
- Which information models are required?
- Which lifecycle and traceability structures are mandatory?
- Which architecture can be frozen before the first POC?

A boundary classification in US011 must not be interpreted as a detailed component allocation.

---

## 31. Conclusion

MBSA Lab OS is defined as the governed public operating foundation of the broader MBSA Lab initiative.

Its current strongest internal foundation is the **Governance Core**, baselined during Sprint 1.

Its target engineering and production responsibilities include the Engineering Framework, POC Factory, Pattern Library, evidence management and publication governance, with maturity states explicitly preserved.

The system is not isolated. It operates across controlled boundaries with:

- private Strategic Control;
- contributors;
- engineering tools;
- GitHub;
- future POCs;
- future educational reuse;
- publication channels;
- future tooling.

The most important architectural invariant is the explicit distinction between:

- public and private;
- strategy and implementation;
- system and repository;
- current capability and future intent;
- context definition and detailed logical architecture.

This context provides the controlled foundation for the remainder of Sprint 2 while preventing premature implementation, maturity inflation and boundary ambiguity.
