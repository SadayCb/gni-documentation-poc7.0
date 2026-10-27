# GNI Software — LOAN_API Documentation

> **Document status:** Draft — Proof of Concept. This document describes a shared PL/SQL package, not an individual Oracle APEX screen.

## Documentation Overview

| Section | Item | Details / Link |
|:--|:--|:--|
| **General** | Document Name | **LOAN_API — Technical & Functional Documentation** |
| | Created Date | 27 October 2026 |
| | Created By | GNI Software — Documentation PoC *(owner to be confirmed)* |
| | Version | 0.1 — Draft |
| **Introduction** | Purpose of this Document | [Purpose & Overview](overview.md) — explain the shared loan operations package for onboarding, implementation and maintenance. |
| | Scope of this Document | Covers `LOAN_API` public interfaces and selected verified implementation behavior. [Getting Started](guides/getting-started.md) · [Workflows](workflows.md) |
| **API Specifications** | Related Tables / API Reference | [Public Procedures & Functions](api/loan-api.md) · [Dependencies / Related Tables](reference/dependencies.md) |
| **Data Model** | Tables | [Data Model & Main Tables](data-model.md) |
| **Error Handling** | Error Messages & Descriptions | [Error Handling Reference](error-handling.md) · [Review Findings](reference/review-findings.md) |

## Documentation Navigation

- [Introduction and Functional Overview](overview.md)
- [Developer Onboarding](guides/getting-started.md)
- [Public API Reference](api/loan-api.md)
- [Operational Workflows](workflows.md)
- [Data Model](data-model.md)
- [Error Handling](error-handling.md)
- [Dependencies](reference/dependencies.md)
- [Review Findings](reference/review-findings.md)

## Source and Review Policy

The PL/SQL package **specification** defines the exposed signatures. The package **body** is used to explain selected behavior and identify dependencies. Unverified business semantics are explicitly marked for review. Do not publish internal implementation details to customers without technical and security approval.

**Scope:** `LOAN_API` only. The earlier Page 2201 documentation is excluded.
