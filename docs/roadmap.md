# Platform Engineering Roadmap

**Status:** Active  
**Current Phase:** Foundation  
**Current Milestone:** M1 — Linux Foundations  
**Last Updated:** 2026-08-26

## Purpose

This public roadmap tracks evidence-driven progression toward Platform Engineering responsibilities. It intentionally excludes employer-confidential implementation details and private skill scoring.

Progress is not measured by courses completed. A capability is considered demonstrated only when supported by implementation, troubleshooting, design work, documentation, automated validation, or realistic project evidence.

## Target Capability

The target state is the ability to take a platform problem and:

1. design an architecture;
2. provision infrastructure using Infrastructure as Code;
3. deploy and operate workloads on Kubernetes;
4. automate software delivery;
5. add observability and security controls;
6. troubleshoot failures systematically;
7. explain engineering trade-offs;
8. own the solution through an operational lifecycle.

## Current Engineering Focus

The foundation phase is deliberately sequenced around the capabilities needed to build and operate a cloud-native delivery platform:

- Linux and systems fundamentals;
- networking fundamentals;
- container engineering;
- Kubernetes deployment and troubleshooting;
- Azure infrastructure;
- Terraform and Infrastructure as Code;
- CI/CD architecture and automation;
- later: GitOps, observability, security, and platform architecture.

Public progress is demonstrated through repository evidence rather than self-reported skill levels.

## Evidence Model

Useful evidence includes:

- working code or configuration;
- reproducible labs;
- automated tests;
- commands and relevant output;
- intentionally reproduced failure scenarios;
- troubleshooting write-ups;
- architecture notes;
- ADRs;
- infrastructure provisioned from code;
- Pull Requests with validation against acceptance criteria.

Course completion by itself is not evidence of engineering capability.

## Weekly Capacity

Planned capacity: **11 hours/week**.

| Day | Planned Focus |
|---|---|
| Monday | Core concepts |
| Tuesday | Hands-on lab |
| Wednesday | Implementation |
| Thursday | Troubleshooting |
| Friday | Review and documentation |
| Saturday | 3-hour implementation block |
| Sunday | 3-hour integration/evidence block |

## 12-Week Foundation Roadmap

### M1 — Linux Foundations

**Target:** Weeks 1–2

Outcomes:

- filesystem fundamentals;
- permissions and ownership;
- process management;
- CPU, memory, and disk inspection;
- services and logs;
- SSH;
- package management;
- basic shell usage;
- systematic troubleshooting.

Acceptance criteria:

- inspect and terminate processes safely;
- distinguish SIGTERM from SIGKILL;
- manage ownership and permissions;
- diagnose a permissions failure;
- inspect CPU, memory, and disk usage;
- inspect service status and logs;
- connect using SSH;
- use standard CLI tools to investigate a system problem without following a tutorial step-by-step.

Planned issues:

1. Set up Linux development environment
2. Practice filesystem and permissions
3. Practice process and resource management
4. Practice Linux service and log troubleshooting
5. Build Linux troubleshooting cheat sheet
6. Complete Linux foundations assessment

### M2 — Networking Foundations

**Target:** Week 3

Topics:

- IP addressing;
- TCP vs UDP;
- ports;
- DNS;
- HTTP/HTTPS/TLS;
- routing;
- NAT;
- firewall fundamentals;
- load balancing.

Tools:

```text
curl
dig
nslookup
ping
traceroute
ss
ip
```

Acceptance criteria:

- explain request flow between networked services;
- isolate DNS, routing, firewall, port, and application failures;
- use CLI tools to identify the failure domain.

### M3 — Docker Foundations

**Target:** Week 4

Deliverable: a small Python HTTP API packaged as a Docker image.

Acceptance criteria:

- build an image independently;
- run and stop containers;
- inspect logs;
- configure environment variables;
- expose ports;
- use bind mounts or persistent storage;
- explain image/container distinction;
- troubleshoot a failing container;
- use a multi-stage build where justified.

### M4 — Kubernetes Fundamentals

**Target:** Weeks 5–7

Topics:

- Pod;
- Deployment;
- ReplicaSet;
- Service;
- Namespace;
- ConfigMap;
- Secret;
- probes;
- requests and limits;
- volumes;
- Ingress;
- rollout and rollback.

Deliverable: deploy the Dockerized Python application to Kubernetes.

Acceptance criteria:

- deploy and expose the workload;
- update and roll back the workload;
- use configuration and secrets;
- configure liveness/readiness probes;
- inspect workloads;
- explain basic resource requests and limits.

### M5 — Kubernetes Troubleshooting

**Target:** Week 8

Required failure scenarios:

- Pod Pending;
- CrashLoopBackOff;
- ImagePullBackOff;
- service not reachable;
- DNS failure;
- invalid configuration;
- failed readiness probe.

For each scenario:

1. reproduce the failure intentionally;
2. identify root cause;
3. document diagnostics;
4. apply the fix;
5. verify recovery.

### M6 — Azure Foundations

**Target:** Week 9

Topics:

- Resource Groups;
- Virtual Networks;
- Subnets;
- Network Security Groups;
- identity;
- Azure Container Registry;
- AKS fundamentals.

Acceptance criteria:

- explain relationships between core resources;
- deploy or interact with basic resources;
- explain how Kubernetes workload networking maps into Azure infrastructure;
- demonstrate basic identity/access understanding.

### M7 — Terraform Foundations

**Target:** Weeks 10–11

Topics:

```text
provider
resource
variable
output
state
module
plan
apply
destroy
```

Acceptance criteria:

- provision infrastructure from code;
- modify infrastructure safely;
- inspect plans before apply;
- explain Terraform state;
- use variables and outputs;
- create at least one reusable module;
- destroy lab infrastructure safely;
- keep provider dependency selection reproducible with the Terraform lock file;
- keep secrets, state, and sensitive variable files out of version control.

### M8 — CI/CD Integration

**Target:** Week 12

Target flow:

```text
Commit
   ↓
CI
   ↓
Python Tests
   ↓
Docker Build
   ↓
Container Registry
   ↓
Deployment
```

Acceptance criteria:

- pipeline designed independently;
- automated tests;
- automated image build;
- image versioning;
- artifact/image publication;
- automated deployment;
- observable failures through pipeline logs;
- documented implementation.

## Portfolio Project — Platform Delivery Lab

The roadmap evolves one project rather than producing unrelated tutorial repositories.

### Stage 1

```text
Git
 │
 ▼
CI Pipeline
 │
 ├── Tests
 │
 └── Docker Build
         │
         ▼
  Container Registry
         │
         ▼
    Kubernetes
         │
         ▼
     Python API
```

### Stage 2

```text
Terraform
   │
   ▼
Azure Infrastructure
   │
   ▼
AKS
   │
   ▼
GitOps
   │
   ▼
Application
   │
   ├── Metrics
   ├── Logs
   └── Traces
```

### Later Evolution

- developer self-service;
- Internal Developer Platform concepts;
- Backstage;
- Crossplane;
- platform APIs;
- Go and Kubernetes extensibility.

## Deferred Topics

Until foundations are stronger, defer:

- Backstage;
- Crossplane;
- service mesh;
- Kubernetes operators;
- advanced Kubernetes internals;
- advanced Go;
- multi-cloud study;
- multiple simultaneous certifications.

## Certification Strategy

Certifications are not a first-phase priority.

```text
Hands-on Skills
      ↓
Project Evidence
      ↓
Production Exposure
      ↓
Certification
```

Potential later certifications include an Azure infrastructure-focused certification and CKA.

## Roadmap Status

| Area | Status |
|---|---|
| Initial assessment | ✅ Complete |
| Weekly capacity defined | ✅ Complete |
| GitHub operating model defined | ✅ Complete |
| 12-week roadmap | ✅ Defined |
| Repository created | ✅ Complete |
| Initial repository setup | ✅ Complete |
| GitHub Project created | ✅ Complete |
| M1–M8 milestones created | ✅ Complete |
| M1 issues defined | ✅ Complete |
| M1 Linux Foundations | 🚧 In progress (1 of 6 issues complete) |
| M2 Networking Foundations | ⬜ Not started |
| M3 Docker Foundations | ⬜ Not started |
| M4 Kubernetes Fundamentals | ⬜ Not started |
| M5 Kubernetes Troubleshooting | ⬜ Not started |
| M6 Azure Foundations | ⬜ Not started |
| M7 Terraform Foundations | ⬜ Not started |
| M8 CI/CD Integration | ⬜ Not started |

## Review Rules

At the end of each milestone:

1. review acceptance criteria;
2. update demonstrated evidence;
3. document blockers;
4. revise upcoming milestones if required;
5. update pacing based on actual velocity.

Every four weeks:

- reassess workload;
- review demonstrated capability;
- confirm the project is producing real engineering evidence;
- remove low-value passive learning;
- add production-relevant work when possible.

## Current Next Actions

1. Complete M1 filesystem and permissions practice (#4).
2. Complete M1 process and resource management practice (#5).
3. Continue the remaining M1 service/log, cheat-sheet, and assessment work (#6–#8).
4. Record reproducible evidence in focused Pull Requests and validate each issue against its acceptance criteria.

## Change Log

| Date | Change |
|---|---|
| 2026-08-23 | Initial assessment and 12-week foundation roadmap defined |
| 2026-08-23 | Weekly capacity set to 11 hours |
| 2026-08-23 | GitHub selected as roadmap and portfolio system |
| 2026-08-23 | Public repository created |
| 2026-08-23 | Initial repository setup completed |
| 2026-08-23 | Public roadmap revised to emphasize demonstrated evidence rather than private skill scoring |
| 2026-08-26 | GitHub Project, M1–M8 milestones, and M1 issue definitions recorded as complete |
| 2026-08-26 | M1 moved to in progress after completing the Linux development environment setup (#3 / PR #10) |
