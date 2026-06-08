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
