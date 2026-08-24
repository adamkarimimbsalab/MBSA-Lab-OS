# MBSA Lab — Git Workflow and Versioning

## 1. Purpose

This document defines the public Git and versioning policy for MBSA Lab engineering artefacts. Its objectives are controlled change, readable history, reproducible baselines, and clear release identity.

It intentionally excludes workstation-specific paths, private orchestration, and historical transaction logs.

## 2. Scope

The policy applies to version-controlled public source, documentation, configuration, tests, evidence references, patterns, and release metadata.

## 3. Repository model

The public repository contains material suitable for public engineering use. Private administration, unpublished working material, credentials, personal data, and confidential evidence remain outside it.

The remote repository is the shared integration reference. A local checkout is not authoritative when it diverges from the accepted remote baseline.

## 4. Branch strategy

### 4.1 Main branch

`main` represents the current accepted public baseline. Direct uncontrolled changes to `main` are prohibited.

### 4.2 Change branches

Material changes use a dedicated branch created from the current accepted baseline. A branch should address one coherent objective and remain short-lived.

Recommended forms include:

```text
feature/<scope>
fix/<scope>
maintenance/<scope>
```

Names should be concise, lowercase where practical, and free of sensitive information.

### 4.3 Branch lifecycle

1. confirm the accepted baseline and clean working state;
2. create the change branch;
3. implement within the approved scope;
4. inspect the diff and run relevant checks;
5. commit the coherent change;
6. review and integrate it;
7. verify the resulting baseline;
8. remove obsolete branches when retention is unnecessary.

## 5. Commit policy

A commit should represent one coherent engineering change. Its message should state the purpose rather than reproduce internal execution detail.

Recommended structure:

```text
<type> - <concise engineering purpose>
```

Examples:

```text
DOC - Clarify evidence package lifecycle
FIX - Correct traceability relationship semantics
MAINT - Normalize public documentation baseline
```

Commits must not include credentials, personal or confidential data, environment-specific administration, or unrelated generated files.

## 6. Integration policy

Integration requires:

- an explicit and reviewed scope;
- relevant verification evidence;
- no unresolved blocking finding;
- controlled conflicts, if any;
- a clean resulting worktree;
- confirmation that the accepted branch points to the intended result.

A non-fast-forward merge may be used when preserving a distinct change boundary improves traceability. The integration strategy should remain consistent and reviewable.

## 7. Version identity

Several identities may coexist and must not be confused:

- document version — the declared maturity of one document;
- artefact version — the identity of a model, implementation, test, or package;
- commit identity — the immutable Git object containing a change;
- baseline identity — the accepted set of mutually consistent artefacts;
- release identifier — the externally communicated version of an approved release.

A Git commit identifies content; it does not by itself prove review, acceptance, safety, or publication authorization.

## 8. Release policy

A release is a deliberately identified and approved baseline intended for use outside the active development context.

Release prerequisites include:

- defined content and intended use;
- completed applicable quality gates;
- known limitations and residual risks;
- traceability to source and evidence;
- rights and publication review;
- competent release authority.

Published releases are immutable. Corrections use a new version, erratum, supersession, or withdrawal record rather than silent replacement.

## 9. Synchronization and baseline checks

Before creating or integrating a change, confirm:

- the current branch is intended;
- the local baseline matches the accepted integration baseline;
- remote references are current;
- ahead/behind state is understood;
- the worktree and staging area contain no unrelated changes.

These checks are objectives, not a mandate for one operating system or command shell.

## 10. Scope and diff quality

Review must consider:

- changed paths;
- semantic changes;
- whitespace and encoding changes;
- generated or binary content;
- accidental removal or disclosure;
- effects on cross-references and evidence.

Large mechanical and semantic changes should be separated when practical so that each can be reviewed independently.

## 11. Corrections and historical integrity

Do not rewrite accepted shared history merely to hide an error. Correct defects through a traceable follow-up unless an exceptional security or legal reason requires controlled history rewriting.

Out-of-scope defects are recorded and handled separately. They must not be corrected opportunistically when doing so would obscure the approved change.

## 12. Tags and releases

Tags may identify approved releases. Annotated tags are preferred when release context, authority, and limitations must be retained.

Tag names should follow a stable project convention and must not imply a maturity level that has not been demonstrated.

## 13. Portability

Public procedures should avoid dependencies on one local directory, user account, shell, or workstation. Commands may be provided as examples, but the governing requirement is the verifiable outcome.

## 14. Compliance checklist

- branch created from the intended baseline;
- change limited to approved scope;
- commit coherent and free of private data;
- relevant tests and reviews complete;
- version and baseline identities unambiguous;
- release claims supported by evidence;
- integration result verified;
- supersession or withdrawal controlled where applicable.
