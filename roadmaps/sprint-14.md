# Sprint-14 Roadmap

## 1. Sprint Identity

* Sprint number: Sprint-14
* Sprint name: `rust_mechanics_lab — Value/Reference + Traits/Generics + Interior Mutability`
* Stage: Stage 2 — Rust Engineering
* Primary project: `rust_mechanics_lab`
* Learning-project root: `/Users/dumplings/workspace/rust_mechanics_lab`
* Governance repository root: `/Users/dumplings/workspace/rust-blockchain-career`
* Roadmap target file: `roadmaps/sprint-14.md`
* Sprint status: Draft only
* Execution status: Not started
* Authorization status: Not authorized for execution

Sprint-14 is a focused Rust mechanics consolidation sprint.

This roadmap draft does not authorize Sprint-14 execution.

Sprint-14 execution requires explicit learner approval after roadmap review.

## 2. Governance Context

Stage 1 — Rust Foundations is PASS / CLOSED.

The current active stage is:

`Stage 2 — Rust Engineering`

Sprint-12 is PASS / CLOSED and counts as completed Stage 2 Rust Engineering learning progress.

Sprint-13 is PASS / CLOSED and counts as completed Stage 2 Rust Engineering learning progress.

The current active sprint is:

`None`

Sprint-14 has not been previously authorized or started.

`devlog_cli` remains the active Stage 2 learning project foundation after Sprint-13, but future continuation requires separate specification approval.

Sprint-14 should not continue `devlog_cli` product expansion by default.

`wallet_cli` should not be continued by default.

`task_tracker` should not become the next teaching project.

Sprint-07 Attempt-1 remains FAILED / DISCARDED. No Sprint-07 Attempt-1 learning progress is credited, reused, or assumed.

Architect Sprint-14 Specification Review result:

`APPROVE WITH REVISIONS for Sprint-14 roadmap drafting only`

This approval allows drafting the Sprint-14 roadmap. It does not authorize Sprint-14 execution.

## 3. Sprint Objective

Sprint-14 consolidates core Rust mechanics that became important during Sprint-13 but still require stronger explicit concept mastery.

The sprint objective is to strengthen the learner’s understanding of:

* value versus reference;
* ownership and borrowing;
* function parameter design using `T`, `&T`, and `&mut T`;
* traits and generics;
* `impl Trait for Type`;
* generic bounds such as `S: Trait`;
* ownership and borrowing with generic parameters;
* `RefCell<T>` and interior mutability.

Sprint-14 prioritizes concept clarity, source-level reasoning, small exercises, and explicit learner validation.

Sprint-14 is intentionally bounded after a high-density Sprint-13.

Sprint-14 must not compensate for Sprint-13 drift by becoming larger.

Sprint-14 must not compress all teaching into one large implementation block.

## 4. Stage Alignment

Sprint-14 aligns with Stage 2 — Rust Engineering.

Stage 2 emphasizes:

* larger project organization;
* trait and generic usage;
* dependency management;
* CLI workflows;
* file and data handling;
* integration testing;
* maintainable error design.

Sprint-14 supports Stage 2 by strengthening the Rust mechanics needed for later engineering work:

* deciding whether APIs should take ownership or borrow;
* understanding trait boundaries;
* understanding generic function signatures;
* reasoning about ownership across generic calls;
* using `RefCell<T>` intentionally in controlled test/fake scenarios.

This sprint is not a product expansion sprint.

It is a Rust mechanics consolidation lab designed to support future Stage 2 engineering capability.

## 5. Project Choice And Rationale

The recommended project is:

`rust_mechanics_lab`

The recommended project root is:

`/Users/dumplings/workspace/rust_mechanics_lab`

Rationale:

Sprint-13 successfully introduced a minimal storage trait and generic workflow boundary inside `devlog_cli`, but concept mastery around traits, generics, ownership, borrowing, and `RefCell<T>` still needs direct reinforcement.

Continuing `devlog_cli` would risk turning remaining work into scattered cleanup or product continuation.

A small dedicated lab project allows the learner to practice the core mechanics directly without file IO, persistence, CLI behavior, or domain complexity distracting from the Rust concepts.

The lab project should be a small library crate, not a product application.

`devlog_cli` may be referenced only as source-review material when useful, for example:

* `EntryStorage`;
* `FileEntryStorage`;
* fake storage tests;
* `RefCell<T>` usage from Sprint-13 tests.

Sprint-14 should not expand `devlog_cli` unless a future Architect-approved roadmap explicitly authorizes that direction.

## 6. Scope

In scope:

* create a fresh small library crate named `rust_mechanics_lab` after execution is explicitly authorized;
* implement small concept-focused exercises;
* practice `T`, `&T`, and `&mut T` function parameter decisions;
* practice ownership, borrowing, move semantics, and clone semantics;
* define one small trait;
* implement the trait for at least one concrete type;
* write one or more generic functions using trait bounds;
* compare concrete functions with generic functions where useful;
* practice passing generic values as owned values, shared references, and mutable references;
* implement a small fake recorder or fake store using `RefCell<T>`;
* compare `RefCell<T>` with ordinary `&mut self` mutation;
* add focused tests tied to the concepts;
* require explicit learner explanation after each checkpoint;
* complete Student Validation, Codex Repository Validation, and Teacher Learning Validation.

## 7. Explicit Non-Goals

Out of scope:

* continuing `devlog_cli` product expansion by default;
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
* persistence;
* file IO;
* full CLI framework;
* `clap`;
* large architecture refactor;
* large trait framework;
* generic-heavy redesign;
* production-grade architecture;
* broad test expansion;
* deep lifetime topic unless unavoidable for a selected small exercise;
* `Rc<RefCell<T>>` deep dive;
* multithreading;
* `Arc<Mutex<T>>`;
* continuation of `wallet_cli`;
* conversion of `task_tracker` into a teaching project;
* reuse or credit of Sprint-07 Attempt-1.

## 8. Learning Outcomes

By the end of Sprint-14, the learner should be able to explain:

* the difference between owned value, shared reference, and mutable reference;
* what it means for a function to take `T`;
* what it means for a function to take `&T`;
* what it means for a function to take `&mut T`;
* when the caller can continue using a value after a function call;
* when a value is moved;
* when cloning is appropriate and what cost it may imply;
* why `&T` is a borrowed read-only view;
* why `&mut T` is an exclusive mutable borrow;
* what a trait is;
* what `impl Trait for Type` means;
* what `S: Trait` means;
* how a generic function depends on behavior instead of one concrete type;
* how ownership works when generic values are passed by value;
* how borrowing works when generic values are passed by reference;
* what `RefCell<T>` does;
* how interior mutability differs from ordinary `&mut` mutation;
* the difference between compile-time borrow checking and runtime borrow checking;
* why `RefCell<T>` is useful in certain fake/test scenarios;
* why `RefCell<T>` is not a general replacement for `&mut`;
* how implementation completion differs from concept mastery.

## 9. Required Learner Design Decisions

The learner must make and explain the following decisions during Sprint-14 execution.

### 9.1 Value / Reference API Decision

The learner must decide whether selected functions should accept:

* `T`;
* `&T`;
* `&mut T`.

The learner should explain:

* whether the function needs ownership;
* whether the function only needs to read;
* whether the function needs to mutate;
* whether the caller can still use the original value after the call;
* whether cloning is justified.

### 9.2 Trait Boundary Decision

The learner must define one small behavior contract as a trait.

The learner should explain:

* what behavior the trait represents;
* which concrete type implements it;
* why the trait should remain small;
* what the trait should not include.

### 9.3 Generic Function Decision

The learner must write at least one generic function using a trait bound.

The learner should explain:

* what the generic type parameter represents;
* what the bound requires;
* how the generic function differs from a concrete function;
* whether the generic function takes ownership or borrows.

### 9.4 Generic Ownership Decision

The learner must compare versions of a function that accept:

* `S`;
* `&S`;
* `&mut S`.

The learner should explain:

* which version consumes the argument;
* which version borrows the argument;
* which version can mutate through the argument;
* whether the original value can be reused afterward.

### 9.5 Interior Mutability Decision

The learner must decide where `RefCell<T>` is justified.

The learner should explain:

* why ordinary `&mut self` may be simpler in normal business logic;
* why `RefCell<T>` can be useful for fake recorders or fake stores;
* what runtime borrow checking means;
* what can go wrong if incompatible borrows happen at runtime.

## 10. Implementation Artifacts

Sprint-14 should produce three small, connected implementation areas.

### 10.1 Ownership / Borrowing Exercise Module

Expected module:

`src/ownership.rs`

Expected work:

* implement small functions that intentionally use `T`, `&T`, and `&mut T`;
* include examples where a value is moved;
* include examples where a value is only read;
* include examples where a value is mutated;
* include one controlled use of clone if useful for comparison.

This module should teach API parameter design, not product behavior.

### 10.2 Trait / Generic Boundary Exercise Module

Expected module:

`src/trait_boundary.rs`

Expected work:

* define one small trait;
* implement the trait for at least one concrete type;
* write one generic function using a trait bound;
* optionally write one concrete function for comparison;
* include owned, shared-reference, and mutable-reference generic examples where useful.

This module should stay small and avoid a framework-style trait design.

### 10.3 Interior Mutability Exercise Module

Expected module:

`src/interior_mutability.rs`

Expected work:

* implement a small fake recorder or fake store using `RefCell<T>`;
* show how `&self` can record calls internally;
* compare this with a design that uses `&mut self`;
* include a conceptual runtime borrow-conflict example if useful, without using runtime panic as normal business logic.

This module should teach `RefCell<T>`, not advanced shared ownership.

## 11. Suggested Module / Boundary Structure

Suggested structure:

* `src/lib.rs`
* `src/ownership.rs`
* `src/trait_boundary.rs`
* `src/interior_mutability.rs`
* `tests/ownership_test.rs`
* `tests/trait_boundary_test.rs`
* `tests/interior_mutability_test.rs`

Suggested responsibilities:

* `ownership.rs`: value/reference exercises, ownership transfer, borrowing, mutation, clone comparison;
* `trait_boundary.rs`: trait definition, concrete implementation, generic bound functions, generic ownership/borrowing variants;
* `interior_mutability.rs`: `RefCell<T>`, fake recorder or fake store, interior mutation through `&self`;
* `lib.rs`: crate-root public facade for the lab exercises;
* `tests/*`: focused behavior tests tied directly to the concepts.

This structure is a recommendation, not a forced design.

The learner may choose different names if the responsibility boundaries remain clear and the project remains a small Rust mechanics lab.

## 12. Checkpoint Plan

### Checkpoint 1 — Value vs Reference

Teaching focus:

* `T`;
* `&T`;
* `&mut T`;
* ownership;
* borrowing;
* mutable borrowing;
* move semantics;
* clone semantics and cost;
* function parameter design.

Learner work:

* implement small functions that intentionally choose between owned, borrowed, and mutably borrowed parameters;
* explain which values are moved and which are borrowed;
* explain when the caller can continue using the original value;
* add focused tests for the selected behavior.

Validation focus:

* learner can explain at least three function signatures;
* learner can predict whether a value remains usable after a call;
* learner can explain one RustRover or compiler-assisted fix if one occurs.

### Checkpoint 2 — Trait / Generic Boundary

Teaching focus:

* trait as behavior contract;
* `impl Trait for Type`;
* generic bound;
* concrete type versus generic type;
* static dispatch.

Learner work:

* define one small trait;
* implement it for at least one concrete type;
* write one generic function using a trait bound;
* optionally compare a concrete function with a generic function;
* add focused tests for trait/generic behavior.

Validation focus:

* learner can explain the trait;
* learner can explain the concrete implementation;
* learner can identify the concrete type;
* learner can identify the generic parameter;
* learner can explain the bound.

### Checkpoint 3 — Generic Ownership And Borrowing

Teaching focus:

* passing `S: Trait`;
* passing `&S`;
* passing `&mut S`;
* ownership with generic values;
* repeated use after function calls.

Learner work:

* implement small variations that accept owned generic values, shared references, and mutable references;
* explain which version consumes, borrows, or mutates the argument;
* add focused tests or source-level examples that demonstrate reusability after calls.

Validation focus:

* learner can reason about whether the original value can be reused after each call;
* learner can explain why generic ownership follows the same ownership rules as concrete ownership.

### Checkpoint 4 — `RefCell<T>` / Interior Mutability

Teaching focus:

* `RefCell<T>`;
* interior mutability;
* compile-time borrow checking versus runtime borrow checking;
* `borrow()`;
* `borrow_mut()`;
* fake/test usage.

Learner work:

* implement a small fake recorder or fake store using `RefCell<T>`;
* show how `&self` can record calls internally;
* compare this with a design using `&mut self`;
* add focused tests for recorded calls or stored values.

Validation focus:

* learner can explain why `RefCell<T>` allows mutation through shared references;
* learner can explain runtime borrow conflicts;
* learner can explain when not to use `RefCell<T>`.

### Checkpoint 5 — Final Concept Validation And Source Review

Teaching focus:

* concept mastery;
* source-level reasoning;
* tradeoff explanation;
* validation separation.

Learner work:

* run local validation;
* answer concept validation questions;
* explain key source-level decisions;
* request Codex validation only after meaningful implementation is complete.

Validation focus:

* learner can explain the difference between implementation completion and concept mastery;
* Teacher Learning Validation is based on explanation and source reasoning, not only code completion;
* all three validation layers remain separate.

## 13. Testing Requirements

Tests are required, but testing must not dominate Sprint-14.

Preferred final test count:

`5 to 7 focused tests total`

Required test coverage:

* at least one test for value/reference behavior;
* at least one test for mutable-borrow behavior;
* at least one test for trait implementation behavior;
* at least one test for generic function behavior;
* at least one test for `RefCell<T>` fake recorder or fake store behavior.

Recommended test examples:

* borrowed read function does not consume the original value;
* mutable borrow function changes the original value;
* owned-value function consumes or returns ownership according to design;
* generic function works with a type implementing the selected trait;
* fake recorder using `RefCell<T>` records calls through `&self`.

Avoid:

* broad test suites;
* testing every private helper;
* complex test frameworks;
* product-style workflows;
* excessive compile-fail testing;
* panic-based runtime borrow conflict tests unless the Teacher explicitly uses one small example for conceptual demonstration.

## 14. Student Validation Requirements

Before requesting formal Codex Repository Validation, the learner should complete Student Validation.

Student Validation should include:

* run `cargo fmt --check`;
* run `cargo check`;
* run `cargo test`;
* review the public API surface;
* explain value/reference decisions;
* explain ownership and borrowing across function calls;
* explain trait/generic decisions;
* explain where `impl Trait for Type` appears;
* explain where `S: Trait` or an equivalent generic bound appears;
* explain ownership and borrowing with generic parameters;
* explain `RefCell<T>` usage;
* explain why `RefCell<T>` is not a replacement for ordinary `&mut`;
* identify 2 to 3 examples of compiler or IDE-assisted corrections if they occurred;
* identify known non-blocking issues if any.

For each compiler or IDE-assisted correction, the learner should explain:

* what the original issue was;
* why Rust rejected or warned about it;
* why the final fix is correct.

Learner-reported command output is useful as local self-check, but it does not replace formal Codex Repository Validation.

## 15. Codex Repository Validation Requirements

Codex Repository Validation is required after meaningful implementation changes during Sprint-14 execution.

Codex validation target for the learning project:

`/Users/dumplings/workspace/rust_mechanics_lab`

Codex should verify:

* `cargo fmt --check` passes;
* `cargo check` passes;
* `cargo test` passes;
* implementation matches Sprint-14 roadmap scope;
* the project remains a small Rust mechanics lab;
* module boundaries are understandable;
* value/reference exercises are present and focused;
* trait/generic exercises are present and focused;
* generic ownership/borrowing examples are present and focused;
* `RefCell<T>` / interior mutability exercise is present and focused;
* tests are concept-focused and not excessive;
* no out-of-scope systems or dependencies were introduced;
* no Solana, Anchor, blockchain networking, wallet behavior, signing, RPC, async Rust, Tokio, database, persistence, full CLI framework, `clap`, large architecture refactor, or production-grade architecture was introduced;
* `devlog_cli` was not expanded by default;
* `wallet_cli` was not continued;
* `task_tracker` was not converted into a teaching project;
* no Sprint-07 Attempt-1 work was reused or credited.

If the governance repository is later updated with `roadmaps/sprint-14.md`, validate separately:

`/Users/dumplings/workspace/rust-blockchain-career`

Codex must not combine governance repository validation and learning-project validation unless the learner explicitly requests a cross-repository audit.

## 16. Teacher Learning Validation Requirements

Teacher Learning Validation is required before Sprint-14 can be closed.

Teacher Learning Validation must include explicit concept validation.

The Teacher should evaluate whether the learner can explain:

* value versus reference;
* owned value versus borrowed view;
* `T`, `&T`, and `&mut T`;
* ownership and borrowing across function calls;
* move semantics;
* clone semantics and cost;
* when a function should take ownership;
* when a function should borrow;
* when a function should mutably borrow;
* trait / `impl` / generic-bound terminology;
* trait as behavior contract;
* `impl Trait for Type` as implementing the behavior contract for a concrete type;
* `S: Trait` as a generic bound;
* concrete type versus generic type;
* static dispatch at the level required by this sprint;
* ownership and borrowing with generic parameters;
* `RefCell<T>` and interior mutability;
* compile-time borrow checking versus runtime borrow checking;
* `borrow()` and `borrow_mut()`;
* why `RefCell<T>` is useful for certain fake/test scenarios;
* why `RefCell<T>` is not a general replacement for `&mut`;
* which concepts remain weak, if any.

Teacher Learning Validation must include at least:

* 3 contrast questions;
* 2 source-level reasoning questions;
* 1 tradeoff question.

Example contrast question categories:

* `T` versus `&T`;
* `&T` versus `&mut T`;
* concrete function versus generic function;
* ordinary mutation through `&mut self` versus interior mutability through `RefCell<T>`.

Example source-level reasoning question categories:

* explain why a specific function signature takes `T`, `&T`, or `&mut T`;
* explain why a generic function uses `S: Trait`;
* explain why `RefCell<T>` is placed inside the fake recorder or fake store.

Example tradeoff question category:

* when should ordinary `&mut` be preferred over `RefCell<T>`, and when is `RefCell<T>` justified?

Codex PASS does not automatically imply Teacher Learning Validation PASS.

Passing tests does not automatically imply Teacher Learning Validation PASS.

Implementation completion must not be treated as concept mastery.

## 17. Completion Criteria

Sprint-14 can be completed only when all of the following are true:

* Sprint-14 execution was explicitly authorized by the learner before implementation began;
* the fresh `rust_mechanics_lab` learning project exists only as an authorized Stage 2 Rust Engineering lab project;
* `devlog_cli` was not expanded by default;
* `wallet_cli` was not continued;
* `task_tracker` was not converted into a teaching project;
* no Sprint-07 Attempt-1 progress or implementation was credited;
* project remained inside Stage 2 Rust Engineering scope;
* value/reference exercises were implemented;
* trait/generic exercises were implemented;
* generic ownership/borrowing exercises were implemented;
* `RefCell<T>` / interior mutability exercise was implemented;
* tests are focused and tied to the sprint concepts;
* preferred test count of 5 to 7 focused tests is met or any deviation is explicitly justified;
* Student Validation is PASS;
* Codex Repository Validation is PASS or has only explicitly accepted non-blocking concerns;
* Teacher Learning Validation is PASS;
* learner can explain the core concepts without relying only on code completion;
* governance repository and learning-project validation remained separate;
* explicit non-goals were respected.

## 18. Teaching Notes

During Sprint-14 execution, technical teaching language must be primarily Chinese.

Important professional terms should be introduced in the form:

`English professional term (Chinese professional translation)`

Examples for Sprint-14:

* ownership (所有权);
* borrowing (借用);
* mutable borrowing (可变借用);
* owned value (拥有所有权的值);
* shared reference (共享引用);
* mutable reference (可变引用);
* move semantics (移动语义);
* clone (克隆);
* function parameter design (函数参数设计);
* trait (特征);
* implementation (实现);
* generic parameter (泛型参数);
* generic bound (泛型约束);
* concrete type (具体类型);
* static dispatch (静态分发);
* interior mutability (内部可变性);
* runtime borrow checking (运行时借用检查);
* compile-time borrow checking (编译期借用检查).

Teaching should use structured instruction, not guided guessing.

The Teacher should teach the concept, mental model, implementation boundary, common mistakes, and acceptance criteria before asking the learner to implement.

Sprint-14 must proceed checkpoint by checkpoint.

The Teacher must not compress all teaching into one large implementation block.

The learner remains the primary implementer.

Teacher examples are allowed, but examples must support understanding, not replace learner reasoning or learner validation.

For core implementation areas, the Teacher may provide patterns, skeletons, targeted snippets, or small examples, but should not routinely provide complete near-final implementation before the learner has practiced the concept.

More complete test examples are acceptable when they reduce testing friction and keep testing supportive.

The Teacher should explicitly validate concept mastery after implementation, especially where the learner followed a Teacher-provided example.

## 19. Repository Validation Separation

Governance repository:

`/Users/dumplings/workspace/rust-blockchain-career`

Learning-project repository:

`/Users/dumplings/workspace/rust_mechanics_lab`

These repositories must be validated separately.

If `roadmaps/sprint-14.md` is later added to the governance repository, that is a governance repository update and should be validated against the governance repository root.

If `rust_mechanics_lab` is created or modified during Sprint-14 execution, that is a learning-project update and should be validated against the learning-project root.

Codex should validate one repository or project root at a time.

Do not combine governance validation and learning-project validation into one prompt unless the learner explicitly requests a cross-repository audit.

## 20. Authorization Statement

This document is a Sprint-14 roadmap draft only.

Sprint-14 roadmap drafting does not authorize Sprint-14 execution.

Sprint-14 execution requires explicit learner approval after roadmap review.

This roadmap does not authorize:

* creating the `rust_mechanics_lab` project;
* modifying learning-project files;
* modifying governance repository files beyond saving this roadmap and minimal current-state synchronization;
* assigning implementation tasks;
* creating implementation code;
* starting Sprint-14 execution;
* continuing `devlog_cli` product expansion;
* continuing `wallet_cli`;
* turning `task_tracker` into a teaching project;
* reusing or crediting Sprint-07 Attempt-1.

The next allowed step is learner review of this saved roadmap and an explicit decision on whether to authorize Sprint-14 execution.

Only after explicit learner approval should the Teacher begin Sprint-14 execution planning.
