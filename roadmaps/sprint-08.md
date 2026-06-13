# Sprint-08 Roadmap

## 1. Sprint Identity

- Sprint number: Sprint-08
- Sprint name: `wallet_cli v0.1 — Minimal CLI Workflow + Command Modeling + User-Facing Error Boundary`
- Stage: Stage 1 — Rust Foundations
- Project: `wallet_cli`
- Project status: From scratch
- Sprint status: Planned / Not Started

## 2. Governance Context

Sprint-07 Attempt-1 failed and was discarded.

Sprint-07 is reserved as an abnormal sprint record and numbering placeholder, not as a completed learning sprint.

No Sprint-07 learning progress is credited.

No Sprint-07 `wallet_cli` implementation is credited.

Future Sprint-08 work must not assume Sprint-07 `wallet_cli` code exists, is valid, complete, partial, reusable, or credited.

If `wallet_cli` is implemented during Sprint-08, it must be created from scratch as a new learning-project implementation.

Sprint-08 does not depend on `tx_parser`.

## 3. Sprint Objective

Sprint-08 uses a mock educational `wallet_cli` project as a Rust Foundations learning vehicle.

The objective is to practice a minimal CLI-style workflow while reinforcing command modeling, simple domain validation, private fields and constructors, `Result`-based error propagation, user-facing error formatting, module organization, public workflow API design, and public-facing tests.

The sprint is about Rust project reasoning and CLI workflow boundaries. It is not about real wallet behavior, real blockchain interaction, or Solana development.

## 4. Stage Alignment

Sprint-08 remains inside Stage 1 — Rust Foundations.

The sprint should reinforce:

- ownership and borrowing in small workflow functions;
- `Result` and error propagation;
- type design through simple domain values;
- private fields and constructors;
- module organization;
- visibility and public API boundaries;
- `main.rs` versus `lib.rs` responsibilities;
- testing habits for public-facing behavior.

The sprint should not advance into Stage 2 Rust Engineering, Stage 3 Blockchain Foundations, or Stage 4 Solana Development topics.

## 5. Scope

In scope:

- a new mock / educational `wallet_cli` project created from scratch;
- minimal raw CLI-like argument handling;
- command modeling for supported commands;
- simple command parsing;
- simple domain validation;
- private fields and constructors for domain values where appropriate;
- a unified CLI error boundary;
- user-facing error messages through `Display`;
- a thin `main.rs`;
- reusable workflow logic on the library side;
- focused tests for success paths and error paths.

Recommended minimal mock commands:

- `balance <address>`
- `transfer <to_address> <amount>`

These commands are educational only. They must not perform real wallet, signing, RPC, network, or blockchain behavior.

## 6. Explicit Non-Goals

Sprint-08 must not teach or include:

- real wallet storage;
- private keys;
- mnemonic phrases;
- real keypairs;
- real transaction signing;
- blockchain network interaction;
- RPC;
- Solana;
- Anchor;
- Async Rust;
- Tokio;
- database usage;
- config files;
- multi-account management;
- `tx_parser` integration;
- `clap` or other complex CLI frameworks;
- trait-heavy abstraction;
- generic-heavy refactor;
- large architecture redesign.

## 7. Learning Outcomes

By the end of Sprint-08, the learner should be able to:

- explain the difference between raw CLI arguments and domain commands;
- model supported commands with an enum or equivalent command model;
- explain why command parsing should return `Result`;
- define simple domain values such as `Address` and `Amount`;
- use private fields and constructors to prevent invalid states;
- keep validation intentionally simple and educational;
- design a user-facing CLI error boundary;
- implement `Display` for user-facing errors;
- separate debug/internal information from user-facing messages where appropriate;
- explain what belongs in `main.rs` versus `lib.rs`;
- choose and justify a public workflow API;
- write tests that validate public-facing behavior without over-binding to internal implementation details.

## 8. Implementation Artifacts

### 8.1 Command Model

The learner should model supported CLI commands.

Expected work:

- represent supported commands such as `balance` and `transfer`;
- parse raw CLI-like args into a command enum or equivalent model;
- handle unknown command;
- handle missing or wrong argument count;
- decide which command parsing API should be public.

### 8.2 Domain Validation

The learner should model simple domain values.

Expected work:

- define `Address` as a simple domain value;
- define `Amount` as a simple domain value;
- use private fields where appropriate;
- use constructors to prevent invalid states;
- validate that an address is non-empty and meets a minimal length rule;
- validate that an amount is parseable and positive;
- avoid real blockchain address validation.

### 8.3 User-Facing Error Boundary

The learner should define a unified CLI error boundary such as `CliError` or `AppError`.

Expected work:

- represent unknown command;
- represent missing argument or wrong argument count;
- represent invalid address;
- represent invalid amount;
- represent related workflow errors as needed;
- implement user-facing formatting through `Display`;
- keep debug information separate from user-facing messages where appropriate.

### 8.4 Public Workflow And Tests

The learner should define a high-level public workflow API.

Possible API shapes include:

- `run(args: &[String]) -> Result<String, CliError>`;
- `parse_command(args: &[String]) -> Result<WalletCommand, CliError>`;
- both APIs with clearly different responsibilities;
- another equivalent design if the learner can justify the boundary.

Expected work:

- keep `main.rs` thin;
- put reusable logic in the library side;
- add tests for success paths and error paths;
- prefer tests that validate public-facing workflow behavior.

## 9. Meaningful Learner Design Decision

The required learner design decision is the public workflow API shape.

The learner must decide and explain:

- whether `parse_command(args: &[String]) -> Result<WalletCommand, CliError>` should be public;
- whether `run(args: &[String]) -> Result<String, CliError>` should be public;
- whether both should exist with different responsibilities;
- which errors belong at the command parsing boundary;
- which errors belong at the public workflow boundary;
- what should remain internal;
- what belongs in `main.rs` versus `lib.rs`.

This decision must be reviewed during the sprint. It should not be treated as a purely mechanical implementation detail.

## 10. Suggested Module Boundaries

Suggested module responsibilities:

- `main.rs`: collect CLI args, call the public workflow API, print success output, print user-facing errors, and choose the process exit behavior if needed.
- `lib.rs`: expose the public workflow API and intentionally chosen public types.
- `command` or `commands`: define supported command models and command parsing behavior.
- `domain`: define `Address`, `Amount`, and simple constructors / validation.
- `error` or `errors`: define `CliError` or `AppError` and `Display` formatting.
- `workflow` or equivalent: coordinate command parsing, validation, and mock command execution into user-facing output.

These boundaries are suggestions, not a mandatory file tree. The learner may choose a different organization if the responsibilities remain clear and the sprint scope remains controlled.

## 11. Checkpoint Plan

### Checkpoint 1 — CLI Workflow Mental Model And Command Modeling

Teaching focus:

- raw CLI args versus domain commands;
- command model responsibility;
- command parsing as a fallible boundary.

Implementation focus:

- define the command model;
- add command parsing behavior;
- handle unknown command and wrong argument count;
- add command parsing tests.

Review focus:

- whether the command model is clear;
- whether parsing errors are represented intentionally;
- whether tests validate meaningful public behavior.

### Checkpoint 2 — Domain Validation And Private Fields

Teaching focus:

- why raw strings should not flow through the whole program;
- private fields as a valid-state protection mechanism;
- constructors as validation boundaries.

Implementation focus:

- define `Address`;
- define `Amount`;
- add simple validation rules;
- add validation tests.

Review focus:

- whether invalid states are prevented;
- whether validation remains intentionally simple;
- whether the implementation avoids real blockchain validation.

### Checkpoint 3 — Error Boundary And User-Facing Output

Teaching focus:

- CLI error boundary;
- user-facing messages versus debug representation;
- `Display` as a user-facing formatting contract.

Implementation focus:

- define the unified CLI error type;
- connect command parsing and domain validation errors to the error boundary;
- implement `Display`;
- format success and failure output.

Review focus:

- whether the error boundary is coherent;
- whether user-facing messages are stable enough to test;
- whether debug concerns are not mixed into normal output.

### Checkpoint 4 — Public Workflow And Final Validation

Teaching focus:

- `main.rs` versus `lib.rs` responsibility boundary;
- high-level public workflow API;
- testing from a public-facing perspective.

Implementation focus:

- finalize the public workflow API;
- keep `main.rs` thin;
- place reusable logic on the library side;
- add public-facing workflow tests;
- run Student Validation.

Review focus:

- whether the public API shape is justified;
- whether tests validate success and error workflows;
- whether the implementation stays within Sprint-08 scope.

## 12. Testing Requirements

Sprint-08 should include tests for both success paths and error paths.

Required test coverage areas:

- valid `balance <address>` workflow;
- valid `transfer <to_address> <amount>` workflow;
- unknown command;
- missing argument or wrong argument count;
- invalid address;
- invalid amount;
- user-facing error formatting for important error variants;
- public workflow behavior through the chosen public API.

Tests should prefer public-facing behavior over internal implementation details.

Tests should not require real wallet storage, keys, signing, RPC, network access, Solana, or `tx_parser`.

## 13. Validation Requirements

Sprint-08 completion requires three independent validation layers.

### 13.1 Student Validation

The learner must:

- implement the code;
- explain changed files;
- explain the command model;
- explain domain validation;
- explain private fields and constructors;
- explain the error boundary;
- explain the chosen public workflow API;
- explain what belongs in `main.rs` versus `lib.rs`;
- run `cargo check`;
- run `cargo test`.

### 13.2 Codex Repository Validation

Codex must:

- inspect repository state;
- confirm changed files;
- confirm scope constraints were followed;
- confirm excluded topics were not introduced;
- confirm tests pass;
- confirm no Sprint-07 work was reused or credited;
- confirm Sprint-08 does not depend on `tx_parser`;
- provide a repository validation report.

### 13.3 Teacher Learning Validation

The Teacher must validate:

- concept understanding;
- command model reasoning;
- domain validation reasoning;
- private field and constructor reasoning;
- module and API boundary understanding;
- error boundary understanding;
- user-facing formatting reasoning;
- testing reasoning;
- design tradeoff explanation for the public workflow API.

Codex Repository Validation PASS does not automatically imply Teacher Learning Validation PASS.

## 14. Completion Criteria

Sprint-08 is complete only when:

- the learner has implemented the mock `wallet_cli` project from scratch;
- the implementation includes command modeling for the approved minimal commands;
- domain values prevent invalid address and amount states according to the sprint's simple rules;
- the implementation has a unified user-facing error boundary;
- user-facing error formatting is implemented through `Display`;
- `main.rs` remains thin;
- reusable logic lives on the library side;
- the learner has made and explained the public workflow API decision;
- success-path and error-path tests are present;
- `cargo check` passes;
- `cargo test` passes;
- Student Validation passes;
- Codex Repository Validation passes;
- Teacher Learning Validation passes;
- no Sprint-07 implementation is reused, assumed, or credited;
- no excluded topics are introduced.

## 15. Handover Notes

Sprint-08 is planned but not started.

This roadmap authorizes future Sprint-08 learning execution only after the learner and Teacher accept the roadmap and begin the sprint.

This roadmap does not create a `wallet_cli` project.

This roadmap does not start implementation.

This roadmap does not continue Sprint-07.

This roadmap does not credit Sprint-07 learning progress.

A future Teacher should teach Sprint-08 checkpoint by checkpoint, using Chinese for technical teaching unless a later approved objective explicitly changes the language requirement.

Repository-ready assets, validation reports, and future closure documents should remain in English by default.
