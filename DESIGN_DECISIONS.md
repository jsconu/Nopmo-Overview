# Design Decisions

These are selected decisions from the private prototype that illustrate the kind of judgment the project is designed to make inspectable.

## Deterministic health before narrative
Where project-health rules can be made explicit, Nopmo computes those signals before asking an LLM to write narrative.

**Reason:** the same evidence should not produce a different health classification because a model phrased its reasoning differently on Tuesday.

**Tradeoff:** deterministic rules can be incomplete or overly rigid, so the system still needs model reasoning for ambiguous synthesis and must expose uncertainty rather than pretend every condition is reducible to a rubric.

## Evidence and provenance are first-class
Findings retain the source signals that support them.

**Reason:** leaders should be able to move from recommendation to evidence instead of trusting an untraceable model assertion.

## Absence is not resolution
A risk is not considered resolved merely because later data fails to mention it.

**Reason:** teams routinely omit unresolved problems from later updates. Closure should require fresh, linked resolution evidence.

## Human review around stakeholder commitments
Committed milestone changes remain reviewable even where lower-impact task updates may be automated.

**Reason:** a milestone is a stakeholder promise and often has downstream business consequences outside the local project system.

## Organization isolation is enforced outside the model
Org/project authorization belongs in application and database boundaries.

**Reason:** prompts and model instructions are not a security boundary.

## Material-change gating
Recurring agent work is gated on meaningful changes where possible.

**Reason:** an unchanged project should not create fresh model cost, fresh prose, or fresh notifications just because the clock advanced.

Time itself can still be material — for example, a milestone moving from future to overdue — so the gate cannot simply mean “did source data change?”

## Failure isolation in background work
One project or connector failure should not poison later work in the same worker cycle.

**Reason:** unattended systems fail differently from interactive demos. A single database or provider error must be visible without cascading across unrelated scopes.

## Refreshed credentials must survive later job failure
OAuth refresh is treated separately from downstream processing.

**Reason:** if a provider rotates a token and the application rolls the new token back because a later step fails, the stored credential can become permanently stale even though refresh itself succeeded.

## LLM output does not grant authority
Models can recommend an action; policy decides whether it can execute.

**Reason:** model confidence is not an access-control primitive and should not be able to expand its own authority.

## Coaching and autonomous behavior are separate from truth
Operating mode may change whether a suggestion queues for approval or can apply automatically. It should not change the underlying evidence or project-health facts.

**Reason:** user preference about autonomy should not rewrite reality.
