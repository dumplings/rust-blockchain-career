# Current Context

## Goal

Become job-ready for entry-level Rust + Blockchain development within 60 days.

## Current Stage

Stage 2 - Rust Engineering

## Current Sprint

None active.

## Current Milestone

Sprint-14 completed and closed.

Final report exists at `reviews/sprint-14-closure.md`.

Final result: PASS / CLOSED.

`rust_mechanics_lab` was completed as the Sprint-14 Stage 2 Rust mechanics consolidation learning project.

Sprint-14 consolidated value/reference reasoning, traits/generics, generic ownership and borrowing, and `RefCell<T>` / interior mutability.

Current active sprint remains None.

Sprint-15 roadmap now exists at `roadmaps/sprint-15.md`.

Sprint-15 is not active, and execution is not authorized.

No Sprint-15 learning project should be created until explicit learner authorization.

## Current Governance Status

The latest `AGENTS.md` has been structurally rewritten as the core governance entry point.

Detailed governance rules now live in role-specific policy documents under `docs/policies/`.

Sprint-07 Attempt-1 failed and was discarded as a teaching execution failure, not as learner completion.

Sprint-07 is reserved as an abnormal sprint record and numbering placeholder, not a normal completed sprint.

No Sprint-07 learning progress is credited.

No `wallet_cli` implementation from Sprint-07 Attempt-1 is credited as official completed learning progress.

Future agents should not assume any Sprint-07 Attempt-1 `wallet_cli` code exists, is valid, complete, or credited.

The discarded Sprint-07 `wallet_cli` attempt is not credited. Sprint-08 later recreated `wallet_cli` from scratch as the official completed learning project for this topic.

If `wallet_cli` is revisited later, future agents should use Sprint-08 as the completed learning record, not Sprint-07.

Sprint-08 is complete and closed. No Sprint-08 execution work remains active.

Sprint-09 is complete and closed. No Sprint-09 execution work remains active.

Sprint-10 is complete and closed. No Sprint-10 execution work remains active.

Sprint-11 is complete and closed. No Sprint-11 execution work remains active.

Stage 1 Exit Assessment is complete and closed. It counts as the Stage 1 exit decision.

Sprint-12 is complete and closed. It counts as completed Stage 2 Rust Engineering learning progress.

Sprint-13 is complete and closed. It counts as completed Stage 2 Rust Engineering learning progress.

Sprint-14 is complete and closed. It counts as completed Stage 2 Rust Engineering learning progress.

Current active sprint after Sprint-14 closure: None.

Sprint-15 roadmap now exists at `roadmaps/sprint-15.md`.

Sprint-15 is not active, and execution is not authorized.

No Sprint-15 learning project should be created until explicit learner authorization.

Before any future sprint planning or execution, the Teacher should read:

- latest `AGENTS.md`;
- current `CONTEXT.md`;
- current `TODO.md`;
- `roadmaps/master-roadmap.md`;
- `docs/policies/teacher-execution-policy.md`;
- `docs/policies/sprint-governance-policy.md`;
- `docs/policies/language-output-policy.md`;
- `roadmaps/stage-1-exit-assessment.md`;
- `reviews/stage-1-exit-assessment.md`;
- `reviews/architect-retirement-handover-2026-06-22.md`, if onboarding a new Architect;
- `roadmaps/sprint-11.md`;
- `reviews/sprint-11-closure.md`;
- `roadmaps/sprint-12.md`;
- `reviews/sprint-12-closure.md`;
- `roadmaps/sprint-13.md`;
- `reviews/sprint-13-closure.md`;
- `roadmaps/sprint-14.md`;
- `reviews/sprint-14-closure.md`;
- current `learning-log.md`.

Sprint-10, Sprint-09, and Sprint-08 files may be used as project-baseline background when needed.

Older Sprint-06 and Sprint-07 files are historical background only, not mandatory startup material, unless a governance ambiguity or historical failure question requires them.

## Current Learning Profile

- Existing programming background: experienced software developer;
- Rust level: around B+;
- Blockchain level: beginner;
- Preferred blockchain direction: Solana first, then general blockchain fundamentals;
- English level: can read technical English slowly, but English training is not the current main priority.

## Current Language Requirements

- Technical teaching language: Chinese
- Technical terminology: English allowed when useful
- Governance document language: English
- Repository-ready roadmap / review / failure review / handover language: English
- English training: secondary objective unless explicitly defined by a sprint

## Completed

- Created the local learning repository: `rust-blockchain-career`;
- Created the GitHub repository;
- Created a ChatGPT Project: `Rust Blockchain Career`;
- Connected local Codex to the repository root;
- Created the first version of the course governance structure;
- Completed and reviewed Sprint-01;
- Completed and reviewed Sprint-02;
- Recorded Sprint-03 termination and failure review;
- Completed and closed Sprint-04;
- Completed and closed Sprint-05;
- Completed and closed Sprint-06;
- Recorded Sprint-07 Attempt-1 as FAILED / DISCARDED;
- Created and accepted Sprint-08 roadmap;
- Completed and closed Sprint-08;
- Created and accepted Sprint-09 roadmap;
- Completed and closed Sprint-09;
- Created Sprint-10 roadmap;
- Completed and closed Sprint-10;
- Created Sprint-11 roadmap;
- Completed and closed Sprint-11;
- Created Stage 1 Exit Assessment specification;
- Completed and closed Stage 1 Exit Assessment;
- Advanced to Stage 2: Rust Engineering;
- Created Sprint-12 roadmap;
- Completed and closed Sprint-12;
- Created Sprint-13 roadmap;
- Completed and closed Sprint-13;
- Created Sprint-14 roadmap;
- Completed and closed Sprint-14;
- Created Sprint-15 roadmap for review only.

## Current Repository Structure

```text
README.md
AGENTS.md
CONTEXT.md
TODO.md
learning-log.md
.gitignore

assets/
docs/
  agents/
  policies/
  runbooks/
notes/
reviews/
roadmaps/
templates/
  daily-log-template.md
  handover-template.md
  note-template.md
  specification-review-template.md
  sprint-review-template.md
```

## In Progress

No active learning sprint.

Current focus:

- review and commit Sprint-13 closure governance updates;
- review and commit the Sprint-14 roadmap and closure governance updates;
- review the saved Sprint-15 roadmap and decide whether to authorize Sprint-15 execution;
- commit the separate `devlog_cli` Sprint-13 implementation if the learner wants to preserve it;
- review and commit the separate `rust_mechanics_lab` Sprint-14 implementation if the learner wants to preserve it;
- carry forward Sprint-14 teaching-process corrections about terminology format, validation question quality, `RefCell` explanation depth, test naming, and field-access auto-deref;
- consider public deserialization boundaries, duplicate-id validation, and overflow-safe id generation only through future approved scope;
- preserve the Teacher direct review plus Codex formal validation collaboration model for Architect review;
- preserve Sprint-07 as a failed / abnormal sprint record;
- ensure no Sprint-07 learning progress is credited;
- keep governance repository validation separate from learning-project validation;
- avoid Solana, blockchain networking, real wallet behavior, or large architecture work unless explicitly approved by a future roadmap.

Sprint-15 roadmap now exists at `roadmaps/sprint-15.md`.

Sprint-15 is not active, and execution is not authorized.

No Sprint-15 learning project should be created until explicit learner authorization.

## Sprint-01 Milestone Summary

Completed:

- Transaction model;
- ParseError;
- JSON parsing via serde_json;
- map_err usage;
- Display implementation;
- success-path testing;
- error-path testing;
- main.rs vs lib.rs reasoning;
- library crate vs binary crate reasoning;
- public API reasoning.

## Sprint-01 Completion

Status:

Completed

Validation:

- Review passed
- cargo test passed

Key outcomes:

- crate boundary understanding
- public API reasoning
- Result-based error handling reasoning
- architecture confidence improvement

## Sprint-02 Completion

Status:

Completed

Validation:

- Review passed
- Sprint-02 reviewed

Key outcomes:

- Parse versus Validation separation
- ValidationError reasoning
- AppError reasoning
- From and into() usage
- Result propagation across modules
- error-boundary reasoning
- responsibility-driven project organization

## Sprint-06 Completion

Status:

Completed

Validation:

- Student Validation passed
- Codex Repository Validation passed
- Teacher Learning Validation passed

Key outcomes:

- public API surface reasoning
- crate boundary design
- module visibility reasoning
- high-level API versus low-level workflow distinction
- public error boundary reasoning
- binary crate and library crate separation
- integration-test perspective

## Next Focus

- review and commit Sprint-13 closure governance updates;
- review and commit the Sprint-14 roadmap and closure governance updates;
- review the saved Sprint-15 roadmap and decide whether to authorize Sprint-15 execution;
- commit the separate `devlog_cli` Sprint-13 implementation if the learner wants to preserve it;
- review and commit the separate `rust_mechanics_lab` Sprint-14 implementation if the learner wants to preserve it;
- carry forward Sprint-14 teaching-process corrections about terminology format, validation question quality, `RefCell` explanation depth, test naming, and field-access auto-deref;
- maintain strict workflow separation between `rust-blockchain-career` governance validation and separate learning-project validation.

Sprint-15 roadmap now exists at `roadmaps/sprint-15.md`.

Sprint-15 is not active, and execution is not authorized.

No Sprint-15 learning project should be created until explicit learner authorization.

## Known Risk

- Teacher mode drift;
- Rust Fundamentals weakening;
- workflow mixing between Learning Workflow and Governance Workflow;
- repository state synchronization drift after abnormal sprint termination.

Long chat sessions may become unreliable over time.

The learning system should not depend on a single chat window, model, or AI platform.

## Active Governance Context

The previous Architect retired after completing the Sprint-07 governance intervention.

The Stage 2 transition Architect also retired after recording the Stage 1 Exit Assessment and Stage 2 transition.

No Architect Agent is currently active.

The next Teacher / Architect session should begin from the current governance baseline rather than assuming an active Architect is already in place.

The latest Architect handover is `reviews/architect-retirement-handover-2026-06-22.md`.

Sprint-03 is terminated / failed due to learning-system execution failure, not Rust knowledge failure.

Do not reopen Sprint-03 automatically.

Sprint-04 validated the updated repository validation reporting workflow: formal repository validation went through a Codex report rather than raw learner-reported command output.

Sprint-05 completed and closed with all validation layers passing.

Sprint-06 completed and closed with all validation layers passing.

The latest `AGENTS.md` structural rewrite and the role-specific policy documents under `docs/policies/` are now the current governance baseline.

Sprint-08 roadmap was created and accepted.

Sprint-08 completed and closed with final status PASS / CLOSED.

Sprint-09 roadmap was created and accepted.

Sprint-09 completed and closed with final status PASS / CLOSED.

Sprint-10 roadmap was created and accepted.

Sprint-10 completed and closed with final status PASS / CLOSED.

Sprint-11 roadmap was created and accepted.

Sprint-11 completed and closed with final status PASS / CLOSED.

Stage 1 Exit Assessment specification was created and accepted.

Stage 1 Exit Assessment completed and closed with final result PASS - Advance To Stage 2.

Sprint-12 roadmap was created and accepted.

Sprint-12 completed and closed with final status PASS / CLOSED.

Stage 2 remains the current learning stage.

Sprint-13 roadmap was created and accepted.

Sprint-13 completed and closed with final status PASS / CLOSED.

Sprint-14 roadmap was created and later completed.

Sprint-14 completed and closed with final status PASS / CLOSED.

Sprint-15 roadmap now exists at `roadmaps/sprint-15.md`.

Sprint-15 is not active, and execution is not authorized.

No Sprint-15 learning project should be created until explicit learner authorization.

Sprint-08 `wallet_cli` implementation summary:

- project was created from scratch during Sprint-08 at `/Users/dumplings/workspace/wallet_cli`;
- Student Validation passed;
- Codex Repository Validation passed;
- Teacher Learning Validation passed;
- `cargo check` passed;
- `cargo test` passed;
- final test count: 31 passed;
- dependencies remained empty;
- no out-of-scope implementation was found;
- no Sprint-07 implementation was credited or reused.

Sprint-09 `wallet_cli` implementation summary:

- project continued from the official Sprint-08 `wallet_cli` baseline;
- Student Validation passed;
- Codex Repository Validation passed with non-blocking notes;
- Teacher Learning Validation passed;
- `cargo check` passed;
- `cargo test` passed;
- final test count: 39 passed;
- introduced `MockWalletState`;
- added state-aware workflow through `run_with_state(args, &mut MockWalletState)`;
- practiced immutable borrowing for read-only balance behavior;
- practiced mutable borrowing for deterministic mock credit behavior;
- preserved non-persistent CLI state boundary;
- no real wallet, persistence, Solana, RPC, async/Tokio, signing, sender-account, insufficient-funds, or blockchain semantics were introduced.

Sprint-10 `wallet_cli` implementation summary:

- project continued from the official Sprint-09 `wallet_cli` baseline;
- Student Validation passed;
- Codex Repository Validation passed;
- Teacher Learning Validation passed;
- `cargo check` passed;
- `cargo test` passed;
- final test count: 42 passed;
- `CliError` was re-exported from the crate root;
- `run`, `run_with_state`, `MockWalletState`, and `CliError` form the intended crate-root public API;
- lower-level errors, command parsing, domain types, and output helpers remain internal to the crate facade;
- no new dependencies or out-of-scope behavior were introduced.

Sprint-11 `wallet_cli` implementation summary:

- project continued from the official Sprint-10 `wallet_cli` baseline;
- Student Validation passed;
- Codex Repository Validation passed;
- Teacher Learning Validation passed;
- `cargo check` passed;
- `cargo test` passed;
- final test count: 42 passed;
- `CliError` is now a public struct with private fields;
- `CliErrorKind` is public and crate-root re-exported;
- final crate-root public API is `wallet_cli::run`, `wallet_cli::run_with_state`, `wallet_cli::MockWalletState`, `wallet_cli::CliError`, and `wallet_cli::CliErrorKind`;
- public `CliError` no longer exposes `CommandParseError` or `DomainValidationError` through public variants or public fields;
- lower-level parse/domain errors remain internal implementation details;
- `From<CommandParseError>` and `From<DomainValidationError>` mapping is preserved;
- `Display for CliError` remains the user-facing formatting boundary;
- workflow/public API tests use `error.kind()` / `CliErrorKind`;
- no new dependencies or out-of-scope behavior were introduced;
- `wallet_cli` is considered sufficiently exhausted for Stage 1 Rust Foundations unless a future review explicitly finds a new high-value reason to revisit it.

Stage 1 Exit Assessment `task_tracker` summary:

- assessment used a fresh project at `/Users/dumplings/workspace/task_tracker`;
- final report exists at `reviews/stage-1-exit-assessment.md`;
- final result: PASS - Advance To Stage 2;
- Student Validation passed;
- Codex Repository Validation passed conditionally with non-blocking concerns;
- Teacher Learning Validation passed;
- `cargo check` passed;
- `cargo test` passed;
- final test count: 4 passed;
- project used no external dependencies;
- project did not continue `wallet_cli`;
- assessment stayed out of Solana, blockchain networking, real wallet behavior, persistence, async Rust, Tokio, `clap`, and large architecture work;
- demonstrated ownership, borrowing, `Result`, error propagation, module boundaries, crate-root public API basics, limited testing habits, small-project navigation, and source-level tradeoff reasoning;
- non-blocking reinforcement areas for Stage 2 include more precise `?` / `From` explanation, stronger success-path assertions, richer public error context when appropriate, and continued ownership / borrowing reasoning in larger codebases.

Sprint-12 `devlog_cli` implementation summary:

- project was created fresh during Sprint-12 at `/Users/dumplings/workspace/devlog_cli`;
- final report exists at `reviews/sprint-12-closure.md`;
- final result: PASS / CLOSED;
- Student Validation passed;
- Codex Repository Validation passed;
- Teacher Learning Validation passed;
- `cargo fmt --check` passed;
- `cargo check` passed;
- `cargo test` passed;
- final test count: 8 passed;
- `devlog_cli` is the official Sprint-12 Stage 2 learning project foundation;
- implementation introduced `DevLogEntry`, `EntryStore`, `DevLogError`, `DevLogErrorKind`, `serde`, `serde_json`, JSON serialization/deserialization, file-backed storage, workflow composition, crate-root public facade re-exports, and focused unit/integration tests;
- Sprint-12 did not continue `wallet_cli`, did not turn `task_tracker` into the next teaching project, and did not reuse or credit Sprint-07 Attempt-1;
- learner feedback: future Stage 2 sprints should increase the absolute amount of Rust-specific learning and practice, not only architecture discussion;
- process observation: preserve the hybrid model of Teacher direct source review plus Codex formal full-project validation.

Sprint-13 `devlog_cli` implementation summary:

- project continued from the official Sprint-12 `devlog_cli` baseline;
- final report exists at `reviews/sprint-13-closure.md`;
- final result: PASS / CLOSED;
- Student local validation passed;
- Codex Repository Validation passed with non-blocking notes;
- Teacher Learning Validation passed;
- `cargo fmt --check` passed;
- `cargo check` passed;
- `cargo test` passed;
- final test count: 13 passed, 0 failed;
- preserved appropriate `Path` / `PathBuf` / `AsRef<Path>` API design;
- added deserialization validation before persisted state is trusted;
- restored `EntryStore::next_id` from loaded entries;
- added bounded context-aware IO error mapping;
- introduced the minimal `EntryStorage` trait and `FileEntryStorage`;
- added a generic workflow boundary and fake-storage testing;
- kept `main.rs` thin and preserved a coherent crate-root public API facade;
- dependencies remained limited to `serde` and `serde_json`;
- future reinforcement areas include the value/reference mental model, ownership and borrowing with generics, trait/generic terminology, `RefCell` / interior mutability, public deserialization boundaries, duplicate-id validation, and overflow-safe id generation;
- Sprint-13 did not continue `wallet_cli`, did not turn `task_tracker` into a teaching project, and did not reuse or credit Sprint-07 Attempt-1.

Sprint-14 `rust_mechanics_lab` implementation summary:

- project used the focused Stage 2 Rust mechanics lab at `/Users/dumplings/workspace/rust_mechanics_lab`;
- final report exists at `reviews/sprint-14-closure.md`;
- final result: PASS / CLOSED;
- Student / implementation validation passed;
- Codex Repository Validation passed;
- Teacher Learning Validation passed;
- `cargo fmt --check` passed;
- `cargo check` passed;
- `cargo test` passed;
- final test result: 13 integration tests passed;
- validated value ownership, shared borrowing, mutable borrowing, ownership transfer, clone from borrow, trait definition and concrete implementation, concrete function versus generic trait-bound function, generic ownership / borrowing / mutable borrowing, and `RefCell<T>` interior mutability for a fake recorder scenario;
- confirmed exclusions included no `dyn Trait`, no `Rc<RefCell<T>>`, no async/threading/concurrency primitives, no external dependencies, and no unrelated CLI, file IO, storage, networking, or blockchain-specific logic;
- non-blocking suggestion: consider `Default` for `FakeRecorder` later if useful, but this was not required for Sprint-14 closure;
- carry-forward teaching-process corrections include terminology format discipline, stronger validation question framing, deeper initial `RefCell<T>` explanation, recommended test names, and field-access auto-deref clarification.

Sprint-07 Attempt-1 failed and was discarded as a teaching execution failure.

Sprint-07 is reserved as an abnormal sprint record, not a normal completed sprint.

No Sprint-07 learning progress is credited.

No `wallet_cli` implementation from Sprint-07 Attempt-1 is credited as official completed learning progress.

Future agents should not assume any Sprint-07 Attempt-1 `wallet_cli` code exists, is valid, complete, or credited.

The discarded Sprint-07 `wallet_cli` attempt remains uncredited.

The next real teaching sprint or specification review should require explicit learner or Architect authorization.

## Future System Notes

The current stage follows the YAGNI principle. Do not split directories too early.

For now, `learning-log.md` is used as a single growth log.

Consider upgrading the structure only if one or more of the following happens:

- `learning-log.md` becomes too long to maintain;
- daily records become frequent and hard to search;
- logs need to be queried by date, sprint, or topic;
- multiple agents need clearer boundaries for handover.

Possible future structure:

```text
reviews/
  daily/
    2026-06-05.md
    2026-06-06.md

  sprints/
    sprint-01.md
    sprint-02.md
```

Upgrade principle:

Do not restructure for structure's sake.
Only split files or directories when the current structure starts to hurt maintenance, search, or handover.

## Latest Sprint Closure

Sprint:

Sprint-14 - `Rust Mechanics Consolidation Lab - Value/Reference + Traits/Generics + Interior Mutability`

Result:

PASS / CLOSED

Summary:

`reviews/sprint-14-closure.md` records the completed Sprint-14 closure.

Sprint-14 completed the focused Stage 2 `rust_mechanics_lab` project and validated value/reference reasoning, traits and generics, generic ownership and borrowing, and `RefCell<T>` / interior mutability through a small concept-focused lab.

Recommendation:

Current active sprint is None. Sprint-15 roadmap now exists at `roadmaps/sprint-15.md`, but Sprint-15 is not active and execution is not authorized. The next allowed step is learner review of the saved roadmap and an explicit decision on whether to authorize Sprint-15 execution. Keep governance repository validation separate from learning-project validation and do not credit Sprint-07 learning progress.

## Latest Assessment

Assessment:

Stage 1 Exit Assessment

Result:

PASS - Advance To Stage 2

Summary:

`reviews/stage-1-exit-assessment.md` records the completed Stage 1 Exit Assessment.

The assessment decided that the learner is ready to leave Stage 1 and begin Stage 2 Rust Engineering.

Assessment focus:

- ownership and borrowing in project context;
- `Result` and error propagation;
- module boundaries and crate-root public API reasoning;
- small Rust project navigation;
- meaningful but limited tests;
- independent implementation and explanation in a small fresh assessment project.

Recommendation:

This assessment recommendation was completed by the later Stage 2 Specification Review, Sprint-12 roadmap, and Sprint-12 execution. Continue using it as the Stage 1 exit evidence, not as the current next action.

## Active Learning Strategy

Primary Teacher:

- ChatGPT Project

Primary Coding Environment:

- Local repository
- Codex

Learning Model:

- student writes code;
- coding agents assist;
- teacher agents guide and review.

Learning should remain project-driven.

Avoid passive content consumption when a practical project can be used instead.
