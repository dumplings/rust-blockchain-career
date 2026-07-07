# Sprint-12 Roadmap

## 1. Sprint Identity

- Sprint number: Sprint-12
- Sprint name: `devlog_cli v0.1 — Stage 2 Project Foundation`
- Stage: Stage 2 — Rust Engineering
- Primary project: `devlog_cli`
- Proposed learning-project root: `/Users/dumplings/workspace/devlog_cli`
- Governance repository root: `/Users/dumplings/workspace/rust-blockchain-career`
- Roadmap target file: `roadmaps/archive/sprint-12.md`
- Sprint status: Draft only
- Execution status: Not started
- Authorization status: Not authorized for execution

Sprint-12 is the first proposed Stage 2 Rust Engineering sprint after the Stage 1 Exit Assessment.

This roadmap draft does not authorize Sprint-12 execution.

Sprint-12 execution requires explicit learner approval after roadmap review.

## 2. Governance Context

Stage 1 — Rust Foundations is PASS / CLOSED.

The Stage 1 Exit Assessment final result is:

```text
PASS - Advance To Stage 2
```

The current active stage is:

```text
Stage 2 — Rust Engineering
```

The current active sprint is:

```text
None
```

Sprint-12 has not been drafted, authorized, or started before this roadmap draft.

Sprint-07 Attempt-1 remains FAILED / DISCARDED. No Sprint-07 Attempt-1 learning progress is credited. No Sprint-07 implementation should be assumed, reused, or credited.

`wallet_cli` is considered sufficiently exhausted for Stage 1 Rust Foundations and should not be continued by default.

`task_tracker` was a Stage 1 Exit Assessment artifact and should not become the next teaching project by default.

Architect Stage 2 Specification Review result:

```text
APPROVE WITH REVISIONS for Sprint-12 roadmap drafting only
```

This approval allows drafting the Sprint-12 roadmap. It does not authorize Sprint-12 execution.

## 3. Sprint Objective

Sprint-12 creates a fresh Stage 2 Rust Engineering project foundation through a small local record-management CLI/library project with JSON file persistence.

The central objective is to move beyond late Stage 1 small-project consolidation into practical Rust engineering work:

- larger project organization;
- dependency management;
- JSON serialization and deserialization;
- file-backed load/save behavior;
- a thin CLI boundary;
- maintainable public error design;
- limited integration-style tests;
- continued reinforcement of ownership, borrowing, `Result`, module boundaries, public API design, and error propagation.

Sprint-12 should teach engineering structure without becoming a large product-design or architecture sprint.

## 4. Stage Alignment

Sprint-12 aligns with Stage 2 — Rust Engineering.

Stage 2 major capabilities include:

- larger project organization;
- trait and generic usage when useful;
- dependency management;
- CLI workflows;
- file and data handling;
- integration testing;
- maintainable error design.

Sprint-12 should introduce Stage 2 through dependency management, file/data handling, and maintainable error boundaries first.

This sprint should not jump ahead into blockchain, Solana, Anchor, async Rust, or large architecture work.

## 5. Project Choice And Rationale

The recommended project is:

```text
devlog_cli
```

Rationale:

`devlog_cli` is a domain-light local record/log project. It is meaningful for the learner’s developer journey while staying focused on Rust engineering rather than product complexity.

The project should model a small collection of local developer log entries, notes, or records. The domain should stay intentionally simple.

Possible domain types:

- `DevLogEntry`
- `EntryStore`
- `RecordStore`
- `Note`
- `NoteBook`

Preferred direction:

- `DevLogEntry`
- `EntryStore`

Possible workflows:

- add an entry;
- list entries;
- find an entry by id;
- mark an entry done, completed, or archived;
- load entries from a JSON file;
- save entries to a JSON file.

The project should teach how Rust code is organized, validated, serialized, persisted, and exposed through a maintainable public workflow boundary.

The project should not become a productivity-app design sprint.

## 6. Scope

In scope:

- create a fresh local Rust learning project after execution is explicitly authorized;
- use a small library + binary crate structure;
- define a simple record/log domain model;
- validate basic domain rules;
- introduce a small dependency set, likely `serde` and `serde_json`;
- serialize and deserialize project data as JSON;
- load records from a JSON file;
- save records to a JSON file;
- define a dedicated storage/file boundary or equivalent workflow boundary;
- keep `main.rs` thin;
- expose a maintainable public API from the library crate;
- define a maintainable public error boundary;
- use `Result` and error propagation intentionally;
- add 3 to 5 focused tests;
- include at least one success-path test;
- include at least one error-path test;
- include at least one file-backed load/save or public workflow test;
- run a final validation cycle;
- complete Student Validation;
- complete Codex Repository Validation;
- complete Teacher Learning Validation.

## 7. Explicit Non-Goals

Out of scope:

- Solana;
- Anchor;
- blockchain networking;
- blockchain account model;
- real wallet behavior;
- private keys;
- signing;
- RPC;
- async Rust;
- Tokio;
- database;
- production-grade persistence;
- large architecture;
- trait-heavy abstraction;
- generic-heavy redesign;
- broad test expansion;
- exhaustive file-system edge cases;
- production CLI framework expansion;
- full `clap`-based CLI unless explicitly justified as a very small dependency-management step;
- output-string churn;
- making testing the main learning burden;
- continuing `wallet_cli` by default;
- turning `task_tracker` into the next teaching project by default;
- reusing or crediting Sprint-07 Attempt-1.

## 8. Learning Outcomes

By the end of Sprint-12, the learner should be able to explain:

- how a Stage 2 Rust project differs from a small Stage 1 Rust Foundations project;
- why dependency management matters when introducing crates such as `serde` and `serde_json`;
- how serialization and deserialization fit into file-backed workflows;
- why file IO should have a clear module or type boundary;
- how to keep `main.rs` thin while library modules contain reusable logic;
- how public API design changes when a project has domain, storage, workflow, and error layers;
- why a public error boundary should avoid exposing unnecessary internal implementation details;
- how `Result` and `?` propagate errors across domain, storage, and workflow boundaries;
- how ownership and borrowing appear in a file-backed record store;
- how to use limited tests to validate behavior without over-testing internal helpers;
- how to make and explain engineering tradeoffs in a larger Rust project.

## 9. Required Learner Design Decisions

The learner must make and explain the following design decisions during execution.

### 9.1 Public API Shape

The learner must decide what the crate-root public API should expose.

Possible public API elements:

- `DevLogEntry`;
- `EntryStore`;
- `DevLogError`;
- `DevLogErrorKind`;
- high-level workflow functions;
- storage/load/save functions or methods.

The learner should explain which types/functions external callers should use directly and which implementation details should remain internal.

### 9.2 Module Boundary For File / Storage Behavior

The learner must decide where file IO belongs.

Acceptable directions:

- a dedicated `storage` module;
- a dedicated `EntryStore` type with load/save methods;
- high-level workflow functions that delegate to a storage boundary.

The learner should explain why file IO should not be scattered across unrelated modules.

### 9.3 Public Error Boundary Shape

The learner must design a maintainable public error boundary.

Preferred direction:

- expose one public project-level error type, such as `DevLogError`;
- optionally expose a high-level `DevLogErrorKind`;
- keep low-level JSON/file/domain details mapped into the public error boundary;
- preserve useful user-facing `Display` output;
- avoid over-engineering a production-grade error framework.

The learner should explain what information belongs in public errors and what should stay internal.

### 9.4 File IO Location

The learner must decide whether file IO belongs primarily in:

- a dedicated store type;
- storage functions;
- workflow functions.

The learner should justify the choice using responsibility boundaries.

### 9.5 `main.rs` Versus Library Modules

The learner must decide what belongs in `main.rs`.

Expected direction:

- `main.rs` parses minimal CLI arguments or delegates immediately;
- `main.rs` should not own core business logic;
- domain validation, storage behavior, workflow behavior, and error design should live in library modules.

## 10. Implementation Artifacts

Sprint-12 should produce three to four connected implementation artifacts.

### 10.1 Domain Model And Validation

Define a small domain model such as `DevLogEntry`.

Expected fields may include:

- id;
- title or text;
- status such as open/done/archived;
- optional timestamp only if it does not increase scope too much.

Required behavior:

- construct valid entries;
- reject invalid entries such as empty titles/text;
- preserve simple ownership rules;
- expose read-only accessors or an intentionally minimal public surface.

### 10.2 JSON Serialization / Deserialization Dependency

Introduce a small dependency set.

Preferred dependencies:

- `serde`;
- `serde_json`.

The learner should understand why dependencies are added, where they appear in `Cargo.toml`, and what capabilities they provide.

The sprint should not introduce many dependencies at once.

### 10.3 File-Backed Load / Save Boundary

Implement a file-backed boundary that can:

- load entries from a JSON file;
- save entries to a JSON file;
- handle invalid JSON or file errors through the public error boundary.

This should be educational file persistence, not production-grade persistence.

Avoid:

- database design;
- locking;
- concurrent writes;
- migration systems;
- complex config;
- extensive filesystem edge-case handling.

### 10.4 Public Workflow And Maintainable Error Boundary

Expose a small public workflow.

Possible workflows:

- add entry;
- list entries;
- find entry by id;
- mark entry done or archived;
- load/save around the workflow.

The public workflow should return `Result<_, DevLogError>` or an equivalent project-level error type.

The final workflow should demonstrate error propagation across domain validation, storage, JSON, and file IO boundaries.

## 11. Suggested Module Boundaries

Suggested structure:

```text
src/
  lib.rs
  main.rs
  entry.rs
  store.rs
  storage.rs
  workflow.rs
  error.rs
tests/
  public_workflow.rs
```

Suggested responsibilities:

- `entry.rs`: domain model and validation;
- `store.rs`: in-memory collection behavior, id lookup, status updates;
- `storage.rs`: JSON file load/save boundary;
- `workflow.rs`: high-level public workflows that connect store and storage behavior;
- `error.rs`: public project error boundary and internal mappings;
- `lib.rs`: crate-root public facade;
- `main.rs`: thin CLI boundary only;
- `tests/public_workflow.rs`: limited integration-style validation of public behavior.

This structure is a recommendation, not a requirement. The learner may choose a different structure if they can explain the responsibility boundaries clearly.

## 12. Checkpoint Plan

### Checkpoint 1 — Stage 2 Project Boundary And Design Decisions

Teaching focus:

- dependency management;
- project organization;
- file/data handling boundary;
- public API boundary;
- error boundary.

Learner work during execution:

- choose the final project/domain naming;
- decide public API shape;
- decide module boundaries;
- decide where file IO belongs;
- decide the public error shape.

Validation focus:

- whether the learner can explain the design before implementing;
- whether the proposed scope remains bounded.

### Checkpoint 2 — Domain Model And Store Foundation

Teaching focus:

- ownership and borrowing in a larger library structure;
- domain validation;
- private fields and public accessors;
- store responsibility.

Learner work during execution:

- implement the domain model;
- implement a minimal store type or equivalent collection boundary;
- validate basic add/find/status behavior.

Validation focus:

- domain remains simple;
- internal representation is not exposed unnecessarily;
- ownership and borrowing are intentional.

### Checkpoint 3 — Dependency Management And JSON Boundary

Teaching focus:

- `serde`;
- `serde_json`;
- serialization;
- deserialization;
- dependency scope.

Learner work during execution:

- add the minimal dependency set;
- make the domain/store serializable as appropriate;
- implement JSON conversion through the intended boundary.

Validation focus:

- dependency use is justified;
- serialization is not mixed into unrelated workflow logic;
- JSON behavior supports the project goal.

### Checkpoint 4 — File-Backed Load / Save And Error Boundary

Teaching focus:

- file IO boundary;
- `Result`;
- `?`;
- error propagation;
- public error contract.

Learner work during execution:

- implement load/save behavior;
- map file, JSON, and domain errors into the public error boundary;
- preserve useful `Display` behavior.

Validation focus:

- file IO has a clear home;
- public errors are maintainable;
- low-level details are not exposed without reason.

### Checkpoint 5 — Public Workflow, Focused Tests, And Final Validation

Teaching focus:

- integration-style testing;
- public API validation;
- final source-level explanation;
- validation separation.

Learner work during execution:

- expose the intended public workflow;
- add or update 3 to 5 focused tests;
- run local validation;
- explain design tradeoffs.

Validation focus:

- tests cover meaningful behavior without dominating the sprint;
- final implementation matches the roadmap scope;
- learner can explain the system at source level.

## 13. Testing Requirements

Tests are required, but testing must not dominate the sprint.

Preferred test count:

```text
3 to 5 focused tests total
```

Required coverage:

- at least one success-path test;
- at least one error-path test;
- at least one file-backed load/save or public workflow test.

Preferred test examples:

- adding a valid entry succeeds;
- empty title/text returns a validation error;
- save then load preserves entries;
- malformed JSON maps into the public error boundary;
- public workflow can add and list entries through the intended API.

Avoid:

- exhaustive file-system edge cases;
- testing every private helper;
- repeated output-string churn;
- making tests the main implementation burden;
- broad CLI output snapshot testing;
- production persistence edge cases.

## 14. Student Validation Requirements

Before requesting formal Codex Repository Validation, the learner should complete Student Validation.

Student Validation should include:

- run `cargo check`;
- run `cargo test`;
- optionally run `cargo fmt --check` if formatting is part of the execution standard;
- review the public API surface;
- explain the final module boundaries;
- explain where file IO lives and why;
- explain the public error boundary;
- explain how dependency management was introduced;
- explain how `Result`, `?`, and error conversion are used;
- identify any known non-blocking issues.

Learner-reported command output is useful as a self-check, but it is not the primary formal repository validation path.

## 15. Codex Repository Validation Requirements

Codex Repository Validation is required after meaningful implementation changes during Sprint-12 execution.

Codex should validate one repository or project root at a time.

For the learning project, validate:

```text
/Users/dumplings/workspace/devlog_cli
```

Codex should verify:

- project builds successfully;
- tests pass;
- implementation matches Sprint-12 scope;
- dependency usage is minimal and justified;
- JSON load/save behavior is present;
- `main.rs` remains thin;
- public API is coherent;
- public error boundary is maintainable;
- tests are focused and not excessive;
- no Solana, Anchor, blockchain networking, wallet behavior, private keys, signing, RPC, async Rust, Tokio, database, or large architecture work was introduced;
- no Sprint-07 Attempt-1 work was reused or credited;
- `wallet_cli` was not continued by default;
- `task_tracker` was not turned into the next teaching project by default.

If the governance repository is updated later with `roadmaps/archive/sprint-12.md`, validate separately:

```text
/Users/dumplings/workspace/rust-blockchain-career
```

Codex must not combine governance repository validation and learning-project validation unless the learner explicitly requests a cross-repository audit.

## 16. Teacher Learning Validation Requirements

Teacher Learning Validation is required before Sprint-12 can be closed.

The Teacher should evaluate whether the learner can explain:

- why `devlog_cli` is an appropriate first Stage 2 project;
- how Stage 2 Rust Engineering differs from late Stage 1 consolidation;
- what dependencies were added and why;
- how JSON serialization/deserialization works in this project;
- where file IO belongs and why;
- how the public API is shaped;
- how public and internal errors are separated;
- how `Result`, `?`, and error propagation work across module boundaries;
- how ownership and borrowing appear in the store/workflow design;
- why the tests are sufficient but not excessive;
- what tradeoffs were made and what was intentionally deferred.

Teacher Learning Validation must not rely only on raw command output. It should include source-level review and learner explanation.

## 17. Completion Criteria

Sprint-12 can be completed only when all of the following are true:

- Sprint-12 execution was explicitly authorized by the learner before implementation began;
- the fresh `devlog_cli` learning project exists only as an authorized Stage 2 project;
- no `wallet_cli` continuation was used by default;
- `task_tracker` was not converted into the next teaching project by default;
- no Sprint-07 Attempt-1 progress or implementation was credited;
- the project contains a small domain model and validation boundary;
- JSON serialization/deserialization is implemented through a minimal dependency set;
- file-backed load/save behavior exists;
- the CLI boundary is thin;
- public workflow and error boundaries are maintainable;
- 3 to 5 focused tests exist and pass;
- Student Validation is PASS;
- Codex Repository Validation is PASS or has only explicitly accepted non-blocking concerns;
- Teacher Learning Validation is PASS;
- scope remained inside Stage 2 Rust Engineering;
- explicit non-goals were respected;
- governance repository and learning-project repository validation were kept separate.

## 18. Teaching Notes

During future Sprint-12 execution, technical teaching language should be primarily Chinese.

Important professional terms should be introduced in the form:

```text
English professional term (Chinese professional translation)
```

Examples for Sprint-12:

- dependency management (依赖管理);
- serialization (序列化);
- deserialization (反序列化);
- persistence boundary (持久化边界);
- public API (公共 API);
- error boundary (错误边界);
- error propagation (错误传播);
- module boundary (模块边界);
- integration test (集成测试).

Teaching should use structured instruction, not guided guessing.

The Teacher should teach the concept and mental model before asking the learner to implement.

Execution should proceed checkpoint by checkpoint.

The learner remains the primary developer.

Code examples are allowed when useful, but the Teacher should not provide near-final production implementation too early for core business logic, type design, error modeling, or workflow design.

More complete test examples are acceptable when they reduce testing friction and keep testing supportive.

Codex should be used for formal repository/source inspection after meaningful implementation changes.

Learner-pasted raw `cargo check` or `cargo test` output should not replace formal Codex Repository Validation.

## 19. Repository Validation Separation

The governance repository and the learning-project repository must be validated separately.

Governance repository:

```text
/Users/dumplings/workspace/rust-blockchain-career
```

Learning-project repository:

```text
/Users/dumplings/workspace/devlog_cli
```

Codex should validate one repository or project root at a time.

If `roadmaps/archive/sprint-12.md` is later added to the governance repository, that is a governance repository update and should be validated against the governance repository root.

If `devlog_cli` is later created and implemented, that is a learning-project update and should be validated against the learning-project root.

Do not combine governance validation and learning-project validation into one prompt unless the learner explicitly requests a cross-repository audit.

## 20. Authorization Statement

This document is a Sprint-12 roadmap draft only.

Sprint-12 roadmap drafting does not authorize Sprint-12 execution.

Sprint-12 execution requires explicit learner approval after roadmap review.

This roadmap does not authorize:

- creating the `devlog_cli` project;
- modifying learning-project files;
- modifying governance repository files;
- asking Codex to update files;
- starting implementation;
- continuing `wallet_cli`;
- turning `task_tracker` into the next teaching project;
- reusing or crediting Sprint-07 Attempt-1.

The next allowed step is learner review of this roadmap draft.

Only after explicit learner approval should the Teacher begin Sprint-12 execution planning or provide an executable repository-update prompt for saving this roadmap.
