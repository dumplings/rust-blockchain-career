# Sprint-15 Roadmap

## 1. Sprint Identity

* Sprint number: Sprint-15
* Sprint name: `Stage 2 Midpoint Assessment — Rust Engineering Integration`
* Stage: Stage 2 - Rust Engineering
* Recommended learning project: `rust_engineering_assessment`
* Recommended internal theme: `record_store`
* Recommended learning-project root: `/Users/dumplings/workspace/rust_engineering_assessment`
* Governance repository root: `/Users/dumplings/workspace/rust-blockchain-career`
* Roadmap target file: `roadmaps/archive/sprint-15.md`
* Sprint status: Draft only
* Execution status: Not started
* Authorization status: Not authorized for execution

Sprint-15 is a Stage 2 midpoint assessment.

Sprint-15 is an assessment-style Rust Engineering integration sprint.

Sprint-15 is not a normal guided implementation sprint.

Sprint-15 is not a product application sprint.

Sprint-15 is not a CLI sprint.

Sprint-15 is not a blockchain sprint.

This roadmap draft does not authorize Sprint-15 execution.

Sprint-15 execution requires explicit learner approval after roadmap review.

Creating `/Users/dumplings/workspace/rust_engineering_assessment` is not authorized by roadmap save alone.

Codex save/update of this roadmap does not authorize implementation.

## 2. Governance Context

Stage 1 - Rust Foundations is PASS / CLOSED.

The current active stage is:

`Stage 2 - Rust Engineering`

Sprint-12 is PASS / CLOSED and counts as completed Stage 2 Rust Engineering learning progress.

Sprint-13 is PASS / CLOSED and counts as completed Stage 2 Rust Engineering learning progress.

Sprint-14 is PASS / CLOSED and counts as completed Stage 2 Rust Engineering learning progress.

The current active sprint is:

`None`

Sprint-15 is not active.

Sprint-15 execution is not authorized.

No Sprint-15 learning project exists or should be created yet.

`devlog_cli` remains a completed Stage 2 learning project foundation from Sprint-12 and Sprint-13, but Sprint-15 should not continue it by default.

`rust_mechanics_lab` was completed in Sprint-14 as a focused Rust mechanics consolidation lab. Sprint-15 should not continue it by default.

`wallet_cli` should not be continued by default.

`task_tracker` should not become the next teaching project.

Sprint-07 Attempt-1 remains FAILED / DISCARDED. No Sprint-07 Attempt-1 learning progress is credited, reused, or assumed.

Architect Sprint-15 Specification Review result:

`APPROVE WITH REVISIONS for Sprint-15 roadmap drafting`

This approval allows drafting and saving the Sprint-15 roadmap. It does not authorize Sprint-15 execution.

## 3. Sprint Objective

Sprint-15 evaluates whether the learner can integrate Stage 2 Rust Engineering capabilities learned across Sprint-12, Sprint-13, and Sprint-14 into a fresh small Rust project.

Sprint-15 is not primarily for introducing many new concepts.

The assessment objective is to determine whether the learner can transfer existing capabilities into a new bounded Rust engineering context with reasonable independence.

The learner should demonstrate practical capability in:

* domain modeling;
* constructor and invariant design;
* private fields and accessors where appropriate;
* ownership and borrowing;
* function parameter choices using `T`, `&T`, and `&mut T`;
* public API facade design;
* public error boundary design;
* `From` / `map_err`;
* serde / JSON boundary;
* deserialization validation;
* file IO / storage boundary;
* trait / generic design tradeoff reasoning;
* focused tests;
* source-level tradeoff reasoning.

Sprint-15 should assess integration, judgment, and explanation quality rather than only whether the code compiles.

Passing tests or Codex Repository Validation must not automatically equal Teacher Learning Validation.

Teacher Learning Validation must include source-level reasoning and tradeoff explanation.

## 4. Stage Alignment

Sprint-15 aligns with Stage 2 - Rust Engineering.

Stage 2 emphasizes:

* larger project organization;
* trait and generic usage;
* dependency management;
* CLI workflows;
* file and data handling;
* integration testing;
* maintainable error design.

Sprint-15 supports Stage 2 by assessing whether the learner can combine:

* dependency management through `serde` and `serde_json`;
* file and data handling through JSON and bounded persistence;
* maintainable error design through public error boundaries and internal error mapping;
* integration testing through focused behavior tests;
* ownership and borrowing decisions at API and workflow boundaries;
* trait/generic judgment without forcing abstraction for its own sake.

Sprint-15 should remain a small Stage 2 midpoint assessment.

It must not become a large product expansion, blockchain sprint, or broad architecture project.

## 5. Project Choice And Rationale

The recommended project is:

`rust_engineering_assessment`

The recommended project root is:

`/Users/dumplings/workspace/rust_engineering_assessment`

The recommended internal theme is:

`record_store`

Rationale:

Sprint-12 introduced a Stage 2 project foundation through `devlog_cli`, including dependency management, `serde`, `serde_json`, JSON serialization/deserialization, file IO boundary, storage boundary, workflow boundary, public API facade, and maintainable error boundary.

Sprint-13 extended Stage 2 engineering work through `Path` / `PathBuf` / `AsRef<Path>`, persistence correctness, deserialization validation, `next_id` restoration, context-aware error mapping, minimal storage trait boundary, generic workflow boundary, and fake-storage testability.

Sprint-14 consolidated Rust mechanics through value/reference reasoning, ownership transfer, shared borrowing, mutable borrowing, trait as behavior contract, `impl Trait for Type`, concrete function versus generic trait-bound function, generic ownership / borrowing / mutable borrowing, and `RefCell<T>` in a fake recorder scenario.

Sprint-15 should not continue `devlog_cli` by default because the assessment should test transfer into a fresh project rather than momentum inside a familiar codebase.

Sprint-15 should not continue `rust_mechanics_lab` because that project already served its role as a focused mechanics consolidation lab.

A fresh small `record_store`-style project gives enough surface area to assess Stage 2 integration without becoming a product application.

Possible conceptual behavior:

* create a `Record`;
* validate record invariants;
* store records in a `RecordStore`;
* add, list, and update records;
* persist records through JSON;
* validate or restore data after deserialization;
* use a small storage trait only if justified by the design;
* provide one file-backed implementation if a storage trait is used;
* optionally provide one fake or in-memory implementation only if it supports focused assessment;
* expose a coherent crate-root public API;
* provide focused tests.

The exact domain names may be adjusted by the Teacher or learner during authorized execution, but the project must remain small, assessment-focused, and Stage 2 aligned.

## 6. Scope

In scope, only after Sprint-15 execution is explicitly authorized:

* create a fresh Cargo library crate named `rust_engineering_assessment`;
* use a small `record_store`-style domain or equivalent bounded assessment domain;
* define one small domain type such as `Record`;
* implement constructor validation and private fields where valid-state protection is useful;
* define one store type such as `RecordStore`;
* implement deterministic id handling;
* decide whether invalid persisted data should be rejected or repaired;
* implement JSON serialization/deserialization with `serde` and `serde_json`;
* implement deserialization validation or invariant restoration before persisted data is trusted;
* implement a bounded file-backed load/save or equivalent persistence boundary;
* keep JSON string conversion separate from file IO where appropriate;
* design a public error type and error kind;
* use `From` where automatic error conversion is enough;
* use `map_err` where context should be attached;
* define a crate-root public API facade;
* make ownership and borrowing decisions using `T`, `&T`, and `&mut T`;
* decide whether a small storage trait is justified;
* if justified, define a small behavior-based trait and use a generic boundary;
* if not justified, explicitly explain why concrete design is sufficient;
* add 6 to 9 focused tests;
* complete Student Validation, Codex Repository Validation, and Teacher Learning Validation.

Sprint-15 should preserve assessment style.

The Teacher may explain task goals, clarify acceptance criteria, answer questions, and review source-level design.

The Teacher may teach or re-teach concepts when the learner is blocked.

The Teacher should not provide a near-final implementation up front.

The Teacher should not over-decompose the full solution into copyable implementation steps.

The learner should make meaningful design decisions.

## 7. Explicit Non-Goals

Out of scope:

* starting Sprint-15 from roadmap save alone;
* creating `/Users/dumplings/workspace/rust_engineering_assessment` before explicit learner authorization;
* modifying any learning-project repository during roadmap save;
* writing implementation code during roadmap save;
* turning Sprint-15 into a normal guided implementation sprint;
* turning Sprint-15 into a product application sprint;
* turning Sprint-15 into a CLI sprint;
* turning Sprint-15 into a blockchain sprint;
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
* full CLI framework;
* `clap`;
* production persistence system;
* broad architecture refactor;
* large trait framework;
* generic-heavy redesign;
* forcing trait/generic abstraction merely for the sake of abstraction;
* deep lifetime topic;
* `Rc<RefCell<T>>`;
* threading;
* `Arc<Mutex<T>>`;
* broad test expansion as filler;
* snapshot-style output testing;
* broad CLI tests;
* exhaustive filesystem edge cases;
* panic-heavy tests;
* continuing `devlog_cli` by default;
* continuing `rust_mechanics_lab`;
* continuing `wallet_cli`;
* turning `task_tracker` into a teaching project;
* reusing or crediting Sprint-07 Attempt-1.

## 8. Expected Learning Outcomes

By the end of Sprint-15, the learner should be able to demonstrate and explain:

* how to organize a fresh small Rust library project with clear module boundaries;
* how domain invariants are represented and protected;
* why some fields should be private;
* when constructors should validate data;
* how deserialized data becomes trusted again;
* when invalid persisted data should be rejected;
* when invalid persisted data may be repaired;
* where JSON string conversion belongs;
* where file IO belongs;
* why workflow logic should not be tightly coupled to file IO when a separation is useful;
* how to use `serde` and `serde_json` at a bounded JSON boundary;
* how to design a maintainable public error boundary;
* how to hide unnecessary internal error details from external callers;
* when `From` is enough for error conversion;
* when `map_err` with context is clearer than automatic `From`;
* which functions take ownership through `T`;
* which functions borrow through `&T`;
* which functions mutate through `&mut T`;
* when cloning is justified and what cost it implies;
* how a crate-root public API facade shapes external usage;
* when a trait/generic boundary is justified;
* when a concrete design is clearer than a trait/generic abstraction;
* how tests should validate behavior without testing every private helper;
* which ownership behaviors are compile-time concepts rather than runtime tests;
* how to classify blocking versus non-blocking issues;
* how implementation success differs from capability validation.

## 9. Required Learner Design Decisions

The learner must make and explain the following decisions during Sprint-15 execution.

### 9.1 Domain Invariant Decision

The learner should explain:

* which states are invalid;
* what the constructor guarantees;
* which fields should be private;
* what external callers are allowed to construct directly;
* how deserialized data becomes trusted again;
* whether invalid persisted data should be rejected or repaired;
* how tests prove the chosen invariant boundary.

### 9.2 Ownership / Borrowing Decision

The learner should explain:

* which functions take `T`;
* which functions take `&T`;
* which functions take `&mut T`;
* when ownership transfer occurs;
* when shared borrowing is enough;
* when mutable borrowing is required;
* when cloning is justified;
* whether the caller can continue using a value after each important function call.

### 9.3 Error Boundary Decision

The learner should explain:

* which errors are domain errors;
* which errors are storage, JSON, or IO errors;
* what the public error type exposes;
* which internal details remain hidden;
* when `From` is enough;
* when `map_err` with context is clearer;
* how user-facing or caller-facing error information remains useful without leaking unnecessary implementation detail.

### 9.4 Storage Boundary Decision

The learner should explain:

* where JSON string conversion belongs;
* where file IO belongs;
* whether load/save should be separated from workflow logic;
* how `Path`, `PathBuf`, or `AsRef<Path>` should be used if file-backed APIs are present;
* how the design avoids trusting external persisted data too early;
* what the storage boundary should not be responsible for.

### 9.5 Trait / Generic Decision

Sprint-15 must not force trait/generic abstraction merely for the sake of abstraction.

The learner must choose and justify one of two valid paths:

* implement a small, behavior-based, justified trait/generic boundary; or
* explicitly explain why adding a trait/generic boundary would be unnecessary or over-engineered for the chosen design.

If the learner implements a trait/generic boundary, the learner should explain:

* what behavior the trait expresses;
* why the trait is small;
* which concrete type implements it;
* why a generic function depends on a trait instead of one concrete type;
* whether a fake implementation improves assessment value;
* whether the generic API takes ownership, borrows immutably, or borrows mutably.

If the learner does not implement a trait/generic boundary, the learner must still explain:

* why the concrete design is sufficient;
* what abstraction would have been possible;
* why that abstraction would not improve clarity, testability, or maintainability;
* why omission is intentional and not accidental.

The trait/generic assessment gate is satisfied by justified design judgment, not by mandatory abstraction.

### 9.6 Testing Decision

The learner should explain:

* which behaviors must be tested;
* which private helpers should not be tested directly;
* which ownership behaviors are compile-time concepts rather than runtime tests;
* why the final test count is enough;
* why the final test count is not excessive;
* which known risks remain untested and why they are acceptable for this assessment.

## 10. Implementation Artifacts

Sprint-15 should produce a small set of connected implementation artifacts only after execution is explicitly authorized.

### 10.1 Domain Model

Expected work:

* define one small domain type such as `Record`;
* protect invariants with constructors and private fields where useful;
* provide accessors only for data that external callers should read;
* avoid over-modeling the domain.

The domain model should make valid and invalid states visible enough for assessment.

### 10.2 Store / Workflow Boundary

Expected work:

* define one store type such as `RecordStore`;
* support a small behavior set such as add, list, and update;
* maintain deterministic id handling;
* separate domain validation from workflow/store coordination where practical;
* avoid building a product-grade storage engine.

The store/workflow boundary should be large enough to assess ownership, borrowing, error propagation, and tests.

### 10.3 JSON / Persistence Boundary

Expected work:

* serialize and deserialize through `serde` and `serde_json`;
* treat persisted JSON as untrusted input;
* validate or restore invariants after deserialization;
* keep JSON conversion separate from file IO where appropriate;
* implement bounded file-backed load/save or an equivalent persistence boundary;
* avoid exhaustive filesystem behavior.

This artifact should assess serde / JSON boundary, deserialization validation, and file IO / storage boundary reasoning.

### 10.4 Error Boundary

Expected work:

* define a public error type and error kind;
* map internal domain, JSON, and IO errors into the public boundary;
* use `From` where automatic conversion is enough;
* use `map_err` where context should be attached;
* keep lower-level implementation details hidden unless exposure is justified.

The error boundary should be maintainable rather than maximally detailed.

### 10.5 Trait / Generic Boundary Or Explicit Omission

Expected work:

* either define a small behavior-based trait and one generic usage if it clearly improves the design;
* or keep the design concrete and provide explicit tradeoff reasoning for not adding a trait/generic boundary.

If used, the trait/generic boundary should support assessment of behavior dependency and testability.

If omitted, the omission must be intentional and explained.

### 10.6 Focused Tests

Expected work:

* write 6 to 9 focused tests;
* include tests for domain invariants;
* include tests for store/workflow behavior;
* include tests for persistence or deserialization validation;
* include tests for error mapping where meaningful;
* include tests for trait/generic behavior if a trait/generic boundary is implemented;
* avoid testing every private helper.

Tests should support the assessment and not dominate it.

## 11. Suggested Module / Boundary Structure

Suggested structure:

* `src/lib.rs`
* `src/record.rs`
* `src/store.rs`
* `src/error.rs`
* `src/storage.rs`
* `src/workflow.rs`, optional if the project needs a workflow boundary
* `tests/domain_test.rs`
* `tests/store_test.rs`
* `tests/persistence_test.rs`
* `tests/public_api_test.rs`, optional if public API validation needs a separate file

Suggested responsibilities:

* `record.rs`: domain type, validation, private fields, accessors;
* `store.rs`: in-memory store behavior, deterministic ids, add/list/update behavior;
* `error.rs`: public error type, public error kind, internal error mapping;
* `storage.rs`: JSON conversion, file-backed load/save, optional trait boundary if justified;
* `workflow.rs`: optional orchestration layer if separating workflow improves clarity;
* `lib.rs`: crate-root public facade;
* `tests/*`: focused integration-style tests against public or intentionally exposed APIs.

This structure is a recommendation, not a forced design.

The learner may choose different names if the responsibility boundaries remain clear and the project stays small.

The learner should avoid adding modules only to make the project look larger.

## 12. Checkpoint Plan

Sprint-15 should proceed through assessment phases rather than one large implementation block.

The Teacher may adjust checkpoint granularity during execution, but must preserve assessment style and avoid providing near-final implementation up front.

### Checkpoint 1 - Assessment Brief And Design Plan

Focus:

* confirm project boundary;
* confirm non-goals;
* identify domain invariants;
* identify public API shape;
* identify storage and error boundary approach;
* decide whether a trait/generic boundary appears likely to be justified.

Learner work:

* propose a small module plan;
* propose core types and responsibilities;
* identify expected tests;
* explain the first-pass trait/generic decision.

Validation focus:

* learner can reason about scope before coding;
* plan stays inside Stage 2 assessment boundaries;
* no learning project is created until execution is explicitly authorized.

### Checkpoint 2 - Domain Model And Store Core

Focus:

* domain invariants;
* constructor validation;
* private fields and accessors;
* ownership and borrowing in store operations;
* deterministic id handling.

Learner work:

* implement the domain type;
* implement the core store behavior;
* add focused tests for domain/store behavior.

Validation focus:

* learner can explain invalid states;
* learner can explain `T`, `&T`, and `&mut T` decisions;
* learner can explain where ownership transfer occurs.

### Checkpoint 3 - Error Boundary And JSON Boundary

Focus:

* public error type;
* public error kind;
* internal error mapping;
* `From` / `map_err`;
* serde / JSON boundary;
* deserialization validation.

Learner work:

* implement public error boundary;
* implement JSON serialization/deserialization;
* validate or restore data after deserialization;
* add focused tests for invalid data and error behavior.

Validation focus:

* learner can explain when `From` is enough;
* learner can explain when `map_err` is clearer;
* learner can explain why external JSON is untrusted;
* learner can explain how deserialized data becomes trusted again.

### Checkpoint 4 - File IO / Storage Boundary And Trait/Generic Decision

Focus:

* file IO / storage boundary;
* separation of JSON conversion and file IO;
* `Path`, `PathBuf`, or `AsRef<Path>` when applicable;
* trait/generic design judgment.

Learner work:

* implement bounded file-backed load/save or equivalent storage boundary;
* decide whether to add a small storage trait/generic boundary;
* if used, implement the trait/generic boundary and any focused fake/in-memory implementation;
* if omitted, write or explain the explicit tradeoff rationale;
* add focused tests for persistence and trait/generic behavior if used.

Validation focus:

* learner can explain storage responsibilities;
* learner can explain whether abstraction improves clarity, testability, or maintainability;
* learner can explain why omission of a trait/generic boundary is intentional if omitted.

### Checkpoint 5 - Final Review, Student Validation, And Codex Validation Prompt

Focus:

* source-level reasoning;
* test review;
* public API review;
* validation separation;
* formal Codex Repository Validation preparation.

Learner work:

* run Student Validation;
* identify known non-blocking issues;
* answer source-level design questions;
* request Codex Repository Validation only after meaningful implementation is complete.

Validation focus:

* learner can explain the design without relying only on passing tests;
* Student Validation is complete before Codex validation;
* governance repository validation and learning-project validation remain separate.

### Checkpoint 6 - Teacher Learning Validation And Sprint Closure Decision

Focus:

* final capability judgment;
* explanation quality;
* blocking versus non-blocking issue classification;
* whether Sprint-15 counts as completed learning progress.

Learner work:

* answer final Teacher validation questions;
* explain source-level tradeoffs;
* explain remaining limitations;
* respond to any Codex validation findings.

Validation focus:

* Teacher Learning Validation is based on understanding and reasoning;
* Codex PASS does not automatically imply Teacher Learning Validation PASS;
* implementation completion is not treated as concept mastery.

## 13. Testing Requirements

Tests are required, but testing must not dominate Sprint-15.

Preferred final test count:

`6 to 9 focused tests`

Required test coverage:

* at least one test for domain invariant validation;
* at least one test for successful store/workflow behavior;
* at least one test for update or mutation behavior if update is implemented;
* at least one test for JSON serialization/deserialization behavior;
* at least one test for invalid persisted data or deserialization validation;
* at least one test for public error mapping where meaningful;
* at least one test for file-backed load/save or equivalent persistence boundary;
* at least one test for trait/generic behavior if a trait/generic boundary is implemented.

The final test set should validate:

* domain invariants;
* workflow behavior;
* persistence behavior;
* error mapping;
* trait/generic boundary if used.

Avoid:

* broad test expansion;
* testing every private helper;
* snapshot-style output tests;
* broad CLI tests;
* exhaustive filesystem edge cases;
* panic-heavy tests;
* using tests as filler.

Some ownership and borrowing behavior is compile-time behavior. The learner should explain those decisions at source level rather than forcing awkward runtime tests.

If the final test count is outside the preferred 6 to 9 range, the Teacher must require a brief justification.

## 14. Student Validation Requirements

Before requesting formal Codex Repository Validation, the learner must complete Student Validation.

Student Validation should include:

* run `cargo fmt --check`;
* run `cargo check`;
* run `cargo test`;
* review the public API surface;
* review module boundaries;
* review whether tests are focused and sufficient;
* identify known blocking issues, if any;
* identify known non-blocking issues, if any;
* explain domain invariants and constructor guarantees;
* explain how deserialized data becomes trusted again;
* explain ownership and borrowing decisions;
* explain where ownership transfer occurs;
* explain where shared borrowing is used;
* explain where mutable borrowing is used;
* explain when cloning is justified;
* explain public API facade decisions;
* explain public error boundary decisions;
* explain `From` / `map_err` usage;
* explain serde / JSON boundary decisions;
* explain file IO / storage boundary decisions;
* explain trait/generic boundary if used;
* if trait/generic boundary is omitted, explain why omission is intentional and not accidental;
* explain why the selected tests are sufficient for this assessment.

For each major compiler or IDE-assisted correction, if any occurred, the learner should explain:

* what the original issue was;
* why Rust rejected or warned about it;
* why the final fix is correct.

Learner-reported command output is useful as local self-check, but it does not replace formal Codex Repository Validation.

## 15. Codex Repository Validation Requirements

Codex Repository Validation is required after meaningful implementation changes during Sprint-15 execution.

Codex validation target for the learning project:

`/Users/dumplings/workspace/rust_engineering_assessment`

Codex should verify:

* `cargo fmt --check` passes;
* `cargo check` passes;
* `cargo test` passes;
* final test count is within the preferred 6 to 9 focused tests range or the deviation is justified;
* implementation matches Sprint-15 roadmap scope;
* project remains a small Stage 2 Rust Engineering assessment;
* project is not a normal guided implementation artifact copied from near-final Teacher code;
* project does not become a product application;
* project does not become a CLI;
* project does not become a blockchain project;
* module boundaries are understandable;
* crate-root public API facade is coherent;
* domain invariants are represented;
* constructors or validation boundaries are meaningful;
* deserialized data is validated or restored before being trusted;
* serde / JSON boundary is present and bounded;
* file IO / storage boundary is present and bounded;
* public error boundary is coherent;
* `From` / `map_err` usage is reasonable for the selected design;
* ownership and borrowing decisions are visible in API signatures;
* trait/generic implementation is present only if justified by the design;
* if trait/generic implementation is omitted, the project does not contain forced abstraction just for assessment optics;
* tests are focused and not excessive;
* no out-of-scope systems or dependencies were introduced;
* no Solana, Anchor, blockchain networking, wallet behavior, signing, RPC, async Rust, Tokio, database, full CLI framework, `clap`, large architecture framework, or production persistence system was introduced;
* `devlog_cli` was not continued by default;
* `rust_mechanics_lab` was not continued;
* `wallet_cli` was not continued;
* `task_tracker` was not converted into a teaching project;
* no Sprint-07 Attempt-1 work was reused or credited.

If the governance repository is updated with `roadmaps/archive/sprint-15.md`, validate separately:

`/Users/dumplings/workspace/rust-blockchain-career`

Codex must not combine governance repository validation and learning-project validation unless the learner explicitly requests a cross-repository audit.

Codex Repository Validation verifies repository state, scope compliance, command results, and implementation alignment. It does not replace Teacher Learning Validation.

## 16. Teacher Learning Validation Requirements

Teacher Learning Validation is required before Sprint-15 can be closed.

Teacher Learning Validation must include explicit assessment-style learning validation.

The Teacher should evaluate whether the learner can explain:

* project module structure;
* crate-root public API facade;
* domain invariants;
* constructor and private-field decisions;
* deserialization validation or invariant restoration;
* ownership and borrowing choices;
* `T`, `&T`, and `&mut T` decisions;
* clone decisions, if any;
* public API and error boundaries;
* `From` and `map_err` decisions;
* storage and serialization boundaries;
* JSON conversion versus file IO separation;
* trait/generic choices if used;
* trait/generic omission rationale if omitted;
* test design and coverage boundaries;
* blocking versus non-blocking issue classification;
* remaining limitations and why they are acceptable or not acceptable.

Teacher Learning Validation must include:

* source-level reasoning questions;
* design tradeoff questions;
* explanation of domain invariants;
* explanation of ownership and borrowing choices;
* explanation of public API and error boundaries;
* explanation of storage and serialization boundaries;
* explanation of trait/generic choices or trait/generic omission;
* blocking versus non-blocking issue classification;
* final capability judgment.

Required validation question categories:

* at least 2 source-level reasoning questions;
* at least 2 design tradeoff questions;
* at least 1 question about domain invariants and deserialization validation;
* at least 1 question about ownership and borrowing;
* at least 1 question about `From` / `map_err`;
* at least 1 question about serde / JSON boundary and file IO / storage boundary;
* at least 1 question about trait/generic design judgment.

The trait/generic design judgment question must allow both valid paths:

* justified trait/generic implementation; or
* justified concrete design without trait/generic abstraction.

Codex PASS does not automatically imply Teacher Learning Validation PASS.

Passing tests does not automatically imply Teacher Learning Validation PASS.

Implementation completion must not be treated as concept mastery.

If the learner cannot explain a major implemented design choice, the Teacher should treat that as a learning-validation risk even if the code passes.

## 17. Completion Criteria

Sprint-15 can be completed only when all of the following are true:

* Sprint-15 execution was explicitly authorized by the learner before implementation began;
* the fresh `rust_engineering_assessment` learning project exists only as an authorized Stage 2 Rust Engineering assessment project;
* no learning-project repository was modified before authorization;
* project remained inside Stage 2 Rust Engineering scope;
* project remained an assessment-style project;
* project did not become a product application;
* project did not become a CLI;
* project did not become a blockchain project;
* `devlog_cli` was not continued by default;
* `rust_mechanics_lab` was not continued;
* `wallet_cli` was not continued;
* `task_tracker` was not converted into a teaching project;
* no Sprint-07 Attempt-1 progress or implementation was credited;
* domain model and invariants were implemented;
* constructor validation or equivalent valid-state protection was implemented where appropriate;
* store/workflow behavior was implemented;
* JSON serialization/deserialization was implemented;
* deserialization validation or invariant restoration was implemented;
* file IO / storage boundary was implemented in bounded scope;
* public API facade is coherent;
* public error boundary is coherent;
* `From` / `map_err` usage is intentional;
* ownership and borrowing choices are intentional;
* trait/generic assessment gate is satisfied through either justified implementation or justified intentional omission;
* tests are focused and tied to the assessment contract;
* preferred test count of 6 to 9 focused tests is met or any deviation is explicitly justified;
* Student Validation is PASS;
* Codex Repository Validation is PASS or has only explicitly accepted non-blocking concerns;
* Teacher Learning Validation is PASS;
* learner can explain the core design and source-level tradeoffs without relying only on code completion;
* governance repository and learning-project validation remained separate;
* explicit non-goals were respected.

Sprint-15 must not be recorded as PASS if:

* execution was not explicitly authorized;
* the learner cannot explain major source-level design decisions;
* the project violates explicit non-goals;
* the trait/generic assessment gate is treated as mandatory abstraction rather than justified design judgment;
* Codex validation and Teacher Learning Validation are collapsed into one decision.

## 18. Teaching Notes

During Sprint-15 execution, technical teaching language must be primarily Chinese.

Repository-ready roadmap, validation, and closure documents should remain English by default.

Important professional terms should be introduced in the form:

`English professional term (Chinese professional translation)`

Examples for Sprint-15:

* domain invariant (领域不变量);
* constructor validation (构造函数校验);
* deserialization validation (反序列化校验);
* public API facade (公共 API 门面);
* error boundary (错误边界);
* error mapping (错误映射);
* `From` conversion (`From` 转换);
* `map_err` context mapping (`map_err` 上下文映射);
* serialization (序列化);
* deserialization (反序列化);
* JSON boundary (JSON 边界);
* file IO boundary (文件 IO 边界);
* storage boundary (存储边界);
* ownership (所有权);
* borrowing (借用);
* mutable borrowing (可变借用);
* trait (特征);
* generic bound (泛型约束);
* over-engineering (过度工程化);
* source-level reasoning (源码级推理);
* tradeoff (权衡).

Sprint-15 should use structured assessment guidance, not guided guessing.

The Teacher should clarify:

* assessment goal;
* implementation boundary;
* non-goals;
* acceptance criteria;
* validation layers.

The Teacher must not provide a near-final implementation up front.

The Teacher must not over-decompose the full solution into copyable implementation steps.

The Teacher may provide limited examples or reminders when the learner is blocked, but examples should support understanding rather than replace learner design judgment.

The learner remains the primary implementer.

The Teacher should avoid tautological validation questions that ask the learner to justify Teacher-dictated design choices.

Validation questions should focus on:

* contrast;
* consequence;
* source-level reasoning;
* error diagnosis;
* tradeoff explanation.

Sprint-15 must not compress all teaching or assessment into one large implementation block.

## 19. Repository Validation Separation

Governance repository:

`/Users/dumplings/workspace/rust-blockchain-career`

Learning-project repository, only if later authorized:

`/Users/dumplings/workspace/rust_engineering_assessment`

These repositories must be validated separately.

Saving this roadmap is a governance repository update.

Creating or modifying the learning project is not authorized by saving this roadmap.

If `roadmaps/archive/sprint-15.md` is updated in the governance repository, validation should target:

`/Users/dumplings/workspace/rust-blockchain-career`

If Sprint-15 execution is later authorized and `/Users/dumplings/workspace/rust_engineering_assessment` is created or modified, validation should target:

`/Users/dumplings/workspace/rust_engineering_assessment`

Codex should validate one repository or project root at a time.

Do not combine governance validation and learning-project validation into one prompt unless the learner explicitly requests a cross-repository audit.

## 20. Authorization Statement

This document is a Sprint-15 roadmap draft only.

Sprint-15 roadmap save does not authorize Sprint-15 execution.

Sprint-15 execution requires explicit learner approval after roadmap review.

Creating `/Users/dumplings/workspace/rust_engineering_assessment` is not authorized by roadmap save alone.

Codex save/update of this roadmap does not authorize implementation.

This roadmap does not authorize:

* creating `/Users/dumplings/workspace/rust_engineering_assessment`;
* modifying learning-project files;
* modifying `/Users/dumplings/workspace/devlog_cli`;
* modifying `/Users/dumplings/workspace/rust_mechanics_lab`;
* modifying `/Users/dumplings/workspace/wallet_cli`;
* modifying `/Users/dumplings/workspace/task_tracker`;
* assigning implementation tasks;
* creating implementation code;
* starting Sprint-15 execution;
* continuing `devlog_cli` by default;
* continuing `rust_mechanics_lab`;
* continuing `wallet_cli`;
* turning `task_tracker` into a teaching project;
* reusing or crediting Sprint-07 Attempt-1.

The next allowed step is learner review of this saved roadmap and an explicit decision on whether to authorize Sprint-15 execution.

Only after explicit learner approval should the Teacher begin Sprint-15 execution planning.
