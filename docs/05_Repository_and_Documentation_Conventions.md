# MBSA Lab — Repository and Documentation Conventions

## 1. Purpose

This document defines conventions for organizing, naming, writing, and maintaining public MBSA Lab artefacts. The objective is a portable, readable, and reviewable repository whose content can evolve without losing engineering meaning.

## 2. Governing principles

- Convention reduces ambiguity but does not override engineering meaning.
- Public material is deliberately curated.
- One authoritative source is preferred over duplicated descriptions.
- Structure is introduced when content requires it, not speculatively.
- Changes preserve traceability and stable references where practical.
- Evidence and limitations take priority over appearance.
- Private administration and local-environment detail remain outside public artefacts.

## 3. Repository structure

The repository root is reserved for project-wide entry points and configuration. Engineering documentation belongs in `docs/`; contribution templates belong in `.github/`; implementation, examples, patterns, scripts, and tests use dedicated directories when such content exists.

Avoid empty taxonomy, duplicate outputs, and root-level clutter.

### 3.1 Directory creation

Create a directory when:

- it has a clear engineering purpose;
- ownership and expected content are understood;
- the content cannot be placed coherently in an existing location;
- its name is stable and portable.

Git does not version empty directories. A placeholder should explain the intended content and be removed when no longer necessary.

## 4. Documentation architecture

Markdown is the primary source format for public engineering documentation.

Foundational documents use a numeric prefix to provide a stable reading order:

```text
docs/00_Project_Overview.md
docs/01_Vision.md
docs/02_Mission.md
...
```

Numeric order indicates navigation, not authority. Each concept should have one authoritative definition, with other documents linking to it.

## 5. Content conventions

An engineering document should make the following clear when relevant:

- purpose and intended audience;
- scope, boundary, and exclusions;
- facts, assumptions, and decisions;
- requirements or governing rules;
- architecture, interfaces, and behaviour;
- verification and validation approach;
- evidence and traceability expectations;
- findings, limitations, and residual risks;
- authority and lifecycle state.

Do not include private operational records, environment-specific administration, personal data, or unpublished status in public documents.

## 6. Markdown conventions

### 6.1 Headings

Use one level-one heading per document. Do not skip heading levels.

```markdown
# Document title

## 1. Main section

### 1.1 Subsection
```

### 6.2 Lists and tables

Use lists for parallel points and tables only when exact comparison improves understanding. Keep cells concise and provide context outside complex tables.

### 6.3 Code and diagrams

Fenced blocks must specify a suitable language when known and must always be closed. Examples must be clearly distinguished from normative requirements.

### 6.4 Links

Use relative links for repository content. Link to the authoritative document or section and avoid unnecessary duplication.

### 6.5 Whitespace

- no trailing spaces or tabs;
- one final LF at end of file;
- blank lines used consistently around headings, lists, and fenced blocks;
- no embedded NUL characters.

## 7. Naming conventions

File and directory names should be descriptive, stable, and portable.

Recommended rules:

- avoid spaces in repository paths;
- use consistent capitalization within a directory;
- preserve platform-defined names such as `README.md`;
- avoid case-only distinctions;
- avoid private identifiers or temporary workflow states in public filenames;
- use extensions that reflect the actual content.

Renaming an established public path requires impact review because external links and traceability may depend on it.

## 8. Text encoding and line endings

Public text files use:

- UTF-8 without BOM;
- canonical LF line endings;
- a final LF;
- no NUL characters;
- no trailing whitespace.

Repository attributes should enforce canonical representation. A local checkout may apply environment-specific presentation only when this does not create canonical divergence.

Blind repository-wide renormalization is prohibited. Normalization scope must be explicit and its diff reviewed.

## 9. GitHub artefacts

Issue and pull-request templates should collect engineering information, not private administration.

Useful fields include:

- problem or change objective;
- scope and exclusions;
- affected artefacts;
- acceptance or verification criteria;
- evidence supplied;
- risks, limitations, and dependencies;
- review authority.

Templates support governance but do not replace technical review.

## 10. Generated and temporary content

Temporary files, editor state, build outputs, caches, credentials, and local backups must not be committed unless they are explicitly governed project artefacts.

Generated documentation must identify:

- its source;
- the generation method and configuration;
- whether generated output or source is authoritative;
- how reproducibility is verified.

Avoid committing multiple equivalent renderings unless each has a justified public use.

## 11. Artefact placement rules

Before adding an artefact, ask:

1. Is it public and authorized?
2. Is it repository-wide or domain-specific?
3. Does an authoritative location already exist?
4. Is it source, generated output, evidence, an example, or a reusable pattern?
5. Does its location remain meaningful as the repository evolves?

If placement remains ambiguous, resolve the information architecture before committing the file.

## 12. Traceability conventions

Traceability may use identifiers, links, metadata, or controlled tables. The mechanism must remain proportional to the decision and understandable without private context.

Public documents should trace to public authoritative artefacts. References to unavailable private evidence must be clearly bounded and must not be used to make an unverifiable public claim.

## 13. Documentation change rules

Before changing documentation:

- assess affected concepts and cross-references;
- identify whether the change is editorial or semantic;
- avoid silent contradictions;
- update the authoritative source first;
- preserve limitations and historical release identity;
- review public/private separation;
- verify links, encoding, structure, and diff quality.

## 14. Terminology

Use project terminology consistently:

- MBSE — model-based systems engineering;
- MBSA — model-based safety assessment;
- verification — evidence of conformance to specified expectations;
- validation — evidence of suitability for intended use;
- POC — a bounded proof of concept, not a production release;
- pattern — reusable engineering knowledge admitted through defined criteria;
- evidence package — controlled aggregation of evidence and identity;
- gate — a decision checkpoint with defined objectives and authority.

Avoid synonymous drift when a term already has an authoritative definition.

## 15. Cross-platform conventions

Repository content must remain usable on common operating systems and filesystems.

- use repository-relative paths in documentation;
- do not publish user-specific absolute paths;
- avoid shell-specific requirements unless the procedure explicitly requires them;
- consider case sensitivity;
- keep encoding and EOL policy under repository control.

Local tool settings do not redefine repository policy.

## 16. Repository hygiene

Review changed and staged content explicitly. Confirm:

- expected paths only;
- no accidental binary or generated files;
- no secrets, personal data, or private orchestration;
- no whitespace or encoding defects;
- no unintended semantic change;
- no broken authoritative references.

Out-of-scope defects should be recorded and corrected through a separately approved change.

## 17. Exceptions

An exception must state:

- the convention being departed from;
- the reason and affected scope;
- the approving authority;
- the duration or closure condition;
- any compensating control.

A local exception does not silently redefine the global convention.

## 18. Review checklist

### Structure

- one primary title;
- coherent heading hierarchy;
- stable placement and naming;
- no unnecessary duplication.

### Engineering content

- scope and assumptions explicit;
- claims bounded by evidence;
- V&V terminology used correctly;
- limitations visible;
- authoritative cross-references valid.

### Public release

- no private administration or local-environment data;
- confidentiality, rights, and attribution reviewed;
- maturity not overstated;
- public source understandable without internal context.

### Text quality

- UTF-8 without BOM;
- LF with final LF;
- no NUL or trailing whitespace;
- fenced blocks balanced;
- links and formatting verified.

## 19. Controlled adoption

New content should comply with these conventions. Existing content is brought into compliance through explicit, reviewable maintenance rather than silent mass rewriting.

Automation may detect defects, but semantic review remains necessary.
