# Sprint-11 Roadmap

## 1. Sprint Identity

- Sprint number: Sprint-11
- Sprint name: `wallet_cli v0.4 — Final Public Error Contract + Source-Level Consolidation`
- Stage: Stage 1 — Rust Foundations
- Primary project: `wallet_cli`
- Project baseline: Official Sprint-10 `wallet_cli` implementation
- Sprint status: Completed / Closed
- Final status: PASS / CLOSED

## 2. Governance Context

Sprint-08 is PASS / CLOSED and is the official `wallet_cli v0.1` baseline.

Sprint-09 is PASS / CLOSED and is the official `wallet_cli v0.2` baseline.

Sprint-10 is PASS / CLOSED and is the official `wallet_cli v0.3` baseline.

Sprint-07 Attempt-1 is FAILED / DISCARDED and receives no learning credit.

Sprint-11 must continue from the official Sprint-10 `wallet_cli` baseline only.

Sprint-11 roadmap drafting was approved after Architect / Codex review result: APPROVE WITH REVISIONS.

Sprint-11 later completed and closed with final status PASS / CLOSED.

Closure is recorded in `reviews/sprint-11-closure.md`.

Sprint-11 should be treated as the final `wallet_cli` consolidation sprint for Stage 1 Rust Foundations unless a future review explicitly finds a new high-value reason to revisit it.

## 3. Sprint Objective

Sprint-11 uses the existing educational `wallet_cli` project to complete the remaining high-value Rust Foundations learning around public error contract design and source-level boundary clarity.

The central objective is to redesign the public `CliError` surface so external callers depend on a clearer public error contract while lower-level parse/domain details remain internal implementation details.

Preferred direction:

- keep `CliError` public;
- redesign `CliError` so it does not expose `CommandParseError` or `DomainValidationError` in public variants;
- prefer a small public `CliError` struct with private fields;
- introduce a public `CliErrorKind`;
- keep lower-level parse/domain errors internal;
- preserve internal `From<CommandParseError>` and `From<DomainValidationError>` mapping;
- preserve `Display` as the user-facing formatting boundary;
- keep the crate-root public facade stable;
- perform only focused source-level cleanup related to error/workflow clarity.

## 4. Stage Alignment

Sprint-11 remains inside Stage 1 — Rust Foundations.

The sprint reinforces:

- public API design;
- public error contract reasoning;
- type design;
- private fields;
- `Result`;
- error propagation;
- `From` conversion;
- `Display`;
- module boundaries;
- crate-root public facade stability;
- source-level clarity;
- limited testing habits.

Sprint-11 must not advance into Stage 2 Rust Engineering, Stage 3 Blockchain Foundations, Stage 4 Solana Development, or Stage 5 Remote Job Preparation.

## 5. Scope

In scope:

- audit the current public `CliError` surface;
- explain why public enum variants and variant payloads can become part of the public API contract;
- redesign `CliError` into a clearer public error contract;
- prefer a public `CliError` struct with private fields;
- introduce a public `CliErrorKind` enum for high-level caller-facing error categories;
- keep `CommandParseError` and `DomainValidationError` internal;
- preserve `From<CommandParseError>` and `From<DomainValidationError>` or equivalent internal mapping;
- preserve user-facing `Display` behavior;
- keep `run`, `run_with_state`, `MockWalletState`, and `CliError` as the intended crate-root public API;
- decide whether `CliErrorKind` should also be crate-root public;
- perform focused source-level cleanup related to error/workflow clarity;
- add or update a small number of public API / error contract tests;
- preserve Sprint-08, Sprint-09, and Sprint-10 behavior;
- run `cargo check`;
- run `cargo test`;
- complete Student Validation;
- complete Codex Repository Validation;
- complete Teacher Learning Validation.

Out of scope:

- real wallet behavior;
- persistence;
- private keys;
- signing;
- sender accounts;
- insufficient-funds behavior;
- transaction history;
- RPC;
- networking;
- Solana;
- Anchor;
- async Rust;
- Tokio;
- `clap`;
- new dependencies;
- new wallet commands;
- file/database/config handling;
- trait-heavy redesign;
- generic-heavy redesign;
- large architecture refactor;
- production error framework design;
- broad test expansion;
- output-string churn;
- style-only cleanup unrelated to public error contract;
- reusing or crediting Sprint-07 Attempt-1 work.

## 6. Learning Outcomes

By the end of Sprint-11, the learner should be able to explain:

- why a public error type is part of a crate's public API contract;
- why public enum variants and variant payloads may expose implementation details;
- why "not re-exported from the crate root" is not always the same as "not part of the public API";
- why `CommandParseError` and `DomainValidationError` should remain internal;
- how internal errors can be mapped into a public error boundary;
- how `From` conversion supports error mapping;
- why `Display` is the user-facing formatting boundary;
- why a public `CliErrorKind` can provide stable public categories without exposing internal error details;
- how private fields protect internal representation;
- how to preserve crate-root public facade stability while changing internal representation;
- how to validate public error contract behavior with limited tests;
- why `wallet_cli` is considered sufficiently exhausted after Sprint-11.

## 7. Required Learner Design Decisions

### 7.1 Final Public Error Shape

The learner must decide and explain the final public error shape.

Preferred direction:

- `CliError` remains public;
- `CliError` becomes a small public struct with private fields;
- `CliErrorKind` becomes the public high-level error category enum;
- lower-level parse/domain errors remain internal.

The learner must explain why this shape is preferred over exposing public enum variants containing lower-level error types.

### 7.2 Public Status Of `CliErrorKind`

The learner must decide whether `CliErrorKind` should be re-exported from the crate root.

Expected reasoning:

- if external callers need to branch on high-level error category, `CliErrorKind` should be public and nameable;
- since Sprint-11 is about public error contract clarity, the likely preferred direction is to expose `CliErrorKind` as part of the public error contract.

### 7.3 Internal Error Mapping Boundary

The learner must explain how lower-level errors flow into the public error contract.

Expected reasoning:

- `CommandParseError` remains internal;
- `DomainValidationError` remains internal;
- `From<CommandParseError>` maps into a public command-related `CliErrorKind`;
- `From<DomainValidationError>` maps into a public validation-related `CliErrorKind`;
- `Display` still produces user-facing messages.

### 7.4 Final `wallet_cli` Boundary Explanation

The learner must explain the final module and public API boundary:

- what the crate exposes;
- what remains internal;
- why `wallet_cli` should not continue accumulating feature work after Sprint-11;
- why the project has served its Stage 1 Rust Foundations purpose.

## 8. Implementation Areas

### 8.1 Public Error Surface Audit

Expected work:

- inspect current `CliError`;
- identify which public variants expose lower-level error types;
- distinguish crate-root facade exposure from public type surface exposure;
- explain why this is the remaining high-value `wallet_cli` issue.

### 8.2 Public Error Contract Redesign

Expected work:

- redesign `CliError` into a public type with private internal representation;
- introduce `CliErrorKind`;
- keep the public error contract small and stable;
- avoid broad abstraction.

Possible Stage 1-compatible shape:

```rust
pub struct CliError {
    kind: CliErrorKind,
    message: String,
}

pub enum CliErrorKind {
    Command,
    Validation,
}
```

The exact shape should be decided during Sprint-11 execution.

### 8.3 Internal Error Mapping

Expected work:

- preserve or update `From<CommandParseError>` mapping;
- preserve or update `From<DomainValidationError>` mapping;
- keep lower-level parse/domain errors internal;
- make the conversion boundary clear.

### 8.4 `Display` Boundary Preservation

Expected work:

- preserve user-facing error formatting;
- keep `Display` as the user-facing message boundary;
- avoid unnecessary output-string churn;
- ensure callers can still format `CliError`.

### 8.5 Focused Source-Level Cleanup

Expected work:

- clean up only code directly related to error/workflow clarity;
- avoid broad refactor;
- keep `main.rs` thin;
- preserve module responsibilities.

### 8.6 Limited Public API / Error Contract Tests

Expected work:

- add or update a small number of tests that validate the public error contract;
- avoid exhaustive error variant tests;
- avoid testing every internal parse/domain detail;
- preserve existing tests.

## 9. Checkpoint Plan

### Checkpoint 1 — Public Error Contract Mental Model

Teaching focus:

- public error contract;
- public enum variants as API;
- variant payloads as API exposure;
- why Sprint-10 solved nameability but not full encapsulation.

Implementation focus:

- inspect current `CliError` shape;
- identify what is exposed through public variants;
- confirm the remaining design issue.

Review focus:

- whether the learner understands why public error type shape matters;
- whether the learner can distinguish crate-root facade exposure from type-level public API exposure;
- whether the learner can explain why this issue is high-value enough for a final `wallet_cli` sprint.

### Checkpoint 2 — Final Public Error Shape Decision

Teaching focus:

- transparent versus opaque error representation;
- public `CliError` struct with private fields;
- public `CliErrorKind`;
- private lower-level error details.

Implementation focus:

- compare possible shapes;
- select the final public error contract;
- decide whether `CliErrorKind` is crate-root public.

Review focus:

- whether the learner can justify the chosen error shape;
- whether lower-level parse/domain details remain internal;
- whether the selected shape is Stage 1-compatible and avoids broad abstraction.

### Checkpoint 3 — Error Mapping And `Display`

Teaching focus:

- `From` conversion;
- internal error mapping;
- preserving `?`-based error propagation;
- `Display` as user-facing formatting boundary.

Implementation focus:

- update `CliError` construction/mapping;
- preserve conversion from lower-level errors;
- preserve user-facing formatting;
- avoid unrelated behavior changes.

Review focus:

- whether internal errors map cleanly into the public error contract;
- whether `Display` remains usable for user-facing output;
- whether behavior remains compatible with prior `wallet_cli` sprints.

### Checkpoint 4 — Focused Source-Level Consolidation

Teaching focus:

- source-level clarity;
- narrow cleanup discipline;
- module responsibility review.

Implementation focus:

- clean up only error/workflow-related code if needed;
- keep `main.rs` thin;
- keep lower-level helpers internal;
- avoid broad refactor.

Review focus:

- whether cleanup directly supports error/workflow clarity;
- whether module responsibilities remain clear;
- whether no product or architecture expansion entered the sprint.

### Checkpoint 5 — Limited Tests And Final Validation

Teaching focus:

- tests as public contract validation;
- regression support without test bloat;
- final source-level review.

Implementation focus:

- add or update limited tests for public error contract;
- run `cargo check`;
- run `cargo test`;
- prepare Student Validation;
- prepare Codex Repository Validation;
- complete Teacher Learning Validation after repository validation.

Review focus:

- whether tests validate public error contract behavior without broad expansion;
- whether Sprint-08, Sprint-09, and Sprint-10 behavior remains valid;
- whether the learner can explain why `wallet_cli` is sufficiently exhausted after Sprint-11.

## 10. Testing Requirements

Testing must remain supportive and limited.

Required testing focus:

- external callers can use `CliError` through the crate root;
- external callers can inspect high-level error kind if `CliErrorKind` is public;
- parse-related failures map to the intended public error category;
- validation-related failures map to the intended public error category;
- `Display` remains usable for user-facing messages;
- existing Sprint-08, Sprint-09, and Sprint-10 behavior remains valid.

Avoid:

- exhaustive error variant testing;
- testing every `CommandParseError` variant;
- testing every `DomainValidationError` variant;
- repeated exact output-string churn;
- broad test expansion;
- test naming as a guessing exercise;
- new test framework mechanics;
- tests unrelated to public error contract.

Possible test names:

- `public_error_contract_exposes_error_kind`;
- `parse_failure_maps_to_command_error_kind`;
- `validation_failure_maps_to_validation_error_kind`;
- `display_still_formats_cli_error_for_users`.

The exact tests should be decided during Sprint-11 execution after the final public error shape is approved.

## 11. Validation Requirements

Sprint-11 completion requires three independent validation layers.

### 11.1 Student Validation

The learner must:

- implement approved Sprint-11 changes;
- explain changed files;
- explain the final public `CliError` design;
- explain why public enum variants can expose implementation details;
- explain whether `CliErrorKind` is public and why;
- explain why `CommandParseError` and `DomainValidationError` remain internal;
- explain how `From<CommandParseError>` and `From<DomainValidationError>` map into the public error contract;
- explain how `Display` remains the user-facing formatting boundary;
- explain what code was cleaned up and why;
- explain why the cleanup stayed narrow;
- explain final `wallet_cli` public API and module boundaries;
- explain why `wallet_cli` is considered sufficiently exhausted after Sprint-11;
- run `cargo check`;
- run `cargo test`.

### 11.2 Codex Repository Validation

Codex must validate the learning project only.

Validation target:

`/Users/dumplings/workspace/wallet_cli`

Codex must:

- inspect repository state;
- confirm changed files;
- run `cargo check`;
- run `cargo test`;
- confirm the implementation builds;
- confirm public `CliError` no longer exposes `CommandParseError` or `DomainValidationError` in public variants;
- confirm lower-level parse/domain errors remain internal;
- confirm internal error mapping is preserved;
- confirm `Display` behavior remains user-facing and usable;
- confirm crate-root public API is intentional;
- confirm lower-level command/domain/output helpers are not exposed without clear reason;
- confirm existing Sprint-08, Sprint-09, and Sprint-10 behavior is preserved;
- confirm tests validate the public error contract without broad test expansion;
- confirm no out-of-scope topics were introduced;
- confirm no real wallet behavior, persistence, signing, sender accounts, insufficient-funds behavior, transaction history, RPC, networking, Solana, async/Tokio, `clap`, new dependencies, new wallet commands, trait-heavy redesign, generic-heavy redesign, or large architecture refactor was introduced;
- confirm no Sprint-07 Attempt-1 work was reused or credited;
- provide a formal repository validation report.

### 11.3 Teacher Learning Validation

The Teacher must validate:

- concept understanding;
- public error contract reasoning;
- enum variant exposure reasoning;
- internal versus public error representation;
- `From` conversion reasoning;
- `Display` boundary reasoning;
- source-level clarity;
- module responsibility reasoning;
- public API boundary reasoning;
- testing reasoning;
- scope discipline;
- final `wallet_cli` consolidation understanding.

Codex Repository Validation PASS does not automatically imply Teacher Learning Validation PASS.

## 12. Completion Criteria

Sprint-11 is complete only when:

- the implementation builds on the official Sprint-10 `wallet_cli` baseline;
- no Sprint-07 Attempt-1 implementation is reused or credited;
- `CliError` remains public;
- `CliError` no longer exposes `CommandParseError` or `DomainValidationError` through public variants;
- lower-level parse/domain errors remain internal;
- internal `From<CommandParseError>` and `From<DomainValidationError>` mapping is preserved or replaced by an equivalent clear mapping;
- `Display` remains the user-facing formatting boundary;
- crate-root public API remains intentional;
- `run`, `run_with_state`, `MockWalletState`, `CliError`, and any approved `CliErrorKind` exposure are explained;
- lower-level command/domain/output helpers remain internal unless explicitly justified;
- focused source-level cleanup is limited to error/workflow clarity;
- no new product behavior is introduced;
- no new dependencies are introduced;
- no real wallet, blockchain, Solana, async, persistence, signing, RPC, or large architecture topics are introduced;
- limited public error contract tests are present or updated;
- testing remains supportive rather than dominant;
- `cargo check` passes;
- `cargo test` passes;
- Student Validation passes;
- Codex Repository Validation passes;
- Teacher Learning Validation passes;
- `wallet_cli` is considered sufficiently exhausted for Stage 1 Rust Foundations unless a future review explicitly finds a new high-value reason to revisit it.

## 13. Teaching Notes For Sprint-11 Execution

- Technical teaching language should be Chinese.
- Important technical terms should be introduced in the form `English professional term (Chinese professional translation)` at first introduction.
- Use direct result-first teaching.
- State the likely correct direction first.
- Explain the reasoning.
- Ask the learner to confirm or make the design decision.
- Avoid slow guided guessing.
- Avoid making the learner infer hidden requirements.
- Keep the learner as the primary implementer.
- Avoid near-final production code too early for core implementation areas.
- More complete test examples are acceptable when they reduce testing friction and keep testing supportive.
- Provide recommended test names when useful.
- Maintain more implementation substance than Sprint-10.
- Avoid broad test expansion.
- Avoid minor style-only cleanup.
- Perform source-level review after meaningful implementation steps.
- Distinguish blocking issues from non-blocking improvements.

## 14. Repository Validation Separation

The `wallet_cli` learning project and the `rust-blockchain-career` governance repository must be validated separately.

This roadmap modifies only the governance repository.

Learning-project validation target:

`/Users/dumplings/workspace/wallet_cli`

Governance repository target:

`/Users/dumplings/workspace/rust-blockchain-career`

Codex should validate one repository or project root at a time unless the learner explicitly requests a cross-repository audit.

## 15. Handover Notes

Sprint-11 is complete and closed.

Sprint-11 final status is PASS / CLOSED.

Sprint-11 continued only from the official Sprint-10 `wallet_cli` baseline.

Sprint-11 should be treated as the final `wallet_cli` consolidation sprint unless a future review explicitly finds a new high-value reason to revisit it.

Closure is recorded in `reviews/sprint-11-closure.md`.

The final intended crate-root public API after Sprint-11 is `wallet_cli::run`, `wallet_cli::run_with_state`, `wallet_cli::MockWalletState`, `wallet_cli::CliError`, and `wallet_cli::CliErrorKind`.

The separate `wallet_cli` learning project must not be modified by governance repository updates.

Repository-ready assets, validation reports, and future closure documents should remain in English by default.
