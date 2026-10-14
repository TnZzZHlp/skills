# Grilling Checklist

Use this checklist selectively. Inspect available evidence first, then ask only questions whose answers materially affect the plan.

## Question design

For each question, identify the decision, why it matters, viable alternatives, and a reasoned recommendation. Keep unrelated decisions separate. Ask about consequences and failure cases, not only the happy path.

Prioritize by impact and dependency: purpose and scope before architecture, architecture before implementation details. Ask 3–5 questions per round when useful; stop repeating resolved topics.

## Goals and success

- Who is the user, operator, buyer, or affected stakeholder?
- What problem is being solved, and what current behavior must change?
- What concrete user journey demonstrates success?
- What measurable outcomes or observable acceptance criteria define success?
- Is this a prototype, MVP, production release, or migration?

Challenge terms such as "fast," "scalable," "secure," "simple," and "production-ready" until their intended meaning is testable.

## Scope and boundaries

- Which capabilities belong in this iteration?
- What is explicitly excluded?
- Which existing behaviors and interfaces must remain compatible?
- Are there distinct releases or independently deliverable slices?
- What is the source of truth when supplied requirements conflict?

Separate necessary requirements from preferences and possible future features.

## Existing project and constraints

- What project root, repository instructions, code, and prior plans apply?
- Which languages, frameworks, platforms, and dependencies are already established?
- What budget, deadline, staffing, hosting, or licensing limits apply?
- What must be reused, and what may be replaced?
- Which environments and deployment targets must be supported?

Do not propose a new stack merely because it is familiar. Cite inspected paths for existing constraints.

## Architecture and responsibility

- What modules or services own each capability?
- What directory structure and module boundaries fit the scope?
- What belongs in dedicated modules rather than bootstrap files or route handlers?
- How do components communicate, and where is state owned?
- What simpler alternatives exist, and why reject them?
- Which decisions are expensive to reverse?

Expose coupled responsibilities, unnecessary distributed systems, and vague ownership.

## Interfaces and data

- What APIs, schemas, events, and external contracts are required?
- Who owns each contract, and which compatibility guarantees apply?
- What data is stored, where, and for how long?
- What consistency, concurrency, idempotency, or ordering behavior is required?
- Are migrations, import/export, or rollback paths needed?
- What happens when a dependency is unavailable or returns invalid data?

Ask for concrete request/response or workflow examples when abstractions conceal disagreement.

## Security and privacy requirements

- Which actors may access which data and actions?
- Where are authentication, authorization, and trust boundaries?
- Is tenant isolation or abuse prevention required?
- Are there sensitive data, retention, or compliance constraints?
- How are secrets managed without embedding them in plans or source?
- What failure behavior prevents unintended exposure?

Gather requirements only; this checklist does not authorize a security audit or penetration test.

## Reliability and operations

- What availability, latency, throughput, and capacity targets actually matter?
- What retry, timeout, recovery, and rollback behavior is required?
- What logging, metrics, auditability, and support workflows are needed?
- How will rollout and migration avoid breaking existing users?
- What tradeoffs are acceptable when targets conflict?

Do not invent numeric targets or treat proposed targets as accepted.

## Delivery and verification

- What dependencies determine phase order?
- What independently verifiable deliverable ends each phase?
- Which concrete acceptance criteria cover the user journey and failure cases?
- What existing validation commands or end-to-end workflows are available?
- What external access, fixtures, or environments will validation require?
- Which deferred decision must be resolved before a later implementation task?

Planning validation and implementation validation are different: checking document consistency does not mean the software passed its acceptance criteria.

## Exit check

Before requesting final approval:

- The goal, scope, and non-goals are unambiguous.
- Hard constraints and consequential decisions are resolved.
- Architecture and interfaces are specific enough to plan work.
- User-facing outcomes and phase acceptance criteria are verifiable.
- Proposed defaults have been explicitly accepted or remain unresolved.
- Every deferred item has user-accepted impact, a resolution step, and the phase it blocks.
- The plan name, output path, phase breakdown, and update scope are ready for explicit approval.

An unresolved issue affecting scope, feasibility, major contracts, security boundaries, or meaningful acceptance is a blocker. Continue questioning rather than writing a formal plan.
