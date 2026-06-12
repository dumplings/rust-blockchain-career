# Architect Retirement Handover

## 1. Handover Identity

Role retiring:

Architect Agent

Project:

rust-blockchain-career

Current stage:

Stage 1 — Rust Foundations

Current active sprint:

None

Next real teaching sprint:

Sprint-08

Reason for retirement:

Architect governance intervention is complete. Sprint-07 Attempt-1 has been formally recorded as failed / discarded, governance files have been synchronized, and AGENTS.md has been structurally rewritten into the current governance baseline.

---

## 2. Current System State

Sprint-07 Attempt-1 is not a completed learning sprint.

Sprint-07 is reserved as a failed / abnormal sprint record and numbering placeholder.

No Sprint-07 learning progress is credited.

No wallet_cli capability is credited.

No wallet_cli implementation from Sprint-07 Attempt-1 should be assumed to exist, be valid, be complete, or be credited.

The original local wallet_cli path is no longer present at:

/Users/dumplings/workspace/wallet_cli

If wallet_cli is revisited later, it should be recreated from scratch unless a future Teacher / Architect explicitly decides otherwise.

The next real teaching sprint should use Sprint-08 numbering.

Future course content should be decided by the next Teacher / Architect based on the latest governance baseline and the learner’s current state.

---

## 3. Files Updated During This Governance Intervention

The following governance files are now important for any future Teacher / Architect:

* AGENTS.md
* CONTEXT.md
* learning-log.md
* roadmaps/sprint-07.md
* reviews/sprint-07-attempt-1-failure-review.md

Current AGENTS.md status:

Structurally rewritten and accepted as the current governance baseline.

Current CONTEXT.md status:

Updated to state that Sprint-07 Attempt-1 failed / discarded, no Sprint-07 learning progress is credited, and Sprint-08 is the next real teaching sprint.

Current learning-log.md status:

Updated to record Sprint-07 Attempt-1 as FAILED / DISCARDED, classified as a teaching execution / governance failure rather than learner Rust failure.

Current roadmaps/sprint-07.md status:

Converted into an abnormal sprint record / numbering placeholder, not a normal roadmap.

Current reviews/sprint-07-attempt-1-failure-review.md status:

Created as the formal failure review for Sprint-07 Attempt-1.

---

## 4. Major Governance Problems Resolved

### 4.1 Sprint size problem

Earlier sprints, especially Sprint-04, Sprint-05, and Sprint-06, exposed a repeated sprint-size issue.

Problem:

Some sprints were too small, with limited implementation density, limited learner design decisions, or insufficient Rust capability growth.

Resolution:

AGENTS.md now requires sprint design to avoid both oversized and undersized learning tasks.

Preferred sprint shape now includes:

* one cohesive learning theme;
* two to four connected implementation tasks or artifacts;
* at least one meaningful learner design decision;
* at least one required test addition or update when behavior or public API behavior changes;
* one final validation cycle.

Future agents should optimize for meaningful learning throughput, not minimum task size.

### 4.2 Teaching mode problem

Old governance language encouraged guided learning / guided discovery.

Problem:

This pushed Teacher Agents toward hints, guessing, vague prompting, and indirect discovery instead of clear teaching.

Resolution:

AGENTS.md now rejects guided discovery / guided guessing as the teaching mode for implementation-heavy technical learning.

The required teaching mode is structured instruction.

Current expected teaching direction:

Teach knowledge clearly
→ Define implementation standard
→ Learner practices implementation
→ Source-level review
→ Validation

### 4.3 Teaching sequence problem

Sprint-07 showed that even after guided discovery was removed, a Teacher could still teach badly by dumping too much material at once or showing code before explaining concepts.

Resolution:

AGENTS.md now includes:

* Teaching is primary; assessment is secondary.
* Concept before code.
* Checkpoint-based teaching.
* Pause and review before progress.

The Teacher should not compress an entire remaining sprint, multiple modules, multiple fixes, and multiple acceptance criteria into one large teaching block.

### 4.4 Code example policy clarified

Problem:

Rules about “Teacher should not complete learning tasks” could be misread as “Teacher should not provide code examples.”

Learner clarified that copying, rewriting, and studying good code can be a valid learning method.

Resolution:

AGENTS.md now allows code examples, reference implementations, partial code, or no code depending on teaching context.

The key restriction is not “no code.”

The key restriction is:

Teacher must not replace the learner’s implementation practice, reasoning, and validation with unreviewed task completion.

### 4.5 Validation boundary clarified

Sprint-07 exposed confusion among:

* learner local self-check;
* Codex repository validation;
* Teacher learning validation.

Problem:

Teacher relied too much on Codex summary PASS or vague acceptability language.

Resolution:

AGENTS.md now clearly separates:

1. Student Validation
2. Codex Repository Validation
3. Teacher Learning Validation

Codex PASS does not automatically mean Teacher learning validation PASS.

Teacher learning validation must include explicit review reasoning.

Learning stage may control complexity, but it must not reduce clarity.

Simple beginner-level code may be acceptable, but unclear boundaries, semantic ambiguity, hidden requirements, or misunderstood design should not be accepted merely because the learner is in an early learning stage.

### 4.6 Failed / discarded sprint handling clarified

Problem:

Before Sprint-07, the system did not clearly distinguish completed sprint, failed sprint attempt, discarded learning progress, and retry / replacement sprint.

Resolution:

AGENTS.md now includes a failed / discarded sprint attempt policy.

Sprint-07 Attempt-1 was formally recorded as failed / discarded.

The next real teaching sprint should start from Sprint-08.

---

## 5. Sprint-07 Attempt-1 Final Status

Sprint-07 Attempt-1 status:

FAILED / DISCARDED

Failure classification:

Teaching execution failure and governance failure.

Not a learner Rust content failure.

Learning progress credited:

No

wallet_cli capability credited:

No

wallet_cli implementation credited:

No

Course content preserved:

No

Project status:

Original wallet_cli path is no longer present.

If wallet_cli is revisited later, it should be recreated from scratch unless a future Teacher / Architect explicitly decides otherwise.

---

## 6. Important Learner Preferences Confirmed

The learner strongly prefers:

* Chinese teaching;
* English technical terms when appropriate;
* direct, clear, structured instruction;
* concept and mental model before code;
* checkpoint-by-checkpoint teaching;
* strict review rather than reassurance;
* no guided guessing;
* no hidden requirements;
* no vague “acceptable at this stage” pass language;
* code examples when they help learning;
* Teacher explaining standards before implementation;
* Codex for repository validation, but not as a replacement for Teacher learning validation.

The learner rejects:

* guided discovery as a teaching mode;
* being asked to infer hidden requirements;
* receiving a whole sprint’s teaching content in one large response;
* code-first teaching where near-final code appears before concept and workflow explanation;
* Teacher advancing when learner confusion has not been resolved;
* raw cargo output being treated as the formal validation path.

---

## 7. Risks for Future Agents

### 7.1 Teacher mode drift

Future Teachers may revert to hints, questions, or guided guessing.

Mitigation:

Read and follow AGENTS.md Teaching Execution Policy.

### 7.2 Overcorrection into code dumping

A Teacher may interpret “code examples allowed” as permission to dump final answers before teaching.

Mitigation:

Follow Concept Before Code and Checkpoint-Based Teaching.

### 7.3 Sprint undersizing

Future Teachers may reduce cognitive load by making sprints too small.

Mitigation:

Follow Task Granularity rules. Reduce confusion, not implementation density.

### 7.4 Validation shortcutting

Future Teachers may use Codex PASS, test pass, or learner local output as enough evidence.

Mitigation:

Codex repository validation and Teacher learning validation are separate.

### 7.5 Rust Fundamentals weakening

Future Teachers may treat earlier success as permanent mastery.

Mitigation:

Stage 1 requires recurring Rust Fundamentals reinforcement.

### 7.6 Workflow mixing

Future agents may ask Codex to implement learning-project code or treat governance updates as learning execution.

Mitigation:

Maintain separation between Governance Workflow and Learning Workflow.

---

## 8. Instructions for the Next Teacher / Architect

Before starting Sprint-08, the next Teacher / Architect must read:

* AGENTS.md
* CONTEXT.md
* learning-log.md
* roadmaps/sprint-07.md
* reviews/sprint-07-attempt-1-failure-review.md

The next Teacher should not continue Sprint-07.

The next Teacher should not treat wallet_cli as existing or partially completed.

The next Teacher should not assume Sprint-07 taught any valid learning content.

The next Teacher should begin with Sprint-08 Specification Review.

The next Teacher should decide whether Sprint-08 should:

* revisit wallet_cli from scratch;
* return to tx_parser;
* choose another Stage 1 Rust Foundations topic.

That decision should be based on the current governance baseline and learner state, not on discarded Sprint-07 content.

---

## 9. Recommended Sprint-08 Startup Requirements

Sprint-08 should begin with:

1. Takeover confirmation
2. Current governance reading confirmation
3. Stage confirmation
4. Teaching language confirmation
5. Sprint scope constraints
6. Specification Review before roadmap
7. Explicit teaching mode commitment

The Teacher should explicitly state that Sprint-08 will use:

Concept Explanation
→ Mental Model
→ Workflow / Boundary
→ Code Example if Useful
→ Learner Practice
→ Source-Level Review
→ Validation

Sprint-08 should not start by assigning implementation.

Sprint-08 should not start by producing a large code block.

Sprint-08 should not compress multiple checkpoints into one response.

---

## 10. Architect Final Assessment

The governance system is now in a better state than before Sprint-07.

Sprint-07 was costly, but it exposed major weaknesses in:

* teaching mode design;
* checkpoint pacing;
* code example policy;
* Teacher / Codex validation boundary;
* failed sprint handling;
* AGENTS.md structure.

These weaknesses have now been addressed in governance files.

Current readiness:

* AGENTS.md baseline: PASS
* Sprint-07 abnormal record: PASS
* Sprint-07 failure review: PASS
* CONTEXT.md synchronization: PASS
* learning-log.md synchronization: PASS
* Sprint-08 readiness: READY FOR SPECIFICATION REVIEW

Architect retirement status:

Ready.

Recommended next action:

Start a new Teacher / Architect session for Sprint-08 preparation, using the latest governance files as the source of truth.
