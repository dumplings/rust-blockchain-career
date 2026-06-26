# Sprint-13 Roadmap

## 1. Sprint Identity

* Sprint number: Sprint-13
* Sprint name: `devlog_cli v0.2 — Rust Mechanics + Persistence Correctness + Minimal Storage Abstraction`
* Stage: Stage 2 — Rust Engineering
* Primary project: `devlog_cli`
* Learning-project root: `/Users/dumplings/workspace/devlog_cli`
* Governance repository root: `/Users/dumplings/workspace/rust-blockchain-career`
* Roadmap target file: `roadmaps/sprint-13.md`
* Sprint status: Draft only
* Execution status: Not started
* Authorization status: Not authorized for execution

Sprint-13 continues from the official Sprint-12 `devlog_cli` baseline.

This roadmap draft does not authorize Sprint-13 execution.

Sprint-13 execution requires explicit learner approval after roadmap review.

## 2. Governance Context

Stage 1 — Rust Foundations is PASS / CLOSED.

The current active stage is:

`Stage 2 — Rust Engineering`

Sprint-12 is PASS / CLOSED and counts as completed Stage 2 Rust Engineering learning progress.

The current active sprint is:

`None`

Sprint-13 has not been previously drafted, authorized, or started.

`devlog_cli` is the official Sprint-12 Stage 2 learning project foundation.

`wallet_cli` should not be continued by default.

`task_tracker` should not become the next teaching project by default.

Sprint-07 Attempt-1 remains FAILED / DISCARDED. No Sprint-07 Attempt-1 learning progress is credited, reused, or assumed.

Architect Sprint-13 Specification Review result:

`APPROVE WITH REVISIONS for Sprint-13 roadmap drafting only`

This approval allows drafting the Sprint-13 roadmap. It does not authorize Sprint-13 execution.

## 3. Sprint Objective

Sprint-13 increases Rust-specific learning density inside the existing `devlog_cli` Stage 2 project.

The sprint objective is to improve persistence correctness, reinforce advanced Rust mechanics, and introduce a minimal trait/generic-based storage abstraction without turning the project into a large architecture redesign.

Primary goals:

* deepen `Path`, `PathBuf`, and `AsRef<Path>` understanding;
* strengthen borrowing, ownership, and move-semantics reasoning at storage/workflow boundaries;
* improve persistence correctness after deserialization;
* restore or validate domain invariants after loading persisted data;
* ensure `EntryStore::next_id` remains consistent after loading;
* improve public error mapping with bounded context;
* introduce a deliberately small storage trait/generic boundary;
* preserve the existing Stage 2 `devlog_cli` foundation.

Sprint-13 intentionally increases learning density compared with Sprint-12, but it must remain checkpoint-based and cohesive.

The sprint must not compress all teaching into one large implementation block.

## 4. Stage Alignment

Sprint-13 aligns with Stage 2 — Rust Engineering.

Stage 2 emphasizes:

* larger project organization;
* trait and generic usage in practical contexts;
* dependency management;
* CLI workflows;
* file and data handling;
* integration testing;
* maintainable error design.

Sprint-13 directly supports Stage 2 by using the existing file-backed `devlog_cli` project to practice:

* practical trait boundaries;
* generic workflow boundaries;
* persistence correctness;
* maintainable error mapping;
* source-level Rust mechanics reasoning;
* focused integration-style testing.

This sprint should not advance into Solana, blockchain networking, async Rust, database systems, or broad product-feature expansion.

## 5. Project Continuation Rationale

Sprint-13 should continue `devlog_cli` because the project still contains high-value Stage 2 Rust Engineering learning opportunities.

Sprint-12 established the project foundation:

* `DevLogEntry`;
* `EntryStore`;
* JSON serialization/deserialization;
* file-backed storage;
* public workflow boundary;
* public error boundary;
* thin `main.rs`;
* focused tests.

Sprint-12 intentionally deferred several correctness and Rust-mechanics topics:

* deserialization validation;
* `next_id` consistency after loading;
* richer but bounded error context;
* deeper `Path` / `AsRef<Path>` reasoning;
* trait/generic abstraction for storage testability.

These topics are connected and cohesive. Splitting them into several smaller sprints would risk low-density continuation work and increase cross-sprint information gaps.

The learner has explicitly raised a valid concern that a larger `devlog_cli` project may create handoff risk across sprints. Sprint-13 should address that risk through checkpoint structure, source-review discipline, and clear handoff expectations, not by cutting required Rust Engineering content.

## 6. Scope

In scope:

* continue from the official Sprint-12 `devlog_cli` baseline;
* preserve the existing project foundation;
* improve storage/workflow path API reasoning;
* review and refine `Path`, `PathBuf`, `AsRef<Path>`, borrowing, and move semantics where appropriate;
* validate or restore `DevLogEntry` invariants after deserialization;
* decide whether to use `TryFrom`, validation constructors, or explicit validation methods;
* ensure `EntryStore::next_id` is consistent after loading persisted data;
* improve context-aware error mapping in a bounded way;
* introduce a minimal storage trait boundary;
* implement one concrete file-backed storage type;
* optionally implement one fake or in-memory storage type only if it directly supports trait/generic learning and focused testing;
* adapt one workflow boundary to use a generic storage dependency if justified;
* preserve the crate-root public API facade discipline;
* preserve thin `main.rs`;
* add or update focused tests;
* keep governance repository validation and learning-project validation separate.

## 7. Explicit Non-Goals

Out of scope:

* Solana;
* Anchor;
* blockchain networking;
* blockchain account model;
* real wallet behavior;
* private keys;
* signing;
* RPC;
* async Rust;
* Tokio;
* database;
* production persistence system;
* full CLI framework;
* `clap`;
* large architecture refactor;
* trait-heavy architecture redesign;
* generic-heavy redesign;
* trait object / dynamic dispatch deep dive unless absolutely necessary and explicitly justified;
* broad product-feature expansion;
* broad test expansion;
* exhaustive filesystem edge cases;
* migration system;
* config system;
* adding many new dependencies;
* continuing `wallet_cli`;
* turning `task_tracker` into a teaching project;
* reusing or crediting Sprint-07 Attempt-1.

## 8. Learning Outcomes

By the end of Sprint-13, the learner should be able to explain:

* the difference between `Path`, `PathBuf`, `&Path`, `&str`, and `String`;
* when an API should accept borrowed path-like input through `AsRef<Path>`;
* where ownership should be kept and where borrowing is sufficient;
* how move semantics appear when values cross storage and workflow boundaries;
* why deserialization can bypass normal constructors;
* how invalid persisted JSON can violate domain invariants;
* how `TryFrom`, validation constructors, or explicit validation methods can restore trusted domain state;
* how `Option` can be converted into `Result` when absence becomes a public error;
* how `From` supports public error mapping;
* when manual `map_err` is better than automatic `From` because additional context is needed;
* where error context belongs: domain, store, storage, or workflow layer;
* why `next_id` must be restored or validated after loading persisted data;
* what a trait-as-behavior-boundary means;
* how a generic bound can make workflow code depend on behavior instead of a concrete implementation;
* how a fake or in-memory storage implementation can support focused tests without becoming a second product backend;
* how to keep a minimal abstraction useful without creating a broad framework.

## 9. Required Learner Design Decisions

The learner must make and explain the following decisions during Sprint-13 execution.

### 9.1 Path API Decision

Decide whether existing storage/workflow path signatures should remain as they are or be refined.

The learner should explain:

* where `PathBuf` ownership is needed;
* where `&Path` borrowing is sufficient;
* why `AsRef<Path>` may improve caller ergonomics;
* whether path conversion should happen at the public API boundary, storage boundary, or workflow boundary.

### 9.2 Deserialization Invariant Decision

Decide how `DevLogEntry` invariants should be restored after deserialization.

Acceptable directions:

* `TryFrom` from a raw deserialized representation;
* validation constructors;
* explicit validation methods after deserialization;
* a bounded custom deserialization strategy if justified.

The learner should explain why normal constructors may not run during `serde` deserialization.

### 9.3 `next_id` Consistency Decision

Decide how `EntryStore` should handle `next_id` after loading persisted data.

Acceptable directions:

* validate serialized `next_id`;
* recompute `next_id` from existing entries;
* repair inconsistent `next_id` during load;
* reject inconsistent persisted data.

The learner should explain the tradeoff between strict validation and tolerant restoration.

### 9.4 Error Context Decision

Decide where additional error context should be attached.

Possible layers:

* domain layer;
* store layer;
* storage layer;
* workflow layer.

The learner should explain when `From` is sufficient and when manual context-aware mapping is clearer.

### 9.5 Storage Abstraction Decision

Decide whether a minimal storage trait is justified now.

The learner should explain:

* what behavior the trait should expose;
* what internal details it should hide;
* why the trait should stay deliberately small;
* whether workflow should depend on concrete file storage or a generic storage boundary;
* whether an in-memory/fake implementation is useful for testing or would be unnecessary abstraction.

### 9.6 Public API Decision

Decide which public API changes are justified.

The learner should explain:

* which types/functions should be crate-root public;
* which storage abstractions should remain internal;
* whether the storage trait should be public or crate-internal;
* how public errors should remain maintainable.

## 10. Implementation Artifacts

Sprint-13 should produce four to five connected implementation artifacts.

### 10.1 Path / Borrowing API Cleanup Or Explanation

Review current path-related APIs in storage and workflow code.

Expected work may include:

* preserving existing signatures if they are already appropriate;
* refining signatures to use `impl AsRef<Path>` or generic path parameters;
* reducing unnecessary ownership transfer;
* improving clarity around borrowing and conversion.

This artifact must include source-level explanation even if the final code change is small.

### 10.2 Deserialization Validation / Invariant Restoration

Ensure persisted JSON cannot silently create trusted invalid domain values.

Expected work may include:

* validating loaded entries;
* introducing a raw persisted representation;
* implementing `TryFrom`;
* using validation constructors;
* adding focused invalid persisted-data tests.

This should remain bounded and should not become a migration system.

### 10.3 `EntryStore::next_id` Consistency After Load

Ensure `next_id` is correct after loading persisted data.

Expected behavior should be intentionally chosen and tested.

Possible accepted behavior:

* recompute `next_id` as one greater than the highest existing id;
* reject persisted stores whose `next_id` would collide;
* repair stale `next_id` during load.

The final design must prevent newly added entries from colliding with existing ids.

### 10.4 Context-Aware Public Error Mapping

Improve error mapping where it clarifies persistence or workflow correctness.

Expected work may include:

* adding bounded error context such as entry id or storage operation;
* preserving a stable public `DevLogError` / `DevLogErrorKind` style;
* using `From` where automatic conversion is enough;
* using manual `map_err` where context must be attached.

Avoid production-grade error framework design.

### 10.5 Minimal Storage Trait / Generic Boundary

Introduce a small storage behavior boundary.

Acceptable directions:

* define `EntryStorage`, `DevLogStorage`, or similarly named trait;
* include only behavior needed by the current load/save or add-entry workflow;
* implement one file-backed concrete storage type;
* adapt one workflow to depend on `S: EntryStorage` if educationally useful;
* add one fake or in-memory implementation only if it directly supports focused testing.

Avoid:

* multiple real storage backends;
* trait hierarchies;
* async traits;
* dynamic dispatch unless explicitly justified;
* large framework-style redesign.

## 11. Suggested Module / Boundary Impact

Current Sprint-12 structure may remain mostly intact.

Possible module impact:

* `entry.rs`

  * domain invariants;
  * validation constructor;
  * possible `TryFrom` support;
  * read-only accessors.

* `store.rs`

  * `EntryStore` collection behavior;
  * `next_id` restoration or validation;
  * add/find/list behavior;
  * store-level invariant checks.

* `storage.rs`

  * file-backed load/save implementation;
  * storage trait if kept near persistence boundary;
  * file-backed concrete storage type.

* `workflow.rs`

  * high-level workflow composition;
  * possible generic workflow boundary using `S: EntryStorage`;
  * context-aware error mapping.

* `error.rs`

  * public `DevLogError`;
  * public `DevLogErrorKind`;
  * `From` conversions;
  * bounded contextual constructors or helpers.

* `lib.rs`

  * crate-root public facade;
  * expose only justified public API.

* `main.rs`

  * remain thin;
  * no core business logic.

This structure is a recommendation, not a forced design. The learner may choose a different structure if responsibility boundaries remain clear and scope stays bounded.

## 12. Checkpoint Plan

### Checkpoint 1 — Rust Mechanics Around Path / Borrowing

Teaching focus:

* `Path`;
* `PathBuf`;
* `AsRef<Path>`;
* `&str`;
* `String`;
* ownership;
* borrowing;
* move semantics;
* API parameter design.

Learner work:

* review current storage/workflow path API;
* decide whether API signatures should stay as they are or be refined;
* explain when values are borrowed, owned, moved, or converted;
* make a small source change only if it improves the API or learning value.

Review focus:

* path values are not moved unnecessarily;
* API signatures are ergonomic but not over-generic;
* learner can explain the difference between caller-owned data and borrowed views.

### Checkpoint 2 — Persistence Invariants

Teaching focus:

* deserialization validation;
* `serde` constructor bypass;
* invariant restoration;
* `TryFrom`;
* validation constructors;
* `Option` to `Result`;
* `next_id` consistency.

Learner work:

* ensure invalid persisted data cannot silently become trusted valid domain data;
* handle or validate `next_id` after loading;
* add focused tests for persisted-data correctness.

Review focus:

* invalid persisted entries are rejected or repaired according to a clear rule;
* `next_id` cannot collide after loading;
* validation belongs to the right layer.

### Checkpoint 3 — Context-Aware Error Mapping

Teaching focus:

* public error boundary;
* `From`;
* manual error mapping;
* `map_err`;
* context ownership;
* layer responsibility.

Learner work:

* improve error mapping only where it clarifies persistence or workflow correctness;
* avoid production-grade error framework design;
* preserve maintainable public error shape.

Review focus:

* low-level details do not leak unnecessarily;
* error context is attached at the layer that knows the context;
* public errors remain usable and understandable.

### Checkpoint 4 — Minimal Storage Trait Boundary

Teaching focus:

* trait as behavior boundary;
* generic bound;
* static dispatch;
* testability;
* abstraction boundary.

Learner work:

* design a minimal storage trait;
* implement one file-backed storage type;
* adapt one workflow to use the abstraction if justified;
* optionally add one fake or in-memory storage for a focused test.

Review focus:

* trait is small and behavior-based;
* generic boundary is understandable;
* abstraction reduces coupling or improves testability;
* design does not become trait-heavy or framework-like.

### Checkpoint 5 — Focused Tests, Source Review, And Final Validation

Teaching focus:

* focused integration-style tests;
* public behavior validation;
* source-level explanation;
* validation separation;
* handoff clarity.

Learner work:

* add or update focused tests;
* run local validation;
* explain 2 to 3 IDE/compiler-assisted Rust mechanics fixes;
* request Codex formal validation after meaningful implementation changes.

Review focus:

* tests cover core correctness without dominating the sprint;
* code remains bounded and maintainable;
* source-level explanation proves understanding;
* final validation layers remain separated.

## 13. Testing Requirements

Tests are required, but testing must not dominate Sprint-13.

Preferred final test count:

`5 to 8 focused tests total`

Required test coverage:

* at least one test for invalid persisted data or deserialization validation;
* at least one test for `next_id` consistency after load;
* at least one workflow-level test if workflow behavior changes;
* at least one public error mapping test if error design changes;
* at least one trait/generic/fake-storage test only if the minimal storage abstraction is implemented.

Recommended test examples:

* loading JSON with invalid entry data returns a validation-related public error;
* loading a store with stale `next_id` is repaired or rejected according to the chosen design;
* after loading existing entries, adding a new entry uses a non-colliding id;
* file-backed storage still loads and saves through the intended boundary;
* workflow can use a fake storage implementation when generic storage is introduced.

Avoid:

* exhaustive filesystem edge cases;
* broad CLI output tests;
* testing every private helper;
* snapshot-style output churn;
* complex test framework setup;
* broad product-feature tests.

## 14. Student Validation Requirements

Before requesting formal Codex Repository Validation, the learner should complete Student Validation.

Student Validation should include:

* run `cargo fmt --check`;
* run `cargo check`;
* run `cargo test`;
* review public API surface;
* explain path API decisions;
* explain how deserialization invariants are restored or validated;
* explain how `next_id` consistency is guaranteed after load;
* explain the public error mapping strategy;
* explain whether the storage trait is public or internal and why;
* explain where generic bounds appear and why;
* identify any known non-blocking issues.

Additional Sprint-13 requirement:

The learner must explain 2 to 3 typical RustRover/compiler-assisted fixes encountered during implementation.

For each fix, explain:

* what the original issue was;
* why Rust rejected or warned about it;
* why the final fix is correct.

Relevant topics may include:

* ownership;
* borrowing;
* move semantics;
* `Path` / `AsRef<Path>`;
* generic bounds;
* trait usage;
* error conversion;
* lifetime-related compiler messages if they naturally appear.

Learner-reported command output is useful as local self-check, but it does not replace formal Codex Repository Validation.

## 15. Codex Repository Validation Requirements

Codex Repository Validation is required after meaningful implementation changes during Sprint-13 execution.

Codex validation target for the learning project:

`/Users/dumplings/workspace/devlog_cli`

Codex should verify:

* project builds successfully;
* `cargo fmt --check` passes;
* `cargo check` passes;
* `cargo test` passes;
* implementation continues from the official Sprint-12 `devlog_cli` baseline;
* scope matches Sprint-13 roadmap;
* path API usage is coherent and not over-engineered;
* deserialization validation or invariant restoration is implemented;
* `EntryStore::next_id` consistency after load is handled;
* public error mapping is improved only in bounded, justified ways;
* storage trait/generic boundary is minimal if implemented;
* one file-backed implementation exists if storage abstraction is introduced;
* fake/in-memory storage exists only if directly justified by focused testing;
* `main.rs` remains thin;
* public API facade remains coherent;
* tests are focused and not excessive;
* no Solana, Anchor, blockchain networking, wallet behavior, signing, RPC, async Rust, Tokio, database, production persistence system, full CLI framework, broad product expansion, or large architecture redesign was introduced;
* no Sprint-07 Attempt-1 work was reused or credited;
* `wallet_cli` was not continued by default;
* `task_tracker` was not turned into the next teaching project.

If the governance repository is later updated with `roadmaps/sprint-13.md`, validate separately:

`/Users/dumplings/workspace/rust-blockchain-career`

Codex must not combine governance repository validation and learning-project validation unless the learner explicitly requests a cross-repository audit.

## 16. Teacher Learning Validation Requirements

Teacher Learning Validation is required before Sprint-13 can be closed.

The Teacher should evaluate whether the learner can explain:

* why Sprint-13 continued `devlog_cli`;
* why the sprint increased Rust mechanics density instead of adding broad product features;
* how `Path`, `PathBuf`, `AsRef<Path>`, `&str`, and `String` differ in this project;
* where values are borrowed, owned, moved, or converted;
* how deserialization can bypass constructors;
* how persisted-data validation or restoration works;
* how `next_id` consistency is guaranteed after loading;
* when `Option` should become `Result`;
* how `From` supports public error mapping;
* when manual error mapping is needed for context;
* why the storage trait is minimal;
* how the generic storage boundary works;
* whether static dispatch is being used and why that is acceptable here;
* how the fake/in-memory storage supports testing if one was added;
* why tests are sufficient but not excessive;
* which public API changes are justified;
* what was intentionally deferred.

Teacher Learning Validation must include source-level review and learner explanation.

Codex PASS does not automatically imply Teacher Learning Validation PASS.

## 17. Completion Criteria

Sprint-13 can be completed only when all of the following are true:

* Sprint-13 execution was explicitly authorized by the learner before implementation began;
* implementation continued from the official Sprint-12 `devlog_cli` baseline;
* no `wallet_cli` continuation occurred by default;
* `task_tracker` was not converted into a teaching project;
* no Sprint-07 Attempt-1 progress or implementation was credited;
* project remained inside Stage 2 Rust Engineering scope;
* path/borrowing/API reasoning was reviewed and explained;
* deserialization validation or invariant restoration was implemented;
* `EntryStore::next_id` consistency after loading was handled;
* public error mapping was improved only in bounded, justified ways;
* minimal storage trait/generic boundary was introduced if still justified after design review;
* if storage abstraction was introduced, one file-backed implementation exists;
* fake/in-memory storage was added only if it directly supported learning or focused tests;
* `main.rs` remained thin;
* public API facade remained coherent;
* 5 to 8 focused tests exist or an equivalent focused test count is explicitly justified;
* Student Validation is PASS;
* Codex Repository Validation is PASS or has only explicitly accepted non-blocking concerns;
* Teacher Learning Validation is PASS;
* governance repository and learning-project validation remained separate;
* explicit non-goals were respected.

## 18. Teaching Notes

During Sprint-13 execution, technical teaching language must be primarily Chinese.

Important professional terms should be introduced in the form:

`English professional term (Chinese professional translation)`

Examples for Sprint-13:

* ownership (所有权);
* borrowing (借用);
* move semantics (移动语义);
* API parameter design (API 参数设计);
* `Path` / `PathBuf` (路径视图 / 路径缓冲区);
* trait (特征);
* generic bound (泛型约束);
* static dispatch (静态分发);
* persistence correctness (持久化正确性);
* deserialization validation (反序列化校验);
* invariant restoration (不变量恢复);
* public error boundary (公共错误边界);
* context-aware error mapping (带上下文的错误映射);
* integration test (集成测试).

Teaching should use structured instruction, not guided guessing.

The Teacher should teach the concept, mental model, implementation boundary, common mistakes, and acceptance criteria before asking the learner to implement.

Sprint-13 must proceed checkpoint by checkpoint.

The Teacher must not compress all implementation tasks into one large block.

The learner remains the primary developer.

Teacher direct source review should be used for:

* Rust mental model explanation;
* ownership and borrowing reasoning;
* trait/generic reasoning;
* error-boundary design discussion;
* source-level teaching;
* checkpoint feedback;
* blocking versus non-blocking distinction.

Codex formal validation should be used for:

* full project-root inspection;
* `cargo fmt --check`;
* `cargo check`;
* `cargo test`;
* scope compliance;
* final validation report.

## 19. Repository Validation Separation

Governance repository:

`/Users/dumplings/workspace/rust-blockchain-career`

Learning-project repository:

`/Users/dumplings/workspace/devlog_cli`

These repositories must be validated separately.

If `roadmaps/sprint-13.md` is later added to the governance repository, that is a governance repository update and should be validated against the governance repository root.

If `devlog_cli` is modified during Sprint-13 execution, that is a learning-project update and should be validated against the learning-project root.

Codex should validate one repository or project root at a time.

Do not combine governance validation and learning-project validation into one prompt unless the learner explicitly requests a cross-repository audit.

## 20. Authorization Statement

This document is a Sprint-13 roadmap draft only.

Sprint-13 roadmap drafting does not authorize Sprint-13 execution.

Sprint-13 execution requires explicit learner approval after roadmap review.

This roadmap does not authorize:

* modifying `devlog_cli`;
* assigning implementation tasks;
* creating implementation code;
* modifying governance repository files;
* asking Codex to update files;
* asking Codex to validate implementation before implementation exists;
* starting Sprint-13 execution;
* continuing `wallet_cli`;
* turning `task_tracker` into a teaching project;
* reusing or crediting Sprint-07 Attempt-1.

The next allowed step is learner review of this roadmap draft.

Only after explicit learner approval should the Teacher prepare a Codex repository-update prompt to save this roadmap or begin Sprint-13 execution planning.
