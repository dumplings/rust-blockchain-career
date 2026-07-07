# Sprint-06 Roadmap

## Sprint Name

tx_parser v0.5 — Public API Surface + Error Boundary Consolidation

## Current Stage

Stage 1: Rust Foundations

## Sprint Theme

Public API Surface + Error Boundary Consolidation

## Sprint Status

Roadmap draft prepared for repository creation.

Implementation has not started.

## Primary Objective

Strengthen Rust Foundations by consolidating the public API surface and public error boundary of the existing `tx_parser` project.

The learner should practice deciding:

* what the crate should expose publicly;
* what should remain internal;
* how high-level APIs should protect users from internal workflow details;
* how `AppError` acts as the public error boundary;
* how tests should validate public API behavior without depending on internal implementation details.

Sprint-06 should be more substantial than Sprint-04 and Sprint-05, while still small enough to complete in one primary learning conversation.

## Project Scope

Project:

* `tx_parser` only

Allowed focus:

* crate public API surface;
* crate boundary and module visibility;
* `pub`, `pub(crate)`, private modules, and `pub use`;
* high-level public API behavior;
* low-level internal workflow hiding;
* `AppError` as the public error boundary;
* `Result<Transaction, AppError>` API behavior;
* integration tests for public API behavior;
* limited unit tests only when they support internal Rust fundamentals;
* small visibility or export adjustments if clearly justified.

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
* large architecture redesign;
* broad public API redesign requiring significant migration;
* changing the project into a production-grade library.

## Sprint Size Constraint

Sprint-06 must be more substantial than Sprint-04 and Sprint-05, but it must not become oversized.

The sprint should contain:

1. one cohesive Rust Foundations theme;
2. two to three connected implementation steps;
3. one validation cycle;
4. one project only;
5. meaningful learner decisions about API exposure and error boundaries.

Sprint-06 should not be reduced to a tiny mechanical change.

Sprint-06 should also not expand into unrelated projects, blockchain topics, advanced Rust abstractions, or large architecture redesign.

## Approved Implementation Shape

Sprint-06 has three connected work areas.

### Step 1: Public API Surface Review

Review the current `tx_parser` public API surface.

The learner should identify:

* which modules are public;
* which functions are public;
* which structs are public;
* which error types are public;
* which items are re-exported from the crate root;
* which public items are intended for external users;
* which public items are low-level internal workflow details;
* which tests currently depend on public API behavior;
* whether any tests depend too strongly on internal implementation details.

This step may produce a short working note during the sprint, but it does not need to create a separate repository document unless the Teacher explicitly requests it.

Expected learner reasoning:

* `parse_and_validate_transaction(input: &str) -> Result<Transaction, AppError>` should remain the high-level public API.
* `Transaction` should remain accessible to external users because it is the successful output type.
* `AppError` should remain accessible to external users because it is the public error boundary.
* Lower-level parse or validation functions should be reviewed carefully before changing visibility.
* Public API cleanup should be based on user-facing behavior, not personal preference.

### Step 2: Minimal Public Boundary Adjustment

Make one or two small API boundary adjustments only if clearly justified by Step 1.

Allowed examples:

* change a `pub mod` to `mod` if the module itself does not need to be part of the public API;
* add or adjust `pub use` exports from the crate root;
* reduce exposure of low-level workflow details if existing behavior can be preserved safely;
* keep necessary public types visible;
* preserve `parse_and_validate_transaction(input: &str) -> Result<Transaction, AppError>` as the high-level public API;
* keep low-level APIs public if changing them would create unnecessary migration or testing complexity.

The learner must be able to explain:

* what changed;
* why the change improves the crate boundary;
* why the change does not break the intended external-user workflow;
* why the change remains small enough for Stage 1: Rust Foundations.

If no safe visibility or export adjustment is justified, the sprint must still include a meaningful test alignment step in Step 3 so that Sprint-06 does not become only a review exercise.

### Step 3: Public API Test Alignment

Update or add tests so they validate the intended public API surface.

Tests should emphasize public behavior rather than internal implementation details.

Expected test focus:

* valid input through `parse_and_validate_transaction` returns a `Transaction`;
* invalid JSON through the public API returns `AppError::Parse`;
* invalid transaction data through the public API returns `AppError::Validation`;
* formatted public error output remains usable through `Display`;
* integration tests interact with the crate like an external user would;
* tests should not require direct access to internal modules unless there is a clear reason.

Test changes should be focused and limited.

Do not create a large test migration unless required by the selected boundary adjustment.

## Learning Workflow

1. Teacher confirms Sprint-06 scope and teaches the minimum concepts required for public API surface, crate boundary, visibility, and error boundary reasoning.
2. Learner inspects current `tx_parser` public exports and explains the current API surface.
3. Learner proposes one small boundary adjustment or explains why no visibility change should be made.
4. Teacher reviews the proposal before implementation.
5. Learner implements the selected boundary adjustment.
6. Learner updates or adds tests for public API behavior.
7. Learner performs local self-checking with `cargo check` and `cargo test`.
8. Teacher generates a Codex repository validation prompt.
9. Codex validates repository state, scope, test behavior, and architecture compliance.
10. Teacher performs learning validation.
11. If all validation layers pass, produce the Sprint-06 closure package.

## Learner and Codex Roles

Learner role:

* primary implementer;
* reviews the current API surface;
* makes the API boundary decision;
* writes code;
* updates tests;
* runs local validation;
* explains design choices.

Teacher role:

* teaches;
* guides;
* reviews learner reasoning;
* prevents scope expansion;
* generates Codex prompts;
* validates learning outcomes.

Codex role:

* repository reviewer;
* repository steward;
* compiler or test validation assistant;
* architecture and scope reviewer;
* repository validation reporter.

Codex must not become the default implementer for Sprint-06 learning-project code.

## Deliverables

Required deliverables:

* current `tx_parser` public API surface review;
* one small public boundary adjustment if justified;
* public API behavior test alignment;
* preservation of `parse_and_validate_transaction(input: &str) -> Result<Transaction, AppError>` as the high-level public API;
* preservation of `AppError` as the public error boundary;
* passing learner local self-check;
* Codex repository validation report;
* Teacher learning validation;
* Sprint-06 closure package if all validation layers pass.

## Completion Criteria

Sprint-06 is complete only when all three validation layers pass:

1. Student Validation;
2. Codex Repository Validation;
3. Teacher Learning Validation.

Implementation completion alone does not mean the sprint is complete.

### Student Validation

Student validation passes when:

* the learner completes the selected Sprint-06 implementation target;
* the learner updates or adds tests for public API behavior;
* `cargo check` passes locally;
* `cargo test` passes locally;
* the learner can explain the current public API surface;
* the learner can explain why specific items are public or internal;
* the learner can explain how `AppError` works as the public error boundary;
* the learner can explain how the tests validate public behavior.

### Codex Repository Validation

Codex validation passes when Codex confirms:

* repository state matches Sprint-06 scope;
* only `tx_parser` is affected;
* no unrelated project expansion is introduced;
* no `wallet_cli`, `mini_blockchain`, blockchain, Solana, Anchor, PDA, Async Rust, or Tokio work is introduced;
* no trait-heavy or generic-heavy refactor is introduced;
* no large architecture redesign is introduced;
* no broad public API redesign requiring significant migration is introduced;
* `parse_and_validate_transaction(input: &str) -> Result<Transaction, AppError>` remains available as the high-level public API;
* `AppError` remains available as the public error boundary;
* any visibility or export adjustment is small, justified, and scope-compatible;
* tests validate public API behavior rather than relying unnecessarily on internal implementation details;
* `cargo check` passes;
* `cargo test` passes.

### Teacher Learning Validation

Teacher validation passes when the learner can explain:

* what the public API surface currently exposes;
* what changed and why, or why no visibility change was justified;
* the difference between high-level public API and low-level internal workflow details;
* why `parse_and_validate_transaction` is the intended high-level public API;
* why `AppError` is the public error boundary;
* how `Result<Transaction, AppError>` protects external users from internal workflow details;
* why integration tests are appropriate for public API validation;
* why Sprint-06 remained within Stage 1: Rust Foundations.

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

Sprint-06 is complete only when:

1. Student Validation passes;
2. Codex Repository Validation passes;
3. Teacher Learning Validation passes;
4. the Sprint-06 closure package is produced.

## Notes for Future Sprints

If Sprint-06 discovers that deeper API cleanup would require a larger migration, that work should be deferred.

Possible future topics:

* crate export strategy refinement;
* deeper public API cleanup;
* larger test migration after visibility changes;
* CLI integration with the high-level public API;
* transition from Rust Foundations to Rust Engineering when Stage 1 exit criteria are met.

These topics require separate Specification Review before implementation.
