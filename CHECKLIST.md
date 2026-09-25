# Production Readiness Checklist

## 1. Service context
- [ ] Owner and escalation path are known.
- [ ] Critical user journeys are documented.
- [ ] Upstream and downstream dependencies are mapped.
- [ ] Data classification and regulatory constraints are understood.

## 2. Reliability objectives
- [ ] SLIs measure user-visible behavior.
- [ ] SLO targets and measurement windows are defined.
- [ ] Error-budget policy exists for material services.
- [ ] Availability and latency targets match business expectations.

## 3. Failure modes
- [ ] Dependency unavailability is handled intentionally.
- [ ] Timeouts are bounded.
- [ ] Retries use backoff and do not amplify overload.
- [ ] Graceful degradation paths are defined.
- [ ] Load shedding behavior is defined.
- [ ] Startup and shutdown are graceful.

## 4. Capacity and scaling
- [ ] Normal and peak demand are quantified.
- [ ] Requests and limits are based on measurements.
- [ ] Autoscaling signals and bounds are understood.
- [ ] Saturation signals are observable.
- [ ] Capacity headroom is explicit.

## 5. Data and recovery
- [ ] Backup scope and retention are defined.
- [ ] Restore has been tested.
- [ ] RPO and RTO are defined where relevant.
- [ ] Data migrations are reversible or safely forward-only.
- [ ] Disaster-recovery dependencies are documented.

## 6. Deployment safety
- [ ] Health and readiness checks represent real service health.
- [ ] Rollback or roll-forward procedure is known.
- [ ] Deployment strategy limits blast radius.
- [ ] Configuration changes are versioned.
- [ ] Feature flags have owners and cleanup expectations.

## 7. Observability
- [ ] Golden signals are measurable.
- [ ] Logs contain enough context for investigation.
- [ ] Distributed traces exist for critical paths where useful.
- [ ] Dashboards answer operational questions.
- [ ] Alerts are actionable and mapped to runbooks.

## 8. Incident readiness
- [ ] On-call ownership is clear.
- [ ] Runbooks cover high-impact failure modes.
- [ ] Incident severity and escalation criteria are known.
- [ ] Post-incident learning has a defined process.

## 9. Security
- [ ] Least privilege is applied.
- [ ] Secrets are not stored in source control.
- [ ] Authentication and authorization failure modes are tested.
- [ ] Dependencies and images are scanned.
- [ ] Audit requirements are met.

## 10. Cost and operations
- [ ] Major cost drivers are known.
- [ ] Operational toil is identified.
- [ ] Manual procedures have owners and automation candidates.
- [ ] Support expectations match staffing and system criticality.
