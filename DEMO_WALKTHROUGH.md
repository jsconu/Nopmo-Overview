# Demo Walkthrough

The design-partner demo is intentionally narrow. It should prove one complete management loop rather than tour the feature set.

## Scenario

Three initiatives are related:

- **Platform API** — owns a delivery needed by downstream testing.
- **Customer Launch** — depends on the API and carries the external go-live commitment.
- **Training & Enablement** — plans content and sessions against the launch date.

The Platform API develops a delivery problem. Two different sources also disagree about the launch date.

## 1. Start on Today

The demo opens on **Today**, not on a project setup screen.

The first view should answer:

> What deserves management attention right now?

### Cross-project impact

Nopmo should show that the Platform API problem affects Customer Launch because regression testing waits on it.

The point is not that two projects are independently yellow. The insight exists because of the relationship between them.

### Conflicting evidence

Two sources contain incompatible launch dates.

Nopmo should surface the disagreement rather than silently selecting the newest value.

The user should be able to inspect the sources and establish the working truth.

### Decision / intervention

The attention item should make the management choice explicit, including the affected projects and supporting evidence.

Consequential changes remain reviewable.

### Outcome check

A prior decision is still being tracked.

The user can record whether the expected result is improving, achieved, mixed, or failed, preserving evidence about what happened after the intervention.

## 2. Open an affected project only when useful

The project view exists to inspect status, evidence, risks/issues, sources, commitments, and project relationships.

Detailed backlog/schedule/resource views are secondary. When a source system such as Jira is connected, Nopmo is not trying to replace that system.

## 3. Show why Nopmo reached the conclusion

A reviewer should be able to distinguish:

- source evidence,
- deterministic findings,
- model inference or explanation,
- proposed changes,
- verified state,
- policy/approval decisions,
- execution results.

The model never grants itself authority.

## What the demo should prove

A design partner should leave understanding that Nopmo:

- detects implications that only exist across projects,
- surfaces disagreement instead of inventing certainty,
- focuses attention rather than producing an endless insight feed,
- keeps consequential actions under explicit control, and
- checks whether decisions actually worked.

That is the demo standard.
