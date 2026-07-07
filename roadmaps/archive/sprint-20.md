# Sprint-20 — Engineering Contract Consolidation

## 1. Sprint Identity

* Sprint number: Sprint-20
* Sprint title: `Engineering Contract Consolidation`
* Stage relationship: Stage 2.5 — Rust Core Philosophy Bridge
* Lifecycle status: Accepted execution contract / completed by Sprint-20 closure
* Execution status: Closed as PASS WITH NOTES / CLOSED; no active execution window
* Preferred learning format: a small standalone library-style concept crate named `rust_engineering_contract_lab`

This roadmap records the accepted Sprint-20 execution contract. Sprint-20 closure does not complete Stage 2.5 or authorize Stage 3 transition.

## 2. Stage Relationship

Sprint-20 belongs to Stage 2.5 — Rust Core Philosophy Bridge.

Its purpose is to consolidate the remaining Stage 2.5 P1 Rust engineering-contract work after the completed Sprint-17, Sprint-18, and Sprint-19 evidence.

Sprint-20 should connect Rust core philosophy back to practical engineering design by focusing on:

* broader trait and generic design;
* public API as caller-facing contract;
* abstraction-boundary tradeoffs;
* public error traits and library error ergonomics;
* explicit reinforcement of Rust common concepts inside source-level design;
* preservation of modules, encapsulation, tests, ownership, borrowing, and prior engineering discipline.

Sprint-20 may become the final teaching sprint before a later Stage 2.5 exit review, but this roadmap does not itself complete Stage 2.5.

## 3. Current State And Authorization Boundary

Execution-lifecycle assumptions for this contract:

* Sprint-19 is closed as `PASS WITH NOTES / CLOSED`.
* No active learning sprint exists.
* Sprint-20 was accepted, executed in a separately authorized Teacher window, and is now closed as `PASS WITH NOTES / CLOSED`.
* Stage 2.5 remains incomplete.
* Stage 3 transition remains unauthorized.
* Sprint-20 closure does not complete Stage 2.5 or authorize Stage 3 transition.

This historical roadmap must not be used to restart teaching, issue new checkpoint work, modify a learning project, complete Stage 2.5, or authorize Stage 3 transition.

## 4. Learning Objectives

By the end of Sprint-20, the learner should be able to:

1. Explain traits and generics as abstraction tools with costs and tradeoffs, not as default design decoration.
2. Decide when a concrete type, generic function, trait bound, enum, or small behavior trait is appropriate.
3. Design a small public API surface that exposes stable caller-facing behavior while keeping implementation details internal.
4. Explain crate-root facade choices, internal module boundaries, visibility, and caller contract.
5. Implement and explain public error ergonomics using `Display`, `std::error::Error`, structured context, and error-kind versus message separation.
6. Explain when source chaining is appropriate and when a simpler error contract is better.
7. Reinforce Rust expression semantics, mutability boundaries, type reasoning, and control-flow reasoning through source-level implementation.
8. Preserve prior ownership, borrowing, modules, encapsulation, testing, and public API capabilities in a bounded engineering context.
9. Explain the final design in terms of engineering contracts: type contract, API contract, abstraction contract, and error contract.

## 5. Scope

Sprint-20 should cover:

### Traits And Generics

* generic functions and generic structs in bounded cases;
* trait bounds as explicit capability requirements;
* static dispatch at a practical source-reading level;
* concrete type versus generic abstraction tradeoffs;
* avoiding over-abstraction;
* small trait design only when it creates a clear contract.

### Public API As Contract

* crate-root facade reasoning;
* public surface selection;
* private modules and internal helpers;
* stable caller-facing behavior;
* invariants preserved behind constructors or methods;
* deciding what stays internal.

### Public Error Traits And Library Error Ergonomics

* custom public error type or error enum;
* `Display` implementation;
* `std::error::Error` implementation;
* error kind versus human-readable message;
* structured context where useful;
* source chaining only when it clarifies the underlying failure relationship;
* tests for success paths and meaningful error paths.

### Rust Common-Concept Reinforcement

Reinforce the following through implementation and explanation rather than trivia drills:

* expression-oriented Rust style;
* `mut` as a binding and API design signal;
* type inference versus explicit type clarity;
* control flow for success and error paths;
* ownership and borrowing at public API boundaries;
* pattern matching and error-flow readability when relevant.

### Preservation Of Prior Capabilities

The sprint should preserve and lightly exercise:

* modules and privacy;
* API boundaries;
* testing habits;
* encapsulation;
* ownership and borrowing discipline;
* iterator and pattern fluency when naturally useful.

## 6. Explicit Non-Goals

Sprint-20 must not expand into:

* blockchain or Solana concepts;
* async Rust;
* concurrency;
* `Arc<T>`, `Mutex<T>`, `Send`, or `Sync`;
* broad trait-object design;
* macros;
* unsafe Rust;
* large framework architecture;
* production-grade library design;
* broad CLI expansion;
* broad persistence or file-system workflow expansion unless the accepted exercise explicitly requires a tiny bounded input source;
* revisiting every previous project;
* one mini-sprint per remaining P1 topic;
* comprehensive documentation, publishing, workspace, or release-profile work;
* replacing learner implementation practice with Codex implementation.

If these topics arise, the Teacher should name them as deferred or out of scope and return to the Sprint-20 contract-consolidation objective.

## 7. Suggested Learning Project Or Exercise Format

Preferred format:

Create a small standalone Rust library-style concept crate named:

`rust_engineering_contract_lab`

The crate should remain deliberately small. It should exist only to validate engineering-contract reasoning, not to become a production library.

A suitable exercise shape is a tiny domain-neutral library that exposes a public facade over a small internal workflow, for example:

* normalize or validate caller-provided records;
* classify a small input into a typed result;
* use one bounded generic or trait boundary only where it clarifies caller behavior;
* return a public error type with structured error kinds and clear display messages;
* keep implementation helpers internal.

The exact domain can be chosen during execution, but it must remain domain-neutral and must not introduce blockchain, Solana, networking, async, persistence, or large CLI concerns.

A bounded revisit of an earlier project may be considered only if a later approved execution decision establishes that the old project has a clear high-value learning reason and enough local source evidence is available. This roadmap does not select or authorize any prior-project modification.

If no code is created or modified, Sprint-20 would need an alternative source-reading and design-review format, but that is not the preferred path because the remaining P1 work benefits from durable implementation evidence.

## 8. Checkpoint Sequence

### Checkpoint 1 — Public API As Contract

Goal:

Build the learner's public-surface and caller-contract reasoning.

Required teaching focus:

* public API as caller-facing contract;
* crate-root facade;
* internal module privacy;
* `pub`, private helpers, and invariants;
* expression, type, and mutability choices visible at API boundaries.

Expected learner work:

* inspect or create a small crate structure;
* define a minimal public facade;
* keep internal helpers private;
* explain what callers are allowed to rely on and what remains internal.

Validation target:

* Teacher checks public-surface reasoning and API boundary explanation.
* If code is created or modified, tests should verify caller-facing behavior rather than internal implementation details.

### Checkpoint 2 — Traits And Generics As Abstraction Boundaries

Goal:

Teach broader but bounded trait/generic design beyond tiny behavior examples.

Required teaching focus:

* concrete type versus generic function versus trait-bound design;
* trait bounds as capability contracts;
* static dispatch at a practical level;
* when generics are useful;
* when generics over-abstract a simple design.

Expected learner work:

* implement or revise one bounded generic or trait-based boundary;
* compare it with a concrete alternative;
* justify why the selected abstraction is useful and not excessive.

Validation target:

* Teacher checks abstraction tradeoff reasoning.
* Tests should prove behavior through the public API, not merely instantiate generic code for its own sake.

### Checkpoint 3 — Public Error Traits And Library Error Ergonomics

Goal:

Teach library-facing error contracts.

Required teaching focus:

* public error type as part of API contract;
* error kind versus message;
* `Display`;
* `std::error::Error`;
* structured context;
* optional source chaining when it models a real underlying cause;
* preserving stable behavior without over-engineering error frameworks.

Expected learner work:

* design and implement a small public error type;
* implement `Display`;
* implement `std::error::Error`;
* expose meaningful error kinds or structured context;
* write tests for success and error paths;
* explain which error details are stable caller contract and which are presentation details.

Validation target:

* Teacher checks error-contract explanation.
* Student and Codex validation should verify compiler/test results and scope compliance if code is used.

### Checkpoint 4 — Integrated Engineering Contract Review

Goal:

Integrate API, trait/generic, error, and Rust common-concept reasoning.

Required teaching focus:

* type contract;
* abstraction contract;
* public API contract;
* error contract;
* ownership and borrowing at public boundaries;
* mutability and control-flow clarity;
* preserving simple design when abstraction is unnecessary.

Expected learner work:

* present the final crate design;
* explain the public contract and internal boundary;
* justify each trait/generic decision;
* explain error design and caller-facing failure semantics;
* identify at least one abstraction that was intentionally avoided;
* identify at least one API detail that was kept private.

Validation target:

* Teacher Learning Validation decides whether the learner can explain engineering tradeoffs, not merely whether code compiles.

## 9. Expected Artifacts

Expected artifacts may include:

* a small standalone crate named `rust_engineering_contract_lab`;
* source files with a bounded public facade and private internal implementation;
* a public error type implementing `Display` and `std::error::Error`;
* one bounded generic or trait-based abstraction when justified;
* focused unit or integration tests for public behavior and error paths;
* learner explanations of API, abstraction, error, and Rust common-concept choices;
* Student Validation results if code is created or modified;
* Codex Repository Validation report if code is created or modified;
* Teacher Learning Validation summary;
* Sprint-20 closure package if the sprint is completed.

No artifact is created merely by accepting or storing this roadmap.

## 10. Validation Requirements

### Student Validation

Student Validation is required if Sprint-20 creates or modifies a learning repository.

Expected commands for the preferred Rust crate:

* `cargo fmt --check`
* `cargo check`
* `cargo test`

The learner should run local self-checks before requesting formal repository validation.

### Codex Repository Validation

Codex Repository Validation is required if Sprint-20 creates or modifies a learning repository.

Formal Codex Repository Validation is not optional when a learning repository is created or modified and used as Sprint-20 completion evidence.

Codex validation should inspect one repository only and should report:

1. Validation target and repository root.
2. Files inspected.
3. Changed files.
4. Scope compliance.
5. Public API and module-boundary compliance.
6. Trait/generic usage and whether it is bounded and justified.
7. Public error type, `Display`, and `std::error::Error` implementation.
8. Test coverage for success and error behavior.
9. Commands run.
10. Compiler and test results.
11. Risks or gaps.
12. Final verdict.

Codex must not be asked to implement the learning project by default.

If Sprint-20 is completed without repository changes, Codex Repository Validation for a learning project is not applicable, and the closure must state why.

### Teacher Learning Validation

Teacher Learning Validation is always required.

Teacher Learning Validation must verify:

* public API contract reasoning;
* internal versus external boundary reasoning;
* trait/generic tradeoff reasoning;
* ability to identify over-abstraction;
* error contract reasoning;
* `Display` and `std::error::Error` understanding;
* error kind versus message distinction;
* source-level type, mutability, expression, and control-flow reasoning;
* preservation of ownership, borrowing, modules, encapsulation, and testing discipline.

Passing tests or receiving Codex PASS does not automatically satisfy Teacher Learning Validation.

## 11. Codex Repository Validation Expectations

If a learning crate is created or modified, the Teacher must generate a separate Codex validation prompt after learner self-check.

The validation prompt should target only the Sprint-20 learning repository.

Codex should report:

* repository root;
* files inspected;
* Git status and changed files;
* commands run;
* compiler and test results;
* scope compliance;
* whether non-goal topics leaked into the implementation;
* whether public API, trait/generic, and error-contract requirements are demonstrated;
* whether tests validate the sprint's core behavior;
* risks or gaps;
* final verdict.

Governance repository validation and learning-project validation must remain separate.

## 12. Teacher Learning Validation Expectations

At sprint closure, the Teacher must explicitly state:

* what was reviewed;
* what the learner correctly understood;
* what remains weak or requires reinforcement;
* whether each checkpoint passes;
* whether the final Sprint-20 learning verdict is PASS, PASS WITH NOTES, or not yet pass;
* whether Sprint-20 should count as completed Stage 2.5 progress within its scope.

Teacher validation should specifically evaluate whether the learner can explain engineering contracts and tradeoffs, not only whether the code is correct.

## 13. Completion Criteria

Sprint-20 may be completed only when:

1. The learner can explain public API as a caller-facing contract.
2. The learner can justify what is public, what is private, and why.
3. The learner can design or evaluate one bounded trait/generic abstraction and explain why it is not over-abstracted.
4. The learner can identify at least one place where a concrete type is better than a generic or trait-based design.
5. The learner can implement and explain a public error type using `Display` and `std::error::Error`.
6. The learner can distinguish error kind, structured context, display message, and optional source chaining.
7. The learner can explain Rust expression, mutability, type, and control-flow choices in the source design.
8. The learner preserves modules, encapsulation, tests, ownership, and borrowing discipline.
9. Student Validation passes if a learning repository was created or modified.
10. Codex Repository Validation passes if a learning repository was created or modified.
11. Teacher Learning Validation passes or passes with notes.
12. No explicit non-goal becomes part of the required sprint scope.

## 14. Closure Requirements

Sprint-20 closure should record:

* final sprint status;
* checkpoint results;
* Student Validation result or not-applicable rationale;
* Codex Repository Validation result or not-applicable rationale;
* Teacher Learning Validation result;
* completed learning objectives;
* remaining reinforcement notes;
* scope and non-goal compliance;
* impact on Stage 2.5 P1 coverage;
* whether Sprint-20 appears sufficient to proceed to a separate Stage 2.5 exit review;
* whether Stage 2.5 remains incomplete until that separate review;
* whether Stage 3 remains unauthorized;
* recommended next action without authorizing Stage 3 transition.

The closure document should be repository-ready English if persisted.

## 15. Notes For Stage 2.5 Exit Review After Sprint-20

If Sprint-20 closes as PASS or PASS WITH NOTES, the recommended next governance action is a separate Stage 2.5 exit review.

That exit review should inspect:

* the Rust Core Coverage Matrix;
* Sprint-17 closure evidence;
* Sprint-18 closure evidence;
* Sprint-19 closure evidence;
* Sprint-20 closure evidence;
* remaining reinforcement notes;
* whether all P0 and P1 pre-Stage-3 requirements are covered or acceptably placed;
* whether Stage 3 Blockchain Foundations can begin without major Rust fundamentals risk.

Sprint-20 closure may provide the final missing teaching evidence for Stage 2.5, but it must not itself authorize Stage 3 transition.

Stage 3 may begin only after a separate governance decision confirms that Stage 2.5 exit criteria are satisfied or that any remaining gaps are explicitly accepted or placed.
