# Sprint-04 Roadmap

## Sprint Name

tx_parser v0.3 — Rust Fundamentals Reinforcement Sprint

## Current Stage

Stage 1: Rust Foundations

## Sprint Theme

Public API Boundary + Error Propagation Reinforcement

## Sprint Status

Roadmap approved for repository creation.

Implementation has not started.

## Primary Objective

Strengthen the learner's ability to reason about public API boundaries, module visibility, and Result-based error propagation in an existing small Rust project.

The learner should be able to decide:

* what should be public;
* what should remain internal;
* how errors should propagate across module boundaries;
* when an error type should be introduced, reused, or kept local;
* how tests should validate success paths and error paths.

## Project Scope

Project:

* tx_parser only

Allowed focus:

* public API boundary;
* module visibility;
* module dependency direction;
* Result and error propagation;
* error type placement;
* success-path and error-path tests.

Out of scope:

* wallet_cli;
* mini_blockchain;
* blockchain concepts;
* Solana;
* Anchor;
* PDA;
* Async Rust;
* Tokio;
* trait-heavy abstraction;
* generic-heavy refactor;
* large architecture redesign.

## Sprint Size Constraint

Sprint-04 must remain intentionally small.

The sprint must be small enough to complete in one primary learning conversation.

If the selected implementation target requires multiple major concepts, multiple projects, extended architecture discussion, or a large redesign, it must be split into a future sprint.

## Learning Workflow

1. Review the current tx_parser state.
2. Select one narrow implementation target related to public API boundary and error propagation.
3. Teach only the minimum Rust concepts needed for that target.
4. Learner implements the change.
5. Learner runs `cargo check`.
6. Learner runs `cargo test`.
7. Teacher generates a Codex repository validation prompt.
8. Codex validates repository state.
9. Teacher performs learning validation.
10. If validation passes, produce the Sprint-04 closure package.

## Learner and Codex Roles

Learner role:

* primary implementer;
* writes the code;
* runs local validation;
* explains design choices.

Teacher role:

* teaches;
* guides;
* reviews understanding;
* generates Codex prompts;
* validates learning outcomes.

Codex role:

* repository reviewer;
* repository steward;
* compiler or test validation assistant;
* architecture and scope checker.

Codex must not become the default implementer for Sprint-04 learning-project code.

## Narrow Implementation Target

Sprint-04 should select exactly one narrow improvement area in tx_parser.

The target should involve an existing workflow and require the learner to reason about:

* which functions belong in the public crate API;
* which modules or helper functions should remain private;
* how Result flows from internal modules to public-facing functions;
* whether an existing error type should be reused or a new error type is justified;
* which tests prove success and error behavior.

The exact implementation target should be chosen only after reviewing the current tx_parser repository state.

## Deliverables

* One small tx_parser implementation improvement.
* Passing cargo check.
* Passing cargo test.
* At least one success-path test.
* At least one error-path test.
* Codex repository validation report.
* Teacher learning validation.
* Sprint-04 closure package if all validation layers pass.

## Completion Criteria

### Student Validation

Student validation passes when:

* the learner completes the selected narrow implementation target;
* cargo check passes;
* cargo test passes;
* the learner can explain the changed public API boundary;
* the learner can explain the Result and error propagation path.

### Codex Validation

Codex validation passes when:

* repository state matches Sprint-04 scope;
* only tx_parser is affected;
* no unrelated project expansion is introduced;
* no blockchain, Solana, Anchor, PDA, Async Rust, or Tokio work is introduced;
* no trait-heavy or generic-heavy refactor is introduced;
* tests validate both success behavior and error behavior;
* the implementation remains small and consistent with Rust Foundations.

### Teacher Validation

Teacher validation passes when the learner can explain:

* why specific items are public or private;
* how module visibility supports the crate boundary;
* how Result propagates across module boundaries;
* why an error type was reused, introduced, or kept local;
* how the tests validate both expected behavior and failure behavior.

## Sprint Completion Rule

Sprint-04 is complete only when all three validation layers pass:

1. Student Validation;
2. Codex Validation;
3. Teacher Validation.

Implementation completion alone does not mean the sprint is complete.
