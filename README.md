# Nopmo — Program Intelligence Across Projects

**A public product and architecture case study for a private working prototype.**

Nopmo starts with the messy systems where work already happens, organizes what they collectively say, and surfaces the few things across projects that deserve management attention.

It is designed for situations where the important conclusion does not live in one Jira issue, one status report, or even one project. A delivery change in one initiative may expose a launch elsewhere, consume a shared resource, contradict a stakeholder commitment, or create a decision that needs leadership attention.

## Source-first by design

Nopmo should not require a team to build a pristine project model before it can help.

The intended first-use experience is:

**connect sources → discover work → resolve ambiguity → confirm structure → keep reconciling it**

If Jira calls something one name, email calls it another, and a meeting implies a dependency nobody
documented, Nopmo should preserve those signals and propose the structure it thinks exists. Humans
confirm or correct the model instead of reconstructing the evidence by hand.

Those corrections should become durable organizational knowledge. If a reviewer confirms that
“Customer Portal,” “Portal Phase 2,” and “CX Portal” refer to the same initiative, Nopmo remembers
those names when future signals arrive instead of repeatedly asking the same identity question.

## What Nopmo is trying to do

Nopmo connects project signals from tools such as Jira, email, chat, calendars, meetings, and documents, then maintains an evidence-backed view of execution over time.

The product is built to answer questions such as:

- What changed that actually matters?
- What other projects are affected?
- Which sources disagree?
- What decision or intervention is needed?
- What evidence supports that conclusion?
- What action is safe to take automatically?
- Did the eventual decision actually improve the situation?

## The management loop

```text
Execution signals
      |
      v
Evidence + source quality
      |
      v
Findings / proposed changes
      |
      v
Verified project state
      |
      v
Cross-project impact + contradictions
      |
      v
Management attention
      |
      v
Decision / bounded action
      |
      v
Outcome check
```

The important design choice is that **an LLM is not the authorization layer**. Models can interpret, explain, draft, and recommend. Deterministic rules, organization boundaries, policy, and explicit review decide what is allowed to happen.

## Current prototype

The private prototype includes:

- organization-scoped authentication and access
- source connectors and normalized project signals
- deterministic status/risk logic with evidence provenance
- longitudinal state and material-change detection
- explicit project-to-project relationships
- cross-project impact propagation
- conflicting-signal detection
- a management Attention Queue
- proposed-change review inside the relevant attention item
- first-class decision history and outcome tracking
- human review boundaries around consequential changes
- recurring background work with failure isolation and LLM cost controls
- OAuth credential refresh/reconnect handling
- groundwork for treating humans, AI agents, and services as work actors

The application source remains private. This repository documents the product thesis, architecture choices, safety boundaries, and representative demo.

## Representative demo

The focused demo uses three related initiatives:

**Platform API → Customer Launch → Training & Enablement**

A blocked API deliverable appears local at first. Nopmo traces the dependency into the customer launch, then into the downstream training commitment. At the same time, two sources disagree about the intended launch date.

The Today experience surfaces:

1. the cross-project consequence,
2. the conflicting launch-date evidence,
3. the management decision that needs attention, and
4. a prior decision whose outcome still needs to be checked.

See [DEMO_WALKTHROUGH.md](DEMO_WALKTHROUGH.md).

## Product thesis

Nopmo is not intended to replace Jira, Smartsheet, Monday, or other systems of record.

Its thesis is that the missing layer is **management intelligence across those systems**: preserving evidence, connecting consequences, identifying disagreement, focusing scarce human attention, and closing the loop after decisions.

See [PRODUCT_THESIS.md](PRODUCT_THESIS.md).

## How AI coding agents are used

AI coding agents generate a significant amount of implementation. That is explicit.

I own the product definition, domain model, prioritization, acceptance criteria, operating policies, architecture review, evaluation design, failure analysis, and the decision about whether generated implementation actually matches the intended behavior.

See [AI_COLLABORATION.md](AI_COLLABORATION.md).

## Status

Nopmo is a prototype under active development and is beginning design-partner testing.
