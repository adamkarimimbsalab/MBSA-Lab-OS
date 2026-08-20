# Git Workflow & Versioning

## 1. Purpose

This document defines the operational Git workflow and versioning rules for MBSA Lab.

It translates the engineering governance established in `docs/03_Engineering_Governance.md` into concrete, reproducible repository practices.

The objective is to make changes to MBSA-Lab-OS:

- identifiable;
- isolated;
- reviewable;
- reproducible;
- traceable to a User Story or approved change;
- safely integrated into `main`;
- recoverable when correction is required.

US006 defines Git workflow mechanisms. It does not replace the engineering governance principles defined by US005.

---

## 2. Scope

This document applies to the public engineering repository:

`MBSA-Lab-OS`

It defines:

1. repository branch model;
2. branch naming convention;
3. branch lifecycle;
4. commit convention;
5. commit message examples;
6. versioning strategy;
7. release rules;
8. merge rules;
9. synchronization rules;
10. change and correction rules;
11. operational Git workflow;
12. compliance checks.

This document does not define:

- GitHub Issue Templates — US007;
- Pull Request Template and review rules — US008;
- authoritative repository/documentation conventions — US009;
- Sprint 1 closure and governance baseline — US010.

---

## 3. Relationship with Engineering Governance

US005 established the engineering governance framework for MBSA Lab.

US005 defines the principles and governance rules for:

- engineering decisions;
- evidence;
- traceability;
- verification and validation;
- change governance;
- publication and confidentiality.

US006 implements the repository-level mechanisms used to apply those principles.

The relationship is therefore:

```text
US005 — Engineering Governance
        ↓
Principles, rules and evidence expectations
        ↓
US006 — Git Workflow & Versioning
        ↓
Branches, commits, versions, merges and releases
```

Git is an engineering control mechanism, not an objective by itself.

A Git operation must remain subordinate to the engineering intent of the change.

The workflow follows the MBSA Lab principles of practicality, simplicity, engineering rigor, reproducibility, incremental development, transparency, open learning, industrial relevance, tool independence and long-term product thinking.

---

## 4. Repository Model

### 4.1 Public engineering repository

`MBSA-Lab-OS` is the public living engineering repository of MBSA Lab.

It contains public, reproducible engineering artefacts such as:

- documentation;
- architecture;
- patterns;
- POCs;
- engineering workflows;
- educational material;
- future tooling and implementation artefacts.

### 4.2 Private control repository

Private control information belongs outside `MBSA-Lab-OS`, in the private control environment represented by:

`MBSA-Lab-Control`

The following must not be committed to the public repository unless explicitly approved for publication:

- private Master Plan;
- confidential information;
- private CV variants;
- private contacts;
- unpublished commercial plans;
- credentials;
- access tokens;
- secrets;
- other private control artefacts.

### 4.3 Remote

The operational remote is:

`origin`

Expected repository:

`https://github.com/adamkarimimbsalab/MBSA-Lab-OS.git`

The validated authentication mode is HTTPS with Git Credential Manager.

SSH is not a required dependency for the MBSA Lab workflow.

---

## 5. Branch Strategy

### 5.1 Main branch

`main` is the stable integration branch.

It represents the current integrated state of the public repository.

Changes must not be developed directly on `main` for normal User Story implementation.

`main` should remain:

- coherent;
- buildable or structurally valid for the repository content concerned;
- traceable;
- free of unfinished User Story work;
- synchronized with `origin/main` after an integration operation.

### 5.2 Feature branches

Each User Story is implemented in a dedicated feature branch.

The operational pattern is:

```text
main
  ↓
feature/USxxx-short-description
  ↓
implementation
  ↓
validation
  ↓
commit
  ↓
push
  ↓
controlled merge
  ↓
main
```

For US006, the dedicated branch is:

`feature/US006-git-workflow-versioning`

### 5.3 One User Story, one implementation branch

A feature branch should normally correspond to one User Story.

This provides:

- clear scope;
- isolated changes;
- simpler review;
- traceable commits;
- controlled integration;
- easier rollback or diagnosis.

Unrelated changes must not be mixed into the User Story branch.

### 5.4 Branch creation baseline

A feature branch must be created from a validated and synchronized `main`.

Before creating a branch:

```powershell
git switch main
git pull --ff-only origin main
git status
```

The working tree must be clean unless an explicitly approved workflow requires otherwise.

### 5.5 Existing branches

Existing historical branches are not automatically modified or deleted as part of a new User Story.

Branch cleanup is governed by the lifecycle rules below and must not rewrite or damage historical project evidence.

---

## 6. Branch Naming Convention

The standard User Story branch naming convention is:

```text
feature/US<NNN>-<short-description>
```

Examples:

```text
feature/US006-git-workflow-versioning
feature/US007-issue-templates
feature/US008-pull-request-template
```

### Naming rules

A User Story branch name must:

- begin with `feature/`;
- contain the three-digit User Story identifier;
- use a concise English description;
- use lowercase letters for the description;
- use hyphens instead of spaces;
- avoid unnecessary punctuation;
- remain stable for the lifetime of the User Story.

Do not create multiple competing branch names for the same User Story unless a documented correction requires it.

---

## 7. Branch Lifecycle

The standard lifecycle is:

```text
1. Validate main
        ↓
2. Create feature branch
        ↓
3. Implement scoped change
        ↓
4. Validate locally
        ↓
5. Commit
        ↓
6. Push feature branch
        ↓
7. Verify remote state
        ↓
8. Synchronize main
        ↓
9. Merge with --no-ff
        ↓
10. Validate merge
        ↓
11. Push main
        ↓
12. Verify main = origin/main
        ↓
13. Apply branch cleanup policy
```

### 7.1 Branch completion

A feature branch is considered complete when:

- its User Story deliverables are implemented;
- local validation is complete;
- the relevant commit(s) are pushed;
- the branch has been integrated into `main`;
- the final `main` state has been verified.

### 7.2 Branch deletion

Feature branches may be deleted after successful integration when they are no longer required.

Deletion is a lifecycle operation, not a requirement for merge completion.

Before deleting a branch, ensure:

- the branch has been merged;
- its commits remain reachable from `main`;
- the final merge has been pushed;
- no unfinished work remains on the branch.

A local deletion may be performed with:

```powershell
git branch -d <branch-name>
```

If the remote branch is also to be deleted:

```powershell
git push origin --delete <branch-name>
```

Remote cleanup should only be performed when the branch lifecycle policy calls for it.

---

## 8. Commit Convention

Commits must provide a concise and traceable description of the change.

The convention is derived from the existing MBSA Lab history and applies to new commits. Existing history must not be rewritten merely to conform to this convention.

### 8.1 User Story implementation commit

The standard format is:

```text
US<NNN> - <Description> v<MAJOR>.<MINOR>
```

Example:

```text
US006 - Git Workflow & Versioning v0.1
```

### 8.2 Additional corrective commit

A correction related to the same User Story may identify the correction explicitly.

Example:

```text
US006 - Correct versioning rules v0.1
```

The exact description should remain short and describe the actual change.

### 8.3 Merge commit

Controlled User Story integration uses an explicit non-fast-forward merge.

Standard format:

```text
Merge US<NNN> - <Description>
```

Example:

```text
Merge US006 - Git Workflow & Versioning
```

### 8.4 Commit rules

A commit should:

- correspond to an identifiable engineering change;
- remain within the active User Story scope;
- avoid unrelated modifications;
- be understandable without inspecting every line;
- preserve traceability to the relevant User Story.

Do not amend or rewrite already integrated historical commits merely to improve naming consistency.

---

## 9. Commit Message Examples

### Valid

```text
US006 - Git Workflow & Versioning v0.1
```

```text
US006 - Correct release rules v0.1
```

```text
Merge US006 - Git Workflow & Versioning
```

### Invalid or discouraged

```text
update
```

Reason: no traceable scope.

```text
changes
```

Reason: no engineering meaning.

```text
US006
```

Reason: insufficient description.

```text
US006 - update everything
```

Reason: scope is unclear.

A commit message is not a substitute for the detailed engineering evidence contained in the artefact itself.

---

## 10. Versioning Strategy

MBSA Lab uses version identifiers to distinguish meaningful states of artefacts and releases.

Versioning must remain proportional to project maturity.

US006 intentionally does not introduce an unnecessarily complex software release-management system.

### 10.1 Document version

Documents may use semantic document versions such as:

```text
v0.1
v0.2
v1.0
```

For Sprint 1 foundation documents, `v0.x` indicates an evolving pre-baseline artefact.

Example:

```text
US006 - Git Workflow & Versioning v0.1
```

### 10.2 POC version

A POC may use its own version identifier when meaningful.

Example:

```text
POC v0.1
```

The POC version describes the state of the POC, not its Git commit.

### 10.3 Repository version

The repository does not require a standalone `VERSION` file at this stage unless a future release strategy explicitly introduces one.

The absence of a `VERSION` file must not be interpreted as absence of traceability.

Git commits and tags provide repository history.

### 10.4 Git commit identity

A Git commit SHA is an immutable Git object identifier.

Example:

```text
33c0e7b6188108c43c9254be58e76852f83e58a8
```

A commit SHA is not a product/document release version.

The two concepts must remain distinct:

```text
Document version → v0.1
Git commit       → immutable SHA
Release          → release identifier/tag
```

### 10.5 Version changes

A version should change when the content reaches a meaningful new state.

Minor edits that do not constitute a meaningful revision should not create artificial version proliferation.

---

## 11. Release Rules

### 11.1 Definition of a release

A release is a deliberately identified, validated state of `main` that is considered suitable as a stable project baseline for a defined purpose.

A release is not automatically created for every User Story.

### 11.2 Release prerequisites

Before creating a release:

1. intended changes must be integrated into `main`;
2. relevant validation must be complete;
3. `main` must be clean;
4. `main` must be synchronized with `origin/main`;
5. release contents must be identifiable;
6. release documentation must be available when required;
7. no known blocking issue may invalidate the intended baseline.

### 11.3 Release identifier

When a formal project release is introduced, the release should use a clear version identifier, for example:

```text
v0.1.0
```

The exact release numbering scheme may evolve with project maturity, but it must remain consistent once formally adopted.

### 11.4 Git tags

A release may be represented by an annotated Git tag.

Example:

```powershell
git tag -a v0.1.0 -m "MBSA Lab OS v0.1.0"
git push origin v0.1.0
```

A release tag must only be created when a release is actually intended.

US006 does not require creation of a release merely to demonstrate that tagging works.

### 11.5 Release evidence

A formal release should identify:

- release version;
- target commit;
- scope;
- validation status;
- relevant documentation;
- known limitations where applicable.

### 11.6 Rollback / correction

If a release or integrated state is found to be incorrect, correction must preserve traceability.

Normal correction strategy:

```text
identified problem
        ↓
new corrective change
        ↓
feature branch
        ↓
validation
        ↓
controlled merge
        ↓
new main state
```

Historical commits should not be rewritten on the shared remote merely to hide an error.

---

## 12. Merge Rules

### 12.1 Normal User Story merge

User Story branches are integrated into `main` using an explicit non-fast-forward merge:

```powershell
git merge --no-ff feature/US006-git-workflow-versioning -m "Merge US006 - Git Workflow & Versioning"
```

This preserves an explicit integration point in the repository history.

### 12.2 Preconditions

Before merge:

```powershell
git switch main
git pull --ff-only origin main
git status
```

The active User Story branch must contain the intended changes and no unrelated work.

### 12.3 Merge validation

After merge:

```powershell
git status
git log --oneline --decorate --graph -n 10
```

The result must confirm:

- merge completed;
- intended artefact is present;
- no unresolved conflict remains;
- working tree is clean.

### 12.4 Merge conflicts

If a conflict occurs:

1. do not force the merge;
2. identify conflicting files;
3. understand the intended change on both sides;
4. resolve deliberately;
5. inspect the result;
6. validate;
7. continue the merge only after the resolution is verified.

If the conflict cannot be resolved confidently, abort the merge and reassess:

```powershell
git merge --abort
```

---

## 13. Synchronization Rules

The authoritative remote is `origin`.

### 13.1 Before branch creation

```powershell
git fetch origin
git switch main
git pull --ff-only origin main
```

### 13.2 Before merge

The local `main` must be refreshed:

```powershell
git switch main
git pull --ff-only origin main
```

This reduces the risk of merging against a stale local baseline.

### 13.3 After feature push

Verify tracking:

```powershell
git branch -vv
```

and inspect history:

```powershell
git log --oneline --decorate --graph -n 10
```

### 13.4 After main push

Refresh the remote references:

```powershell
git fetch origin
```

Then verify:

```powershell
git rev-parse main
git rev-parse origin/main
```

The two values must be identical after a successful integration push.

### 13.5 Clean working tree

A completed workflow must end with:

```powershell
git status
```

showing a clean working tree.

---

## 14. Change and Correction Rules

### 14.1 Change during an active User Story

If the User Story changes while its branch is active:

1. confirm that the change remains within US scope;
2. update the affected artefact;
3. validate the change;
4. create a traceable commit;
5. continue the normal workflow.

If the requested change materially expands the User Story scope, stop and assess whether it belongs to another User Story.

### 14.2 Change outside scope

Do not add unrelated improvements merely because they are discovered during implementation.

Record or defer them to the appropriate future User Story.

Examples:

- Issue templates → US007;
- PR template → US008;
- repository/documentation conventions → US009;
- Sprint closure/baseline → US010.

### 14.3 Correction after merge

A defect discovered after merge should normally be corrected through a new change rather than by rewriting public history.

The correction must remain traceable.

### 14.4 Historical integrity

Do not rewrite shared history to make the project appear cleaner.

Existing commits are project evidence.

---

## 15. Operational Workflow

The following workflow is the standard MBSA Lab User Story execution pattern.

### Phase A — Audit

```powershell
cd D:\GRAZADAM\MBSA_LAB\00_MBSA_Lab_OS
git status
git branch --show-current
git remote -v
git fetch origin
git log --oneline --decorate --graph -n 15
git rev-parse main
git rev-parse origin/main
```

Confirm the baseline before modification.

### Phase B — Create User Story branch

```powershell
git switch main
git pull --ff-only origin main
git switch -c feature/US<NNN>-<short-description>
```

Verify:

```powershell
git status
git branch --show-current
```

### Phase C — Implement

Create or modify only the artefacts required by the active User Story.

For US006:

```text
docs/04_Git_Workflow_and_Versioning.md
```

is the dedicated deliverable.

### Phase D — Validate

At minimum:

```powershell
git status
git diff
git diff --check
```

Inspect the actual artefact and verify:

- scope;
- terminology;
- paths;
- commands;
- branch names;
- version examples;
- release rules;
- relationship with US005;
- boundaries with future User Stories;
- absence of private information.

### Phase E — Commit

Stage only intended files:

```powershell
git status --short
git add <intended-files>
git diff --cached --check
git diff --cached --stat
git diff --cached
```

Then commit using the applicable convention.

### Phase F — Push

```powershell
git push -u origin feature/US<NNN>-<short-description>
```

Verify the remote tracking state.

### Phase G — Integrate

```powershell
git switch main
git pull --ff-only origin main
git log main..feature/US<NNN>-<short-description> --oneline
git merge --no-ff feature/US<NNN>-<short-description> -m "Merge US<NNN> - <Description>"
```

### Phase H — Finalize

```powershell
git status
git push origin main
git fetch origin
git rev-parse main
git rev-parse origin/main
git log --oneline --decorate --graph -n 12
```

Confirm:

```text
main = origin/main
working tree = clean
```

---

## 16. Compliance Checklist

Before declaring a User Story integrated, verify:

### Branch governance

- [ ] correct User Story branch exists;
- [ ] branch was created from a validated `main`;
- [ ] branch naming convention is respected;
- [ ] unrelated changes are absent;
- [ ] branch lifecycle is documented or understood.

### Commit governance

- [ ] User Story is identifiable in commit message;
- [ ] commit description is meaningful;
- [ ] version identifier is used where applicable;
- [ ] merge commit is identifiable;
- [ ] historical commits were not rewritten unnecessarily.

### Versioning

- [ ] document version is distinct from Git SHA;
- [ ] POC version is distinct from repository history;
- [ ] release version is distinct from commit identity;
- [ ] version changes are meaningful.

### Release governance

- [ ] release is created only when intentionally required;
- [ ] release target is a validated `main`;
- [ ] release identifier is unambiguous;
- [ ] tag, when used, points to the intended release commit;
- [ ] release evidence is available.

### Integration

- [ ] local validation is complete;
- [ ] `git diff --check` is clean;
- [ ] feature branch was pushed;
- [ ] remote state was verified;
- [ ] `main` was refreshed before merge;
- [ ] merge used the controlled `--no-ff` workflow;
- [ ] merge was validated;
- [ ] `main` was pushed;
- [ ] `main` and `origin/main` are synchronized;
- [ ] working tree is clean.

### Governance alignment

- [ ] workflow is consistent with US005;
- [ ] public/private repository boundaries are respected;
- [ ] US006 remains limited to Git Workflow & Versioning;
- [ ] US007–US010 responsibilities are not absorbed.

---

## 17. US006 Acceptance Criteria

| ID | Acceptance Criterion | Verification |
|---|---|---|
| AC-01 | Git workflow is documented | Document review |
| AC-02 | Branch strategy is defined | Section 5 |
| AC-03 | Branch naming convention is defined | Section 6 |
| AC-04 | Commit convention is defined | Section 8 |
| AC-05 | Valid commit examples are provided | Section 9 |
| AC-06 | Versioning strategy is defined | Section 10 |
| AC-07 | Release rules are defined | Section 11 |
| AC-08 | Merge rules are defined | Section 12 |
| AC-09 | Synchronization rules are defined | Section 13 |
| AC-10 | Workflow is consistent with Engineering Governance | Section 3 + review against US005 |
| AC-11 | US006 does not absorb US007–US010 | Section 2 + review |
| AC-12 | Sprint 1 documentation conventions are respected | Document review |
| AC-13 | No private control information is introduced | Repository review |
| AC-14 | Local Git validation is completed | `git diff --check`, status |
| AC-15 | US006 branch is pushed | Remote verification |
| AC-16 | US006 is integrated using controlled merge | Merge history |
| AC-17 | `main` is synchronized with `origin/main` | SHA comparison |
| AC-18 | Working tree is clean after integration | `git status` |

---

## 18. Relationship with the MBSA Lab Engineering Pattern

Git workflow supports the MBSA Lab evidence chain:

```text
CV claim
   ↓
MBSA Lab evidence
   ↓
POC
   ↓
Architecture / Model
   ↓
Implementation
   ↓
Validation
   ↓
Video
   ↓
GitHub artefact
   ↓
Professional discussion
```

Git provides traceability and reproducibility across this chain.

It does not replace engineering validation.

A Git commit proves that a change was recorded; it does not, by itself, prove that the engineering content is correct.

---

## 19. Relationship with the V-Cycle

The Git workflow supports the V-cycle by providing controlled evidence for engineering changes.

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

Git workflow contributes primarily to:

- change identification;
- configuration traceability;
- reproducibility;
- evidence preservation;
- controlled integration.

Engineering verification and validation remain separate activities.

---

## 20. Operational Reference — US006

US006 is implemented on:

```text
feature/US006-git-workflow-versioning
```

The expected deliverable is:

```text
docs/04_Git_Workflow_and_Versioning.md
```

The expected implementation sequence is:

```text
Validated main
    ↓
US006 feature branch
    ↓
Document implementation
    ↓
Local validation
    ↓
US006 commit
    ↓
Feature push
    ↓
Remote verification
    ↓
main synchronization
    ↓
--no-ff merge
    ↓
main validation
    ↓
origin/main synchronization
```

No release is created automatically by completing US006.

No historical Git commit is rewritten.

No private control artefact is added to the public repository.

US006 is complete only when its acceptance criteria and definition of done are satisfied by actual repository evidence.
