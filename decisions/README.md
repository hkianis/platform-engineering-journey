# Architecture Decision Records

This directory stores Architecture Decision Records (ADRs) for decisions that have meaningful technical alternatives or long-term consequences.

## ADR Format

Each ADR should contain:

1. **Context** — problem, constraints, and relevant assumptions
2. **Decision** — selected approach
3. **Alternatives Considered** — credible options that were rejected
4. **Consequences** — benefits, costs, risks, and follow-up work
5. **Status** — proposed, accepted, superseded, or deprecated

## Naming

Use sequential filenames:

```text
ADR-001-<decision-title>.md
ADR-002-<decision-title>.md
```

## Planned Decisions

Potential future ADRs include:

- primary cloud choice;
- Kubernetes local-development strategy;
- CI/CD implementation choice;
- Terraform state strategy;
- GitOps controller choice;
- observability architecture.

Do not create an ADR merely to create documentation. Use one when a decision has real alternatives and future readers need the rationale.
