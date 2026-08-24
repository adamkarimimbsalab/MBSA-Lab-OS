# MBSA Lab

MBSA Lab is an open engineering initiative for learning, demonstrating, and reusing model-based systems engineering (MBSE) and model-based safety assessment (MBSA) practices.

The project connects systems thinking, architecture, safety reasoning, verification and validation, traceability, software prototyping, and technical communication through inspectable engineering artefacts.

## Purpose

MBSA Lab aims to make rigorous engineering methods understandable and reproducible without presenting demonstrations as production-ready systems.

Its public material is intended to help practitioners:

- understand how engineering concerns relate across a lifecycle;
- inspect the reasoning behind models, requirements, evidence, and decisions;
- build bounded proofs of concept;
- distinguish demonstrated capability from planned capability;
- reuse admitted patterns without losing their assumptions and limitations.

## Engineering approach

The project follows several principles:

- define the problem and system boundary before selecting a solution;
- separate facts, assumptions, inferences, claims, and decisions;
- keep engineering, safety, verification, evidence, and publication concerns distinct;
- prefer objective evidence over unsupported claims;
- maintain bidirectional traceability proportional to risk and maturity;
- use explicit quality gates and decision authority;
- preserve limitations and negative findings;
- evolve incrementally through reviewable baselines.

## Scope

The public repository contains the engineering foundation of MBSA Lab, including:

- project vision, mission, and governance;
- system context and logical architecture;
- a minimal engineering framework;
- a lifecycle and factory model for proofs of concept;
- traceability and evidence-package models;
- integrated quality-gate principles;
- pattern definition and admission rules;
- a minimal interface for engineering video releases;
- readiness criteria for selecting and authorizing a first proof of concept.

Implementation assets, validated POCs, admitted patterns, and released media are added only when evidence supports their stated maturity.

## Repository structure

```text
MBSA-Lab-OS/
├── .github/        Contribution templates
├── docs/           Public engineering documentation
├── examples/       Bounded examples when available
├── patterns/       Admitted reusable patterns when available
├── poc/            Proof-of-concept assets when available
├── scripts/        Reproducible utilities when available
└── README.md       Repository entry point
```

The presence of a directory or a documented capability does not by itself prove implementation or operational maturity.

## Public and private information

This repository is deliberately curated for public engineering use. Non-public operational, administrative, personal, and environment-specific information is maintained outside the public baseline.

Public engineering concepts remain documented when they are necessary to understand the architecture, lifecycle, evidence, or governance model.

## Documentation

Start with [Project Overview](docs/00_Project_Overview.md), then follow the numbered documents in `docs/`.

Each document states its own scope and limitations. Later documents refine earlier concepts; no single document should be interpreted in isolation when making an engineering claim.

## Contribution

Contributions should be reviewable, evidence-based, scoped, and consistent with the repository conventions. Proposed changes must preserve public/private separation and avoid overstating maturity.

## License

Licensing terms are defined by the repository license file when present. Third-party assets retain their respective rights and must not be added without compatible authorization.
