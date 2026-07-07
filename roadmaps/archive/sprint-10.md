# Sprint-10 Roadmap

## 1. Sprint Identity

- Sprint number: Sprint-10
- Sprint name: `wallet_cli v0.3 — Public API Contract + Error Boundary Cleanup`
- Stage: Stage 1 — Rust Foundations
- Primary project: `wallet_cli`
- Project baseline: Official Sprint-09 `wallet_cli` implementation
- Sprint status: Completed / Closed
- Final status: PASS / CLOSED

## 2. Governance Context

Sprint-08 is PASS / CLOSED and is the official `wallet_cli v0.1` baseline.

Sprint-09 is PASS / CLOSED and is the official `wallet_cli v0.2` baseline.

Sprint-07 Attempt-1 is FAILED / DISCARDED and receives no learning credit.

Sprint-10 must continue from the official Sprint-09 baseline only.

Sprint-10 roadmap drafting was approved after Architect / Codex review result: APPROVE WITH REVISIONS.

Sprint-10 later completed and closed with final status PASS / CLOSED.

Closure is recorded in `reviews/sprint-10-closure.md`.

## 3. Sprint Objective

Sprint-10 uses the existing educational `wallet_cli` project to practice public API design in a small Rust crate.

The central learning decision is whether `CliError` should be re-exported from the crate root because public workflow functions such as `run` and `run_with_state` return `Result<String, CliError>`.

This must not be only a one-line re-export task. The sprint should cover the broader public API contract:

- audit the current crate-root public API;
- decide whether `CliError` should be re-exported;
- decide whether lower-level error types such as `CommandParseError` and `DomainValidationError` should remain internal or become part of the public error contract;
- confirm whether `run`, `run_with_state`, and `MockWalletState` are the intended public API;
- keep lower-level command, domain, and output helpers internal unless there is a clear public API reason to expose them;
- implement a small crate-root public facade cleanup;
- validate the public API with a small number of public API / integration-style tests.

## 4. Stage Alignment

Sprint-10 remains inside Stage 1 — Rust Foundations.

The sprint reinforces:

- `pub`, `pub(crate)`, and private visibility;
- crate-root public facade;
- module boundaries;
- public API design;
- `Result`;
- error boundary reasoning;
- source-level clarity;
- small Rust project navigation;
- lightweight testing habits.

Sprint-10 must not advance into Stage 2 Rust Engineering, Stage 3 Blockchain Foundations, Stage 4 Solana Development, or Stage 5 Remote Job Preparation.

## 5. Scope

In scope:

- public API audit;
- crate-root facade review;
- `CliError` crate-root re-export decision;
- lower-level error visibility decision;
- public status review for `run`, `run_with_state`, and `MockWalletState`;
- small `lib.rs` / public facade cleanup;
- limited visibility cleanup using `pub`, `pub(crate)`, or private visibility where appropriate;
- preservation of existing Sprint-08 and Sprint-09 behavior;
- limited public API validation tests;
- `cargo check`;
- `cargo test`;
- Student Validation;
- Codex Repository Validation;
- Teacher Learning Validation.

Out of scope:

- real wallet behavior;
- persistence;
- private keys;
- signing;
- sender accounts;
- insufficient-funds behavior;
- transaction history;
- RPC or network behavior;
- Solana or Anchor;
- async Rust or Tokio;
- `clap`;
- new dependencies;
- new wallet commands;
- file, database, or config handling;
- trait-heavy or generic-heavy redesign;
- large architecture refactor;
- blockchain account semantics;
- production wallet semantics;
- reusing or crediting Sprint-07 Attempt-1 work.

## 6. Learning Outcomes

By the end of Sprint-10, the learner should be able to explain:

- what a crate-root public facade is;
- why public functions should return types that external callers can name cleanly;
- whether `CliError` belongs in the public crate-root API;
- why lower-level errors may remain internal even if the public error boundary is exposed;
- the difference between public workflow APIs and internal helper APIs;
- when to use `pub`, `pub(crate)`, or private visibility;
- why exposing fewer internals can improve maintainability;
- why hiding too much can make a public API awkward;
- why `Result<String, CliError>` is part of the public API contract;
- how to validate public API usability with limited tests.

## 7. Required Learner Design Decisions

### 7.1 Should `CliError` be re-exported from the crate root?

The learner must decide and explain:

- whether external callers should import `wallet_cli::CliError`;
- whether public functions returning `Result<String, CliError>` imply that `CliError` should be part of the crate-root public facade;
- whether exposing `CliError` improves public API clarity;
- whether exposing `CliError` leaks too much internal detail;
- how this decision affects `run` and `run_with_state`.

### 7.2 Should lower-level error types remain internal?

The learner must decide and explain:

- whether `CommandParseError` should remain internal;
- whether `DomainValidationError` should remain internal;
- whether external callers should handle only `CliError`;
- whether exposing lower-level errors would create unnecessary public API commitments.

### 7.3 What is the intended public API surface?

The learner must confirm and explain whether the public API should include:

- `run`;
- `run_with_state`;
- `MockWalletState`;
- `CliError`.

The learner must explain why lower-level command, domain, and output helpers should or should not remain internal.

## 8. Implementation Areas

### 8.1 Public API Audit

Expected work:

- inspect the current crate-root exports;
- identify intentionally public versus accidentally public items;
- identify whether public functions expose types that are not conveniently reachable from the crate root;
- identify which modules and helpers should remain internal.

### 8.2 Error Boundary Contract Decision

Expected work:

- decide whether `CliError` should be re-exported;
- decide whether lower-level errors should remain internal;
- preserve `CliError` as the public workflow error boundary unless there is a clearly justified alternative.

### 8.3 Crate-Root Facade Cleanup

Expected work:

- implement a small public facade cleanup based on the approved decision;
- expose only selected public API items;
- avoid broad module exposure unless justified;
- keep `main.rs` thin;
- preserve existing behavior.

### 8.4 Public API Validation Tests

Expected work:

- add or update only a small number of tests;
- validate public API usage from an external-caller perspective;
- avoid exhaustive edge-case enumeration;
- avoid output-string churn;
- avoid turning testing into the main sprint workload.

## 9. Checkpoint Plan

### Checkpoint 1 — Public API Contract Mental Model And Audit

Teaching focus:

- public API contract;
- crate-root facade;
- visibility;
- nameable public return types.

Implementation focus:

- review the current public exports;
- identify the `CliError` public API issue;
- identify lower-level items that likely should remain internal.

Review focus:

- whether the learner understands the public API contract;
- whether the public facade issue is described accurately;
- whether the audit distinguishes workflow API from internal helpers.

### Checkpoint 2 — Error Boundary Decision

Teaching focus:

- public error boundary;
- `Result<T, E>` as an API contract;
- public versus internal error types.

Implementation focus:

- decide whether `CliError` should be crate-root public;
- decide whether `CommandParseError` and `DomainValidationError` remain internal;
- record learner reasoning before code changes.

Review focus:

- whether the learner can justify the public error boundary;
- whether the lower-level error visibility decision is intentional;
- whether the decision preserves a clean API contract.

### Checkpoint 3 — Crate Facade Cleanup

Teaching focus:

- `pub use`;
- `pub`;
- `pub(crate)`;
- private visibility;
- facade design.

Implementation focus:

- apply the approved public facade cleanup;
- preserve behavior;
- avoid architecture drift.

Review focus:

- whether crate-root exports match the approved public API;
- whether broad module exposure was avoided unless justified;
- whether existing behavior remains unchanged.

### Checkpoint 4 — Public API Validation And Final Review

Teaching focus:

- limited public API validation;
- tests as contract support rather than the main learning objective;
- final source-level review.

Implementation focus:

- add limited public API validation tests;
- run `cargo check`;
- run `cargo test`;
- prepare Student Validation;
- prepare Codex Repository Validation;
- complete Teacher Learning Validation after repository validation.

Review focus:

- whether tests validate the public API contract without dominating the sprint;
- whether final code stays inside Sprint-10 scope;
- whether the learner can explain the public facade, error boundary, and visibility choices.

## 10. Testing Requirements

Testing must support the public API learning objective and must not dominate the sprint.

Required testing focus:

- public crate-root API can be used as intended;
- `run` remains usable from the crate root;
- `run_with_state` remains usable from the crate root if it remains public;
- `MockWalletState` remains usable from the crate root if it remains public;
- `CliError` is nameable from the crate root if the learner decides to re-export it;
- existing Sprint-08 and Sprint-09 behavior remains valid.

Avoid:

- exhaustive error variant testing;
- exhaustive display formatting tests;
- repeated exact output-string churn;
- test naming as a guessing exercise;
- new test framework mechanics;
- broad internal module tests unrelated to the public API contract.

Suggested possible test names:

- `public_api_exposes_stateful_workflow_boundary`;
- `public_api_exposes_cli_error_boundary`;
- `public_workflow_still_returns_user_facing_result`.

The exact tests should be decided during sprint execution after the public API decision is made.

## 11. Validation Requirements

Sprint-10 completion requires three independent validation layers.

### 11.1 Student Validation

The learner must:

- implement approved Sprint-10 changes;
- explain changed files;
- explain the final crate-root public API;
- explain whether `CliError` is re-exported and why;
- explain whether lower-level error types remain internal and why;
- explain whether `run`, `run_with_state`, and `MockWalletState` are public and why;
- explain which helpers remain internal and why;
- explain the use of `pub`, `pub(crate)`, or private visibility;
- explain how public API tests validate the intended contract;
- run `cargo check`;
- run `cargo test`.

### 11.2 Codex Repository Validation

Codex must validate only the learning project:

`/Users/dumplings/workspace/wallet_cli`

Codex must:

- inspect repository state;
- confirm changed files;
- run `cargo check`;
- run `cargo test`;
- confirm public API cleanup matches Sprint-10 scope;
- confirm the `CliError` public contract decision is implemented consistently;
- confirm lower-level error types are either internal or intentionally exposed with justification;
- confirm `run`, `run_with_state`, and `MockWalletState` public API status is clear;
- confirm lower-level command, domain, and output helpers are not exposed without clear reason;
- confirm Sprint-08 and Sprint-09 behavior is preserved;
- confirm no out-of-scope topics were introduced;
- confirm no real wallet behavior, persistence, signing, RPC, Solana, async/Tokio, new dependencies, trait-heavy redesign, generic-heavy redesign, or large architecture refactor was introduced;
- confirm no Sprint-07 Attempt-1 work was reused or credited;
- provide a formal repository validation report.

### 11.3 Teacher Learning Validation

The Teacher must validate:

- concept understanding;
- public API reasoning;
- crate-root facade reasoning;
- visibility reasoning;
- error boundary reasoning;
- module responsibility reasoning;
- source-level clarity;
- testing reasoning;
- scope discipline.

Codex Repository Validation PASS does not automatically imply Teacher Learning Validation PASS.

## 12. Completion Criteria

Sprint-10 is complete only when:

- the implementation builds on the official Sprint-09 `wallet_cli` baseline;
- no Sprint-07 Attempt-1 implementation is reused or credited;
- the current crate-root public API has been audited;
- the learner has made and explained the `CliError` public contract decision;
- the learner has made and explained the lower-level error visibility decision;
- the public status of `run`, `run_with_state`, and `MockWalletState` is intentional and explained;
- lower-level command, domain, and output helpers remain internal unless explicitly justified;
- crate-root facade cleanup is implemented if approved during execution;
- existing Sprint-08 and Sprint-09 behavior is preserved;
- `main.rs` remains thin;
- no new dependencies are introduced;
- no real wallet, blockchain, Solana, async, persistence, signing, RPC, or large architecture topics are introduced;
- limited public API validation tests are present or updated;
- testing remains supportive rather than dominant;
- `cargo check` passes;
- `cargo test` passes;
- Student Validation passes;
- Codex Repository Validation passes;
- Teacher Learning Validation passes.

## 13. Teaching Notes For Sprint-10 Execution

- Technical teaching language should be Chinese.
- Important technical terms should be introduced in the form `English professional term (Chinese professional translation)` at first introduction.
- The learner prefers a faster teaching cadence for Sprint-10.
- Do not simplify or remove core content, but teach in a more direct result-first style.
- Prefer: state the likely correct result, explain the reasoning, then ask the learner to make or confirm the design decision.
- Avoid slow guided guessing.
- Avoid making the learner infer hidden requirements.
- Use structured instruction over guided discovery.
- Keep the learner as the primary implementer.
- Do not provide near-final production code too early for core implementation areas.
- More complete test examples are acceptable when they reduce testing friction and support API validation.
- Provide recommended test names when useful.
- Keep testing supportive rather than dominant.

## 14. Repository Validation Separation

The governance repository and `wallet_cli` learning project must be validated separately.

This roadmap modifies only the governance repository.

Learning-project validation target:

`/Users/dumplings/workspace/wallet_cli`

Governance repository target:

`/Users/dumplings/workspace/rust-blockchain-career`

Codex should validate one repository or project root at a time unless the learner explicitly requests a cross-repository audit.

## 15. Handover Notes

Sprint-10 is complete and closed.

Sprint-10 continued only from the official Sprint-09 `wallet_cli` baseline.

The separate `wallet_cli` learning project must not be modified by governance repository updates.

Repository-ready assets, validation reports, and future closure documents should remain in English by default.
