# Subplan Template

Use this structure for `subplans/NNN-<phase-name>.md` after the breakdown is approved. Replace placeholders, remove irrelevant sections and template guidance, and use English.

Keep phase and task IDs stable when updating. Preserve existing progress; never imply implementation happened because a plan was generated. New task and acceptance items start unchecked. Check tasks after completing their work and required checks; check acceptance items only after verification passes, with recorded evidence.

---

# <NNN>: <Phase Title>

## Metadata

- Phase ID: <NNN>
- Master plan: [<Project title>](../README.md)
- Implementation state: Not started
- Dependencies: <linked phase IDs or None>
- Goal references: <master-plan goal IDs>
- Decision references: <applicable master-plan decision IDs>

## Objective

<One coherent objective with an observable completion boundary.>

## Scope

### Included

- <capability, behavior, or bounded responsibility>

### Excluded

- <work delegated to other phases or outside project scope>

## Preconditions

- <dependency deliverable, resolved deferred question, approved contract, or required environment>

## Design

### Module boundaries and target paths

| Module or path | Existing or proposed | Responsibility | Planned change |
| --- | --- | --- | --- |
| <repository-relative path> | <existing/proposed> | <ownership> | <bounded change> |

### Interfaces and data

<Relevant APIs, schema changes, events, storage ownership, compatibility constraints, and error cases. Reference master-plan decisions rather than contradicting them.>

### Operational behavior

<Applicable authorization, isolation, failure recovery, retries, observability, migration, rollout, or rollback requirements.>

## Deliverables

- <concrete artifact, working behavior, interface, migration, or operational outcome>

## Acceptance criteria

- [ ] **<NNN>-AC01: <observable outcome, including relevant failure cases>**
  - Planned verification: <specific end-to-end or manual check>
  - Required environment: <prerequisites>
  - Verification evidence: Not run.

## Implementation tasks

- [ ] **<NNN>-T01: <Actionable task title>**
  - Depends on: <phase or task IDs, or None>
  - Target paths: <known repository-relative paths or explicitly proposed modules>
  - Action: <specific changes, including design constraints>
  - Expected output: <observable artifact or behavior>
  - Acceptance references: <NNN>-AC01
  - Planned validation: <grounded command or concrete check>
  - Completion evidence: Not completed; checks not run.

- [ ] **<NNN>-T02: <Actionable task title>**
  - Depends on: <NNN>-T01
  - Target paths: <paths or modules>
  - Action: <specific changes>
  - Expected output: <observable artifact or behavior>
  - Acceptance references: <applicable criterion IDs>
  - Planned validation: <grounded command or concrete check>
  - Completion evidence: Not completed; checks not run.

<Add only the tasks needed for this phase, in dependency order. Do not use vague tasks such as "implement the feature" without bounded changes and expected outputs. Prefer end-to-end validation; do not add unit-test tasks unless requested.>

## Risks and mitigations

| Risk | Impact | Mitigation or rollback | Related task |
| --- | --- | --- | --- |
| <risk> | <impact> | <concrete response> | <task ID> |

## Deferred decisions

| Question | Accepted impact | Resolution task | Blocks |
| --- | --- | --- | --- |
| <accepted nonblocking question> | <consequence> | <task ID> | <dependent task or phase> |

<Use "None" if no details are deferred. Unresolved planning blockers must be resolved before generating this file.>

## Completion and handoff

- <contracts or outputs needed by dependent phases>
- During separately authorized implementation, check each task when its work and required checks are complete; check each acceptance item only after its verification passes. Record the actual commands/procedure, outcome, and evidence location.
- All required task and acceptance checkboxes must be checked before this subplan is ready for its completion commit. Failed, skipped, blocked, or not-run checks remain unchecked and prevent completion.
- Update this document and the master-plan phase state, then inspect working/staged changes and stage only this subplan's implementation and progress updates using explicit paths or reviewed hunks. Preserve unrelated user edits and pre-existing staged changes; pause if safe separation is impossible.
- Create one separate completion commit for this subplan before starting its dependent phase. Follow repository conventions; otherwise use `feat(<plan-name>): complete subplan <NNN> - <phase-name>`. Do not combine completed subplans or commit once per checklist item.
- Verify success and report the commit hash. If committing fails, phase closure remains pending commit; do not claim full completion. Missing Git/repository/identity, failed hooks, or already committed work require user guidance. Do not automatically initialize Git, change identity, bypass hooks, push, rewrite history, or create empty commits.
- Validation results: Not run; this document describes planned work.
- Implementation requires separate authorization; do not execute tasks or create completion commits as part of plan generation.
