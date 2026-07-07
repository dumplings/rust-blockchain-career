# Lifecycle Policy

## Purpose

This policy owns sprint and governance lifecycle rules. It defines state
transitions, roadmap acceptance, execution start, closure, failure, governance
review, observations, handovers, and state synchronization.

`CONTEXT.md` is the only live-state owner. Roadmaps are execution contracts;
reviews, closures, handovers, ledgers, and indexes are evidence. Evidence files
must not override or duplicate live state.

## Sprint State Machine

| State | Meaning | Required durable output |
| --- | --- | --- |
| `PROPOSED` | A candidate direction exists but has not passed specification review. | Optional working proposal |
| `SPEC_REVIEWED` | Scope, stage alignment, density, prerequisites, validation, and risks were reviewed. | Specification Review when the decision must persist |
| `ROADMAP_DRAFTED` | A sprint-specific execution contract exists but has not been accepted. | Roadmap draft |
| `ACCEPTED_WAITING_START` | The learner accepted the roadmap; no execution has begun. | Accepted roadmap and synchronized `CONTEXT.md` |
| `ACTIVE` | An authorized Teacher window may teach and assign checkpoint work. | Synchronized `CONTEXT.md` |
| `VALIDATION_PENDING` | Implementation or checkpoint work is complete enough for final required validation. | Current validation evidence |
| `CLOSED_PASS` | All required validation passed and the sprint counts as completed learning. | Closure and state/coverage updates |
| `CLOSED_PASS_WITH_NOTES` | Required validation passed with recorded non-blocking gaps. | Closure and state/coverage updates |
| `STOPPED_UNCREDITED` | Execution stopped without a validated completion boundary. | Failure/stop evidence when needed |
| `FAILED_DISCARDED` | The attempt failed and does not count as completed learning. | Failure review when the failure is meaningful |

Normal transitions:

`PROPOSED -> SPEC_REVIEWED -> ROADMAP_DRAFTED -> ACCEPTED_WAITING_START -> ACTIVE
-> VALIDATION_PENDING -> CLOSED_PASS | CLOSED_PASS_WITH_NOTES`

Exceptional transitions:

- `ACTIVE -> STOPPED_UNCREDITED`
- `ACTIVE | VALIDATION_PENDING -> FAILED_DISCARDED`
- `VALIDATION_PENDING -> ACTIVE` when additional accepted-scope work is required

Forbidden transitions:

- no proposal, review, roadmap draft, repository update, next-action entry, or
  startup checklist may skip directly to `ACTIVE`;
- closed, stopped, or failed work must not silently return to `ACTIVE`;
- a replacement after stopped or failed work requires an explicit new or revised
  accepted scope;
- sprint closure does not automatically advance the curriculum stage or start the
  next sprint;
- evidence files do not create authority by describing a possible next action.

## Specification And Roadmap Lifecycle

The Teacher is the default pedagogical owner of sprint specifications and
roadmaps. The Architect reviews stage alignment, scope, workflow separation, or
governance risk when needed. The learner owns final acceptance.

A Specification Review should establish:

- current stage and relevant validated coverage;
- candidate capability boundary and stage alignment;
- learning density and project-continuation value;
- scope and explicit non-goals;
- learner implementation and explanation work;
- prerequisite inventory and dependency uncertainty;
- Student, Codex, and Teacher validation requirements;
- external baseline and job-transfer value when domain alignment matters;
- risks and decisions required before roadmap acceptance.

A roadmap is a sprint-specific execution contract. It should contain identity,
objective, stage alignment, evidence gap, scope, non-goals, checkpoint sequence,
project boundary, sprint-specific prerequisites, validation requirements,
completion criteria, and unique risks. It should reference rather than restate
global role, language, lifecycle, validation, and handoff rules.

Stage 3, Stage 4, and other job-oriented roadmaps must identify a credible
external baseline, real-world workflow, toy boundary, transferable capability,
interview relevance, and path toward realistic work. Secret handling must remain
explicit: private keys, seed phrases, credentials, real-funds information, and
sensitive tokens must not be pasted into agent chat or committed.

Sprint design should be cohesive and substantial enough to create meaningful
capability growth. Avoid both mechanical low-density tasks and unrelated scope
expansion. When an existing project has exhausted its learning value, move to a
better capability boundary instead of extending it for momentum alone.

## Acceptance And Execution Start

Roadmap acceptance creates `ACCEPTED_WAITING_START`; it does not create `ACTIVE`.

The transition to `ACTIVE` requires all of the following:

1. an accepted current roadmap;
2. an explicit learner command to start the sprint or checkpoint work;
3. a window explicitly authorized to act as Teacher;
4. a passing Teacher Startup Checklist.

Project creation, implementation assignments, and checkpoint instruction are
allowed only after `ACTIVE`.

The learner may combine roadmap acceptance and execution start only when the
message unambiguously makes both decisions and authorizes the current window as
Teacher.

## Architect-To-Teacher Transition

An execution-start command does not by itself convert an Architect or governance
window into a Teacher window.

If the learner addresses a start command to an Architect, the Architect may:

- confirm the accepted roadmap and readiness state;
- prepare the Teacher startup material;
- provide a handoff or copy-ready Teacher launch instruction.

The Architect must not begin teaching, assign checkpoint work, or create a
learning project unless the learner explicitly authorizes that same window to
switch to Teacher or starts a separate Teacher window. The Teacher Startup
Checklist must then pass.

## Active Execution And Scope Adjustment

The Teacher owns checkpoint teaching and learning validation; the learner owns
implementation. Execution must follow the accepted roadmap's sequence, scope,
non-goals, and validation requirements.

Pace or density problems should be handled at checkpoint boundaries by narrowing,
reinforcing, deferring, or splitting work. A material scope change requires a
separate learner decision and, when necessary, governance review. Runtime
miscalibration is not learner failure.

When required implementation work is complete, move to `VALIDATION_PENDING`.
This state does not imply pass or closure.

## Closure

Closure decides whether work counts as completed learning progress. A normal
closure must record:

- final lifecycle state;
- scope completed and scope excluded;
- Student Validation;
- Codex Repository Validation when required;
- Teacher Learning Validation;
- interview-prep pack or explicit learner waiver when required;
- capability growth and remaining gaps;
- coverage changes supported by evidence;
- recommended next action without authorizing it.

Closures are English repository assets by default. A pass establishes current
capability within the validated boundary, not permanent mastery.

## Stopped And Failed Work

Stopped or failed work receives no automatic learning credit. Code may be kept,
discarded, or reused later, but completion credit requires formal revalidation
under an accepted boundary.

Use `STOPPED_UNCREDITED` when execution ended without a valid completion boundary.
Use `FAILED_DISCARDED` when the attempt is explicitly rejected or invalidated.
Create a failure review when the event discards learning progress, exposes a
reusable failure mode, triggers governance review, or requires agent replacement.

Do not reopen a failed sprint by implication. A retry or replacement must define
its own accepted scope.

## Governance Lifecycle

Governance work follows:

`Observed Need -> Governance Review When Needed -> Decision -> Codex Repository
Update -> Human Review`

Create or change rules only for a demonstrated ambiguity, recurring failure,
state drift, durable knowledge risk, or structural simplification need. Prefer
updating the canonical owner and removing downstream copies over adding another
warning layer.

Governance reviews should distinguish:

- current state;
- reusable policy;
- sprint execution contract;
- validated or historical evidence;
- implementation or teaching error that does not require a new rule.

## Observation Lifecycle

An observation is a compact signal for a governance-relevant issue likely to
recur. Do not use observations as a brainstorming backlog.

- first occurrence: observe and preserve incident evidence where relevant;
- repeated occurrence: governance review required;
- disposition: `ACCEPTED`, `REJECTED`, or `RETIRED`.

When a rule already covers the issue, correct execution and retire the
observation. Active observations may be recorded in `CONTEXT.md`; detailed
incident evidence belongs in the relevant closure, failure review, or governance
review.

## Handover Lifecycle

Handovers are conditional historical evidence, not a default lifecycle step and
not startup authority. Create one only when an agent transition has unique
information that is not already preserved in `CONTEXT.md`, the accepted roadmap,
a closure, or another evidence file.

A necessary handover should contain only unique transition facts, unresolved
risks, and task-specific evidence pointers. It must not reproduce the current
state, startup bundle, or global rules as a competing source.

## Cross-Agent Requests

When another agent must act, provide a ready-to-send request containing:

1. target role;
2. purpose;
3. authoritative current state;
4. required files or evidence;
5. requested decision or action;
6. scope boundaries and non-goals;
7. expected output;
8. authorization status;
9. evidence-delivery method for remote roles.

Do not require the learner to reconstruct missing repository context manually.

## State Synchronization And Human Review

Update `CONTEXT.md` only at meaningful state transitions such as acceptance,
start, stop/failure, validation boundary, closure, stage transition, or a current
risk/authorization change. Do not write the same live state into reviews,
roadmaps, handovers, indexes, or logs.

Coverage ledgers and `learning-log.md` may be updated when validated learning
changes their evidence. Git status, diffs, and commit history are supporting
evidence, not governance goals. The learner owns final review, commit timing,
commit grouping, and push decisions.
