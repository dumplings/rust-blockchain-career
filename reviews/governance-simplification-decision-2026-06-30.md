# Governance Simplification Decision — 2026-06-30

## Decision Status

- Implementation status: Complete
- Acceptance status: Accepted by learner on 2026-06-30
- Scope: Governance repository only
- Learning execution: Not started or authorized by this decision

## Problem

The governance architecture was sound, but several active surfaces had begun to duplicate the same rules. A stale Specification Review template still required cumulative historical inputs, the human runbook maintained a second Architect prompt, current tasks mixed actions with standing constraints, and sprint roadmaps repeated global policy at length.

## Decisions

1. Teacher owns pedagogical roadmap design by default.
   - Teacher owns objectives, checkpoints, exercises, learning density, and validation design.
   - Architect reviews stage alignment, scope, workflow separation, and governance consistency when risk exists.
   - Learner retains final direction, acceptance, and start authority without becoming detailed curriculum QA.

2. Solana-first is a specialization priority, not the curriculum order.
   - Curriculum order remains Rust capability, general blockchain foundations, then deeper Solana development.

3. Durable rules have one canonical owner.
   - Prompts, templates, runbooks, roadmaps, and role policies may add short operational reminders but must not create competing full rules.

4. `CONTEXT.md` and `TODO.md` have separate responsibilities.
   - `CONTEXT.md` owns current facts, authorization, risks, and next transition.
   - `TODO.md` contains only actionable work with a completion condition.

5. Sprint roadmaps are sprint-specific execution contracts.
   - They retain objectives, scope, non-goals, learner decisions, checkpoints, artifacts, sprint-specific validation, and completion criteria.
   - They reference global lifecycle, role, language, and workflow policy instead of restating it.
   - Historical roadmaps remain as-of artifacts and are not retroactively rewritten.

6. Architect launch guidance has one portable source.
   - `docs/agents/architect-standard-prompt.md` is the only canonical Architect launch prompt.
   - The human runbook references it instead of maintaining another version.

7. The observation queue holds active observations plus a compact closed ledger.
   - Detailed incident evidence remains in the relevant failure review, closure, or governance review.

8. Browser-based Teacher and Architect roles use Codex as the repository bridge.
   - Required canonical files are delivered as attachments or pasted content.
   - Codex supplies scoped local-file, Git, diff, and repository-validation evidence.
   - Remote roles must not claim direct local inspection or require the learner to reconstruct technical evidence manually.

9. Recurring browser roles have canonical launch prompts.
   - `docs/agents/architect-standard-prompt.md` launches Architect windows.
   - `docs/agents/teacher-standard-prompt.md` launches accepted Sprint Teacher windows.
   - Architect prepares the task-specific attachments and addendum; Learner creates execution authority by deliberately sending the explicit start command.

10. Learner-facing conversation and persistent artifact language are separate.
   - Browser-based Teacher, Architect, and Codex conversation defaults to Chinese.
   - Repository-ready governance documents and cross-agent prompts default to English.
   - A structured takeover or governance verdict in chat remains learner-facing conversation unless a repository-ready artifact is explicitly requested.

## Files Changed

- `AGENTS.md`
- `README.md`
- `CONTEXT.md`
- `TODO.md`
- `roadmaps/master-roadmap.md`
- `roadmaps/sprint-18.md`
- `reviews/rust-core-coverage-matrix.md`
- `reviews/architect-retirement-handover-2026-06-30-post-governance-simplification.md`
- `docs/README.md`
- `docs/agents/architect-standard-prompt.md`
- `docs/agents/teacher-standard-prompt.md`
- `docs/agents/architect-bootstrap-guide.md`
- `docs/runbooks/system-operator-manual-zh.md`
- `docs/policies/sprint-governance-policy.md`
- `docs/policies/governance-lifecycle-policy.md`
- `docs/policies/codex-collaboration-policy.md`
- `docs/policies/language-output-policy.md`
- `templates/specification-review-template.md`
- `governance/observations.md`

## Preserved Boundaries

- No learning-project repository was inspected or modified.
- No Sprint execution was started.
- Existing closure, failure, learning-history, and historical roadmap evidence was not rewritten.
- The three-layer validation model and learner-primary implementation boundary remain unchanged.
- No new policy layer was created.

## Validation

- `git diff --check`: PASS
- Repository-wide Markdown trailing-whitespace scan: PASS
- Repository-wide Markdown conflict-marker scan: PASS
- Canonical Architect prompt search: PASS; one launch prompt remains
- Canonical Teacher prompt search: PASS; one launch prompt remains
- Sprint-18 accepted/not-started state consistency check: PASS
- Learning-project repositories accessed or modified: None
