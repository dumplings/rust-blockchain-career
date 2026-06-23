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

### Sprint-10 Roadmap Draft

Outcome:

Roadmap drafted / Execution not authorized

Sprint:

`wallet_cli v0.3 - Public API Contract + Error Boundary Cleanup`

Stage:

Stage 1 - Rust Foundations

Repository Asset:

- `roadmaps/sprint-10.md`

Planning Summary:

- Sprint-10 is proposed as a continuation from the official Sprint-09 `wallet_cli` baseline.
- The central learning decision is whether `CliError` should be re-exported from the crate root because public workflow functions return `Result<String, CliError>`.
- The sprint should cover the broader public API contract, including crate-root facade design, lower-level error visibility, public status of `run`, `run_with_state`, and `MockWalletState`, and limited public API validation tests.
- Testing should support public API validation and must not dominate the sprint.

Governance Notes:

- Sprint-10 execution has not started.
- Sprint-10 execution requires explicit learner approval after roadmap creation.
- The `wallet_cli` learning project was not modified by roadmap creation.
- Governance repository validation and `wallet_cli` learning-project validation must remain separate.
- No Sprint-07 learning progress is credited.

Next Focus:

- Review and commit Sprint-10 roadmap and current-state governance updates.
- Decide whether to explicitly authorize Sprint-10 execution from `roadmaps/sprint-10.md`.

### Sprint-10 Completion

Outcome:

PASS / CLOSED

Sprint:

`wallet_cli v0.3 - Public API Contract + Error Boundary Cleanup`

Stage:

Stage 1 - Rust Foundations

Validation:

- Student Validation passed.
- Codex Repository Validation passed.
- Teacher Learning Validation passed.
- `cargo check` passed.
- `cargo test` passed.
- Final test count: 42 passed.

Implementation Summary:

- Continued from the official Sprint-09 `wallet_cli` baseline.
- Re-exported `CliError` from the crate root.
- Confirmed `run`, `run_with_state`, `MockWalletState`, and `CliError` as the intended crate-root public API.
- Kept `CommandParseError` and `DomainValidationError` as lower-level internal errors.
- Kept lower-level command, domain, and output helpers internal.
- Added limited public API validation tests for external-caller usage.
- Preserved Sprint-08 and Sprint-09 behavior.
- Introduced no new dependencies or product behavior.

Rust Capabilities Reinforced:

- public API contract reasoning;
- crate-root public facade design;
- `pub use`;
- `Result<T, E>` as public API contract;
- public error boundary reasoning;
- lower-level error internalization;
- limited integration-style public API tests;
- visibility and module boundary discipline.

Governance Notes:

- Sprint-10 counts as completed learning progress.
- No Sprint-07 learning progress is credited.
- Governance repository validation and `wallet_cli` learning-project validation must remain separate.
- `CliError` is public and its variants still reflect lower-level parse/domain categories; this is a non-blocking future design note, not a Sprint-10 closure blocker.

Next Focus:

- Review and commit Sprint-10 closure governance updates.
- Commit the separate `wallet_cli` Sprint-10 implementation.
- Decide whether to authorize the next Stage 1 Rust Foundations step / future specification review.

## 2026-06-21

### Sprint-11 Completion

Outcome:

PASS / CLOSED

Sprint:

`wallet_cli v0.4 - Final Public Error Contract + Source-Level Consolidation`

Stage:

Stage 1 - Rust Foundations

Validation:

- Student Validation passed.
- Codex Repository Validation passed.
- Teacher Learning Validation passed.
- `cargo check` passed.
- `cargo test` passed.
- Final test count: 42 passed.

Implementation Summary:

- Continued from the official Sprint-10 `wallet_cli` baseline.
- Completed the final public error contract cleanup.
- Redesigned `CliError` as a public struct with private fields.
- Introduced public `CliErrorKind`.
- Re-exported `CliErrorKind` from the crate root.
- Kept `wallet_cli::run`, `wallet_cli::run_with_state`, `wallet_cli::MockWalletState`, `wallet_cli::CliError`, and `wallet_cli::CliErrorKind` as the intended final public API.
- Removed lower-level parse/domain error exposure from public `CliError` variants and public fields.
- Preserved `From<CommandParseError>` and `From<DomainValidationError>` mapping into public `CliError`.
- Preserved `Display for CliError` as the user-facing formatting boundary.
- Updated workflow/public API tests to use `error.kind()` and `CliErrorKind`.
- Preserved Sprint-08, Sprint-09, and Sprint-10 behavior.
- Introduced no new dependencies or out-of-scope behavior.

Rust Capabilities Reinforced:

- public error contract reasoning;
- public enum variant exposure reasoning;
- public struct with private fields;
- public error kind design;
- internal error mapping through `From`;
- `Display` as user-facing formatting boundary;
- crate-root public facade stability;
- public API / workflow tests;
- source-level consolidation discipline.

Governance Notes:

- Sprint-11 counts as completed Stage 1 Rust Foundations learning progress.
- No Sprint-07 learning progress is credited.
- Governance repository validation and `wallet_cli` learning-project validation must remain separate.
- `wallet_cli` is considered sufficiently exhausted for Stage 1 Rust Foundations unless a future review explicitly finds a new high-value reason to revisit it.
- Future checkpoints should use Codex for repository/source inspection after meaningful implementation changes, while keeping learner self-check as a local aid rather than the primary review source.

Next Focus:

- Review and commit Sprint-11 closure governance updates.
- Commit the separate `wallet_cli` Sprint-11 implementation.
- Decide whether to authorize Stage 1 exit assessment, a new Stage 1 Rust Foundations project, Stage 2 Rust Engineering preparation, or another Architect-approved next step.

### Stage 1 Exit Assessment Specification

Outcome:

Specification accepted.

This planning entry was later superseded by the completed Stage 1 Exit Assessment record below.

Repository Asset:

- `roadmaps/stage-1-exit-assessment.md`

Governance Assets Updated:

- `docs/policies/sprint-governance-policy.md`
- `templates/specification-review-template.md`

Purpose:

- Define a Stage 1 Exit Assessment before deciding whether to advance to Stage 2.
- Evaluate Stage 1 capability through a high-density assessment rather than another low-density `wallet_cli` continuation.
- Preserve the conclusion that `wallet_cli` is sufficiently exhausted for Stage 1 Rust Foundations.
- Add explicit learning-density and project-continuation checks to sprint planning governance.

Assessment Intent:

- Verify ownership and borrowing in project context.
- Verify intentional `Result` and error propagation.
- Verify module boundaries and crate-root public API reasoning.
- Verify small Rust project navigation.
- Verify meaningful but limited testing habits.
- Use a small fresh assessment project by default rather than extending `wallet_cli`.

Next Focus:

- Completed by the later Stage 1 Exit Assessment execution.
- See `Stage 1 Exit Assessment Completion` below.

### Stage 1 Exit Assessment Completion

Outcome:

PASS / CLOSED - Advance To Stage 2

Repository Assets:

- `roadmaps/stage-1-exit-assessment.md`
- `reviews/stage-1-exit-assessment.md`

Assessment Project:

- `/Users/dumplings/workspace/task_tracker`

Validation:

- Student Validation: PASS
- Codex Repository Validation: CONDITIONAL PASS - repository validation passed with non-blocking concerns
- Teacher Learning Validation: PASS
- `cargo check`: PASS
- `cargo test`: PASS
- Final test count: 4 passed

Summary:

- The learner completed a fresh small Rust assessment project instead of continuing `wallet_cli`.
- The assessment project used no external dependencies.
- The project stayed out of Solana, blockchain networking, real wallet behavior, persistence, async Rust, Tokio, `clap`, and large architecture work.
- The implementation demonstrated `Task`, `TaskTracker`, internal `TaskError`, public `TaskTrackerError`, `From<TaskError> for TaskTrackerError`, `Display`, crate-root public API re-exports, private fields, `pub(crate)` internal construction and mutation, read-only task listing through `&[Task]`, and four focused tests.
- The deterministic `next_id` design was Teacher-provided scaffolding and should not be counted as strong independent design evidence.
- The learner still demonstrated sufficient independent reasoning around ownership, borrowing, visibility, error boundaries, module responsibility, public API design, source-level explanation, and tradeoffs.

Stage 2 Reinforcement Notes:

- Make `?` / `From` explanation more precise.
- Strengthen success-path assertions when appropriate.
- Consider richer public error context when the project needs it.
- Continue ownership and borrowing reasoning in larger Rust codebases.

Next Focus:

- Run a separate Stage 2 Specification Review.
- Do not start or draft Sprint-12 automatically from this assessment report alone.
- Keep `task_tracker` separate from governance repository updates.

## 2026-06-23

### Sprint-12 Completion

Outcome:

PASS / CLOSED

Project:

`devlog_cli`

Topics Learned:

- dependency management
- serde
- serde_json
- serialization
- deserialization
- JSON boundary
- file IO boundary
- storage boundary
- workflow boundary
- public API facade
- maintainable error boundary
- `From`
- `?`
- `ok_or_else`
- `Path`
- `AsRef<Path>`
- integration tests
- engineering tradeoffs

Insights:

- JSON string conversion and file IO should be separated.
- `workflow.rs` composes lower-level boundaries.
- Public errors protect external callers from internal implementation details.
- Stage 2 requires more engineering structure, but future sprints should increase Rust-specific mechanics practice.
