# Demo Walkthrough

A strong Nopmo demo should show a chain of evidence and control, not a collection of disconnected AI features.

## Scenario
A delivery issue in one project threatens a dependency used by another project.

### 1. Source refresh
A connector receives or fetches an updated issue or message. The raw source identity and timestamp are preserved.

### 2. Normalization
The source-specific object becomes a project signal that downstream logic can understand without depending on Jira-, Slack-, or email-specific fields.

### 3. Material-change check
The system determines whether the new information changes the project state enough to warrant additional work.

This prevents a scheduler from generating new model calls and new prose for an unchanged project.

### 4. Project reasoning
Status/risk/dependency logic evaluates the new signal against existing project state and related evidence.

The reviewer should be able to distinguish direct evidence, deterministic classification, model inference, and model-written explanation.

### 5. Cross-project interpretation
If another project depends on the affected deliverable, the portfolio layer should surface that relationship rather than treating the issue as isolated.

### 6. Recommendation / decision request
The system describes what deserves attention. When a real management choice exists, the output should make the missing owner, deadline, or decision explicit.

### 7. Human review
The user can inspect the evidence behind the recommendation before accepting a consequential change.

### 8. Bounded action
Policy — not model confidence — determines whether the action can be executed automatically, queued for approval, or blocked.

### 9. Longitudinal memory
The next run compares against retained state so the system can distinguish new, persistent, improving, deteriorating, stale, or resolved conditions.

## What the demo should prove

A reviewer should leave understanding:

- where the evidence came from
- what the model inferred versus what the application computed
- why the recommendation exists
- why an action was or was not allowed
- whether another project is affected
- what will happen on the next run if nothing changes

That is a stronger demonstration of agentic program intelligence than showing a chatbot answer a project-management question.
