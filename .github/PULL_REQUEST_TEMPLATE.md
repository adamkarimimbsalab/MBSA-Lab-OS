# Pull Request

> Use this template to provide the evidence needed to review and
> integrate a change into MBSA Lab.\
> Keep the Pull Request focused on the implemented change. Link to the
> originating Issue or User Story instead of duplicating its full
> content.

------------------------------------------------------------------------

## 1. Summary

Provide a concise description of the change implemented by this Pull
Request.

```{=html}
<!--
Explain what changed and the resulting outcome.
Focus on the implemented change, not the full history of the originating Issue.
-->
```
## 2. Related Issue / User Story

Identify the work item that authorized or motivated this change.

-   Related Issue: \#
-   User Story: US\_\_\_
-   Other traceability reference: N/A

```{=html}
<!--
Use "N/A" only when no Issue/User Story is applicable, and explain why if necessary.
-->
```
## 3. Scope

### In Scope

List the changes intentionally included in this Pull Request.

-   

### Out of Scope

List relevant items deliberately excluded from this Pull Request.

-   

```{=html}
<!--
The Pull Request should contain only work required by its stated scope.
Unrelated improvements should be handled separately.
-->
```
## 4. Changes Made

Describe the concrete changes introduced.

-   

```{=html}
<!--
Examples:
- added or updated an engineering artefact;
- modified source code;
- updated a model;
- added validation evidence;
- corrected a documented defect;
- introduced or updated repository support files.
-->
```
## 5. Affected Artefacts

List the files, models, code, tests, documents, diagrams, or other
artefacts affected by the change.

-   

```{=html}
<!--
Include only materially affected artefacts.
-->
```
## 6. Engineering Impact

Assess the engineering impact of the change.

-   [ ] No material engineering impact
-   [ ] Requirements affected
-   [ ] Architecture affected
-   [ ] MBSE model affected
-   [ ] Safety / MBSA reasoning affected
-   [ ] Implementation affected
-   [ ] Verification affected
-   [ ] Validation affected
-   [ ] Traceability affected
-   [ ] Public engineering meaning affected
-   [ ] Other impact described below

### Impact Details

N/A

```{=html}
<!--
For a significant change, document the reason for change, affected artefacts,
impact, validation required, and resulting decision as applicable.
Do not mark "No material engineering impact" if another material-impact item is selected.
-->
```
## 7. Verification

Describe how the implemented change was checked against its defined
requirements, acceptance criteria, or expected technical behaviour.

### Verification Performed

-   

### Verification Result

-   [ ] PASS
-   [ ] FAIL
-   [ ] NOT APPLICABLE --- justified below

### Verification Evidence

-   

### Justification if Not Applicable

N/A

```{=html}
<!--
Do not claim verification without a defined verification activity and supporting evidence.
Evidence may reference commands, tests, logs, diffs, models, screenshots, reports,
or other reproducible artefacts as appropriate.
-->
```
## 8. Validation

Describe how the result was assessed against the intended engineering
purpose or expected use.

### Validation Performed

-   

### Validation Result

-   [ ] PASS
-   [ ] FAIL
-   [ ] NOT APPLICABLE --- justified below

### Validation Evidence

-   

### Justification if Not Applicable

N/A

```{=html}
<!--
Verification and validation are distinct activities.
If validation is not applicable to the scope of this Pull Request, state why.
-->
```
## 9. Acceptance Criteria

Confirm the acceptance criteria defined by the related Issue / User
Story.

-   [ ] AC-01:
-   [ ] AC-02:
-   [ ] AC-03:

```{=html}
<!--
Add or remove entries to match the originating work item.
Do not invent acceptance criteria during review merely to complete this section.
-->
```
## 10. Evidence and Traceability

Provide references that allow the reviewer to follow the relevant
engineering chain.

### Evidence

-   

### Traceability

-   

```{=html}
<!--
Use only the traceability levels applicable to this change.

Typical MBSA Lab progression:
Problem
→ Requirement
→ Architecture
→ Implementation
→ Verification
→ Validation
→ Evidence

References may include Issues, commits, documents, models, tests, reports,
POC results, or other repository artefacts.
-->
```
## 11. Risks and Limitations

Identify material residual risks, known limitations, unresolved
assumptions, or constraints.

None identified.

```{=html}
<!--
Do not hide a known limitation to obtain merge approval.
If none are identified, retain "None identified."
-->
```
## 12. Documentation Impact

-   [ ] No documentation change required
-   [ ] Documentation added or updated in this Pull Request
-   [ ] Documentation update required separately
-   [ ] Not applicable

### Details

N/A

```{=html}
<!--
Identify documentation that was changed or remains to be updated.
Do not absorb unrelated repository/documentation convention work into this Pull Request.
-->
```
## 13. Publication and Confidentiality Check

Confirm that the proposed change is suitable for the public
`MBSA-Lab-OS` repository.

-   [ ] Technical content is appropriate for its stated public scope
-   [ ] Assumptions and material limitations are explicit where required
-   [ ] Claims are supported by appropriate evidence
-   [ ] No industrial or customer confidential information is included
-   [ ] No private personal information is included
-   [ ] No credentials, secrets, tokens, or private keys are included
-   [ ] No private CV variants, unreleased commercial plans, or private
    project-control information are included
-   [ ] Any source engineering context has been appropriately abstracted
    or anonymized where necessary

```{=html}
<!--
If any item cannot be confirmed, this Pull Request is not ready for public integration.
-->
```
## 14. Review and Merge Readiness

### Author Checklist

-   [ ] The Pull Request is linked to the relevant Issue / User Story
    where applicable
-   [ ] The Pull Request contains only intended changes
-   [ ] No unrelated modification is included
-   [ ] Affected artefacts have been reviewed
-   [ ] Verification is complete or explicitly justified as not
    applicable
-   [ ] Validation is complete or explicitly justified as not applicable
-   [ ] Required evidence is referenced
-   [ ] Acceptance criteria are satisfied or any exception is explicit
-   [ ] Risks and limitations are documented
-   [ ] Documentation impact has been assessed
-   [ ] Publication and confidentiality checks are complete
-   [ ] Local Git validation is complete
-   [ ] `git diff --check` reports no formatting error
-   [ ] The feature branch has been pushed and is ready for review

### Reviewer Checklist

-   [ ] Scope is clear and consistent with the related work item
-   [ ] Changes match the stated scope
-   [ ] Engineering impact has been assessed appropriately
-   [ ] Verification evidence is sufficient for the claims made
-   [ ] Validation evidence is sufficient where applicable
-   [ ] Traceability is adequate for the maturity and impact of the
    change
-   [ ] Risks, limitations, and assumptions are acceptable or explicitly
    addressed
-   [ ] Public-release and confidentiality requirements are satisfied
-   [ ] No blocking issue remains before integration
-   [ ] Pull Request is ready for controlled merge

## 15. Reviewer Notes

N/A

```{=html}
<!--
Use this section for review decisions, requested corrections, or material observations.
Do not use it to replace Issues for new work discovered during review.
-->
```
