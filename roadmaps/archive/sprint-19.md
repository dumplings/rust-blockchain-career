# Sprint-19 — Smart Pointers And Interior Mutability

## 1. Sprint Identity

* Sprint number: Sprint-19
* Sprint title: `Smart Pointers And Interior Mutability`
* Stage relationship: Stage 2.5 — Rust Core Philosophy Bridge
* Lifecycle status: Accepted execution contract / completed by Sprint-19 closure
* Execution status: Closed as PASS WITH NOTES / CLOSED; no active execution window
* Preferred learning format: a small standalone concept crate named `rust_smart_pointer_lab`

## 2. Stage Relationship

Sprint-19 belongs to Stage 2.5 — Rust Core Philosophy Bridge.

Its purpose is to cover the ownership-topology portion of the Stage 2.5 bridge after the learner has already completed sufficient current-point coverage for:

* closures and iterators;
* systematic pattern matching;
* collection ownership behavior;
* deeper ownership and borrowing mental models;
* explicit lifetime reasoning.

Sprint-19 should strengthen the learner's ability to reason about owned indirection, shared ownership, non-owning links, deterministic cleanup, runtime borrow checking, and interior mutability before Stage 3 Blockchain Foundations.

This roadmap does not complete Stage 2.5 by itself.

## 3. Current State And Authorization Boundary

Current closure-state assumptions:

* Sprint-18 is closed.
* No active learning sprint exists.
* Sprint-19 was accepted as an execution contract and is now closed as PASS WITH NOTES / CLOSED.
* Sprint-20 is not drafted, accepted, active, or authorized.
* Stage 2.5 remains incomplete.
* Stage 3 transition is unauthorized.
* Sprint-19 closure does not authorize Sprint-20 execution.
* Sprint-19 closure does not authorize Stage 3 transition.

This historical roadmap must not be used to start new checkpoint teaching, modify a learning repository, authorize Sprint-20, or authorize Stage 3 transition.

## 4. Learning Objectives

By the end of Sprint-19, the learner should be able to:

1. Explain smart pointers as ownership-topology and resource-lifecycle tools, not merely as "advanced references."
2. Use `Box<T>` to model owned heap indirection and simple boxed ownership shapes.
3. Explain `Deref`, deref coercion, and ergonomic access through smart pointers.
4. Explain `Drop` as deterministic cleanup at the end of ownership.
5. Explain `Rc<T>` as single-threaded shared ownership.
6. Explain `Weak<T>` as a non-owning link used to avoid ownership cycles or observe shared structures without extending ownership.
7. Explain `RefCell<T>` as runtime borrow checking and interior mutability.
8. Contrast ordinary `&mut` design with `RefCell<T>` and explain when interior mutability is justified.
9. Explain borrow guard behavior and the risk of runtime borrow failure.
10. Reason through bounded source examples involving `Box<T>`, `Rc<T>`, `Weak<T>`, and `RefCell<T>`.
11. Preserve prior ownership, borrowing, lifetime, iterator, pattern, module, API, and testing capabilities while adding smart-pointer reasoning.

## 5. Scope

Sprint-19 should cover:

### `Box<T>`

* owned indirection;
* heap allocation as an implementation detail;
* simple recursive or boxed shapes when useful;
* owned values versus borrowed views;
* why `Box<T>` is still single ownership.

### `Deref`

* access through smart pointers;
* deref coercion at a practical level;
* ergonomic API use without deep trait-object expansion;
* how deref supports usability without changing ownership rules.

### `Drop`

* deterministic cleanup;
* ownership-end reasoning;
* cleanup order at a simple source-reading level;
* the relationship between ownership end and resource release.

### `Rc<T>`

* single-threaded shared ownership;
* clone as reference-count increment, not deep value clone;
* ownership extension through shared owners;
* contrast with ordinary references;
* strong count reasoning at a conceptual level.

### `Weak<T>`

* non-owning references to shared allocations;
* `upgrade` and absence handling;
* why weak links do not keep the value alive;
* cycle-risk reasoning;
* parent/child or observer-style examples at bounded complexity.

### `RefCell<T>`

* interior mutability;
* runtime borrow checking;
* `borrow` and `borrow_mut`;
* borrow guard lifetime and release behavior;
* runtime panic risk when borrow rules are violated;
* contrast with ordinary `&mut`.

### Composition

* bounded `Rc<RefCell<T>>` examples only when they clarify the difference between shared ownership and interior mutability;
* design reasoning for whether a structure needs ordinary borrowing, owned values, shared ownership, weak links, or runtime borrow checking;
* explicit explanation of why smart pointers should not be used as default replacements for simpler ownership design.

## 6. Explicit Non-Goals

Sprint-19 must not expand into:

* `Arc<T>`;
* `Mutex<T>`;
* `Send`;
* `Sync`;
* threads or channels;
* async Rust;
* Solana or blockchain concepts;
* broad trait-object design;
* full public error contract cleanup;
* broad architecture or framework work;
* production-grade graph or tree libraries;
* unsafe Rust;
* advanced lifetime bounds;
* higher-ranked trait bounds;
* self-referential structures;
* large-scale library design;
* extensive public API hardening unrelated to smart pointers and interior mutability.

If these topics arise naturally, the Teacher should name them as deferred topics and return to the Sprint-19 scope.

## 7. Suggested Learning Project Or Exercise Format

The preferred execution format is a small standalone concept crate named:

`rust_smart_pointer_lab`

The crate is not created by roadmap drafting. Project creation requires separate Sprint-19 execution authorization after roadmap acceptance and an explicit learner start command.

The lab should remain small and should exist only to support concept validation. It must not become a production data-structure library.

Bounded source-reading or chat-only exercises may replace the crate only if the Teacher gives a concrete execution-time reason, such as avoiding unnecessary repository work for a narrowly scoped concept check or preserving sprint density after learner feedback. If that happens, the Teacher must still preserve the Sprint-19 learning objectives and Teacher Learning Validation requirements.

Suggested exercise surfaces for the preferred crate:

1. A tiny boxed recursive or nested ownership example using `Box<T>`.
2. A small source-reading or implementation exercise involving `Deref` and `Drop`.
3. A small shared structure using `Rc<T>` and `Weak<T>` to reason about ownership cycles.
4. A small `RefCell<T>` example that demonstrates runtime borrow checking and borrow guard behavior.
5. A final design-choice explanation comparing ordinary borrowing, owned values, `Box<T>`, `Rc<T>`, `Weak<T>`, and `RefCell<T>`.

If code is created or modified, tests should verify only the sprint's core behavior. Tests should not become the main workload.

## 8. Checkpoint Sequence

### Checkpoint 1 — Owned Indirection: `Box<T>`, `Deref`, And `Drop`

Goal:

Build the learner's mental model for owned indirection and resource lifecycle.

Required teaching focus:

* `Box<T>` as owned heap indirection;
* owned value versus reference;
* `Deref` and ergonomic access;
* `Drop` and deterministic cleanup;
* why these tools still follow ordinary ownership rules.

Expected learner work:

* Read or implement a bounded `Box<T>` example.
* Explain owner, allocation, access path, and cleanup point.
* Explain why `Box<T>` is not shared ownership.

Validation target:

* Teacher checks concept explanation and source-level ownership tracing.
* Student Validation and Codex Repository Validation apply if the `rust_smart_pointer_lab` repository is created or modified.

### Checkpoint 2 — Shared Ownership: `Rc<T>`

Goal:

Teach single-threaded shared ownership and contrast it with ordinary borrowing.

Required teaching focus:

* `Rc<T>` as shared ownership;
* clone as reference-count increment;
* why `Rc<T>` can extend the life of an allocation;
* why `Rc<T>` is not ordinary `&T`;
* when `Rc<T>` is appropriate and when ownership should remain simpler.

Expected learner work:

* Read or implement a bounded `Rc<T>` example.
* Trace how many owners exist and when the shared allocation can be dropped.
* Explain why ordinary references would not represent the same ownership relationship.

Validation target:

* Teacher checks whether the learner can distinguish shared ownership from borrowing.
* Tests may verify basic shared structure behavior if repository code is used.

### Checkpoint 3 — Non-Owning Links: `Weak<T>` And Cycle Reasoning

Goal:

Teach non-owning links and ownership-cycle risk.

Required teaching focus:

* `Weak<T>` as a non-owning pointer to an `Rc<T>` allocation;
* `upgrade` and absence handling;
* why weak links do not keep the value alive;
* simple parent/child or observer-style topology;
* ownership-cycle prevention.

Expected learner work:

* Read or implement a bounded `Rc<T>` / `Weak<T>` relationship.
* Explain which edges own and which edges do not.
* Explain what would go wrong if every edge were `Rc<T>`.

Validation target:

* Teacher checks cycle-risk reasoning.
* If repository code is used, tests may verify `upgrade` behavior before and after owners are dropped.

### Checkpoint 4 — Interior Mutability: `RefCell<T>`

Goal:

Teach runtime borrow checking and deliberate interior mutability.

Required teaching focus:

* `RefCell<T>` as interior mutability;
* contrast with ordinary `&mut`;
* `borrow` and `borrow_mut`;
* borrow guard behavior;
* runtime borrow failure and panic risk;
* why `RefCell<T>` is not a general replacement for good ownership design.

Expected learner work:

* Read or implement a bounded `RefCell<T>` example.
* Explain when the borrow guard is active.
* Explain why a conflicting runtime borrow fails.
* Explain whether ordinary `&mut` would be better in a simpler design.

Validation target:

* Teacher checks runtime-vs-compile-time borrow reasoning.
* If repository code is used, tests may include a controlled runtime borrow failure case only if it strengthens understanding.

### Checkpoint 5 — Integrated Ownership-Topology Design Review

Goal:

Integrate all Sprint-19 concepts into design reasoning.

Required teaching focus:

* choosing among owned values, references, `Box<T>`, `Rc<T>`, `Weak<T>`, and `RefCell<T>`;
* preserving ordinary ownership and borrowing as the default;
* using smart pointers only when the ownership topology requires them;
* avoiding concurrency and async drift.

Expected learner work:

* Explain a small ownership topology using the sprint's vocabulary.
* Justify each pointer or ownership choice.
* Identify at least one place where `RefCell<T>` would be overuse.
* Identify at least one place where `Weak<T>` is more appropriate than `Rc<T>`.

Validation target:

* Teacher Learning Validation must decide whether the learner can explain design tradeoffs, not merely whether code compiles.

## 9. Expected Artifacts

Depending on execution choice, expected artifacts may include:

* a small standalone concept crate named `rust_smart_pointer_lab`;
* bounded source files in that crate;
* small tests for ownership-topology behavior;
* learner explanations of ownership, shared ownership, weak links, runtime borrow checking, and tradeoffs;
* a final Teacher Learning Validation summary;
* a Codex Repository Validation report if a learning repository is created or modified;
* a Sprint-19 closure package if the sprint is completed.

No artifact is created merely by this roadmap draft.

## 10. Validation Requirements

### Student Validation

Student Validation is required if Sprint-19 creates or modifies a learning repository.

Expected commands for the preferred Rust learning crate:

* `cargo fmt --check`
* `cargo check`
* `cargo test`

If Sprint-19 is completed entirely through bounded source-reading or chat-only reasoning without repository changes, Student Validation for repository code is not applicable, but learner explanation and Teacher Learning Validation remain required.

### Codex Repository Validation

Codex Repository Validation is required if Sprint-19 creates or modifies a learning repository.

If Sprint-19 is completed entirely through bounded source-reading or chat-only reasoning without repository changes, Codex Repository Validation for a learning project is not applicable.

Teacher may decide when to request Codex validation and how to structure the validation prompt, but formal repository validation is not optional when a learning repository has been created or modified and is used as sprint completion evidence.

Codex validation should check:

1. Validation target and repository root.
2. Files inspected.
3. Changed files.
4. Scope compliance.
5. Whether the implementation stays within Sprint-19 non-goals.
6. Compiler and test results.
7. Whether the code demonstrates the required smart-pointer and interior-mutability concepts.
8. Risks or gaps.
9. Final verdict.

Codex must not be asked to implement the learning project by default.

### Teacher Learning Validation

Teacher Learning Validation is always required.

Teacher Learning Validation must verify:

* concept understanding;
* ownership-topology reasoning;
* source-level explanation;
* distinction between ownership and borrowing;
* distinction between shared ownership and ordinary references;
* distinction between `Rc<T>` and `Weak<T>`;
* runtime borrow checking and borrow guard reasoning;
* appropriate versus inappropriate use of `RefCell<T>`;
* design tradeoff explanation.

Passing tests or receiving Codex PASS does not automatically satisfy Teacher Learning Validation.

## 11. Codex Repository Validation Expectations

If `rust_smart_pointer_lab` or another learning repository is created or modified, the Teacher must generate a separate Codex validation prompt after learner self-check.

The prompt should validate one repository only.

Codex should not modify the learning project unless explicitly authorized by the learner.

Codex should report:

* repository root;
* files inspected;
* Git status and changed files;
* commands run;
* compiler/test results;
* scope compliance;
* whether any non-goal topics leaked into the implementation;
* whether the project demonstrates the Sprint-19 concepts;
* final verdict.

Governance repository validation and learning-project validation must remain separate.

If no learning repository is created or modified, Codex Repository Validation for a learning project is not applicable, and the closure should state why.

## 12. Teacher Learning Validation Expectations

At sprint closure, the Teacher must explicitly state:

* what was reviewed;
* what the learner correctly understood;
* what remains weak or requires reinforcement;
* whether each checkpoint passes;
* whether the final Sprint-19 learning verdict is PASS, PASS WITH NOTES, or not yet pass;
* whether Sprint-19 should count as completed Stage 2.5 progress within its scope.

Teacher validation should not use vague labels without reasoning.

## 13. Completion Criteria

Sprint-19 may be completed only when:

1. The learner can explain `Box<T>`, `Deref`, and `Drop` in ownership and resource-lifecycle terms.
2. The learner can explain `Rc<T>` as shared ownership and distinguish it from ordinary references.
3. The learner can explain `Weak<T>` as non-owning and use it to reason about ownership cycles.
4. The learner can explain `RefCell<T>` as runtime borrow checking and distinguish it from ordinary `&mut`.
5. The learner can explain borrow guard behavior and runtime borrow failure.
6. The learner can justify when interior mutability is appropriate and when ordinary mutable borrowing is preferable.
7. The learner can complete the integrated ownership-topology design review.
8. Student Validation passes if a learning repository was created or modified.
9. Codex Repository Validation passes if a learning repository was created or modified.
10. Teacher Learning Validation passes or passes with notes.
11. No explicit non-goal becomes part of the required sprint scope.

## 14. Closure Requirements

Sprint-19 closure should record:

* final sprint status;
* checkpoint results;
* Student Validation result or not-applicable rationale;
* Codex Repository Validation result or not-applicable rationale;
* Teacher Learning Validation result;
* completed learning objectives;
* remaining reinforcement notes;
* scope and non-goal compliance;
* impact on Stage 2.5 P1 coverage;
* whether Stage 2.5 remains incomplete;
* whether Stage 3 remains unauthorized;
* recommended next planning action without authorizing Sprint-20 execution.

The closure document should be repository-ready English if persisted.

## 15. Notes For Future Sprint-20 Planning

Sprint-20 should remain a future planning direction only.

Likely direction:

`Sprint-20 — Engineering Contract Consolidation`

Candidate topics:

* broader trait and generic design;
* public API as contract;
* abstraction-boundary tradeoffs;
* public error traits;
* `Display`;
* `std::error::Error`;
* structured error context;
* library-facing error ergonomics;
* possible bounded revisit of earlier engineering-assessment code only if later approved.

Sprint-20 should not be drafted, accepted, started, or authorized by Sprint-19 planning alone.

A separate Specification Review should decide whether Sprint-20 is still needed after Sprint-19 closure and after the Rust-core coverage ledger is reviewed against completed evidence.
