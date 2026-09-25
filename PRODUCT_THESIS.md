# Product Thesis

## Nopmo is not “AI project management software”

The long-term opportunity is not another task tracker with an AI sidebar.

Teams already have systems of record. The harder problem is that management attention is fragmented: the evidence that a project is drifting may be spread across an overdue Jira item, a customer email, a meeting transcript, a calendar dependency, and a status update written three days later.

Nopmo is an attempt to build the intelligence and operating layer across those systems.

## Five hypotheses

### 1. The useful unit is a signal, not a prompt
A prompt is ephemeral. A project signal has source, time, ownership, project context, and provenance. Normalizing signals makes reasoning source-agnostic and allows the system to preserve history.

### 2. AI should explain judgment more often than invent judgment
Many project-health decisions can be grounded in checkable conditions: date movement, dependency state, unresolved blockers, stale evidence, committed milestones, budget thresholds, or missing ownership.

Where deterministic logic is strong enough, the model should explain and synthesize rather than silently redefine the rule.

### 3. Program intelligence needs memory across time
A system that reads today's status without knowing yesterday's status cannot reliably distinguish new, persistent, improving, deteriorating, resolved, or stale conditions.

State and trajectory are product features, not implementation details.

### 4. The output should be a management action or decision
Summaries are useful, but managers ultimately need to know what deserves attention, who needs to decide, what is blocked, and what options are available.

Nopmo therefore treats decisions, dependencies, risks, and suggested actions as first-class objects rather than prose hidden in a status paragraph.

### 5. Autonomy should be graduated
The safe automation level depends on consequence.

Refreshing a source is different from editing a task. Editing a task is different from changing a committed milestone. Drafting an internal update is different from sending an external customer message.

The system should earn autonomy behavior by behavior, with deterministic boundaries, review, auditability, and a fallback to human action.

### 6. Nopmo should infer structure before asking for structure
Organizations rarely present a clean project model. The same work may appear under different names
across email, chat, meetings, ticketing tools, spreadsheets, and executive conversations.

Nopmo should therefore start with evidence, propose the project/program structure it thinks exists,
and ask people to confirm or correct that structure. It should not require teams to recreate clean
metadata inside Nopmo before the system can become useful.

A useful design test is:

> Could Nopmo retrieve or responsibly infer this before asking a person to enter it?

Human effort should be concentrated on ambiguity, correction, decisions, and authorization.

### 6. Nopmo should adapt to the work

Organizations are messy before software sees them. Project names differ across systems. Dates conflict.
Dependencies are implied in meetings but absent from trackers. Important work may not have a clean
project object at all.

Nopmo should therefore connect to the world as it exists, reconstruct a coherent working model, and
ask humans mainly where ambiguity or consequence requires judgment.

The default interaction should be:

**observe → infer structure → show evidence → confirm/correct → monitor**

not:

**create structure → maintain it manually → ask AI to analyze it**

A practical design test follows from this: before adding a required field or setup step, ask whether
Nopmo can derive a useful hypothesis from existing evidence instead.

Humans should spend their time confirming, correcting, deciding, and authorizing—not acting as
Nopmo's data-entry layer.

## What would falsify the thesis?

The project should be considered unsuccessful if real users find that:

- cross-system context adds little beyond the source tools themselves
- recommendations are too noisy to deserve management attention
- evidence is technically present but too cumbersome to inspect
- maintaining normalized state creates more complexity than value
- human review queues become another inbox nobody trusts
- the system cannot explain why it acted or declined to act
- automation savings are outweighed by correction and oversight cost

Those are product questions prototype usage should test.
