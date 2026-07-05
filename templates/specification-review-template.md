# Specification Review Template

## Review Identity

- Proposed sprint:
- Stage:
- Primary project:
- Review owner:
- Review date:
- Execution status:

## Current State

Summarize the authoritative current state, including:

- active sprint status;
- previous sprint outcome;
- current stage;
- current milestone;
- known failed, discarded, or non-credited work.

## Documents Reviewed

List the files used as review evidence.

Use current repository state and stage-relevant evidence rather than a cumulative historical bundle.

Core review inputs usually include:

- `AGENTS.md`
- `CONTEXT.md`
- `roadmaps/master-roadmap.md`
- `docs/policies/sprint-governance-policy.md`
- the learner's current direction or candidate decision
- the approved coverage artifact for the current stage, when one exists

Load conditionally when the decision requires them:

- `TODO.md` when selecting or changing current actionable work;
- Teacher, Codex, language, or governance policy for the corresponding operational question;
- a previous roadmap or closure when the candidate depends on carry-forward scope or validated outcomes;
- a failure review or handover when failure handling or authority continuity is relevant;
- `learning-log.md` when chronology or evidence cannot be resolved from current state, coverage, and relevant reviews.

Do not require the full learning log, all historical roadmaps, or the latest handover merely because they exist.

## Proposed Direction

State the candidate sprint direction in one or two paragraphs.

## Learning Density And Project Continuation

Assess whether the proposed sprint has enough learning density to justify a dedicated sprint.

Address:

- whether the sprint is at risk of being too small or too diffuse;
- whether related remaining work should be consolidated into one sprint;
- whether the proposed project still has meaningful learning value for the current stage;
- whether the project should be continued, finalized through a consolidation sprint, replaced by a new project, or followed by a stage exit assessment.

If the same project has already been used across multiple sprints, explicitly state whether the project is still worth continuing and why.

## Stage Alignment

Explain why the proposed direction fits the current stage and long-term roadmap.

Explicitly state which stage the sprint should not advance into.

## External Baseline And Job-Transfer Target

- Authoritative source or recognized benchmark:
- Real-world concept or workflow:
- Toy or simplification boundary:
- Transferable engineering capability:
- Interview or industry relevance:
- Path toward a more realistic artifact or workflow:
- Real-world setup or prerequisites, if applicable:

Quality gate: state the concrete real-world work, interview capability, or professional engineering capability gained; if it is unclear or unsupported by the external baseline or stage coverage gap, recommend revision before roadmap acceptance.

Do not include secrets in the review. Keep private keys, seed phrases, real-funds credentials, API secrets, and sensitive tokens out of chat and repository artifacts; refer only to safe local environment-variable or ignored local-config setup.

## Proposed Scope

In scope:

- Scope item.

Out of scope:

- Non-goal.

## Expected Learner Work

List the implementation, explanation, debugging, testing, or design work expected from the learner.

List any new crate, tool, API pattern, protocol concept, Rust syntax surface, or support concept that must be confirmed or taught before use; keep the prerequisite inventory compact.

## Expected Tests And Validation

Required validation layers:

1. Student Validation
2. Codex Repository Validation
3. Teacher Learning Validation

Expected checks:

- Check or command.

Repository validation target:

- Repository or project root.

## Risks And Ambiguities

List scope risks, stage-alignment risks, learning-density risks, project-exhaustion risks, workflow risks, technical ambiguities, or missing information.

## Decisions Needed

List the decisions required before roadmap creation or sprint execution.

Examples:

- learner approval;
- Architect review;
- scope revision;
- repository update;
- project continuation or exit decision;
- replacement of the proposed direction.

## Recommended Next Action

State the next action and who should perform it.

## Authorization Status

State clearly:

- whether this is a review only;
- whether roadmap creation is authorized;
- whether sprint execution is authorized.

Specification Review does not authorize sprint execution by itself.

## Language Note

Specification Review reports are repository-oriented outputs and should be written in English by default.
