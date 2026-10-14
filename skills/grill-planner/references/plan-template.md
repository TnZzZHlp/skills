# Master Plan Template

Use this structure for `docs/plans/<confirmed-plan-name>/README.md` after explicit approval. Replace placeholders with confirmed information. Remove irrelevant sections and all template guidance. Use English.

Implementation status must be truthful. A newly approved plan is not an implemented feature. New success criteria start unchecked; check them only when verified and record evidence. Preserve verified progress when updating.

---

# <Project or Feature Title>

## Plan metadata

- Plan name: <confirmed-kebab-case-name>
- Project root: <approved project root; use a portable repository-relative description where possible>
- Plan directory: <approved repository-relative directory>
- Planning state: Approved
- Implementation state: Not started
- Approval: <concise reference to explicit user confirmation; no invented identity or timestamp>

## Summary

<Problem, intended users, desired outcome, and current context.>

## Goals and success criteria

- [ ] **G01: <goal>** — <specific observable outcome>
  - Planned verification: <concrete check and prerequisites>
  - Verification evidence: Not run.

## Scope

### Included

- <capability or required behavior>

### Non-goals

- <explicitly excluded capability>

## Current state and evidence

| Finding | Evidence | Planning impact |
| --- | --- | --- |
| <repository fact or user-supplied requirement> | <path or confirmed source> | <constraint or opportunity> |

<For a greenfield project, identify that no existing implementation was inspected.>

## Constraints

- <accepted technical, product, compatibility, operational, or delivery constraint>

## Architecture

### Responsibility boundaries

| Module or service | Responsibility | Owned state or contract |
| --- | --- | --- |
| <module> | <bounded responsibility> | <state or interface> |

### Proposed directory structure

<Repository-grounded directory/module tree. Distinguish existing paths from proposed paths. Keep entry points thin.>

### Interfaces and data flows

<Key APIs, schemas, events, storage ownership, external dependencies, and failure behavior.>

### Operational requirements

<Applicable security, privacy, reliability, observability, migration, and rollback requirements.>

## Decisions

| ID | Decision | Rationale | Alternatives and tradeoffs |
| --- | --- | --- | --- |
| D01 | <confirmed decision> | <reason> | <rejected alternatives and consequences> |

## Accepted assumptions

| ID | Assumption | Impact if false | User acceptance |
| --- | --- | --- | --- |
| A01 | <explicitly accepted nonblocking assumption> | <impact> | <confirmation reference> |

<Use "None" when no assumptions were accepted.>

## Subplans

| ID | Subplan | Goal and deliverables | Depends on | Acceptance boundary | Implementation state |
| --- | --- | --- | --- | --- | --- |
| 001 | [<Phase title>](subplans/001-<phase-name>.md) | <scope and outputs> | None | <observable completion boundary> | Not started |
| 002 | [<Phase title>](subplans/002-<phase-name>.md) | <scope and outputs> | 001 | <observable completion boundary> | Not started |

### Execution order

<Dependency order, integration checkpoints, and safe parallel work if relevant. No work is launched by this plan.>

## Validation strategy

| Criterion | Planned check | Environment or prerequisite | State |
| --- | --- | --- | --- |
| G01 | <grounded end-to-end check or observable verification> | <required access, data, or environment> | Not run |

<List known commands only when supported by repository evidence or an approved tooling decision. Do not claim checks passed.>

## Risks

| Risk | Impact | Mitigation | Affected phase |
| --- | --- | --- | --- |
| <risk> | <impact> | <action or contingency> | <phase ID> |

## Accepted deferred questions

| ID | Deferred question | Accepted impact | Resolution step | Must resolve before |
| --- | --- | --- | --- | --- |
| Q01 | <nonblocking detail> | <user-accepted consequence> | <concrete decision or investigation> | <phase or task> |

<Use "None" if nothing is deferred. Do not put unresolved planning blockers here.>

## Implementation progress and commits

- During separately authorized implementation, check completed task items and verified acceptance items in each subplan, and update the corresponding phase state here. Check master-plan success criteria only after their full outcome is verified; record actual evidence.
- A finished subplan requires all its task and acceptance checkboxes checked. Failed, skipped, blocked, or not-run checks prevent completion.
- Include that subplan's implementation changes and verified plan progress in one separate completion commit before starting the next dependent subplan. Do not batch multiple completed subplans into one commit.
- Inspect working and staged changes; stage only reviewed paths or hunks for that subplan. Preserve unrelated edits and pre-existing staged work. If safe separation is impossible, pause for guidance.
- Follow repository commit conventions; otherwise use `feat(<plan-name>): complete subplan <NNN> - <phase-name>`. Report the verified commit hash in the handoff, not a fabricated hash in this document.
- Commit failure leaves phase closure pending commit. Missing Git/repository/identity, failed hooks, or already committed changes require user guidance; do not initialize Git, alter identity, bypass hooks, rewrite history, push, or create empty commits automatically.
- Plan generation and plan-only revisions do not create these completion commits.

## Handoff

<Identify the first phase and its prerequisites for a separately authorized implementation workflow. State that generating this plan does not start implementation.>
