# Stage 1 Exit Assessment Specification

## 1. Assessment Identity

- Assessment name: Stage 1 Exit Assessment
- Stage under review: Stage 1 - Rust Foundations
- Assessment status: PASS / CLOSED
- Primary purpose: decide whether the learner is ready to leave Stage 1 and begin Stage 2 Rust Engineering
- Primary evaluator: Teacher Agent
- Repository validation: Codex, if the assessment includes code changes
- Learner role: primary implementer and primary explainer

This assessment is not Sprint-12.

This assessment does not start a new learning sprint by itself.

Execution required explicit learner approval after this specification was reviewed.

The assessment was later completed and recorded in `reviews/stage-1-exit-assessment.md`.

## 2. Assessment-Time State Basis

Authoritative state when this assessment was specified:

- Current stage: Stage 1 - Rust Foundations
- Current active sprint: None
- Sprint-11 is PASS / CLOSED
- `wallet_cli` is considered sufficiently exhausted for Stage 1 Rust Foundations unless a future review identifies a new high-value reason to revisit it
- Sprint-07 Attempt-1 remains FAILED / DISCARDED and receives no learning credit

Recent completed Stage 1 evidence:

- `tx_parser` reinforced parsing, validation, public API, error boundary, and crate organization
- `wallet_cli` reinforced command modeling, domain validation, public workflow API, mock state, ownership, borrowing, crate-root facade, and public error contract design

## 3. Assessment Purpose

The assessment should determine whether the learner can independently use and explain Stage 1 Rust Foundations in project context.

The assessment should not teach a large amount of new material.

The assessment should not become another normal implementation sprint.

The assessment should verify capability across:

- ownership and borrowing;
- `Result` and error propagation;
- module organization;
- crate boundaries;
- public API basics;
- testing habits;
- small Rust project navigation;
- source-level explanation and tradeoff reasoning.

## 4. Assessment Outcomes

The final outcome must be one of:

### PASS - Advance To Stage 2

Use this result when the learner demonstrates enough independent Stage 1 capability to begin Stage 2 Rust Engineering.

Minor gaps may remain, but they should be manageable as reinforcement during Stage 2.

### CONDITIONAL PASS - Advance With Reinforcement Notes

Use this result when the learner is mostly ready for Stage 2, but specific Stage 1 weaknesses should be tracked explicitly.

The assessment report must list the reinforcement notes and explain how they should be carried into Stage 2.

### NOT YET - Run Targeted Stage 1 Reinforcement

Use this result when the learner still has blocking weakness in one or more Stage 1 exit criteria.

The assessment report must recommend one targeted Stage 1 reinforcement sprint or task, with a clear reason.

## 5. Assessment Shape

The assessment should be high-density and bounded.

Preferred structure:

1. Project navigation and source reading
2. Focused implementation task in a small new assessment project
3. Focused tests and local validation
4. Learner explanation and tradeoff review
5. Codex repository validation, if code was written
6. Teacher final assessment report

The assessment should use a new small Rust assessment project rather than extending `wallet_cli` by default.

Reason:

- `wallet_cli` has already served its Stage 1 learning purpose
- a new small project tests transfer of capability instead of familiarity with one codebase
- a fresh project reduces the risk of low-density continuation work

The new project should stay small enough to complete within one assessment conversation.

## 6. Suggested Assessment Project

Recommended project direction:

`task_tracker` or another equivalent small Rust library + binary crate.

The project should be domain-light and Rust-focused.

Possible minimal domain:

- tasks have an id, title, and status;
- supported commands or workflows include adding a task, marking a task done, and listing tasks;
- state is in-memory only;
- errors are explicit and user-facing;
- library code exposes a small public workflow API;
- binary code remains thin.

The exact project name and domain may be changed by the Teacher if the replacement preserves the assessment goals and avoids blockchain/product scope.

## 7. Required Assessment Capabilities

The assessment should verify that the learner can:

- define simple domain types with clear validation boundaries;
- model a small workflow using enums or equivalent type design;
- use `Result<T, E>` intentionally;
- propagate errors with `?` where appropriate;
- design a small public error boundary;
- implement `Display` for user-facing errors or justify another user-facing formatting boundary;
- separate library and binary responsibilities;
- keep `main.rs` thin;
- choose what belongs in the crate-root public API;
- keep internal helpers private unless there is a public API reason to expose them;
- use ownership and borrowing correctly in a small in-memory workflow;
- write or update a small number of meaningful tests;
- explain code organization and tradeoffs.

## 8. Scope

In scope:

- small fresh Rust project for assessment;
- one cohesive workflow;
- simple domain validation;
- simple in-memory state if useful;
- public workflow API;
- public error boundary;
- thin binary entry point;
- limited tests for success and error behavior;
- learner explanation of implementation and design decisions;
- `cargo check`;
- `cargo test`;
- Codex repository validation if code is written;
- Teacher final assessment report.

Out of scope:

- Solana;
- blockchain networking;
- real wallet behavior;
- transaction signing;
- private keys;
- persistence;
- database usage;
- config files;
- async Rust;
- Tokio;
- `clap` or other CLI frameworks;
- external dependencies unless explicitly approved;
- trait-heavy abstraction;
- generic-heavy redesign;
- large architecture refactor;
- broad test expansion;
- continuing `wallet_cli` by default;
- treating this assessment as Sprint-12 without explicit approval.

## 9. Testing Load

Tests are required, but they must support assessment rather than dominate it.

Expected test shape:

- 2 to 5 focused tests;
- at least one success-path test;
- at least one error-path test;
- at least one public API or workflow-level test;
- state mutation or no-mutation test only if the selected project uses mutable state.

Avoid:

- exhaustive edge-case enumeration;
- repeated output-string churn;
- testing every internal helper;
- making test naming a guessing exercise;
- turning the assessment into a testing sprint.

The Teacher may provide recommended test names and test structure when that reduces friction.

## 10. Validation Layers

The assessment should use three independent validation layers when code is written:

1. Student Validation
2. Codex Repository Validation
3. Teacher Learning Validation

### 10.1 Student Validation

The learner must:

- complete the agreed assessment implementation;
- run `cargo check`;
- run `cargo test`;
- explain changed files;
- explain public API choices;
- explain error boundary choices;
- explain ownership and borrowing choices;
- explain module boundaries;
- explain tests and what they validate;
- identify at least one tradeoff or alternative design.

### 10.2 Codex Repository Validation

Codex should validate the assessment project only.

Codex must:

- inspect repository state;
- confirm changed files;
- run `cargo check`;
- run `cargo test`;
- confirm implementation matches assessment scope;
- confirm Stage 1 concepts are present;
- confirm no out-of-scope topics were introduced;
- confirm the learner did not merely extend `wallet_cli` by default;
- provide a formal repository validation report.

### 10.3 Teacher Learning Validation

Teacher must evaluate:

- concept understanding;
- implementation independence;
- code navigation;
- ownership and borrowing reasoning;
- `Result` and error propagation reasoning;
- public API and module boundary reasoning;
- testing reasoning;
- explanation quality;
- readiness for Stage 2.

Codex Repository Validation PASS does not automatically imply Teacher Learning Validation PASS.

## 11. Assessment Report

The Teacher should produce a repository-ready assessment report after execution.

Recommended file:

`reviews/stage-1-exit-assessment.md`

The report should include:

- assessment identity;
- files and repositories used;
- assessment tasks completed;
- validation results;
- learner strengths;
- learner weaknesses;
- Stage 1 exit criteria evaluation;
- final result: PASS, CONDITIONAL PASS, or NOT YET;
- recommended next step;
- any governance or teaching process notes.

## 12. Stage 1 Exit Criteria Mapping

The final report must explicitly map evidence to the Stage 1 exit criteria from `roadmaps/master-roadmap.md`:

1. Explain ownership and borrowing in project context.
2. Use Result and error propagation intentionally.
3. Organize small Rust projects with clear module boundaries.
4. Explain crate boundaries and public API basics.
5. Write and run meaningful tests.
6. Navigate and modify small Rust projects without confusion.

Each criterion should be marked:

- PASS;
- PARTIAL;
- FAIL.

## 13. Authorization Rules

This specification does not authorize assessment execution.

The learner must explicitly authorize the Stage 1 Exit Assessment before a Teacher begins execution.

The Teacher must not start Sprint-12, Stage 2, or a new project sprint as a side effect of this assessment specification.

The Teacher may recommend a next direction after assessment, but stage transition requires explicit learner approval and repository state synchronization.

## 14. Recommended Next Action

The assessment has been completed.

Final result:

PASS - Advance To Stage 2

Final report:

`reviews/stage-1-exit-assessment.md`

Recommended next action:

Run a separate Stage 2 Specification Review before drafting or starting Sprint-12.
