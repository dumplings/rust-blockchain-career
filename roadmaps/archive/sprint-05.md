# Sprint-05 Roadmap

## Sprint Name

tx_parser v0.4 — User-Facing Error Display + Visibility Refinement

## Current Stage

Stage 1: Rust Foundations

## Sprint Theme

Error Display + API Visibility Reinforcement

## Sprint Status

Roadmap approved for repository creation.

Implementation has not started.

## Primary Objective

Strengthen Rust Foundations by improving or confirming user-facing error display behavior in the existing `tx_parser` project, while minimally reviewing public/internal API boundaries.

The learner should be able to explain:

* how internal error structure differs from user-facing error messages;
* why `Display` matters for errors returned from public APIs;
* how `ValidationError` and/or `AppError` should be displayed to users;
* how tests can validate error formatting behavior;
* when an API should be public, `pub(crate)`, or private;
* why visibility refinement should be minimal and review-driven in this sprint.

## Project Scope

Project:

* `tx_parser` only

Allowed focus:

* `Display` behavior for `ValidationError` and/or `AppError`;
* user-facing error message clarity;
* `Result`-based error boundaries;
* public API behavior;
* minimal public/internal API boundary review;
* at most one small visibility adjustment if clearly justified and low-risk;
* tests for error display behavior.

Out of scope:

* `wallet_cli`;
* `mini_blockchain`;
* blockchain concepts;
* Solana;
* Anchor;
* PDA;
* Async Rust;
* Tokio;
* trait-heavy abstraction;
* generic-heavy refactor;
* broad public API redesign;
* large architecture redesign.

## Sprint Size Constraint

Sprint-05 should be slightly more substantial than Sprint-04, but still intentionally small.

The sprint must remain small enough to complete in one primary learning conversation.

The sprint should contain:

1. one cohesive theme;
2. at most two closely related implementation steps;
3. one validation cycle;
4. no new project.

Do not compensate for Sprint-04 being small by expanding Sprint-05 into multiple major topics.

## Approved Implementation Shape

Sprint-05 has two closely related work areas.

### Step 1: User-Facing Error Display

Improve or confirm user-facing `Display` behavior for `ValidationError` and/or `AppError`.

The learner should review the current error types and decide whether the current `Display` implementations are clear enough for users of the public API.

Possible work includes:

* implementing `Display` for `ValidationError` if missing;
* improving `Display` for `ValidationError` if unclear;
* implementing or improving `Display` for `AppError`;
* ensuring `AppError` display delegates or wraps lower-level error messages appropriately;
* adding tests that check formatted error output, not only enum variants.

This step should reinforce:

* `std::fmt::Display`;
* enum-based error design;
* public error boundaries;
* user-facing versus internal error representation;
* test-driven validation of error behavior.

### Step 2: Minimal Visibility Review

Review the current public/internal API boundary in `tx_parser`.

This review should focus on whether the current exposed APIs support the intended public crate behavior after Sprint-04 introduced `parse_and_validate_transaction(input: &str) -> Result<Transaction, AppError>`.

Visibility refinement must remain minimal and review-driven.

Allowed result options:

1. no visibility change, if current visibility is acceptable for the sprint;
2. one small visibility adjustment, only if it is clearly justified and low-risk.

If changing low-level API visibility such as `parse_transaction` or `validate_transaction` would require large restructuring, break existing tests significantly, or expand the sprint beyond one primary learning conversation, defer that change to a future sprint.

This step should not become a broad public API redesign.

## Learning Workflow

1. Review current `tx_parser` error types and public API surface.
2. Teach only the minimum Rust concepts required for `Display`, error formatting, and visibility review.
3. Learner implements the selected small change.
4. Learner adds or adjusts tests for error display behavior.
5. Learner performs local self-checking with `cargo check` and `cargo test`.
6. Teacher generates a Codex repository validation prompt.
7. Codex validates repository state, scope, tests, and behavior.
8. Teacher performs learning validation.
9. If validation passes, produce the Sprint-05 closure package.

## Learner and Codex Roles

Learner role:

* primary implementer;
* writes the code;
* runs local validation;
* explains design choices;
* explains user-facing error display behavior;
* explains visibility decisions.

Teacher role:

* teaches;
* guides;
* reviews understanding;
* generates Codex prompts;
* validates learning outcomes;
* prevents scope expansion.

Codex role:

* repository reviewer;
* repository steward;
* compiler or test validation assistant;
* scope checker;
* architecture and visibility review assistant.

Codex must not become the default implementer for Sprint-05 learning-project code.

## Deliverables

Required deliverables:

* one small `tx_parser` implementation improvement or confirmation around user-facing error display;
* tests that validate error display behavior;
* public/internal API boundary review;
* at most one small visibility adjustment, only if clearly justified and low-risk;
* passing learner local self-check;
* Codex repository validation report;
* Teacher learning validation;
* Sprint-05 closure package if all validation layers pass.

## Completion Criteria

Sprint-05 is complete only when all three validation layers pass:

1. Student Validation;
2. Codex Repository Validation;
3. Teacher Learning Validation.

Implementation completion alone does not mean the sprint is complete.

### Student Validation

Student validation passes when:

* the learner completes the selected Sprint-05 implementation target;
* the learner adds or updates tests for error display behavior;
* `cargo check` passes locally;
* `cargo test` passes locally;
* the learner can explain how `Display` works for the relevant error types;
* the learner can explain the difference between internal error structure and user-facing messages;
* the learner can explain whether any visibility change was made and why.

### Codex Repository Validation

Codex validation passes when Codex confirms:

* repository state matches Sprint-05 scope;
* only `tx_parser` is affected;
* no unrelated project expansion is introduced;
* no wallet_cli, mini_blockchain, blockchain, Solana, Anchor, PDA, Async Rust, or Tokio work is introduced;
* no trait-heavy or generic-heavy refactor is introduced;
* no broad public API redesign is introduced;
* error display behavior is implemented or confirmed through tests;
* tests validate formatted error behavior, not only enum variant matching;
* any visibility adjustment is minimal, justified, and low-risk;
* if visibility changes were deferred, the deferral is reasonable and scope-preserving;
* `cargo check` passes;
* `cargo test` passes.

### Teacher Learning Validation

Teacher validation passes when the learner can explain:

* why `Display` is used for user-facing error messages;
* how `ValidationError` and/or `AppError` display behavior works;
* how error display relates to public API usability;
* why tests should check formatted error output;
* what the current public API surface exposes;
* whether low-level APIs should remain public, become internal, or be deferred for future review;
* why Sprint-05 remained within Rust Foundations rather than becoming a broad architecture sprint.

## Formal Validation Rule

Formal repository validation must go through a Codex repository validation report.

Learner local validation is useful and encouraged, but pasted learner command output is not the primary formal validation path.

Preferred validation workflow:

Student implementation
→ Student local self-check
→ Teacher-generated Codex validation prompt
→ Codex repository validation report
→ Teacher learning validation

## Sprint Completion Rule

Sprint-05 is complete only when:

1. Student Validation passes;
2. Codex Repository Validation passes;
3. Teacher Learning Validation passes;
4. the Sprint-05 closure package is produced.

## Notes for Future Sprints

If Sprint-05 discovers that low-level API visibility requires a larger redesign, that work should be deferred.

Possible future topics:

* `tx_parser` public API surface cleanup;
* low-level API internalization;
* crate export strategy;
* test migration after visibility refinement.

That future work should require a separate Specification Review before implementation.
