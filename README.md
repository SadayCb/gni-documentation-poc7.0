# GNI Software — LOAN_API Documentation

> **Document status:** Draft — Proof of Concept. This document describes a shared PL/SQL package, not an individual Oracle APEX screen.

## Documentation Overview

| Section | Item | Details / Link |
|:--|:--|:--|
| **General** | Document Name | **LOAN_API — Technical & Functional Documentation** |
| | Created Date | 27 October 2026 |
| | Created By | GNI Software — Loan Team |
| | Version | 0.1 — Draft |
| **Introduction** | Purpose of this Document | [Purpose & Overview](docs/overview.md) — explain the shared loan operations package for onboarding, implementation and maintenance. |
| | Scope of this Document | Covers `LOAN_API` public interfaces and selected verified implementation behavior. [Getting Started](docs/guides/getting-started.md) · [Workflows](docs/workflows.md) |
| **API Specifications** | Procedures & Functions / API Reference | [Public Procedures & Functions](docs/api/loan-api.md) · [Dependencies / Related Tables](docs/reference/dependencies.md) |
| **Data Model** | Tables | [Data Model & Main Tables](docs/data-model.md) |
| **Error Handling** | Error Messages & Descriptions | [Error Handling Reference](docs/error-handling.md) · [Review Findings](docs/reference/review-findings.md) |

## Documentation Navigation

- [Introduction and Functional Overview](docs/overview.md)
- [Developer Onboarding](docs/guides/getting-started.md)
- [Public API Reference](docs/api/loan-api.md)
- [Operational Workflows](docs/workflows.md)
- [Data Model](docs/data-model.md)
- [Error Handling](docs/error-handling.md)
- [Dependencies](docs/reference/dependencies.md)
- [Review Findings](docs/reference/review-findings.md)

## Source and Review Policy

The PL/SQL package **specification** defines the exposed signatures. The package **body** is used to explain selected behavior and identify dependencies. Unverified business semantics are explicitly marked for review. Do not publish internal implementation details to customers without technical and security approval.
