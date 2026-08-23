# Platform Engineering Journey

Hands-on, evidence-driven progression toward Platform Engineering and eventually Senior Platform Engineering responsibilities.

This repository is the working portfolio for building practical capability across Linux, networking, containers, Kubernetes, Azure, Terraform, CI/CD, GitOps, observability, security, and platform architecture.

## Current Status

- Phase: Foundation
- Current milestone: M1 — Linux Foundations
- Weekly capacity: 11 hours
- Primary cloud: Azure
- Target market: Sweden / EU

## Operating Principles

1. **Evidence over course completion.** A topic is not complete until it produces working implementation, troubleshooting evidence, documentation, tests, or an engineering decision.
2. **Issues define measurable deliverables.** Issues should normally represent 2–6 hours of engineering work.
3. **Changes go through branches and Pull Requests.** Direct changes to `main` are reserved for trivial administration only.
4. **Acceptance criteria determine completion.** "I watched/read it" is not a valid Definition of Done.
5. **No employer-confidential material.** This public repository must not contain Volvo Cars internal code, URLs, package names, architecture, credentials, data, or proprietary information.

## Planned Learning Path

```text
Linux + Networking
        ↓
Containers
        ↓
Kubernetes
        ↓
Azure + Terraform
        ↓
CI/CD Architecture
        ↓
GitOps
        ↓
Observability + Security
        ↓
Platform Engineering
        ↓
Production Ownership
        ↓
Platform Architecture
```

## Repository Layout

The structure grows only when there is a real artifact to store. Empty directories are intentionally avoided.

```text
platform-engineering-journey/
├── README.md
├── docs/
├── app/
├── docker/
├── kubernetes/
├── terraform/
├── scripts/
├── .github/
└── decisions/
```

## Git Workflow

```text
Issue
  ↓
feature / chore / docs branch
  ↓
Implementation
  ↓
Validation against acceptance criteria
  ↓
Pull Request
  ↓
Review
  ↓
Merge to main
  ↓
Issue closed
```

## Definition of Done

A substantial issue requires meaningful evidence such as one or more of the following:

- working implementation;
- tested configuration;
- reproducible troubleshooting scenario;
- automated test;
- architecture note;
- ADR;
- infrastructure provisioned from code;
- monitoring/alerting configuration;
- Pull Request with documented validation.

Course completion alone does not satisfy the Definition of Done.

## Roadmap

The detailed career and engineering roadmap is maintained in [`docs/roadmap.md`](docs/roadmap.md).

## Current Foundation Milestones

| Milestone | Target |
|---|---|
| M1 — Linux Foundations | Weeks 1–2 |
| M2 — Networking Foundations | Week 3 |
| M3 — Docker Foundations | Week 4 |
| M4 — Kubernetes Fundamentals | Weeks 5–7 |
| M5 — Kubernetes Troubleshooting | Week 8 |
| M6 — Azure Foundations | Week 9 |
| M7 — Terraform Foundations | Weeks 10–11 |
| M8 — CI/CD Integration | Week 12 |

## Public Repository Safety

Never commit:

- credentials, tokens, keys, certificates, or `.env` secrets;
- Terraform state files;
- private endpoints or internal hostnames;
- proprietary source code;
- employer-specific artifacts or confidential documentation;
- production data.

This repository must remain independently reproducible using generic lab infrastructure and public tooling.
