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
