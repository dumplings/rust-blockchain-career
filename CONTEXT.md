# Current Context

## Goal

Become job-ready for entry-level Rust + Blockchain development within 60 days.

## Current Stage

Stage 1: Rust Foundations

## Current Sprint

None active.

## Current Milestone

Sprint-07 Attempt-1 failed / discarded.

Sprint-07 is reserved as an abnormal sprint record.

The next real teaching sprint should use Sprint-08.

## Current Governance Status

The latest `AGENTS.md` has been structurally rewritten and should be treated as the current governance baseline.

Sprint-07 Attempt-1 failed and was discarded as a teaching execution failure, not as learner completion.

Sprint-07 is reserved as an abnormal sprint record and numbering placeholder, not a normal completed sprint.

No Sprint-07 learning progress is credited.

No `wallet_cli` implementation from Sprint-07 Attempt-1 is credited as official completed learning progress.

Future agents should not assume any Sprint-07 Attempt-1 `wallet_cli` code exists, is valid, complete, or credited.

The original `/Users/dumplings/workspace/wallet_cli` path is no longer present.

If `wallet_cli` is revisited later, it should be recreated from scratch unless a future Teacher or Architect explicitly decides otherwise.

Future course content should be decided by the next Teacher / Architect based on the latest governance baseline and learner state.

Before designing Sprint-08, the next Teacher should read:

- latest `AGENTS.md`;
- `reviews/sprint-06-closure.md`;
- `roadmaps/sprint-07.md`;
- `reviews/sprint-07-attempt-1-failure-review.md`;
- `reviews/architect-retirement-handover-2026-06-13.md`;
- current `CONTEXT.md`;
- current `learning-log.md`.

## Current Learning Profile

- Existing programming background: experienced software developer;
- Rust level: around B+;
- Blockchain level: beginner;
- Preferred blockchain direction: Solana first, then general blockchain fundamentals;
- English level: can read technical English slowly, but English training is not the current main priority.

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
- Recorded Sprint-07 Attempt-1 as FAILED / DISCARDED.

## Current Repository Structure

```text
README.md
AGENTS.md
CONTEXT.md
TODO.md
learning-log.md
.gitignore

assets/
notes/
reviews/
roadmaps/
templates/
  daily-log-template.md
  handover-template.md
  note-template.md
  sprint-review-template.md
```

## In Progress

No active learning sprint.

Current focus:

- preserve Sprint-07 as a failed / abnormal sprint record;
- ensure no Sprint-07 learning progress is credited;
- prepare Sprint-08 only through Specification Review;
- wait for the next Teacher / Architect to select the Sprint-08 direction based on the current governance baseline and learner state.

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

- Sprint-08 Specification Review when a next Teacher / Architect is ready;
- Sprint-08 direction selection;
- continued Rust Fundamentals reinforcement.

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

The latest `AGENTS.md` structural rewrite is now the current governance baseline.

Sprint-07 Attempt-1 failed and was discarded as a teaching execution failure.

Sprint-07 is reserved as an abnormal sprint record, not a normal completed sprint.

No Sprint-07 learning progress is credited.

No `wallet_cli` implementation from Sprint-07 Attempt-1 is credited as official completed learning progress.

Future agents should not assume any Sprint-07 Attempt-1 `wallet_cli` code exists, is valid, complete, or credited.

The original `/Users/dumplings/workspace/wallet_cli` path is no longer present.

The next real teaching sprint should use Sprint-08 numbering.

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

Sprint-07 Attempt-1 Failure Review

Result:

FAILED / DISCARDED

Summary:

Sprint-07 Attempt-1 was a teaching execution failure, not learner completion and not learner Rust content failure.

Governance outcomes:

- `AGENTS.md` was structurally rewritten and is the current governance baseline;
- `roadmaps/sprint-07.md` records Sprint-07 as an abnormal sprint placeholder;
- `reviews/sprint-07-attempt-1-failure-review.md` records the formal failure review;
- no Sprint-07 learning progress or `wallet_cli` capability is credited.

Recommendation:

Do not continue Sprint-07. Do not treat Sprint-07 as completed. The next real teaching sprint should use Sprint-08 and should be designed by the next Teacher / Architect after reading the latest governance baseline.

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
