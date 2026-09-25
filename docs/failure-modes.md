# Failure Modes and Resilience

Production readiness should describe what the service does when assumptions stop being true.

## Questions for every dependency

- What if it is slow?
- What if it returns errors?
- What if it is completely unavailable?
- What if only one region or zone can reach it?
- What if responses are stale or malformed?
- What if retry traffic becomes larger than original traffic?

## Graceful degradation

Degradation preserves the most valuable user journeys while disabling or simplifying lower-priority work.

Examples:
- serve cached data with explicit staleness;
- disable recommendations while keeping checkout available;
- switch a synchronous enrichment step to asynchronous processing;
- return a reduced response instead of timing out the entire request.

## Load shedding

Load shedding intentionally rejects work before saturation causes uncontrolled failure.

A useful design identifies:
- admission point;
- priority of work;
- rejection signal;
- retry guidance;
- metrics showing shed load;
- recovery behavior.

## Failure-mode table

| Failure | Detection | User impact | Automatic behavior | Operator action |
|---|---|---|---|---|
| dependency timeout | latency/error metric | degraded response | bounded timeout + fallback | investigate dependency |
| overload | saturation + queue depth | selective rejection | load shedding | scale or reduce demand |
| data-store outage | connection/error metric | read/write impact | failover or degraded mode | execute recovery runbook |
