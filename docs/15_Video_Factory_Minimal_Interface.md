# MBSA Lab OS — Video Factory Minimal Interface

## 1. Purpose

This document defines the minimal public interface for creating, reviewing, releasing and maintaining engineering videos. A video is a communication projection. It does not replace engineering sources, V&V results, Evidence Packages, Claims, Findings, limitations or authorized decisions.

No capture or publication begins before an exploitable baseline and the applicable readiness conditions exist.

## 2. Boundary

The interface begins with an identified request and a controlled Video Source Package. It ends with an authorized Video Release Package and lifecycle records for retention, correction, supersession or withdrawal.

The model is tool-neutral. OBS and x264 are examples of an available environment, not architectural dependencies.

## 3. Stable identities

Four identities are mandatory:

| Identity | Purpose |
|---|---|
| VIDREQ | Video request and communication objective |
| VIDWORK | Controlled working production |
| VIDREL | Authorized release identity |
| VIDERR | Erratum, correction or withdrawal record |

Each identity includes version, owner, state, scope, classification, related configuration and relevant supersession links. A published VIDREL is immutable; later correction creates a linked version or VIDERR.

## 4. Interface packages

### 4.1 Video Source Package

The Video Source Package identifies:

- request, audience, purpose and permitted claims;
- exploitable engineering baseline and configuration;
- authoritative sources and Evidence Package references;
- open findings, limitations and required disclosures;
- storyboard, script and capture plan;
- classification, rights, licences and consent;
- publication constraints and decision authority.

### 4.2 Video Release Package

The Video Release Package identifies:

- VIDREL and the exact media asset;
- source VIDREQ and VIDWORK;
- POC, configuration, revision and controlled source references;
- technical, semantic, evidence and publication reviews;
- Claims, Findings, limitations and decisions represented;
- captions, transcript, accessibility assets and audience metadata;
- integrity, classification, rights and release location;
- retention, correction, supersession, withdrawal and reopening rules.

These packages bound the interface. They may reference controlled sources instead of duplicating them.

## 5. Exploitable baseline

An exploitable baseline has stable identity, known configuration, accessible authoritative sources, sufficient evidence for the intended claims, visible findings and limitations, and an owner authorized to release those sources for production use.

Baseline existence is necessary but not sufficient. The request, rights, audience, safety and publication boundary must also be ready.

## 6. Fourteen-step workflow

1. **Request or proposal** — create VIDREQ and state audience, purpose and intended claims.
2. **Qualification** — assess value, scope, classification, risks and authority.
3. **Baseline and readiness** — confirm an exploitable baseline and stop conditions.
4. **Sources and rights** — assemble the Video Source Package.
5. **Brief, storyboard and script** — define the communication projection and disclosures.
6. **Capture plan and environment** — identify scenes, data, tools and configurations.
7. **Recording** — create controlled source media under VIDWORK.
8. **Editing** — produce an identified candidate without altering engineering truth.
9. **Technical review** — assess media integrity, intelligibility and accessibility.
10. **Semantic and Engineering Review** — assess accuracy, context and overstatement.
11. **Evidence and Traceability Review** — verify claims, sources, results and limitations.
12. **Publication decision** — authorize, condition, reject or defer release.
13. **Controlled release** — create VIDREL and the Video Release Package.
14. **Feedback and lifecycle** — retain, correct, supersede, withdraw or reopen as required.

Skipping a production activity through tailoring does not remove its objective or required evidence.

## 7. Checkpoints and integrated Gates

The workflow may use:

- CP-VID-01 — request and baseline readiness;
- CP-VID-02 — source, script and capture readiness;
- CP-VID-03 — technical and semantic review readiness;
- CP-VID-04 — evidence, publication and release readiness.

CP-VID checkpoints organize work. They do not create a competing Gate family or issue publication authority. Applicable integrated Engineering, Evidence, Classification and Publication Gates retain authority.

## 8. Separated reviews

### 8.1 Technical Quality Review

Checks media readability, audio, framing, encoding, synchronization, captions, transcript, accessibility and file integrity. Technical Quality `PASS` does not authorize publication.

### 8.2 Semantic and Engineering Review

Checks accuracy, configuration context, terminology, causal statements, safety meaning, omissions, demonstrations and risk of over-promise.

### 8.3 Evidence and Traceability Review

Checks that each material claim is supported by identified sources and evidence, that negative results and limitations remain visible, and that the video does not substitute presentation for proof.

### 8.4 Publication Review

Checks audience, classification, rights, licences, consent, privacy, accessibility, release channel, retention and authority. It produces the release decision.

The four reviews may be coordinated, but their concerns and outcomes remain distinct.

## 9. Release traceability

Every release remains traceable to the related POC or subject, configuration, controlled revision, sources, Evidence Package, Claims, Findings, limitations, review records and decisions. Where software behavior is shown, the implementation revision is identified without turning the public video into an operational development log.

A transcript or storyboard is a view of the release and remains linked to VIDREL. A public surrogate identifies the information it abstracts or omits.

## 10. Corrections and lifecycle

Before publication, candidate edits remain versions of VIDWORK. After publication, a release is never silently overwritten.

Minor corrections use an identified erratum or new VIDREL as appropriate. Material semantic errors, invalidated evidence, rights changes or unsafe interpretation may require withdrawal and reopening. Supersession identifies the replacement and migration notice. Retention preserves the released asset, decision and applicable restrictions.

## 11. Failure modes and stop conditions

Production or publication stops when the baseline is absent or invalid, intended claims exceed evidence, Critical findings are unresolved, configuration is unknown, required rights or consent are missing, classification is incompatible with the audience, semantic review fails, or publication authority is absent.

Tool failure, corrupted capture, missing audio, unreviewed edits and trace breaks create findings. They do not become successful evidence through presentation quality.

## 12. Classification, rights and public surrogates

Source access and public release are separate. Restricted details may be replaced by an authorized public surrogate that preserves the allowed engineering meaning and states its limitations.

Licences, image and voice consent, personal data, trademarks, third-party material and export constraints are evaluated and retained with the release decision.

## 13. Tailoring

- **T1** supports a concise communication item with compact records and essential reviews.
- **T2** uses structured source and release packages, formal review records and lifecycle controls.
- **T3** adds stronger independence, assurance, integrity, accessibility and retention controls.

Tailoring shall not remove baseline identity, claim-to-evidence traceability, semantic review, publication authority, rights review, limitation disclosure or controlled release lifecycle.

## 14. Conceptual POC application

The interface can describe an Emergency Stop Button provisional reference, a Door Interlock Safety System alternative and an Overtemperature Protection System alternative. Each would require its own baseline, evidence, safety context and publication decision.

The applications are conceptual and non-implementing. No POC is selected, started, accepted or demonstrated by this document.

## 15. Maturity and limitations

The Video Factory Core remains `PARTIAL` or at the level actually supported by evidence. This interface does not claim an implemented production platform, validated media pipeline, completed recording, released video or automated traceability.

Conformance is demonstrated only by populated Video Source and Video Release Packages, completed reviews, actual evidence and authorized lifecycle decisions for an identified release.
