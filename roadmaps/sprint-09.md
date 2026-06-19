# Sprint-09 Roadmap

## 1. Sprint Identity

* Sprint number: Sprint-09
* Sprint name: `wallet_cli v0.2 — In-Memory Mock State + Ownership/Borrowing Workflow`
* Stage: Stage 1 — Rust Foundations
* Primary project: `wallet_cli`
* Project baseline: Official Sprint-08 `wallet_cli` implementation
* Sprint status: Completed / Closed
* Final status: PASS / CLOSED

## 2. Governance Context

Sprint-08 is PASS / CLOSED and is the official completed learning record for the `wallet_cli` command modeling, domain validation, public workflow API, and user-facing error boundary topic.

Sprint-07 Attempt-1 is FAILED / DISCARDED. It receives no learning credit. No Sprint-07 implementation should be assumed, reused, or credited.

Sprint-09 must continue only from the official Sprint-08 `wallet_cli` baseline.

Sprint-09 passed Teacher Specification Review and Architect Scope Review.

Architect review result:

* APPROVE WITH REVISIONS for roadmap drafting.

This roadmap incorporates the required Architect revisions:

* define the mock state boundary precisely;
* state that memory is not persistent across separate CLI process runs;
* require a learner design decision around the public workflow/state API;
* keep command behavior minimal and deterministic;
* prefer reusing `balance` and `transfer`;
* keep data structures simple;
* require tests for read-only access, mutable state transition, error paths, and no-mutation-on-error behavior;
* preserve all explicit non-goals;
* clarify the exact boundary of the `transfer-like state transition`.

Sprint-09 later completed and closed with final status PASS / CLOSED.

Closure is recorded in `reviews/sprint-09-closure.md`.

## 3. Sprint Objective

Sprint-09 uses the existing educational `wallet_cli` project to practice state-aware Rust workflow design.

The objective is to reinforce ownership, borrowing, mutable borrowing, state transition reasoning, public API boundaries, module responsibility, and testing habits through a deliberately small in-memory mock state layer.

This sprint is not about real wallet behavior. It is not about blockchain account state. It is not about persistence, signing, RPC, Solana, or production wallet architecture.

The sprint should help the learner understand how Rust code expresses the difference between:

* read-only access through immutable borrowing;
* state-changing access through mutable borrowing;
* state ownership;
* public API boundaries for stateful workflows;
* tests that prove state does or does not change.

## 4. Stage Alignment

Sprint-09 remains inside Stage 1 — Rust Foundations.

The sprint reinforces:

* ownership and borrowing;
* immutable references;
* mutable references;
* `Result` and error propagation;
* module organization;
* crate boundaries;
* public API basics;
* small project navigation;
* testing success paths and error paths.

Sprint-09 must not advance into:

* Stage 2 — Rust Engineering as a broad architecture expansion;
* Stage 3 — Blockchain Foundations;
* Stage 4 — Solana Development;
* Stage 5 — Remote Job Preparation.

The sprint may use wallet-flavored mock terminology only as an educational shell for Rust practice.

## 5. Mock State Boundary

Sprint-09 must define a small educational mock state boundary.

Acceptable direction:

* introduce one small type such as `MockWalletState` or `WalletState`;
* store deterministic in-memory mock balances;
* allow read-only balance lookup;
* allow a minimal transfer-like state transition;
* validate behavior through library-level tests;
* keep the data structure simple.

Important boundary rule:

Memory is not persistent across separate CLI process runs.

If `main.rs` participates in the stateful workflow, it may instantiate a default mock state for one execution only. This must not be described as real wallet storage, real account persistence, or real blockchain state.

The mock state is allowed to exist because it creates meaningful Rust ownership and borrowing practice. It is not a product feature.

## 6. Transfer-Like State Transition Boundary

The existing command shape is:

* `transfer <to_address> <amount>`

Sprint-09 must not reinterpret this command as a real wallet transfer.

For this sprint, `transfer` means only:

* a deterministic mock in-memory operation;
* performed inside one process execution or one test-controlled state value;
* used only to practice mutable borrowing and state transition reasoning;
* allowed to update the mock balance associated with `to_address`;
* allowed to reduce or update only a deliberately named mock source value if the learner and Teacher choose that design during the sprint;
* not allowed to imply a real sender account, real funds, real account ownership, transaction signing, transaction history, network submission, or blockchain settlement.

The roadmap-preferred simplest interpretation is:

* `balance <address>` reads the mock balance for `address`;
* `transfer <to_address> <amount>` increases the mock balance for `to_address` by `amount` in the in-memory state;
* this operation is a mock credit operation, not a real debit-from-sender transfer.

If the learner proposes a mock source pool, it must remain explicitly educational and deterministic. It must not introduce insufficient-funds behavior unless the Teacher explicitly approves it as a small Rust error-handling exercise inside the sprint. By default, insufficient-funds behavior is out of scope because it can imply real fund accounting and production wallet semantics.

Sprint-09 must not introduce:

* sender account modeling;
* from-address arguments;
* private keys;
* account ownership;
* real balances;
* insufficient-funds semantics by default;
* transaction history;
* transaction IDs;
* multi-account production behavior;
* ledger semantics;
* blockchain account semantics.

The phrase “transfer-like state transition” exists only to create a small mutable state change for ownership and borrowing practice.

## 7. Scope

In scope:

* continue from the official Sprint-08 `wallet_cli` implementation;
* define one small in-memory mock state type;
* use deterministic mock data;
* practice immutable borrowing for read-only balance behavior;
* practice mutable borrowing for transfer-like state transition behavior;
* preserve or deliberately extend the existing public workflow boundary;
* reuse `balance` and `transfer` where possible;
* keep command behavior minimal and deterministic;
* add state-aware tests;
* test that read-only balance behavior does not mutate state;
* test that transfer-like behavior mutates state;
* test that invalid command or validation errors do not mutate state;
* keep `main.rs` thin;
* preserve public-facing workflow tests;
* preserve user-facing error formatting expectations;
* run `cargo check`;
* run `cargo test`.

Out of scope:

* real wallet storage;
* persistent state across CLI invocations;
* private keys;
* mnemonic phrases;
* real keypairs;
* transaction signing;
* blockchain network interaction;
* RPC;
* Solana;
* Anchor;
* Async Rust;
* Tokio;
* database usage;
* config files;
* file persistence;
* multi-account production behavior;
* real balance queries;
* real transaction history;
* sender account modeling;
* insufficient-funds behavior by default;
* transaction IDs;
* ledger semantics;
* blockchain account semantics;
* `tx_parser` integration;
* `clap` or another CLI framework;
* trait-heavy abstraction;
* generic-heavy refactor;
* large architecture redesign;
* reusing or crediting Sprint-07 Attempt-1 work.

## 8. Learning Outcomes

By the end of Sprint-09, the learner should be able to:

* explain why stateful workflows require clearer ownership boundaries than stateless workflows;
* explain the difference between immutable borrowing and mutable borrowing in project context;
* explain why a read-only workflow should borrow state immutably;
* explain why a state-changing workflow should borrow state mutably;
* explain why memory inside a CLI process is not persistent across separate command executions;
* design a small state type without turning it into real wallet architecture;
* explain why `transfer <to_address> <amount>` is only a deterministic mock state transition in this sprint;
* justify a public workflow/state API decision;
* write or explain tests that prove state mutation and no-mutation behavior;
* keep module responsibilities clear;
* preserve a thin `main.rs`;
* explain why the sprint remains Rust Foundations rather than Blockchain Foundations.

## 9. Required Learner Design Decision

The required learner design decision is the public workflow/state API shape.

The learner must compare and justify options such as:

1. Preserve the existing public API:

   * `run(args: &[String]) -> Result<String, CliError>`

2. Add a state-aware workflow API:

   * `run_with_state(args: &[String], state: &mut MockWalletState) -> Result<String, CliError>`

3. Separate read-only and mutable workflows:

   * one path that borrows state immutably for balance;
   * one path that borrows state mutably for transfer-like state transition.

4. Use another equivalent shape if the learner can justify:

   * ownership boundary;
   * borrowing model;
   * testability;
   * public API clarity;
   * compatibility with Sprint-08 design.

The learner must explain:

* which API should be public;
* which API should remain internal;
* where state is owned;
* where state is borrowed immutably;
* where state is borrowed mutably;
* what belongs in `main.rs`;
* what belongs in the library;
* how the design avoids implying real persistent CLI wallet state;
* how the design avoids implying real wallet transfer semantics.

This decision must be reviewed before final validation.

## 10. Implementation Artifacts

### 10.1 Mock State Type

Expected work:

* define a small state type such as `MockWalletState` or `WalletState`;
* keep the state educational and deterministic;
* use simple standard-library data structures only if needed;
* avoid production account-system design;
* provide minimal methods or functions needed by the approved workflow.

Possible responsibilities:

* initialize deterministic mock balances;
* read a balance for a validated address;
* apply a minimal transfer-like state change that is explicitly not real wallet transfer behavior.

The exact implementation shape should be decided during the sprint, not assumed by this roadmap.

### 10.2 Read-Only Balance Workflow

Expected work:

* connect the existing `balance` command to the mock state;
* read state through immutable borrowing where appropriate;
* return deterministic user-facing output;
* ensure the read-only path does not mutate state;
* add tests that prove the state remains unchanged.

### 10.3 Mutable Transfer-Like Workflow

Expected work:

* connect the existing `transfer` command to a small deterministic state transition;
* treat the operation as a mock state update for borrowing practice only;
* prefer a simple mock credit operation to `to_address`;
* use mutable borrowing where state changes are required;
* avoid sender account modeling;
* avoid real fund accounting;
* avoid transaction history;
* avoid insufficient-funds behavior by default;
* avoid real transaction semantics;
* add tests that prove state changes correctly.

### 10.4 Error And No-Mutation Behavior

Expected work:

* preserve existing command parsing and domain validation error behavior;
* ensure invalid commands do not mutate state;
* ensure invalid address or amount input does not mutate state;
* ensure failed state-transition behavior, if any, does not partially mutate state;
* add tests for important no-mutation-on-error cases.

### 10.5 Public Workflow Boundary

Expected work:

* decide whether to preserve, extend, or supplement `run(args)`;
* decide whether to expose `run_with_state`;
* keep public API design intentional;
* keep `main.rs` thin;
* avoid large public API redesign unrelated to the ownership/borrowing goal.

## 11. Suggested Module Boundaries

Existing Sprint-08 modules should be reused where appropriate.

Suggested responsibilities:

* `main.rs`:

  * collect CLI args;
  * instantiate default mock state for one process execution only if needed;
  * call the selected public workflow API;
  * print success output;
  * print user-facing errors;
  * remain thin.

* `lib.rs`:

  * expose the selected public workflow API;
  * expose only intentionally public types;
  * preserve a clear crate boundary.

* `command.rs`:

  * continue representing command parsing and validated command conversion if that remains the current structure.

* `domain.rs`:

  * continue representing `Address`, `Amount`, and validation rules.

* `errors.rs`:

  * continue representing `CliError` and user-facing formatting;
  * add only state-related error variants if required.

* `state.rs` or equivalent:

  * define the small educational mock state type;
  * keep state operations minimal;
  * avoid real wallet or blockchain semantics.

* `workflow.rs`:

  * coordinate command parsing, validation, state access, state transition, and output formatting;
  * keep ownership and borrowing boundaries visible.

These are suggested boundaries, not mandatory file names. The learner may choose another organization if responsibilities remain clear and scope stays controlled.

## 12. Checkpoint Plan

### Checkpoint 1 — State Boundary And Ownership Mental Model

Teaching focus:

* state ownership;
* immutable borrowing;
* mutable borrowing;
* why stateful workflows need clearer boundaries than stateless workflows;
* why CLI memory is not persistent across separate invocations;
* why the `transfer` command is only a deterministic mock operation in this sprint.

Implementation focus:

* inspect the Sprint-08 project structure;
* propose the mock state boundary;
* define the state type shape at a high level;
* identify where the state should be owned and where it should be borrowed.

Review focus:

* whether the mock state is precise and small;
* whether the design avoids real wallet semantics;
* whether transfer-like behavior is clearly not real fund transfer;
* whether ownership and borrowing are explicit;
* whether the learner can explain non-persistent CLI memory.

### Checkpoint 2 — Public Workflow / State API Decision

Teaching focus:

* public API boundary;
* state-aware workflow APIs;
* testability;
* preserving versus extending an existing API.

Implementation focus:

* compare possible API shapes;
* decide whether to preserve `run(args)`, add `run_with_state`, or use another justified boundary;
* document the reasoning before implementation proceeds.

Review focus:

* whether the public API decision is intentional;
* whether read-only and mutable behavior are distinguishable;
* whether `main.rs` can remain thin;
* whether tests can validate behavior cleanly.

### Checkpoint 3 — Read-Only Balance Path

Teaching focus:

* immutable borrowing;
* read-only behavior;
* tests that prove no mutation.

Implementation focus:

* connect `balance` to mock state;
* return deterministic output;
* avoid mutation;
* add tests for read-only behavior.

Review focus:

* whether balance behavior uses immutable borrowing where appropriate;
* whether no-mutation behavior is tested;
* whether output remains user-facing and deterministic.

### Checkpoint 4 — Mutable Transfer-Like Path And No-Mutation-On-Error

Teaching focus:

* mutable borrowing;
* deterministic mock state transition;
* avoiding partial mutation on error;
* error propagation across a stateful workflow;
* avoiding real transfer semantics.

Implementation focus:

* connect `transfer` to a small deterministic state transition;
* mutate state only after parsing and validation succeed;
* keep the behavior as a mock credit/update operation rather than a real transfer;
* preserve error behavior;
* add tests for successful mutation;
* add tests for invalid input and no-mutation-on-error behavior.

Review focus:

* whether mutable borrowing is used intentionally;
* whether state transition behavior is small and clear;
* whether invalid command or validation error leaves state unchanged;
* whether sender accounts, insufficient-funds behavior, transaction history, real wallet behavior, or blockchain semantics were not introduced.

### Final Validation Checkpoint

Teaching focus:

* integrated explanation of ownership, borrowing, state boundary, public API, transfer-like mock behavior, and tests;
* final scope compliance.

Implementation focus:

* run Student Validation;
* prepare for Codex Repository Validation;
* complete Teacher Learning Validation.

Review focus:

* whether the learner can explain the implementation;
* whether `cargo check` passes;
* whether `cargo test` passes;
* whether Codex validates repository state and scope compliance;
* whether Teacher Learning Validation passes independently from Codex.

## 13. Testing Requirements

Sprint-09 must include or update tests for both success paths and error paths.

Required test coverage areas:

* default or deterministic mock state initialization;
* valid `balance <address>` read-only behavior;
* `balance` path does not mutate state;
* valid `transfer <to_address> <amount>` deterministic mock state transition behavior;
* transfer-like path mutates state as expected;
* transfer-like path does not require or imply a sender account;
* transfer-like path does not create transaction history;
* unknown command does not mutate state;
* missing or wrong argument count does not mutate state;
* invalid address does not mutate state;
* invalid amount does not mutate state;
* failed state transition, if any, does not partially mutate state;
* public workflow behavior through the chosen public API.

Tests should prefer public-facing behavior and state behavior over internal implementation details.

Tests must not require:

* real wallet storage;
* keys;
* signing;
* RPC;
* network access;
* Solana;
* async runtime;
* external dependencies.

## 14. Validation Requirements

Sprint-09 completion requires three independent validation layers.

### 14.1 Student Validation

The learner must:

* implement the approved Sprint-09 code changes;
* explain changed files;
* explain the mock state boundary;
* explain why the mock state is not real wallet state;
* explain why memory is not persistent across separate CLI invocations;
* explain why transfer-like behavior is not a real wallet transfer;
* explain why no sender account, real funds, transaction history, or production multi-account semantics were introduced;
* explain ownership of the state;
* explain where immutable borrowing is used;
* explain where mutable borrowing is used;
* explain the public workflow/state API decision;
* explain what belongs in `main.rs` versus the library;
* explain state transition tests;
* explain no-mutation-on-error tests;
* run `cargo check`;
* run `cargo test`.

### 14.2 Codex Repository Validation

Codex must validate the learning project only.

Validation target:

`/Users/dumplings/workspace/wallet_cli`

Codex must:

* inspect repository state;
* confirm changed files;
* confirm scope constraints were followed;
* confirm no out-of-scope topics were introduced;
* confirm no real wallet, persistence, signing, RPC, Solana, async/Tokio, database, `clap`, trait-heavy abstraction, generic-heavy redesign, or large architecture redesign was introduced;
* confirm no sender account modeling, insufficient-funds behavior by default, transaction history, ledger semantics, or blockchain account semantics were introduced;
* confirm no Sprint-07 Attempt-1 work was reused or credited;
* confirm the implementation builds;
* run `cargo check`;
* run `cargo test`;
* confirm tests cover read-only behavior, mutable state transition, and no-mutation-on-error behavior;
* provide a formal repository validation report.

### 14.3 Teacher Learning Validation

The Teacher must validate:

* concept understanding;
* ownership reasoning;
* immutable borrowing reasoning;
* mutable borrowing reasoning;
* state boundary reasoning;
* transfer-like mock operation reasoning;
* public API reasoning;
* module responsibility reasoning;
* error propagation reasoning;
* testing reasoning;
* scope discipline.

Codex Repository Validation PASS does not automatically imply Teacher Learning Validation PASS.

Teacher Learning Validation must include explicit review reasoning, not vague acceptability language.

## 15. Completion Criteria

Sprint-09 is complete only when:

* the implementation builds on the official Sprint-08 `wallet_cli` baseline;
* no Sprint-07 Attempt-1 implementation is reused or credited;
* a small educational in-memory mock state boundary exists;
* the state boundary does not imply real wallet behavior or persistent CLI state;
* the transfer-like operation remains a deterministic mock in-memory operation only;
* no sender account modeling, real funds, transaction history, production multi-account semantics, or blockchain account semantics are introduced;
* read-only balance behavior uses an appropriate immutable state access boundary;
* transfer-like behavior uses an appropriate mutable state access boundary;
* invalid commands and validation errors do not mutate state;
* the learner has made and explained the public workflow/state API decision;
* `main.rs` remains thin;
* public-facing workflow behavior remains testable;
* state transition behavior is tested;
* no-mutation-on-error behavior is tested;
* `cargo check` passes;
* `cargo test` passes;
* Student Validation passes;
* Codex Repository Validation passes;
* Teacher Learning Validation passes;
* all explicit non-goals are preserved.

## 16. Explicit Non-Goals Confirmation

Sprint-09 must not include:

* real wallet storage;
* persistent state across CLI invocations;
* private keys;
* mnemonic phrases;
* real keypairs;
* transaction signing;
* blockchain network interaction;
* RPC;
* Solana;
* Anchor;
* Async Rust;
* Tokio;
* database usage;
* config files;
* file persistence;
* multi-account production behavior;
* real balance queries;
* real transaction history;
* sender account modeling;
* insufficient-funds behavior by default;
* transaction IDs;
* ledger semantics;
* blockchain account semantics;
* `tx_parser` integration;
* `clap` or another CLI framework;
* trait-heavy abstraction;
* generic-heavy refactor;
* large architecture redesign;
* Sprint-07 Attempt-1 credit or reuse.

## 17. Repository Validation Separation

The `wallet_cli` learning project and the `rust-blockchain-career` governance repository must be validated separately.

Learning-project validation target:

`/Users/dumplings/workspace/wallet_cli`

Governance repository target, only if this roadmap is later written to the repository:

`/Users/dumplings/workspace/rust-blockchain-career`

A Codex prompt should validate one repository or project root at a time unless the learner explicitly requests a cross-repository audit.

## 18. Handover Notes

This roadmap initially did not start Sprint-09 execution by itself.

Sprint-09 was later executed and completed after learner approval.

Sprint-09 closure is recorded in `reviews/sprint-09-closure.md`.

Sprint-09 learning-project code lives in the separate `wallet_cli` repository.

The governance repository update should be reviewed and committed separately from the `wallet_cli` learning-project implementation changes.
