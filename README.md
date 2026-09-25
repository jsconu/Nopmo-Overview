# Nopmo — Agentic Program Intelligence

**A public product and architecture case study for a private working prototype.**

Nopmo explores what project and program management looks like when AI moves beyond summarizing work and starts continuously interpreting delivery signals, identifying what deserves attention, preparing decisions, and taking bounded actions under explicit human oversight.

The production prototype is private. This repository intentionally documents the **product thinking, system design, safety model, evaluation approach, and demo flow** without publishing the private application source code, credentials, or customer data.

## The problem

Project information is fragmented across Jira, email, chat, calendars, meetings, documents, spreadsheets, and people's heads.

Most AI project tools stop at one of two places: summarizing the context they are given, or attaching a chatbot to an existing project-management application.

Nopmo is aimed at a different layer: **program intelligence across systems and over time.**

It is designed to answer questions like:

- What materially changed since the last review?
- Which signals point to a real delivery risk rather than normal project noise?
- Is a dependency merely waiting, actively blocked, or becoming dangerous?
- Which decision needs a human owner and deadline?
- What action is safe to suggest?
- What action, if any, is safe to execute automatically?
- What evidence supports the conclusion?

## Core operating loop

```text
Jira / Email / Chat / Calendar / Meetings / Documents
                         |
                         v
                  Source connectors
                         |
                         v
              Normalized project signals
                         |
                         v
          Deterministic checks + agent reasoning
                         |
              +----------+-----------+
              |          |           |
            Status      Risk     Dependencies
              |          |           |
              +----------+-----------+
                         |
                         v
              Decisions / recommendations
                         |
                         v
               Human review boundaries
                         |
                         v
          Bounded action + audit / history
```

The important design choice is that **an LLM is not the authorization layer**. Model output can interpret, explain, draft, and recommend. Deterministic rules, organization boundaries, operating mode, and explicit approval policies decide what is allowed to happen.

## What exists in the private prototype

The working prototype includes real application slices rather than only prompt demos:

- organization-scoped authentication and access
- Jira and communication connector work
- normalized project signals
- project, risk, status, backlog, schedule, portfolio, communications, and task-update workflows
- longitudinal project state and material-change detection
- evidence/provenance handling
- human approval queues for consequential actions
- coaching vs. autonomous operating modes
- recurring background work with per-org controls
- failure isolation and observability
- LLM usage caps and change-gating to avoid unnecessary model calls
- OAuth refresh handling and reconnect states
- calibration/evaluation work using synthetic scenarios and reviewed datasets
- explicit guardrails around milestone changes, customer-facing work, and communications

This repository does **not** claim every connector or autonomous behavior is production-ready. The point of the prototype is to make the hard operating questions testable.

## The product thesis

The differentiator is not “many agents.”

Specialist agents are an implementation technique. The product thesis is that an AI-native program system should maintain context across time, separate evidence from inference, reason across projects rather than inside one ticket, surface management decisions rather than just summaries, preserve inspectability, and make automation graduated and reversible.

See [PRODUCT_THESIS.md](PRODUCT_THESIS.md).

## Representative demo flow

A useful Nopmo demo traces one real signal through the system:

1. A Jira issue or communication signal changes.
2. The connector refreshes and normalizes it.
3. The system determines whether the change is material.
4. Risk/status/dependency logic evaluates the signal in project context.
5. Cross-project context can change the interpretation.
6. Nopmo surfaces a recommendation or decision request.
7. A human can inspect the supporting evidence.
8. Any consequential action passes through the appropriate policy or approval boundary.
9. The outcome is retained for later comparison rather than forgotten on the next prompt.

See [DEMO_WALKTHROUGH.md](DEMO_WALKTHROUGH.md).

## Design decisions worth challenging

Examples include:

- Why not let the LLM determine project health?
- Why keep provenance for every material finding?
- Why not auto-close a risk when it disappears from the next status update?
- Why are committed milestone changes harder to automate?
- Why gate recurring model work on material change?
- Why is organization authorization enforced outside the prompt?

See [DESIGN_DECISIONS.md](DESIGN_DECISIONS.md).

## How AI coding agents are used

AI coding agents generate a significant amount of implementation. That is explicit, not hidden.

The work I own is product definition, domain modeling, prioritization, acceptance criteria, operating policies, architecture review, evaluation design, failure analysis, and deciding whether generated implementation actually matches the intended system behavior.

I use AI to increase implementation leverage; I do not treat generated code or generated product claims as automatically correct.

See [AI_COLLABORATION.md](AI_COLLABORATION.md).

## What this portfolio is intended to demonstrate

- AI product design
- technical program tradeoffs
- multi-system workflows
- human-in-the-loop automation
- reliability and observability
- model cost and change gating
- data isolation and credential boundaries
- evaluations and evidence
- enterprise adoption constraints

## Related open-source project

[Project Risk Agent](https://github.com/jsconu/project-risk-agent) extracts evidence-backed risks, issues, dependencies, and decision requests from project signals. It provides a smaller, fully public view of several ideas that also matter in Nopmo.

## Status

Nopmo is a prototype under active development. The application source remains private while the product model, design decisions, and selected architecture are shared here for review and discussion.
