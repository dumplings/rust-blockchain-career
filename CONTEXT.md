# Current Context

## Goal

Become job-ready for entry-level Rust + Blockchain development within 60 days.

## Current Stage

Stage 1: Rust Foundations

## Current Sprint

None active.

## Current Milestone

Sprint-11 completed and closed.

Sprint-11 `wallet_cli` implementation passed final validation.

`wallet_cli` is considered sufficiently exhausted for Stage 1 Rust Foundations unless a future review explicitly finds a new high-value reason to revisit it.

Candidate next focus: Stage 1 exit assessment, a new Stage 1 Rust Foundations project, Stage 2 Rust Engineering preparation, or another Architect-approved direction.

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

Before starting the next sprint or future specification review, the Teacher should read:

- latest `AGENTS.md`;
- current `CONTEXT.md`;
- current `TODO.md`;
- `roadmaps/master-roadmap.md`;
- `docs/policies/teacher-execution-policy.md`;
- `docs/policies/sprint-governance-policy.md`;
- `docs/policies/language-output-policy.md`;
- `roadmaps/sprint-11.md`;
- `reviews/sprint-11-closure.md`;
- `roadmaps/sprint-10.md`;
- `reviews/sprint-10-closure.md`;
- current `learning-log.md`.

Sprint-09 and Sprint-08 files may be used as project-baseline background when needed.

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
- Completed and closed Sprint-11.

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

- review and commit Sprint-11 closure governance updates;
- commit the separate `wallet_cli` Sprint-11 implementation;
- decide whether to authorize Stage 1 exit assessment, a new Stage 1 Rust Foundations project, Stage 2 Rust Engineering preparation, or another Architect-approved next step;
- continue Stage 1 Rust Foundations reinforcement;
- preserve Sprint-07 as a failed / abnormal sprint record;
- ensure no Sprint-07 learning progress is credited;
- keep governance repository validation separate from learning-project validation;
- avoid Solana, Async Rust, Tokio, blockchain networking, real wallet behavior, or large architecture work unless explicitly approved by a future roadmap.

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

- decide whether to authorize Stage 1 exit assessment, a new Stage 1 Rust Foundations project, Stage 2 Rust Engineering preparation, or another Architect-approved next step;
- continued Rust Fundamentals reinforcement;
- maintain strict workflow separation between `rust-blockchain-career` governance validation and `wallet_cli` learning-project validation.

## Known Risk

- Teacher mode drift;
- Rust Fundamentals weakening;
- workflow mixing between Learning Workflow and Governance Workflow;
- repository state synchronization drift after abnormal sprint termination.

Long chat sessions may become unreliable over time.

The learning system should not depend on a single chat window, model, or AI platform.

## Active Governance Context

The previous Architect retired after completing the Sprint-07 governance intervention.

No Architect Agent is currently active.

The next Teacher / Architect session should begin from the current governance baseline rather than assuming an active Architect is already in place.

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

## Latest Assessment

Assessment:

Sprint-11 Closure Report

Result:

PASS / CLOSED

Summary:

Sprint-11 completed the Stage 1 Rust Foundations sprint:

`wallet_cli v0.4 — Final Public Error Contract + Source-Level Consolidation`

Sprint-11 continued from the official Sprint-10 `wallet_cli` baseline and passed Student Validation, Codex Repository Validation, and Teacher Learning Validation.

Learning outcomes:

- final public error contract design;
- public `CliError` struct with private fields;
- public and crate-root re-exported `CliErrorKind`;
- internal parse/domain errors hidden from public `CliError` variants and public fields;
- `From` mapping from lower-level errors into public `CliError`;
- `Display` as user-facing formatting boundary;
- workflow/public API tests using `error.kind()`;
- final `wallet_cli` crate-root public API stability.

Recommendation:

Review and commit Sprint-11 closure governance updates. Commit the separate `wallet_cli` Sprint-11 implementation. Decide whether to authorize Stage 1 exit assessment, a new Stage 1 Rust Foundations project, Stage 2 Rust Engineering preparation, or another Architect-approved next step. Keep governance repository validation separate from `wallet_cli` learning-project validation. Do not credit Sprint-07 learning progress. Do not start or draft Sprint-12 without explicit authorization.

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
