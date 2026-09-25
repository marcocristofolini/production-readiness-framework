# Production Readiness Framework

A practical framework for deciding whether a service is ready to operate safely in production.

The goal is not a vanity maturity score. The goal is to make **risks, assumptions, failure modes and operational responsibilities explicit before users discover them for you**.

## Review flow

```mermaid
flowchart LR
    A[Service Context] --> B[Reliability Objectives]
    B --> C[Failure Modes]
    C --> D[Capacity & Overload]
    D --> E[Observability]
    E --> F[Deployment & Recovery]
    F --> G[Incident Readiness]
    G --> H[Decision & Actions]
```

## Review dimensions

1. Reliability objectives and SLOs
2. Dependencies and failure modes
3. Capacity, scaling and overload protection
4. Data integrity, backup and recovery
5. Deployment, rollback and change safety
6. Observability and alerting
7. Incident response and ownership
8. Security, identity and secrets
9. Cost and operational sustainability

Start with [CHECKLIST.md](CHECKLIST.md) and use [templates/service-readiness-review.md](templates/service-readiness-review.md) for an actual review.

## Principles

- A deployment succeeding is not proof of production readiness.
- Graceful degradation should be intentional.
- Retry, timeout and circuit-breaking policies must be designed together.
- Load shedding protects useful work during overload.
- Alerts should represent actionable risk or user impact.
- Recovery procedures should be tested, not merely documented.
- Unknowns are valid review outcomes when they are recorded and assigned.

## Decision states

A review can end as:
- **Ready** — no known blocker for the defined launch scope.
- **Conditional** — launch is acceptable only with explicit mitigations, limits or follow-up dates.
- **Not ready** — one or more known risks should be addressed before launch.

These are contextual decisions, not universal maturity ratings.
