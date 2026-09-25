# How I Build With AI Coding Agents

AI coding agents are a major part of how Nopmo is implemented.

I want that to be explicit because the project is partly about learning what changes when an experienced program leader can use AI as implementation leverage.

## What the coding agent does
Depending on the task, an AI coding agent may inspect an existing codebase, propose an implementation plan, generate application code, write or update tests, refactor code, identify likely defects, draft documentation, and compare implementation against requested behavior.

## What I own
I am responsible for the parts that determine whether the product is worth building and whether generated implementation is acceptable:

- defining the user and business problem
- deciding what behavior the system should have
- supplying domain context from real program-management experience
- setting acceptance criteria and constraints
- deciding which actions need human review
- challenging claims that overstate what the product does
- prioritizing failure modes and security concerns
- reviewing architecture choices and tradeoffs
- deciding what must be deterministic vs. model-driven
- shaping evaluation scenarios
- testing the prototype as a skeptical user
- deciding whether a generated change actually advances the product

## What I am still learning
I am not presenting myself as a traditional software engineer or ML researcher.

The technical goal is different: become capable of leading AI-native product/program work with enough depth to trace a system end to end, interrogate generated architecture, recognize dangerous assumptions, reproduce failures, and work effectively with engineers and coding agents.

## A useful standard
The standard I use is not “could I have typed this implementation without AI?”

It is:

> Can I explain why this component exists, what contract it has, what can fail, what should be tested, what the security boundary is, what tradeoff we accepted, and how I would know if the behavior is wrong?

If the answer is no, the feature is not mature enough merely because the code runs.

## Why this matters
Coding agents dramatically reduce the cost of turning a product hypothesis into something testable.

That makes product judgment, evaluation, architecture review, domain expertise, and the ability to direct and critique AI-generated work more important — not less.
