# Learning Log

## 2026-06-06

### Topics Learned

- serde
- serde_json
- Result
- map_err
- Display
- unit testing
- error-path testing
- module organization
- main.rs vs lib.rs
- public API concepts

### Insights

- Code organization exists for humans, not compilers.
- Responsibilities should drive module boundaries.
- Library crates provide reusable capabilities.
- Binary crates consume capabilities.

## 2026-06-07

### Sprint-01 Review

Outcome:

PASS

Validated:

- crate boundaries
- public API design
- module visibility
- dependency direction
- Result reasoning
- error propagation reasoning

Key Insight:

Understanding project organization is more important than memorizing individual Rust features.

Additional Insight:

Public APIs define what a crate offers.
Internal modules define how the crate works.

## 2026-06-08

### Sprint-02 Review

Outcome:

PASS

Capability Growth:

- Strengthened Parse versus Validation separation.
- Understood ValidationError as the representation of business-rule failures.
- Understood AppError as an application-level error boundary.
- Practiced From and into() for error conversion.
- Improved Result propagation reasoning across modules.
- Improved understanding of error boundaries.
- Reinforced responsibility-driven project organization.

Key Insight:

Capability grew from organizing a small Rust project toward reasoning about multi-stage workflows and module-level responsibilities.

Additional Insight:

Good Rust project structure makes responsibilities visible.
Error types should clarify where a failure belongs.

## 2026-06-10

### Sprint-03 Termination Recovery

Outcome:

Sprint-03 was terminated before completion.

Notes:

- Sprint-03 produced governance lessons, but it did not complete its planned learning execution.
- The previous Architect retired due to long-conversation drift.
- A new Architect Agent took over.
- Repository state synchronization is being restored before Sprint-04 creation.
- Sprint-04 should be created only after Specification Review.

## 2026-06-10

### Sprint-04 Completion

Outcome:

PASS / CLOSED

Capability Growth:

- Reinforced public API boundary design through `parse_and_validate_transaction`.
- Practiced a high-level parse-and-validate library API.
- Propagated ParseError and ValidationError through AppError.
- Added integration tests for public API success, parse error, and validation error behavior.
- Successfully used the Codex repository validation report workflow for formal validation.

Follow-up Areas:

- Finer-grained Rust visibility: `pub` vs `pub(crate)` vs private.
- Deciding whether low-level APIs should remain public or become internal.
- Clean Git change-set discipline during sprint execution.
- User-facing error formatting / `Display` for ValidationError and AppError.
- Continued Rust Fundamentals reinforcement before larger Rust Engineering topics.

## 2026-06-11

### Sprint-05 Completion

Outcome:

PASS / CLOSED

Capability Growth:

- Implemented `Display` for `ValidationError` and `AppError`.
- Confirmed `AppError` delegates user-facing formatting to inner error types.
- Added focused tests for formatted error output using `format!("{}", err)`.
- Reviewed visibility and made no visibility change.
- Completed formal validation through a Codex repository validation report.

Follow-up Areas:

- Continue Rust Fundamentals reinforcement.
- Consider future `tx_parser` public API surface cleanup only through Specification Review.
- Defer low-level API internalization, crate export strategy, and test migration until clearly needed.

### Sprint-06 Completion

Outcome:

PASS / CLOSED

Capability Growth:

- Consolidated the `tx_parser` public API surface.
- Preserved `parse_and_validate_transaction(input: &str) -> Result<Transaction, AppError>` as the high-level public API.
- Removed crate-root public re-exports of lower-level workflow functions.
- Reinforced crate boundary, module visibility, and public error boundary reasoning.
- Updated binary usage to consume the high-level public API.
- Completed formal validation through Student Validation, Codex Repository Validation, and Teacher Learning Validation.

Follow-up Areas:

- Deepen public error contract reasoning.
- Continue practicing when to expose or hide inner error types.
- Continue Rust Fundamentals reinforcement before larger Rust Engineering topics.

## 2026-06-13

### Sprint-07 Attempt-1 Failure Record

Outcome:

FAILED / DISCARDED

Classification:

Sprint-07 Attempt-1 was a teaching execution failure and governance failure, not learner completion and not learner Rust content failure.

Learning Credit:

- No Sprint-07 Attempt-1 learning progress is credited.
- No `wallet_cli` capability is credited.
- No `wallet_cli` implementation from Sprint-07 Attempt-1 is credited as official completed learning progress.
- Sprint-07 teaching content is discarded.

Governance Outcome:

Sprint-07 produced governance improvements rather than completed learning outcomes.

Relevant governance outputs:

- `AGENTS.md` structural rewrite;
- `roadmaps/sprint-07.md` abnormal sprint record;
- `reviews/sprint-07-attempt-1-failure-review.md`.

Repository / Project Status:

- The original `/Users/dumplings/workspace/wallet_cli` path is no longer present.
- Future agents should not assume any Sprint-07 Attempt-1 `wallet_cli` code exists, is valid, complete, or credited.
- If `wallet_cli` is revisited later, it should be recreated from scratch unless a future Teacher or Architect explicitly decides otherwise.

Next Step:

The next real learning sprint should be Sprint-08. Future course content should be decided by the next Teacher / Architect based on the latest governance baseline and learner state.

### Governance Structure Update

Outcome:

AGENTS.md split into a core governance entry point plus role-specific policy documents.

Repository Assets Updated:

- `AGENTS.md`
- `docs/policies/teacher-execution-policy.md`
- `docs/policies/sprint-governance-policy.md`
- `docs/policies/codex-collaboration-policy.md`
- `docs/policies/language-output-policy.md`
- `docs/policies/governance-lifecycle-policy.md`

Purpose:

- reduce patch-style rule accumulation in `AGENTS.md`;
- allow future agents to load only the policy documents relevant to their role;
- keep current sprint state in `CONTEXT.md` rather than in long-lived governance rules;
- preserve cross-agent interoperability through English repository assets.

### Documentation Directory Reorganization

Outcome:

The `docs/` directory was reorganized into purpose-based subdirectories.

Repository Structure:

- `docs/policies/` for role-specific and workflow-specific governance policies;
- `docs/agents/` for agent startup, takeover, and bootstrap documents;
- `docs/runbooks/` for human-facing operating manuals;
- `docs/README.md` for the documentation directory map.

Purpose:

- make `docs/` easier to understand;
- separate policy documents from startup prompts and human runbooks;
- help future agents load the correct documents for their role.

## 2026-06-16

### Sprint-08 Start

Outcome:

Sprint-08 roadmap created and accepted.

Sprint:

`wallet_cli v0.1 — Minimal CLI Workflow + Command Modeling + User-Facing Error Boundary`

Stage:

Stage 1 — Rust Foundations

Project:

`wallet_cli`

Project Status:

From scratch.

### Sprint-08 Micro-checkpoint 1A

Outcome:

PASS

Completed:

- created a fresh `/Users/dumplings/workspace/wallet_cli` Cargo project;
- created `src/main.rs`, `src/lib.rs`, and `src/command.rs`;
- kept `src/lib.rs` limited to `mod command;`;
- kept `src/main.rs` as default `Hello, world!`;
- kept `src/command.rs` empty;
- kept dependencies empty;
- validated `wallet_cli` separately from the `rust-blockchain-career` governance repository.

Next Step:

Continue Sprint-08 with Micro-checkpoint 1B: command model only.

Governance Note:

Sprint-08 validation should keep the governance repository and the separate `wallet_cli` learning project as separate validation targets.

## 2026-06-17

### Sprint-08 Completion

Outcome:

PASS / CLOSED

Sprint:

`wallet_cli v0.1 — Minimal CLI Workflow + Command Modeling + User-Facing Error Boundary`

Stage:

Stage 1 — Rust Foundations

Validation:

- Student Validation passed.
- Codex Repository Validation passed.
- Teacher Learning Validation passed.
- `cargo check` passed.
- `cargo test` passed.
- Final test count: 31 passed.

Implementation Summary:

- Created `wallet_cli` from scratch during Sprint-08.
- Implemented command modeling for `balance` and `transfer`.
- Implemented fallible command parsing.
- Implemented domain values for `Address` and `Amount`.
- Used private fields, constructors, and accessors for valid-state protection.
- Implemented domain validation and validated command conversion.
- Implemented `CliError` as the public workflow error boundary.
- Used `From` conversions and `Display` for user-facing error formatting.
- Implemented success output formatting.
- Exposed a public library-side workflow through `run(args: &[String]) -> Result<String, CliError>`.
- Kept `main.rs` thin.
- Added success-path and error-path tests.

Rust Capabilities Reinforced:

- enum modeling;
- `Result` and error propagation;
- custom error types;
- `From` conversion;
- `Display` formatting;
- private fields and constructors;
- accessors;
- module boundaries;
- crate-root re-exports;
- public API boundary reasoning;
- library crate versus binary crate responsibilities;
- CLI workflow responsibility separation;
- testing success paths and error paths.

Governance Notes:

- Sprint-08 counts as completed learning progress.
- Sprint-08 replaces the discarded Sprint-07 `wallet_cli` attempt as the official completed learning record for this topic.
- No Sprint-07 learning progress is credited.
- Governance repository validation and `wallet_cli` learning-project validation must remain separate.

Next Focus:

- Prepare Sprint-09 Specification Review.
- Continue Stage 1 Rust Foundations reinforcement.
- Avoid Solana, Async Rust, Tokio, blockchain networking, or large architecture work unless explicitly approved by a future sprint roadmap.

## 2026-06-20

### Sprint-09 Completion

Outcome:

PASS / CLOSED

Sprint:

`wallet_cli v0.2 - In-Memory Mock State + Ownership/Borrowing Workflow`

Stage:

Stage 1 - Rust Foundations

Validation:

- Student Validation passed.
- Codex Repository Validation passed with non-blocking notes.
- Teacher Learning Validation passed.
- `cargo check` passed.
- `cargo test` passed.
- Final test count: 39 passed.

Implementation Summary:

- Continued from the official Sprint-08 `wallet_cli` baseline.
- Introduced `MockWalletState`.
- Used private state fields and `HashMap<String, u64>` for deterministic mock balances.
- Implemented read-only balance lookup through immutable borrowing.
- Implemented deterministic mock credit behavior through mutable borrowing.
- Added `run_with_state(args: &[String], state: &mut MockWalletState) -> Result<String, CliError>`.
- Kept `run(args)` as the simple public workflow API by creating temporary state and delegating to `run_with_state`.
- Updated balance and transfer user-facing output.
- Cleaned crate-root public exports to expose the selected public workflow/state API.
- Added tests for state initialization, read-only behavior, mutation behavior, and no-mutation-on-error behavior.

Rust Capabilities Reinforced:

- owned values and state ownership;
- `let mut` versus `&mut`;
- `&self` versus `&mut self`;
- immutable borrowing;
- mutable borrowing;
- `HashMap`;
- `HashMap::entry(...).or_insert(...)`;
- `impl Into<String>`;
- crate public facade versus internal module paths;
- public workflow/state API reasoning;
- state transition tests;
- no-mutation-on-error tests.

Governance Notes:

- Sprint-09 counts as completed learning progress.
- Sprint-09 remained inside Stage 1 Rust Foundations.
- No Sprint-07 learning progress is credited.
- Governance repository validation and `wallet_cli` learning-project validation must remain separate.
- Tests should support the primary Rust learning objective and should not dominate implementation-heavy Rust Foundations sprints.
- Future Teachers should teach newly required Rust concepts directly rather than silently avoiding them.

Non-Blocking Follow-up Areas:

- Optional future improvement: add invalid transfer address no-mutation coverage.
- Future public API cleanup: decide whether `CliError` should be re-exported from the crate root because `run` and `run_with_state` return `Result<String, CliError>`.

Next Focus:

- Review and commit Sprint-09 closure governance updates.
- Commit the separate `wallet_cli` Sprint-09 implementation.
- Decide whether to authorize the next Stage 1 Rust Foundations step / Sprint-10 Specification Review.
