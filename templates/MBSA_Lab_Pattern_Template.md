# MBSA Lab Pattern Template

## 0. Use restrictions

This template captures a Pattern Candidate and its controlled evaluation. A
completed template is not an admission decision, validation claim, publication
authorization or target reuse authorization.

Do not replace missing information with unsupported assertions. Use
`NOT_AVAILABLE`, `NOT_APPLICABLE — <rationale>` or an explicit Finding. Preserve
negative, contradictory, invalid and inconclusive results.

## 1. Pattern Register and document control

| Field | Value |
|---|---|
| Candidate identifier | `[PAT-<domain>-<sequence>]` |
| Pattern Version identifier | `[PATVER-<pattern-id>-<version>]` |
| Candidate name | `[name]` |
| Pattern Family | `[PATFAM identifier or NOT_APPLICABLE]` |
| Current Pattern state | `[DRAFT / CANDIDATE / IN_REVIEW / ...]` |
| Content owner | `[role or controlled identity]` |
| Configuration baseline | `[baseline identity]` |
| Source revision | `[immutable revision]` |
| Classification | `[PUBLIC / PRIVATE / BOUNDARY_SHARED]` |
| Publication authority | `[authority or NOT_DECIDED]` |
| Rights/licence position | `[rights statement]` |
| Created / updated | `[ISO 8601 date]` |
| Supersedes | `[Pattern Version or NONE]` |
| Superseded by | `[Pattern Version or NONE]` |

## 2. Candidate status statement

> This record describes a Pattern Candidate unless an applicable immutable
> Admission Record explicitly establishes another state. Repository presence,
> review, publication, POC success or template completion does not constitute
> admission.

## 3. Context

### 3.1 Bounded context

`[Describe domain, lifecycle phase, actors, environment, configuration and
scope boundaries.]`

### 3.2 Recurring problem

`[State the problem independently of the proposed solution and reference its
authoritative sources.]`

### 3.3 Forces and tensions

| ID | Force or tension | Source | Priority | Conflict/interaction |
|---|---|---|---|---|
| `FOR-01` | `[description]` | `[reference]` | `[high/medium/low]` | `[related forces]` |

### 3.4 Stakeholders and concerns

| Stakeholder or role | Concern | Decision influence |
|---|---|---|
| `[role]` | `[concern]` | `[review/authority/consumer]` |

## 4. Generic solution

### 4.1 Solution statement

`[Describe the reusable solution structure without binding it unnecessarily to
a source implementation.]`

### 4.2 Essential structure

`[Identify elements, responsibilities, relations and control flows that define
the Pattern.]`

### 4.3 Invariants

| ID | Non-tailorable invariant | Rationale | Verification method |
|---|---|---|---|
| `INV-01` | `[invariant]` | `[why essential]` | `[inspection/analysis/test]` |

### 4.4 Variation points and permitted tailoring

| ID | Variation point | Allowed alternatives | Constraints | Tailoring level |
|---|---|---|---|---|
| `VAR-01` | `[variation]` | `[options]` | `[constraints]` | `[T1/T2/T3]` |

### 4.5 Implementation-specific details excluded from the Pattern

`[List source-specific technologies, values or structures that are not part of
the generic contract.]`

## 5. Preconditions, assumptions and constraints

| ID | Type | Statement | Source | Status | Reopening trigger |
|---|---|---|---|---|---|
| `PAC-01` | `[precondition/assumption/constraint]` | `[statement]` | `[reference]` | `[confirmed/open]` | `[trigger]` |

## 6. Consequences and trade-offs

| ID | Type | Consequence | Affected concern | Evidence or rationale |
|---|---|---|---|---|
| `CON-01` | `[positive/negative/conditional]` | `[consequence]` | `[concern]` | `[reference]` |

## 7. Limitations and counter-indications

| ID | Limitation or counter-indication | Scope | Enforcement/check | Propagation target |
|---|---|---|---|---|
| `LIM-01` | `[statement]` | `[bounded scope]` | `[method]` | `[admission/publication/reuse]` |

## 8. Alternatives and trade-offs view

| Alternative ID | Description | Evaluation criteria | Advantages | Disadvantages | Disposition and rationale |
|---|---|---|---|---|---|
| `ALT-01` | `[alternative]` | `[criteria]` | `[advantages]` | `[disadvantages]` | `[selected/rejected/deferred]` |

At least one credible alternative shall be evaluated. A straw-man alternative
does not satisfy this obligation.

## 9. Source POC and baseline view

| Source POC ID | Configuration | Baseline/revision | Environment | Lifecycle state | Evidence Package | Applicability limit |
|---|---|---|---|---|---|---|
| `[POC-ID]` | `[configuration]` | `[immutable identity]` | `[environment]` | `[state]` | `[EP-ID]` | `[limit]` |

Pattern Candidate extraction through `PLC-12` is a handoff only. Record POC
closure and publication status separately.

## 10. Claim–Evidence–Limitation Matrix

| Claim ID | Bounded Claim | Configuration/scope | Evidence IDs | Result position | Limitations | Strength assessment |
|---|---|---|---|---|---|---|
| `CLM-01` | `[claim]` | `[scope]` | `[evidence]` | `[PASS/FAIL/INVALID/INCONCLUSIVE/MIXED]` | `[limits]` | `[supported/partially supported/unsupported]` |

The strength of a Claim shall not exceed its supporting Evidence.

## 11. Negative results and Findings register

| Finding ID | Type | Description | Affected object | Severity | Evidence | Disposition | Owner | Blocking |
|---|---|---|---|---|---|---|---|---|
| `FND-01` | `[negative/contradictory/missing/invalid/inconclusive]` | `[description]` | `[identity]` | `[severity]` | `[reference]` | `[open/accepted/rework/waived]` | `[owner]` | `[yes/no]` |

Do not delete rejected evidence or adverse results after admission.

## 12. Applicability/Non-Applicability Matrix

| Domain/context | Applicable? | Supporting rationale/evidence | Exclusions | Required adaptation | V&V to renew |
|---|---|---|---|---|---|
| `[context]` | `[yes/no/unknown]` | `[reference]` | `[exclusions]` | `[changes]` | `[activities]` |

Unknown applicability shall be recorded as unknown, not inferred as applicable.

## 13. Candidate admission checklist

| Obligation | Class | Applicable | Evidence/reference | Result | Finding/limitation |
|---|---|---|---|---|---|
| `PAO-01` identity/version | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-02` roles/authority | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-03` problem/context | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-04` generic solution | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-05` alternatives/trade-offs | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-06` consequences/counter-indications | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-07` source configuration | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-08` Evidence/Claims | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-09` negative results/Findings | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-10` applicability boundaries | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-11` tailoring invariants | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-12` classification/rights | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-13` lifecycle/change controls | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| `PAO-14` Admission Record | `MANDATORY` | `YES` | `[reference]` | `[PASS/FAIL]` | `[reference]` |
| Safety obligations | `CONDITIONAL` | `[YES/NO]` | `[reference/rationale]` | `[result]` | `[reference]` |
| Third-party rights | `CONDITIONAL` | `[YES/NO]` | `[reference/rationale]` | `[result]` | `[reference]` |
| Public surrogate | `CONDITIONAL` | `[YES/NO]` | `[reference/rationale]` | `[result]` | `[reference]` |
| Cross-context evidence | `CONDITIONAL` | `[YES/NO]` | `[reference/rationale]` | `[result]` | `[reference]` |
| Waiver controls | `CONDITIONAL` | `[YES/NO]` | `[reference/rationale]` | `[result]` | `[reference]` |

Completeness is assessed over applicable obligations. A complete checklist may
contain FAIL and does not itself authorize admission.

## 14. Integrated Gate instances

| Gate Instance | Gate type | Object/scope/baseline | Entry status | Decision | Decision record |
|---|---|---|---|---|---|
| `[GI-ID]` | `[GATE-GOV-01/02, GATE-ENG-09, GATE-EVI-*, GATE-PUB-*, GATE-CLS-*]` | `[bounded identity]` | `[status]` | `[decision]` | `[reference]` |

Pattern state shall not be copied from a Gate state. Record the admission
decision and resulting Pattern state separately.

## 15. Review and authority record

| Role | Identity | Independence requirement | Review position | Date |
|---|---|---|---|---|
| Candidate owner | `[identity]` | `[requirement]` | `[position]` | `[date]` |
| Engineering reviewer | `[identity]` | `[requirement]` | `[position]` | `[date]` |
| Evidence reviewer | `[identity]` | `[requirement]` | `[position]` | `[date]` |
| Safety reviewer | `[identity/NOT_APPLICABLE]` | `[requirement]` | `[position]` | `[date]` |
| Publication authority | `[identity]` | `[requirement]` | `[position]` | `[date]` |
| Pattern admission authority | `[identity]` | `[requirement]` | `[decision authority]` | `[date]` |

## 16. Admission Decision Record

| Field | Value |
|---|---|
| Admission Record ID | `[PADM-...]` |
| Candidate / Pattern Version | `[identifiers]` |
| Decision scope and baseline | `[scope]` |
| Tailoring level | `[T1/T2/T3]` |
| Criteria set | `[reference]` |
| Evidence Package(s) | `[identifiers]` |
| Open Findings | `[identifiers or NONE]` |
| Waivers | `[identifiers or NONE]` |
| Reviewer positions | `[references]` |
| Decision | `[ADMIT / ADMIT_WITH_LIMITATIONS / REJECT / REWORK / DEFER]` |
| Rationale | `[rationale]` |
| Enforceable limitations | `[limitations or NONE]` |
| Actions and owners | `[actions]` |
| Resulting Pattern state | `[state]` |
| Admission authority | `[identity]` |
| Effective date | `[ISO 8601 date]` |
| Reopening triggers | `[triggers]` |

The Admission Record shall be immutable after baselining. Corrections require a
linked amendment or new decision record.

## 17. Publication and rights view

| Component/reference | Classification | Owner | Rights status | Publication decision | Public surrogate | Limitation |
|---|---|---|---|---|---|---|
| `[item]` | `[PUBLIC/PRIVATE/BOUNDARY_SHARED]` | `[owner]` | `[status]` | `[GO/NO-GO/REWORK]` | `[reference/NONE]` | `[limit]` |

Technical PASS and Pattern admission do not grant publication permission.

## 18. Reuse Applicability Assessment

### 18.1 Target identification

| Field | Value |
|---|---|
| Assessment ID | `[PRA-...]` |
| Pattern Version | `[PATVER-...]` |
| Target context/configuration | `[identity and baseline]` |
| Target owner | `[role]` |
| Target reuse authority | `[authority]` |
| Assessment date | `[date]` |

### 18.2 Source-to-target comparison

| Dimension | Source envelope | Target condition | Compatible? | Gap/action |
|---|---|---|---|---|
| Problem/context | `[source]` | `[target]` | `[yes/no/partial]` | `[action]` |
| Forces | `[source]` | `[target]` | `[yes/no/partial]` | `[action]` |
| Assumptions | `[source]` | `[target]` | `[yes/no/partial]` | `[action]` |
| Constraints | `[source]` | `[target]` | `[yes/no/partial]` | `[action]` |
| Architecture/interfaces | `[source]` | `[target]` | `[yes/no/partial]` | `[action]` |
| Configuration/environment | `[source]` | `[target]` | `[yes/no/partial]` | `[action]` |
| Safety context | `[source]` | `[target]` | `[yes/no/partial]` | `[action]` |
| Evidence transferability | `[source]` | `[target]` | `[yes/no/partial]` | `[action]` |

### 18.3 Assurance renewal

| Requirement/Safety/V&V item | Reusable evidence | Non-transferable evidence | Activity to renew | Acceptance authority |
|---|---|---|---|---|
| `[item]` | `[reference]` | `[reference]` | `[activity]` | `[authority]` |

### 18.4 Target decision

| Field | Value |
|---|---|
| Decision | `[APPLY / APPLY_WITH_ADAPTATION / DO_NOT_APPLY / DEFER]` |
| Adaptations | `[changes or NONE]` |
| Limitations and residual risks | `[list]` |
| Required baselines and actions | `[list]` |
| Authority and date | `[identity/date]` |
| Reopening triggers | `[triggers]` |

Admission of the source Pattern does not predetermine this decision.

## 19. Version/Supersession/Retention View

| Pattern Version | State | Admission Record | Predecessor | Successor | Migration scope | Retention/access | Effective date |
|---|---|---|---|---|---|---|---|
| `[PATVER]` | `[state]` | `[PADM]` | `[version/NONE]` | `[version/NONE]` | `[scope]` | `[rule]` | `[date]` |

## 20. Change and impact record

| Change ID | Changed object | Material? | Affected Claims/Evidence/reuse records | Required Gate reopening | Decision |
|---|---|---|---|---|---|
| `[CHG-ID]` | `[identity]` | `[yes/no]` | `[references]` | `[Gates]` | `[decision]` |

## 21. Tailoring record

| Field | Value |
|---|---|
| Tailoring level | `[T1/T2/T3]` |
| Combined or reduced records | `[description]` |
| Rationale | `[rationale]` |
| Essential objectives preserved | `[evidence]` |
| Governance decision | `[reference]` |

Tailoring shall not remove identity, context/problem, solution, alternatives,
limitations, Evidence, negative results, authority, admission decision,
target-specific applicability, publication boundary, change control or
retention.

## 22. Completion and verification checklist

- [ ] No real admission is inferred from template completion.
- [ ] Candidate, Pattern, Example, Rule, Template and Artefact are distinct.
- [ ] Identity, version, baseline, owner and classification are present.
- [ ] Context, recurring problem, forces and generic solution are bounded.
- [ ] Alternatives, consequences, limitations and counter-indications exist.
- [ ] Source POC, configuration and Evidence Packages are navigable.
- [ ] Claims do not exceed supporting Evidence.
- [ ] Negative, invalid, contradictory and inconclusive results remain visible.
- [ ] Mandatory and applicable conditional obligations are dispositioned.
- [ ] Reviewers and decision authorities are distinguished.
- [ ] Pattern state, Gate state and DEBUG are not conflated.
- [ ] Admission and target reuse decisions remain separate.
- [ ] Change, reopening, supersession, retirement and retention are controlled.
- [ ] Publication boundary, rights and public surrogate are dispositioned.
- [ ] `T1/T2/T3` tailoring preserves essential objectives.
- [ ] No product readiness, certification, conformity or safety-integrity claim
      is inferred.
- [ ] UTF-8 without BOM/NUL, LF, final LF and no trailing whitespace pass.
- [ ] Authoritative sources and immutable revisions are referenced.

## 23. Template status

This template is an unpopulated control structure. It contains no admitted or
validated Pattern, no selected POC and no reuse authorization. Its use remains
subject to the Pattern Definition and Admission Rules, applicable Gates,
Evidence, authority and controlled baselines.
