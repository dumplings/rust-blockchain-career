# Governance Observation Queue

Observations should eventually become:

- Accepted
- Rejected
- Retired

The queue should remain small.

Do not use this file for general ideas or brainstorming.

New observations should be specific, governance-relevant, and likely to recur. Historical one-time observations may remain in this file after they are retired.

Last reviewed:
2026-06-13

Review result:
The legacy observations below have been closed, accepted, or integrated into the current governance baseline where appropriate. Future observations should not remain indefinitely in `Observing` after the scheduled review point has passed.

---

## GOV-001

Title:
Prerequisite Awareness

Status:
Retired

Occurrences:
1

First Seen:
Sprint-02

Description:

Teacher introduced a Rust API/concept before explicit introduction.

Example:

- into()

Current Decision:

Retired.

Rationale:

This was a single observed prerequisite-awareness issue. `docs/policies/teacher-execution-policy.md` now covers the underlying risk through Concept Before Code, Teaching Before Assessment, and explicit implementation standards.

Disposition:

No standalone governance rule is required.

---

## GOV-002

Title:
Sprint Transition Rule

Status:
Accepted

Occurrences:
1

First Seen:
Sprint-02 Closure

Description:

Sprint closure required additional discussion regarding:

- Closure Package
- Repository Update
- Sprint initiation conditions

Current Decision:

Accepted and integrated into the governance baseline.

Rationale:

Sprint transition requirements are now covered by `docs/policies/sprint-governance-policy.md`, `docs/policies/governance-lifecycle-policy.md`, and `docs/policies/codex-collaboration-policy.md`.

Disposition:

No further observation is needed unless sprint transition failures recur under the current governance baseline.

---

## GOV-003

Title:
Closure Package Requirement

Status:
Accepted

Occurrences:
2

First Seen:
Sprint-01 Closure

Most Recent:
Sprint-02 Closure

Description:

Closure Packages were required before repository updates.

Current Decision:

Accepted and integrated into the governance baseline.

Rationale:

This observation reached two occurrences and should not remain in `Observing`. Closure package expectations are now covered by `docs/policies/sprint-governance-policy.md` and `docs/policies/governance-lifecycle-policy.md`.

Disposition:

No further observation is needed unless closure-package failures recur under the current governance baseline.

---

## GOV-005

Title:
Teaching Mode Balance

Status:
Accepted

Occurrences:
2

First Seen:
Sprint-03

Most Recent:
Sprint-07 Attempt-1

Description:

A teacher may overuse guided discovery and Mentor Mode for learners who possess strong general engineering experience but limited Rust engineering experience.

Potential consequence:

- reduced learning velocity;
- excessive effort spent inferring teacher intent;
- insufficient direct Rust knowledge transfer.

Question:

Should learner stage influence the balance between:

- Instructor Mode
- Mentor Mode

Historical suggested balance for Rust Foundations, not retained as a fixed rule:

Instructor Mode:
70-80%

Mentor Mode:
20-30%

Current Decision:

Accepted and reframed.

Rationale:

The original Instructor Mode / Mentor Mode ratio should not become a fixed numerical rule. The underlying governance issue is now reframed as a requirement for structured instruction over guided discovery, concept before code, checkpoint-based teaching, and pause-and-review before progress.

Disposition:

Integrated into `docs/policies/teacher-execution-policy.md`.

---

## GOV-006

Title:
Workflow Context Verification

Status:
Accepted

Occurrences:
2

First Seen:
Sprint-03

Most Recent:
Sprint-07 Attempt-1

Description:

Execution issues occurred because the Teacher operated under an incorrect workflow context.

Examples:

- Learning Workflow vs Software-Team Workflow
- Governance Workflow vs Conversation Workflow

Question:

Should future governance require explicit workflow-context verification?

Possible examples:

- Learning Workflow
- Governance Workflow
- Review Workflow
- Takeover Workflow

Current Decision:

Accepted and integrated into the governance baseline.

Rationale:

Sprint-03 and Sprint-07 Attempt-1 both exposed workflow-context and validation-boundary drift. The current governance baseline now requires explicit workflow separation, role boundaries, validation layers, and Teacher startup verification through `AGENTS.md`, `docs/policies/teacher-execution-policy.md`, and `docs/policies/sprint-governance-policy.md`.

Disposition:

No further observation is needed unless workflow-context drift recurs under the current governance baseline.
