# Repository & Documentation Conventions

**Document:** `docs/05_Repository_and_Documentation_Conventions.md`\
**Repository:** `MBSA-Lab-OS`\
**User Story:** US009 --- Repository / Documentation Conventions\
**Sprint:** Sprint 1\
**Purpose:** Establish the authoritative repository-structure,
documentation, naming, placement, text-format, publication-boundary, and
repository-hygiene conventions for MBSA Lab OS.

------------------------------------------------------------------------

## 1. Purpose

This document defines the authoritative repository and documentation
conventions for the public MBSA Lab engineering repository.

It converts the engineering principles established by
`docs/03_Engineering_Governance.md` and the repository workflow
established by `docs/04_Git_Workflow_and_Versioning.md` into explicit
rules governing:

1.  repository structure;
2.  artefact placement;
3.  documentation organization;
4.  file and directory naming;
5.  Markdown conventions;
6.  text encoding and line endings;
7.  Git text normalization;
8.  public/private repository boundaries;
9.  repository hygiene;
10. traceability between repository artefacts;
11. creation and evolution of repository directories;
12. conventions for GitHub contribution artefacts;
13. consistency checks for new repository content;
14. exceptions and controlled evolution of these conventions.

The objective is not to redesign the repository.

The objective is to make the repository predictable, understandable,
maintainable, reviewable, reproducible, and suitable for progressive
engineering growth.

US009 therefore establishes conventions for future work while preserving
the validated history and artefacts produced by US001 through US008.

------------------------------------------------------------------------

## 2. Scope

### 2.1 Repository in scope

These conventions apply to the public engineering repository:

`MBSA-Lab-OS`

They apply to new and modified repository content unless a more specific
approved convention governs a particular subsystem.

### 2.2 Artefacts in scope

The conventions apply, as relevant, to:

-   root-level repository files;
-   Markdown documentation;
-   GitHub Issue templates;
-   Pull Request templates;
-   YAML configuration;
-   source directories;
-   architecture artefacts;
-   examples;
-   patterns;
-   scripts;
-   templates;
-   tools;
-   academy material;
-   video-related repository material;
-   website-related repository material;
-   wiki-related repository material;
-   roadmap artefacts;
-   future engineering and POC artefacts;
-   future workflow definitions.

### 2.3 Out of scope

US009 does not redefine:

-   engineering governance established by US005;
-   Git branch, commit, merge, versioning, and release rules established
    by US006;
-   Issue workflow semantics established by US007;
-   Pull Request review semantics established by US008;
-   Sprint 1 closure and governance baseline, which belongs to US010;
-   product-specific architecture conventions not yet introduced;
-   language-specific source-code style rules not yet required;
-   CI/CD implementation;
-   release automation;
-   repository-wide historical rewriting merely for stylistic
    uniformity.

### 2.4 Governing relationship

The intended hierarchy is:

``` text
US005 — Engineering Governance
    ↓
US006 — Git Workflow & Versioning
    ↓
US007 — Issue Templates
    ↓
US008 — Pull Request Template
    ↓
US009 — Repository & Documentation Conventions
    ↓
US010 — Sprint 1 Closure & Governance Baseline
```

US009 must remain compatible with all preceding layers.

------------------------------------------------------------------------

## 3. Governing Principles

### 3.1 Convention over ambiguity

A contributor should be able to determine where an artefact belongs and
how it should be named without inventing a new repository structure for
every change.

### 3.2 Preserve engineering meaning

Repository organization exists to support engineering work.

Structure, naming, and formatting must not replace engineering
reasoning, evidence, verification, validation, or traceability.

### 3.3 Evidence over assumption

Repository state must be verified using actual files, Git state, or
other appropriate evidence.

A directory shown in a local filesystem is not necessarily a versioned
repository artefact.

A Git commit proves that a change was recorded; it does not prove that
its engineering content is correct.

### 3.4 Minimal necessary structure

Do not introduce directories, indexes, metadata, or conventions without
a concrete purpose.

Empty local directories must not be interpreted as Git-managed
structure.

### 3.5 Stable public baseline

`main` remains the stable integration branch as defined by US006.

Repository conventions must support a clean, understandable integrated
state.

### 3.6 Progressive evolution

The repository may evolve as MBSA Lab matures.

Evolution must be deliberate, traceable, scoped, and compatible with
existing governance.

### 3.7 Public by deliberate curation

The public repository is not a dumping ground for all project material.

Publication must respect the confidentiality and public/private
boundaries defined by Engineering Governance.

### 3.8 No unnecessary historical rewriting

Existing integrated commits and historical artefacts are project
evidence.

Do not rewrite history merely to make older content conform
aesthetically to newer conventions.

------------------------------------------------------------------------

## 4. Repository Model

### 4.1 Public engineering repository

`MBSA-Lab-OS` is the public living engineering repository.

It may contain:

-   project orientation;
-   engineering governance;
-   Git workflow rules;
-   repository conventions;
-   public documentation;
-   public architecture material;
-   reusable patterns;
-   examples;
-   public POCs and supporting artefacts;
-   public educational material;
-   public tooling;
-   GitHub contribution mechanisms.

### 4.2 Private control material

Private project-control material does not belong in the public
repository.

The public/private boundary defined in
`docs/03_Engineering_Governance.md` remains authoritative.

Examples of material that must not be introduced into the public
repository without explicit publication approval include:

-   confidential industrial information;
-   customer-confidential information;
-   secrets or credentials;
-   private contacts;
-   private personal information;
-   private CV variants;
-   private project-control information.

Private control material belongs in the appropriate private control
repository, identified by Engineering Governance as `MBSA-Lab-Control`.

### 4.3 Publication decision

Before introducing an artefact into `MBSA-Lab-OS`, verify:

1.  that the artefact belongs to the public engineering scope;
2.  that its technical content is appropriate for publication;
3.  that confidential information is excluded;
4.  that secrets and private information are excluded;
5.  that the artefact is understandable for its intended audience;
6.  that the evidence supporting its claims is proportionate;
7.  that its repository placement is appropriate.

------------------------------------------------------------------------

## 5. Current Versioned Repository Baseline

At the time US009 was prepared, the versioned repository baseline
included the following principal files:

``` text
.gitattributes
.gitignore
CHANGELOG.md
LICENSE
README.md

.github/
    ISSUE_TEMPLATE/
        bug_report.md
        config.yml
        engineering_task.md
        feature_request.md
    PULL_REQUEST_TEMPLATE.md

docs/
    00_Project_Overview.md
    01_Vision.md
    02_Mission.md
    03_Engineering_Governance.md
    04_Git_Workflow_and_Versioning.md
```

US009 adds:

``` text
docs/05_Repository_and_Documentation_Conventions.md
```

This baseline is descriptive evidence of the repository at US009.

It must not be interpreted as a permanent prohibition on future files or
directories.

------------------------------------------------------------------------

## 6. Repository Root Conventions

### 6.1 Root purpose

The repository root is reserved for repository-wide entry points,
controls, metadata, and universally relevant files.

### 6.2 Root-level files

Examples of legitimate root-level files include:

-   `README.md`;
-   `LICENSE`;
-   `CHANGELOG.md`;
-   `.gitignore`;
-   `.gitattributes`;
-   future repository-wide configuration files when justified.

### 6.3 Avoid root clutter

Domain-specific documents should not be placed at the root merely for
convenience.

Prefer a domain-appropriate directory such as:

-   `docs/`;
-   `.github/`;
-   `architecture/`;
-   `patterns/`;
-   `examples/`;
-   `scripts/`;
-   `templates/`;
-   `tools/`.

### 6.4 Root changes require repository-wide relevance

A new root-level file should have repository-wide significance.

If its purpose is local to a subsystem, place it in the relevant
subsystem.

------------------------------------------------------------------------

## 7. Directory Conventions

### 7.1 Existing top-level directory intent

The local repository structure observed during US009 included the
following top-level directories:

``` text
.github/
academy/
architecture/
assets/
docs/
examples/
patterns/
plugin/
roadmap/
scripts/
templates/
tools/
videos/
website/
wiki/
```

Some of these directories were empty locally at the time of inspection.

### 7.2 Git and empty directories

Git does not version empty directories.

Therefore:

-   an empty local directory is not repository evidence by itself;
-   repository documentation must not claim that an empty directory is
    part of the versioned baseline unless a tracked artefact establishes
    it;
-   a directory becomes materially represented in Git when it contains a
    tracked file.

### 7.3 Creating a new directory

Create a new directory only when:

1.  a real artefact needs that location;
2.  its purpose is clear;
3.  no existing directory is more appropriate;
4.  its name is consistent with repository conventions;
5.  the change remains within the active User Story scope.

### 7.4 Placeholder files

Do not create `.gitkeep` or equivalent placeholder files merely to make
a speculative directory visible in Git.

A placeholder is acceptable only when retaining an otherwise empty
directory is an explicit engineering requirement.

### 7.5 Directory ownership

A directory should have one understandable primary purpose.

Avoid directories whose scope overlaps ambiguously with existing
directories.

### 7.6 Nested documentation directories

The local `docs/` tree observed during US009 included empty domain
directories such as:

``` text
docs/academy/
docs/architecture/
docs/business/
docs/engineering/
docs/patterns/
docs/plugin/
docs/poc_factory/
docs/roadmap/
docs/video_factory/
docs/vision/
docs/website/
```

These local empty directories must not be treated as versioned baseline
until tracked content is introduced.

Future use should be driven by actual documentation needs.

------------------------------------------------------------------------

## 8. Documentation Architecture

### 8.1 Markdown as documentation source

The Project Overview establishes Markdown as the Single Source of
Documentation.

Accordingly, repository-native engineering documentation should normally
be authored in Markdown.

### 8.2 `docs/` as primary engineering documentation area

The `docs/` directory is the primary location for repository-level
engineering documentation.

### 8.3 Foundational document sequence

Sprint 1 foundational documents use an ordered numeric prefix:

``` text
00_Project_Overview.md
01_Vision.md
02_Mission.md
03_Engineering_Governance.md
04_Git_Workflow_and_Versioning.md
05_Repository_and_Documentation_Conventions.md
```

The numeric prefix expresses intentional reading and governance order.

### 8.4 Numeric prefix rules

For this foundational sequence:

-   use two digits;
-   preserve existing numbering;
-   do not renumber historical documents merely to insert new material;
-   allocate new numbers deliberately;
-   do not reuse an existing number for a different foundational
    document.

### 8.5 Domain documentation

Domain-specific documentation should be placed in an appropriate domain
location when the domain becomes materially populated.

Do not create duplicate copies of the same authoritative information in
multiple directories.

### 8.6 Single authoritative source

For a governed rule, prefer one authoritative source and reference it
elsewhere.

Avoid maintaining competing copies of the same normative content.

### 8.7 Cross-document references

When one document depends on another repository document, use a
repository-relative path in backticks, for example:

`docs/03_Engineering_Governance.md`

References should identify the authoritative artefact rather than
reproduce large blocks unnecessarily.

------------------------------------------------------------------------

## 9. Documentation Content Conventions

### 9.1 Purpose first

A substantial engineering document should make its purpose explicit near
the beginning.

### 9.2 Scope

Where relevant, distinguish:

-   what the document governs;
-   what it does not govern;
-   interfaces with adjacent governance artefacts.

### 9.3 Facts, decisions, assumptions, and evidence

Engineering documentation must not blur:

-   verified facts;
-   design or governance decisions;
-   assumptions;
-   expected results;
-   actual evidence;
-   limitations.

### 9.4 Evidence-first language

Do not state that an operation succeeded unless there is evidence
supporting the statement.

Examples:

-   do not invent a commit SHA;
-   do not state that a branch was pushed without remote evidence;
-   do not state that `main = origin/main` without verification;
-   do not state that a GitHub behavior was validated if it was not
    actually observed.

### 9.5 Verification and validation

Where applicable, documentation should distinguish verification from
validation in accordance with Engineering Governance.

### 9.6 Limitations

Known limitations or unverified claims must be explicit.

Absence of evidence must not be represented as evidence of correctness.

### 9.7 Operational material

Commands intended to be executed should be:

-   explicit;
-   reproducible;
-   scoped;
-   reviewed for destructive effects;
-   consistent with the actual repository path when a concrete path is
    intentionally documented.

### 9.8 Avoid accidental environment corruption

Special care is required when embedding command paths or shell snippets.

Invisible or binary characters must not be allowed to corrupt executable
examples.

------------------------------------------------------------------------

## 10. Markdown Conventions

### 10.1 Extension

Markdown files use:

``` text
.md
```

### 10.2 Headings

Use Markdown ATX headings:

``` text
# Heading 1
## Heading 2
### Heading 3
```

### 10.3 Heading hierarchy

Use headings hierarchically.

Do not skip levels without a structural reason.

### 10.4 One primary title

A substantial standalone document should normally contain one level-1
title.

### 10.5 Numbered sections

Foundational governance documents may use numbered level-2 sections to
improve navigation and traceability.

Example:

``` text
## 1. Purpose
## 2. Scope
## 3. Principles
```

### 10.6 Lists

Use Markdown lists for sets of related items.

Prefer ordered lists where sequence matters and unordered lists where it
does not.

### 10.7 Checklists

Use task lists when they represent actionable acceptance, readiness,
review, or compliance checks.

Example:

``` text
- [ ] Repository scope is correct.
- [ ] Documentation impact has been assessed.
```

### 10.8 Tables

Use Markdown tables when they improve comparison or traceability.

Avoid tables when ordinary prose or a list is clearer.

### 10.9 Code

Use inline backticks for:

-   file paths;
-   branch names;
-   commands referenced in prose;
-   Git identifiers;
-   configuration keys.

Use fenced code blocks for multi-line commands, examples, structures, or
configuration.

### 10.10 PowerShell blocks

Use:

```` text
```powershell
git status
```
````

when presenting PowerShell commands in documentation.

### 10.11 Repository trees

Use fenced text blocks for repository structures.

### 10.12 Links and references

Prefer stable repository-relative references for internal artefacts.

Avoid links whose only purpose is decorative.

### 10.13 Whitespace

Avoid trailing whitespace.

`git diff --check` should pass before a change is committed.

------------------------------------------------------------------------

## 11. File Naming Conventions

### 11.1 General principle

A filename should communicate the artefact's purpose without requiring
the reader to open it.

### 11.2 Foundational documentation

Foundational documentation uses:

``` text
NN_Descriptive_Name.md
```

where:

-   `NN` is the two-digit sequence;
-   words are separated by underscores;
-   major words use readable title-style capitalization;
-   the extension is lowercase `.md`.

Examples:

``` text
03_Engineering_Governance.md
04_Git_Workflow_and_Versioning.md
05_Repository_and_Documentation_Conventions.md
```

### 11.3 GitHub templates

GitHub Issue template filenames use descriptive lowercase snake_case:

``` text
bug_report.md
feature_request.md
engineering_task.md
```

GitHub configuration uses the platform-recognized filename:

``` text
config.yml
```

The repository-level Pull Request template uses:

``` text
PULL_REQUEST_TEMPLATE.md
```

because that name has platform meaning and is already established.

### 11.4 Do not rename platform-defined artefacts for stylistic uniformity

Platform conventions take precedence where GitHub requires or recognizes
a specific path or filename.

### 11.5 New filenames

For new files:

-   use clear English names;
-   avoid spaces unless an external standard requires them;
-   avoid ambiguous abbreviations;
-   avoid temporary names such as `final`, `final2`, `new`, or `test`
    for governed artefacts;
-   avoid embedding dates in filenames unless the artefact is genuinely
    date-based;
-   use versions in filenames only when there is a defined reason to
    maintain multiple file versions side by side.

------------------------------------------------------------------------

## 12. Directory Naming Conventions

### 12.1 General form

Repository directories should use concise, descriptive lowercase names.

Existing examples include:

``` text
docs
architecture
examples
patterns
scripts
templates
tools
website
```

### 12.2 Multi-word directories

Where a multi-word directory is required, use lowercase snake_case
unless a platform or subsystem imposes another convention.

Existing local examples include:

``` text
poc_factory
video_factory
```

### 12.3 Avoid case-only distinctions

Do not create paths that differ only by case.

The repository must remain usable across case-sensitive and
case-insensitive filesystems.

### 12.4 Avoid spaces in repository paths

Do not introduce spaces in new repository directory names unless
required by an external tool.

------------------------------------------------------------------------

## 13. GitHub Repository Artefact Conventions

### 13.1 `.github/`

GitHub-specific contribution and automation artefacts belong under
`.github/`.

### 13.2 Issue templates

Issue templates belong under:

``` text
.github/ISSUE_TEMPLATE/
```

The established categories are:

1.  Bug Report;
2.  Feature Request;
3.  Engineering Task.

Do not collapse these categories without an explicit governance
decision.

### 13.3 Issue template engineering structure

The existing templates establish recurring concepts including:

-   context;
-   objective or summary;
-   scope;
-   affected artefacts;
-   evidence;
-   acceptance criteria;
-   verification/validation;
-   traceability;
-   dependencies;
-   risks/limitations.

Future template changes should preserve compatibility with Engineering
Governance.

### 13.4 Pull Request template

The repository Pull Request template belongs at:

``` text
.github/PULL_REQUEST_TEMPLATE.md
```

It structures:

-   summary;
-   related Issue/User Story;
-   scope;
-   changes;
-   affected artefacts;
-   engineering impact;
-   verification;
-   validation;
-   acceptance criteria;
-   evidence and traceability;
-   risks and limitations;
-   documentation impact;
-   publication/confidentiality;
-   review and merge readiness;
-   reviewer notes.

### 13.5 Scope separation

Issue Templates and Pull Request Template have different
responsibilities.

Issue templates structure the entry and definition of work.

The Pull Request template structures review and integration readiness.

Repository/documentation conventions define how the resulting artefacts
are organized.

Do not merge these responsibilities.

------------------------------------------------------------------------

## 14. Text Encoding Convention

### 14.1 Repository text encoding

New repository text files should use UTF-8.

UTF-8 without BOM is preferred for repository-native text unless a tool
explicitly requires another encoding.

### 14.2 Why encoding is explicit

Text encoding must not be left to accidental editor defaults.

Inconsistent encoding can cause:

-   unreadable characters;
-   corrupted command examples;
-   false binary detection;
-   noisy diffs;
-   cross-platform inconsistencies.

### 14.3 Binary content

Binary artefacts must not be forced through text normalization.

Future binary types should be classified explicitly in `.gitattributes`
when needed.

### 14.4 Validation

When text corruption is suspected, inspect the actual bytes rather than
relying only on terminal rendering.

------------------------------------------------------------------------

## 15. Line Ending Convention

### 15.1 Canonical repository line ending

Canonical repository text uses LF line endings.

### 15.2 Rationale

A canonical LF baseline provides:

-   deterministic Git storage;
-   cross-platform consistency;
-   reduced diff noise;
-   predictable Markdown/YAML behavior;
-   clearer repository diagnostics.

### 15.3 Windows working trees

A Windows working tree may display CRLF depending on Git and editor
behavior.

The authoritative concern is that repository normalization is explicit
and that the Git index stores normalized text consistently.

### 15.4 `core.autocrlf`

Developer-local `core.autocrlf` settings must not be the repository's
only line-ending policy.

Repository-level `.gitattributes` is authoritative for tracked content
covered by its rules.

------------------------------------------------------------------------

## 16. `.gitattributes` Baseline

US009 establishes the following repository text-normalization baseline:

``` gitattributes
* text=auto
.gitattributes text eol=lf
.gitignore text eol=lf
*.md text eol=lf
*.yml text eol=lf
*.yaml text eol=lf
*.txt text eol=lf
```

### 16.1 Meaning

`* text=auto`

allows Git to classify ordinary content automatically unless a more
specific rule applies.

`.gitattributes text eol=lf`

ensures that `.gitattributes` is text with canonical LF.

`.gitignore text eol=lf`

ensures that `.gitignore` is text with canonical LF.

`*.md text eol=lf`

normalizes Markdown.

`*.yml text eol=lf`

and

`*.yaml text eol=lf`

normalize YAML.

`*.txt text eol=lf`

normalizes plain-text artefacts.

### 16.2 Future extensions

Add explicit rules when new text or binary formats become materially
relevant.

Do not expand `.gitattributes` speculatively without a repository need.

### 16.3 No blind global renormalization

Introducing `.gitattributes` does not require an uncontrolled
repository-wide rewrite.

A global command such as:

``` powershell
git add --renormalize .
```

must not be executed automatically merely because `.gitattributes` was
added.

If repository-wide renormalization becomes necessary, treat it as a
deliberate scoped change with diff review and evidence.

------------------------------------------------------------------------

## 17. Repository Hygiene Rules

### 17.1 Working tree awareness

Before modifying repository structure:

``` powershell
git status
```

must be used to understand the current state.

### 17.2 Scope control

A User Story should contain only changes required by its scope, except
when a directly blocking defect is discovered and the corrective action
is explicitly documented and traceable.

### 17.3 Diff quality

Before commit:

``` powershell
git diff --check
```

and, after staging:

``` powershell
git diff --cached --check
```

should produce no whitespace errors.

### 17.4 Tracked-file awareness

Use Git to distinguish versioned repository state from local filesystem
state.

Useful commands include:

``` powershell
git ls-files
git status --short
git ls-files --eol
```

### 17.5 Do not infer versioned structure from `tree`

Filesystem commands such as `tree` show local directories, including
untracked and empty directories.

Use them for inspection, not as sole proof of Git-managed repository
structure.

### 17.6 Avoid unrelated cleanup

Do not opportunistically rewrite unrelated files during a scoped User
Story merely to make formatting uniform.

### 17.7 Historical artefacts

Do not amend or rewrite already integrated historical commits merely to
improve naming or formatting consistency.

Correct forward with a traceable commit when correction is required.

------------------------------------------------------------------------

## 18. US009 Repository Hygiene Finding and Corrective Baseline

### 18.1 Context

During the US009 repository audit, the repository had:

``` text
core.autocrlf=true
```

and no `.gitattributes` file.

The working tree showed heterogeneous line-ending states.

### 18.2 Detected anomaly

`git ls-files --eol` identified:

``` text
docs/04_Git_Workflow_and_Versioning.md
```

as:

``` text
i/-text w/-text
```

before the US009 correction.

This was anomalous for a Markdown document.

### 18.3 Byte-level investigation

Binary inspection showed that the file contained exactly one NUL byte.

The NUL byte was located at byte offset:

``` text
16007
```

The file size before correction was:

``` text
22848 bytes
```

### 18.4 Safe backup

Before repair, a byte-for-byte backup was created outside the repository
working tree.

### 18.5 Controlled repair

The repair removed only the NUL byte using byte-level processing.

After repair:

``` text
file size = 22847 bytes
NUL count = 0
```

### 18.6 Proof of minimal modification

A byte-level comparison reconstructed the expected file by removing only
NUL bytes from the backup and compared it with the repaired file.

The comparison returned:

``` text
True
```

This proved that the binary repair itself removed only the detected NUL
byte.

### 18.7 Semantic defect exposed by repair

After removing the NUL, the affected command line was visible as:

``` text
cd D:\GRAZADAM\MBSA_LAB_MBSA_Lab_OS
```

This was not the actual repository path.

The active repository path was:

``` text
D:\GRAZADAM\MBSA_LAB\00_MBSA_Lab_OS
```

The line was therefore corrected to:

``` text
cd D:\GRAZADAM\MBSA_LAB\00_MBSA_Lab_OS
```

### 18.8 Final Git classification

After repair, staging, and `.gitattributes` application, Git reported:

``` text
i/lf    w/lf    attr/text eol=lf        docs/04_Git_Workflow_and_Versioning.md
```

The Markdown document was therefore restored to an explicit text/LF
state.

### 18.9 Corrective commit

The corrective baseline was committed on the US009 feature branch with:

``` text
437b1cd78b4c333e80b038575866342cce1676fc
```

Commit message:

``` text
US009 - Add repository text normalization baseline
```

The commit contained:

``` text
A  .gitattributes
M  docs/04_Git_Workflow_and_Versioning.md
```

with:

``` text
2 files changed, 8 insertions(+), 1 deletion(-)
```

### 18.10 Lessons

This finding establishes the following durable rules:

1.  repository text normalization must be explicit;
2.  `.gitattributes` is the repository-level authority for covered text
    formats;
3.  terminal rendering alone is insufficient to diagnose encoding
    corruption;
4.  unexpected Git binary classification must be investigated;
5.  byte-level defects must be repaired with byte-safe methods;
6.  a binary repair must be followed by semantic review;
7.  command examples must be validated against intended operational
    meaning;
8.  unrelated historical files must not be mass-rewritten as a side
    effect;
9.  repository hygiene defects discovered during a User Story must be
    documented if corrected;
10. corrective commits must remain traceable.

------------------------------------------------------------------------

## 19. `.gitignore` Convention

### 19.1 Purpose

`.gitignore` excludes local, generated, transient, or
environment-specific files that should not be versioned.

### 19.2 Existing exclusions

At US009 audit time, `.gitignore` included:

``` text
bin/
target/
.settings/
.metadata/
.classpath
.project
*.log
*.tmp
.DS_Store
Thumbs.db
```

### 19.3 Rules

Add an ignore pattern only when the excluded content is genuinely not
part of the repository baseline.

Do not ignore an artefact merely because it is inconvenient to review.

Do not use broad patterns that could silently hide required engineering
evidence.

### 19.4 Review

When adding an ignore rule, verify that it does not suppress intended
source, documentation, configuration, or evidence artefacts.

------------------------------------------------------------------------

## 20. Generated and Temporary Files

### 20.1 Temporary files

Temporary files should not be committed.

Examples include:

-   `*.tmp`;
-   local logs;
-   editor temporary files;
-   OS metadata.

### 20.2 Build outputs

Generated build outputs should normally remain outside version control
unless the project explicitly requires them as published artefacts.

### 20.3 Generated documentation

Generated documentation may be committed only when there is a deliberate
publication or distribution reason.

The source of truth must remain identifiable.

### 20.4 Duplicate outputs

Avoid committing both source and generated copies when doing so creates
ambiguity about which is authoritative.

------------------------------------------------------------------------

## 21. Artefact Placement Decision Rules

When introducing a new artefact, apply this decision sequence.

### 21.1 Is it repository-wide?

If yes, consider the repository root only if the artefact is a
repository-wide entry point, control, or metadata file.

### 21.2 Is it engineering documentation?

If yes, use `docs/` or an appropriate established documentation domain.

### 21.3 Is it GitHub-specific?

If yes, use `.github/` and follow GitHub-recognized paths.

### 21.4 Is it an architecture artefact?

Use the architecture area when the artefact is materially part of
architecture work and that structure is active.

### 21.5 Is it a reusable pattern?

Use `patterns/` when the artefact is intentionally reusable as a pattern
rather than project-specific documentation.

### 21.6 Is it an example?

Use `examples/` for demonstrative artefacts that are not authoritative
production or governance content.

### 21.7 Is it a script or tool?

Use `scripts/` for scripts and `tools/` for broader tooling, subject to
future subsystem-specific conventions.

### 21.8 Is its location unclear?

Do not create a new directory immediately.

Clarify the artefact's responsibility first.

------------------------------------------------------------------------

## 22. Traceability Conventions

### 22.1 User Story traceability

Significant Sprint work should remain traceable to its User Story.

### 22.2 Git traceability

Branch and commit traceability follows US006.

US009 does not redefine branch or commit syntax.

### 22.3 Documentation traceability

When a document implements a specific User Story, the relationship
should be understandable from the document, commit history, or both.

### 22.4 Related artefacts

Where useful, identify related:

-   Issues;
-   User Stories;
-   documents;
-   architecture artefacts;
-   implementation artefacts;
-   verification evidence;
-   validation evidence.

### 22.5 Proportionality

Traceability must remain proportional to engineering complexity and
value.

Do not create traceability overhead without engineering benefit.

------------------------------------------------------------------------

## 23. Documentation Change Rules

### 23.1 Assess documentation impact

Every significant repository change should consider whether
documentation must be:

-   added;
-   updated;
-   left unchanged;
-   updated in a separate scoped change.

### 23.2 No silent contradiction

A new document must not silently contradict an existing authoritative
governance document.

If a rule must change:

1.  identify the authoritative source;
2.  make the change explicitly;
3.  assess dependent artefacts;
4.  preserve traceability.

### 23.3 Avoid duplication

Reference existing governance rather than copying it wholesale.

### 23.4 Correcting documentation defects

A factual or operational defect in an existing document should be
corrected forward with a traceable commit.

Do not rewrite Git history solely to conceal the defect.

------------------------------------------------------------------------

## 24. Naming and Terminology Consistency

### 24.1 Project naming

Use established project names consistently:

``` text
MBSA Lab
MBSA-Lab-OS
MBSA-Lab-Control
```

where each specific form is appropriate.

### 24.2 User Stories

Use the form:

``` text
US009
```

for User Story identifiers.

### 24.3 Sprint references

Use:

``` text
Sprint 1
```

unless a machine-readable format requires another representation.

### 24.4 Engineering terminology

Prefer the terminology already established by Engineering Governance,
including:

-   artefact;
-   evidence;
-   traceability;
-   verification;
-   validation;
-   acceptance criteria;
-   public/private boundary;
-   engineering impact;
-   risks and limitations.

### 24.5 Avoid synonymous drift

Do not introduce new terminology for an established concept without a
reason.

------------------------------------------------------------------------

## 25. Cross-Platform Conventions

### 25.1 Repository portability

Repository content should remain usable on common development
environments.

### 25.2 Path separators in documentation

Use repository-relative forward-slash paths when describing repository
locations:

``` text
docs/05_Repository_and_Documentation_Conventions.md
```

Use Windows backslash paths only when documenting an actual
PowerShell/local filesystem command where that path is intentionally
environment-specific.

### 25.3 Case sensitivity

Do not rely on case-insensitive filesystem behavior.

Use the exact tracked path spelling.

### 25.4 Line endings

Use repository normalization rather than relying on OS defaults.

### 25.5 Encoding

Use UTF-8 for repository-native text.

------------------------------------------------------------------------

## 26. Local Environment vs Repository Convention

### 26.1 Local settings are not repository policy

Developer-specific settings may differ.

Examples include:

-   `core.autocrlf`;
-   editor preferences;
-   terminal encoding;
-   local filesystem paths.

### 26.2 Repository-controlled settings

Where consistency matters across contributors, prefer versioned
repository controls such as:

-   `.gitattributes`;
-   `.gitignore`;
-   future `.editorconfig` if deliberately introduced.

### 26.3 `.editorconfig`

No `.editorconfig` existed at the US009 audit baseline.

US009 does not require one merely for completeness.

It may be introduced later if editor-level conventions become necessary
and the change is scoped and justified.

------------------------------------------------------------------------

## 27. Repository Structure Evolution

### 27.1 Evolution trigger

Change repository structure when a real engineering need exists.

### 27.2 Before structural change

Assess:

1.  existing structure;
2.  affected references;
3.  documentation impact;
4.  Git history impact;
5.  automation impact;
6.  contributor impact;
7.  public URLs or links if applicable.

### 27.3 Moves and renames

Moves and renames must be deliberate.

Review the Git diff and update references.

### 27.4 Avoid speculative taxonomy

Do not build a deep directory taxonomy in advance of actual artefacts.

### 27.5 Stable paths

Prefer stable paths for authoritative documents.

Repeated renaming reduces discoverability and creates unnecessary link
churn.

------------------------------------------------------------------------

## 28. Repository Review Checklist

Before committing a repository-structure or documentation change,
verify:

### Scope

-   [ ] The change belongs to the active User Story.
-   [ ] Unrelated cleanup has not been mixed in.
-   [ ] Public/private boundaries are respected.

### Placement

-   [ ] Every new artefact is in an appropriate directory.
-   [ ] No unnecessary root-level file has been introduced.
-   [ ] No speculative empty-directory placeholder has been introduced.

### Naming

-   [ ] Filenames are descriptive.
-   [ ] Existing platform-defined names are preserved.
-   [ ] Foundational document numbering is preserved.
-   [ ] New directory names follow established conventions.

### Documentation

-   [ ] Purpose is clear.
-   [ ] Scope is clear where necessary.
-   [ ] Facts and assumptions are distinguishable.
-   [ ] Evidence is not invented.
-   [ ] Limitations are explicit where relevant.
-   [ ] References point to authoritative sources.

### Text quality

-   [ ] Text files use appropriate UTF-8 encoding.
-   [ ] Repository text normalization is compatible with
    `.gitattributes`.
-   [ ] No unintended binary/NUL content is present.
-   [ ] `git diff --check` passes.

### Git

-   [ ] `git status` is understood before staging.
-   [ ] Only intended files are staged.
-   [ ] `git diff --cached --check` passes.
-   [ ] The staged diff has been reviewed.
-   [ ] Commit conventions from US006 are followed.

------------------------------------------------------------------------

## 29. Documentation Review Checklist

Before considering a substantial engineering document ready:

-   [ ] The title identifies the subject clearly.
-   [ ] The document purpose is explicit.
-   [ ] Scope and boundaries are explicit where needed.
-   [ ] Heading hierarchy is coherent.
-   [ ] Terminology is consistent with existing governance.
-   [ ] Repository paths are correct.
-   [ ] Commands are syntactically and semantically reviewed.
-   [ ] Claims are supported by evidence or identified as assumptions.
-   [ ] Verification and validation are distinguished where applicable.
-   [ ] Risks or limitations are stated where relevant.
-   [ ] Public/private boundaries are respected.
-   [ ] No secrets or confidential information are present.
-   [ ] No accidental binary characters are present.
-   [ ] Markdown diff quality checks pass.

------------------------------------------------------------------------

## 30. Operational Validation Commands

The following commands are useful for validating
repository/documentation convention compliance.

### 30.1 Current branch

``` powershell
git branch --show-current
```

### 30.2 Repository state

``` powershell
git status
```

### 30.3 Tracked files

``` powershell
git ls-files
```

### 30.4 Text/EOL classification

``` powershell
git ls-files --eol
```

### 30.5 Attribute resolution

``` powershell
git check-attr -a -- <path>
```

### 30.6 Unstaged whitespace check

``` powershell
git diff --check
```

### 30.7 Staged whitespace check

``` powershell
git diff --cached --check
```

### 30.8 Staged scope

``` powershell
git diff --cached --name-status
```

### 30.9 Staged summary

``` powershell
git diff --cached --stat
```

### 30.10 Staged content

``` powershell
git diff --cached
```

These commands provide evidence.

Their expected results must not be invented.

------------------------------------------------------------------------

## 31. Exception Rules

### 31.1 Exceptions must have a reason

A convention may be overridden when:

-   a platform requires a specific path or filename;
-   a tool requires a specific encoding or format;
-   an external standard governs the artefact;
-   a subsystem has an approved more-specific convention;
-   backward compatibility requires preservation of an existing path.

### 31.2 Document significant exceptions

If an exception materially affects maintainability, interoperability, or
governance, document the reason.

### 31.3 Local exception does not silently redefine global convention

A specific exception must not be treated as a new repository-wide rule
without an explicit decision.

------------------------------------------------------------------------

## 32. Relationship with Engineering Governance --- US005

US005 remains authoritative for:

-   engineering decision principles;
-   evidence;
-   traceability;
-   verification;
-   validation;
-   change governance;
-   publication;
-   confidentiality;
-   public/private boundaries.

US009 operationalizes repository and documentation organization within
those principles.

US009 does not weaken the requirement that engineering claims be
supported by appropriate reasoning and evidence.

------------------------------------------------------------------------

## 33. Relationship with Git Workflow & Versioning --- US006

US006 remains authoritative for:

-   branch strategy;
-   branch naming;
-   branch lifecycle;
-   commit conventions;
-   versioning;
-   releases;
-   merges;
-   synchronization;
-   correction rules.

US009 adds repository-content conventions.

Where this document contains Git commands, they support
repository/documentation validation and do not replace US006.

------------------------------------------------------------------------

## 34. Relationship with Issue Templates --- US007

US007 defines structured entry points for:

-   Bug Reports;
-   Feature Requests;
-   Engineering Tasks.

US009 governs where those templates reside and how repository
conventions apply to them.

US009 does not redefine the purpose of each Issue category.

------------------------------------------------------------------------

## 35. Relationship with Pull Request Template --- US008

US008 defines the Pull Request review and integration structure.

US009 supports US008 by making repository placement, naming,
documentation impact, text normalization, and hygiene expectations
explicit.

The Pull Request remains responsible for review readiness.

This document remains responsible for repository/documentation
conventions.

------------------------------------------------------------------------

## 36. Relationship with Sprint 1 Closure --- US010

US010 is responsible for Sprint 1 closure and governance baseline.

US009 must provide a stable convention baseline that US010 can assess.

US009 must not pre-emptively declare Sprint 1 closed.

------------------------------------------------------------------------

## 37. US009 Acceptance Criteria

  -----------------------------------------------------------------------
  ID                      Acceptance Criterion    Evidence
  ----------------------- ----------------------- -----------------------
  AC-01                   Repository structure    Sections 4--7
                          conventions are defined

  AC-02                   Root-level placement    Section 6
                          rules are defined

  AC-03                   Directory creation and  Section 7
                          empty-directory rules
                          are defined

  AC-04                   Documentation           Section 8
                          architecture is defined

  AC-05                   Markdown conventions    Section 10
                          are defined

  AC-06                   File naming conventions Section 11
                          are defined

  AC-07                   Directory naming        Section 12
                          conventions are defined

  AC-08                   GitHub artefact         Section 13
                          placement conventions
                          are defined

  AC-09                   UTF-8 text convention   Section 14
                          is defined

  AC-10                   LF canonical            Section 15
                          line-ending convention
                          is defined

  AC-11                   `.gitattributes`        Section 16
                          normalization baseline
                          is defined

  AC-12                   Repository hygiene      Section 17
                          rules are defined

  AC-13                   US009                   Section 18
                          text-normalization
                          defect and repair are
                          documented

  AC-14                   `.gitignore` principles Section 19
                          are defined

  AC-15                   Artefact placement      Section 21
                          decision rules are
                          defined

  AC-16                   Documentation           Section 22
                          traceability
                          conventions are defined

  AC-17                   Documentation change    Section 23
                          rules are defined

  AC-18                   Terminology conventions Section 24
                          are defined

  AC-19                   Cross-platform          Section 25
                          conventions are defined

  AC-20                   Local-vs-repository     Section 26
                          configuration boundary
                          is defined

  AC-21                   Repository evolution    Section 27
                          rules are defined

  AC-22                   Repository and          Sections 28--29
                          documentation review
                          checklists exist

  AC-23                   Operational validation  Section 30
                          commands are provided

  AC-24                   Exception governance is Section 31
                          defined

  AC-25                   Compatibility with      Sections 32--35
                          US005--US008 is
                          explicit

  AC-26                   US010 boundary is       Section 36
                          preserved

  AC-27                   No private control      Repository/document
                          information is          review
                          introduced

  AC-28                   No historical Git       Git review
                          history is rewritten by
                          US009

  AC-29                   US009 implementation    Git evidence
                          remains traceable
                          through Git

  AC-30                   Final repository state  Final Gate evidence
                          is validated from
                          actual evidence
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 38. US009 Definition of Done

US009 is complete only when all applicable conditions below are
satisfied by actual evidence.

### Repository conventions

-   [ ] `docs/05_Repository_and_Documentation_Conventions.md` exists.
-   [ ] Repository structure conventions are documented.
-   [ ] Placement conventions are documented.
-   [ ] Naming conventions are documented.
-   [ ] Markdown conventions are documented.
-   [ ] Text encoding conventions are documented.
-   [ ] Line-ending conventions are documented.
-   [ ] `.gitattributes` baseline is documented.
-   [ ] Repository hygiene rules are documented.

### Corrective baseline

-   [ ] `.gitattributes` is versioned.
-   [ ] The detected NUL defect in
    `docs/04_Git_Workflow_and_Versioning.md` remains corrected.
-   [ ] The affected PowerShell path is correct.
-   [ ] `docs/04_Git_Workflow_and_Versioning.md` is classified as text
    with LF normalization.

### Quality

-   [ ] `git diff --check` passes.
-   [ ] `git diff --cached --check` passes before commit.
-   [ ] No unintended files are included.
-   [ ] No private/confidential material is included.
-   [ ] The final document is coherent with US005--US008.

### Git lifecycle

-   [ ] US009 work is performed on the dedicated US009 feature branch.
-   [ ] US009 implementation commit(s) are traceable.
-   [ ] The feature branch is pushed when ready.
-   [ ] Integration into `main` follows US006.
-   [ ] Integration uses the established explicit `--no-ff` merge
    policy.
-   [ ] `main` is pushed.
-   [ ] `main` and `origin/main` equality is verified.
-   [ ] Feature-branch cleanup is performed according to the established
    lifecycle.
-   [ ] `git fetch --prune` is executed when remote cleanup is
    completed.

### Evidence

-   [ ] Actual commit SHA(s) are captured.
-   [ ] Actual merge SHA is captured.
-   [ ] Actual final `main` SHA is captured.
-   [ ] Actual `origin/main` SHA is captured.
-   [ ] Final working-tree state is captured.
-   [ ] Final branch state is captured.
-   [ ] US009 closure report documents the complete operational history.

------------------------------------------------------------------------

## 39. Controlled Adoption Rules

### 39.1 New content

New content should comply with this document from the point US009 is
integrated.

### 39.2 Existing content

Existing content should not be mass-rewritten solely for stylistic
conformity.

Correct existing content when:

-   a real defect exists;
-   a future User Story legitimately modifies it;
-   a repository-wide normalization change is explicitly approved.

### 39.3 Incremental compliance

When an existing artefact is materially changed, bring the modified area
into compliance where practical without creating unrelated scope.

### 39.4 Tooling

Future automated checks may enforce parts of these conventions.

Automation must reflect the documented policy rather than silently
create a different policy.

------------------------------------------------------------------------

## 40. Operational Reference --- Adding a New Foundational Document

The following sequence illustrates the repository/documentation controls
applicable to a new foundational document.

### Phase A --- Verify repository state

``` powershell
git status
git branch --show-current
```

Confirm the active User Story branch and understand all existing
changes.

### Phase B --- Create the artefact

Place the document under:

``` text
docs/
```

using the approved foundational naming pattern.

### Phase C --- Validate text quality

``` powershell
git diff --check
git ls-files --eol
```

### Phase D --- Inspect scope

``` powershell
git status --short
git diff --stat
git diff
```

### Phase E --- Stage explicitly

``` powershell
git add <intended-path>
```

### Phase F --- Validate staged content

``` powershell
git diff --cached --check
git diff --cached --name-status
git diff --cached --stat
git diff --cached
```

### Phase G --- Commit

Use the applicable US006 commit convention.

Do not invent the resulting SHA.

Capture it from Git after the commit.

------------------------------------------------------------------------

## 41. Operational Reference --- Detecting Text Anomalies

If Git unexpectedly classifies a text document as binary:

### Step 1 --- Inspect EOL classification

``` powershell
git ls-files --eol
```

### Step 2 --- Inspect attributes

``` powershell
git check-attr -a -- <path>
```

### Step 3 --- Inspect bytes if necessary

Use byte-level inspection to detect:

-   NUL bytes;
-   BOMs;
-   unexpected encoding;
-   corrupted sequences.

### Step 4 --- Back up before repair

Create a byte-for-byte backup outside the repository working tree.

### Step 5 --- Apply minimal repair

Modify only the confirmed defect.

### Step 6 --- Prove the delta

Use byte comparison and Git diff.

### Step 7 --- Review semantics

A technically minimal byte repair may expose a semantic defect.

Review the affected line or section.

### Step 8 --- Stage and validate

``` powershell
git add <path>
git diff --cached --check
git diff --cached
git ls-files --eol
```

### Step 9 --- Commit traceably

Use a clear corrective commit message consistent with US006.

------------------------------------------------------------------------

## 42. Anti-Patterns

The following practices are prohibited or strongly discouraged.

### Repository anti-patterns

-   creating directories without real artefacts;
-   using the root as a catch-all;
-   duplicating authoritative documents;
-   introducing unrelated cleanup into a scoped User Story;
-   renaming historical artefacts merely for aesthetic consistency;
-   treating local empty directories as Git evidence;
-   adding placeholder files without an engineering reason.

### Documentation anti-patterns

-   unsupported claims;
-   invented Git evidence;
-   undocumented assumptions;
-   ambiguous authoritative sources;
-   contradictory governance rules;
-   invalid executable command examples;
-   accidental binary characters in text files;
-   private or confidential information in public documentation.

### Git/text anti-patterns

-   relying solely on `core.autocrlf` as repository policy;
-   blindly running repository-wide renormalization;
-   treating terminal mojibake as definitive evidence of file
    corruption;
-   rewriting shared history to hide a correction;
-   staging all files without reviewing scope.

------------------------------------------------------------------------

## 43. Governance Summary

The repository convention can be summarized as:

``` text
Engineering meaning first
        ↓
One authoritative location
        ↓
Clear naming and placement
        ↓
UTF-8 repository text
        ↓
Canonical LF normalization
        ↓
Explicit Git attributes
        ↓
Scoped and reviewed diffs
        ↓
Evidence-based Git lifecycle
        ↓
Public/private boundary respected
        ↓
Traceable evolution
```

------------------------------------------------------------------------

## 44. Final Rules

1.  `MBSA-Lab-OS` is the public engineering repository.
2.  Private control material remains outside the public repository.
3.  Markdown is the primary repository-native documentation source.
4.  `docs/` is the primary location for engineering documentation.
5.  Foundational Sprint documents preserve their ordered two-digit
    naming sequence.
6.  Root-level files require repository-wide relevance.
7.  Empty local directories are not Git-managed repository evidence.
8.  Do not create speculative directory structures.
9.  GitHub-specific artefacts belong under `.github/` using
    platform-recognized paths.
10. New repository text should use UTF-8.
11. Canonical repository line endings are LF.
12. `.gitattributes` is the repository-level normalization authority for
    covered formats.
13. Local Git/editor settings do not replace repository policy.
14. Do not blindly renormalize the entire repository.
15. Review actual Git diffs before commit.
16. `git diff --check` and `git diff --cached --check` are baseline
    quality controls.
17. Do not invent Git state or evidence.
18. Correct defects forward with traceable commits.
19. Do not rewrite historical commits merely for convention compliance.
20. Preserve the responsibility boundaries established by US005--US008.
21. US009 defines repository/documentation conventions; it does not
    close Sprint 1.
22. US010 remains responsible for Sprint 1 closure and governance
    baseline.

------------------------------------------------------------------------

## 45. Conclusion

US009 establishes a controlled repository and documentation baseline for
MBSA Lab OS.

The repository is expected to evolve, but that evolution must remain:

-   intentional;
-   understandable;
-   scoped;
-   traceable;
-   cross-platform;
-   evidence-based;
-   compatible with Engineering Governance;
-   compatible with Git Workflow & Versioning;
-   compatible with the Issue and Pull Request mechanisms;
-   safe for public engineering publication.

The conventions defined here are deliberately practical.

They are intended to prevent ambiguity and recurring repository defects
without introducing unnecessary process.

The US009 audit itself demonstrated why this matters: an absent
repository-level text policy allowed heterogeneous working-tree behavior
and concealed a NUL byte inside a Markdown document. The defect was
isolated, repaired with byte-level evidence, semantically reviewed, and
converted into a durable `.gitattributes` baseline.

That corrective sequence is part of the engineering evidence for US009
and must be retained in the US009 closure report.

US009 is complete only when this document and the associated repository
baseline have passed the applicable acceptance criteria, Git lifecycle,
integration, synchronization, cleanup, and final evidence gates.
