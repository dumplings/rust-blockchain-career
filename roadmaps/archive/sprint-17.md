# Sprint-17 — Stage 2.5 Remaining Rust Core Fluency And Pattern Matching Consolidation

## 1. Sprint Identity

- Sprint number: Sprint-17
- Sprint title: `Stage 2.5 Remaining Rust Core Fluency And Pattern Matching Consolidation`
- Sprint status: Accepted / ready for Teacher execution
- Execution status: Not started
- Authorization status: Accepted for future Teacher execution, but not yet executed
- Current active sprint: None
- Stage relationship: Stage 2.5 — Rust Core Philosophy Bridge
- Previous sprint state: Sprint-16 stopped before completion / partial unvalidated progress
- Sprint-16 closure: None
- Preferred learning project: `/Users/dumplings/workspace/rust_core_fluency_lab`
- Project status for Sprint-17: Existing partial, unvalidated material; not inspected or modified during roadmap drafting
- Source planning review: `reviews/archive/planning/stage-2-5-remaining-coverage-review.md`
- Coverage reference: `reviews/rust-core-coverage-matrix.md`
- Stage 3 transition: Not authorized

Post-execution status note: the identity and authorization language in this roadmap records the accepted pre-execution boundary. Sprint-17 later completed and closed with PASS WITH NOTES; `reviews/sprint-17-closure.md` is the authoritative completion record. That separate Sprint-17 completion boundary does not complete or close Sprint-16, complete the original Unit 1 execution boundary, complete Stage 2.5, or authorize Stage 3 transition.

The learner accepted this roadmap before execution. Recording acceptance makes Sprint-17 ready for a future Teacher execution window but does not start Sprint-17, modify or validate the learning project, complete Sprint-16, or authorize Stage 3 transition.

## 2. Sprint Purpose

Sprint-17 is a normally sized Stage 2.5 sprint for remaining Rust Core Fluency and pattern matching consolidation.

It is not a continuation of Sprint-16. Sprint-16 remains stopped before completion, not closed, and without completion credit.

Sprint-17 should:

- briefly revalidate the iterator and collection work recorded as partial Sprint-16 progress;
- complete project-applied closure capture and transformation learning;
- make systematic pattern matching the main new learning focus;
- integrate iterators, closures, patterns, and collection ownership in one bounded exercise.

Deep lifetime reasoning, ownership topology, and smart-pointer topology remain assigned to later Stage 2.5 planning.

## 3. Stage Alignment And Learning Density

Sprint-17 addresses the unfinished Rust Core Fluency portion of Stage 2.5 without absorbing the later lifetime, smart-pointer, or engineering-contract units.

The sprint preserves normal workload through four connected checkpoints:

1. a short diagnostic revalidation gate;
2. closure consolidation in project context;
3. systematic pattern matching;
4. one bounded integrated exercise and final validation cycle.

Learning density should come from source reading, prediction, implementation, explanation, and focused validation. The sprint must avoid both compressing multiple later Stage 2.5 topic groups into one roadmap and fragmenting each syntax form into a separate lesson.

## 4. Relationship To Sprint-16

Sprint-16 recorded partial, unvalidated progress in iterator and collection work and partially introduced closure capture concepts.

Sprint-17 does not inherit Sprint-16 completion credit.

The Sprint-16 material is handled through an internal Sprint-17 revalidation gate:

- it is not a Sprint-16 continuation;
- it is not a separate sprint;
- it does not reopen Sprint-16;
- it does not close Sprint-16;
- it grants no automatic coverage credit;
- it establishes whether short reinforcement is needed before new Sprint-17 work.

Only evidence produced and validated under the accepted Sprint-17 completion boundary may count toward Sprint-17 completion.

## 5. Learning Project Choice

Preferred project target:

`/Users/dumplings/workspace/rust_core_fluency_lab`

This project was created during authorized Sprint-16 execution. Its existing code is partial, unvalidated material.

Sprint-17 may continue using it because:

- the domain is already aligned with iterators, closures, patterns, and collection ownership;
- retaining a bounded lab avoids unnecessary project churn;
- future work can focus on learning transfer instead of project setup;
- the Sprint-17 roadmap defines a new completion and validation boundary.

Before implementation, the future Teacher must conduct a brief source-level review with the learner to establish:

- what code currently exists;
- which behavior the learner can explain;
- which source is retained, revised, or replaced;
- how the existing modules support the Sprint-17 scope;
- which tests already exist and what they prove.

That review occurs only during future Sprint-17 Teacher execution. This governance acceptance update does not inspect, validate, or modify the project.

If the source-level review shows that continuing the project would obscure the learning goals, the Teacher should stop and request a separate governance decision before selecting a new project. The Teacher must not silently change the project target.

## 6. Learning Objectives

By the end of an authorized Sprint-17 execution, the learner should be able to:

1. Explain `iter`, `iter_mut`, and `into_iter` item ownership and borrowing differences.
2. Explain when borrowed slices, mutable slices, and owned vectors are appropriate API inputs.
3. Explain why a `String` or non-`Copy` enum may need to be cloned from borrowed data when producing owned output.
4. Explain closure parameters versus captured variables.
5. Explain shared-borrow, mutable-borrow, and move capture in concrete examples.
6. Explain why a closure binding may need to be mutable.
7. Explain conceptual `Fn`, `FnMut`, and `FnOnce` through how captured values are used.
8. Use closures inside iterator pipelines without treating them as opaque syntax.
9. Compare closures with named helper functions.
10. Use `match`, `if let`, `let ... else`, and natural `while let` intentionally.
11. Destructure structs, enums, tuples, and references.
12. Explain refutable patterns, irrefutable patterns, guards, and exhaustiveness.
13. Choose loops or iterator chains based on clarity, ownership, mutation, and control flow.
14. Integrate iterators, closures, patterns, and collection ownership in one bounded exercise.

## 7. Required Scope

### 7.1 Iterator And Collection Revalidation

Required diagnostic boundary:

- `iter`, `iter_mut`, and `into_iter`;
- borrowed slices such as `&[T]`;
- mutable borrowed slices such as `&mut [T]`;
- owned `Vec<T>` workflows;
- `HashSet` duplicate detection;
- `HashMap` counting or grouping;
- owned output from borrowed inputs;
- cloning `String` or non-`Copy` enum state when justified;
- loops for mutation-heavy logic;
- item ownership in small source examples.

### 7.2 Closure Consolidation

Required coverage:

- closure parameters versus captured variables;
- shared-borrow capture;
- mutable-borrow capture;
- mutable closure bindings such as `let mut bump = || { count += 1; };`;
- move capture;
- conceptual `Fn`, `FnMut`, and `FnOnce`;
- closures inside iterator pipelines;
- closure versus named helper-function tradeoffs;
- project-applied closure transformation work.

### 7.3 Pattern Matching Fluency

Required coverage:

- `match`;
- `if let`;
- `let ... else`;
- natural `while let`;
- destructuring structs;
- destructuring enums;
- destructuring tuples;
- destructuring references;
- refutable and irrefutable patterns;
- match guards;
- exhaustive state handling;
- choosing an appropriate pattern form for a concrete problem.

### 7.4 Integrated Fluency

The final exercise must combine:

- iterators;
- closures;
- pattern matching;
- collection ownership;
- `HashSet` or `HashMap`;
- owned output versus borrowed input;
- clone decisions;
- loop-versus-iterator tradeoffs.

The implementation should remain small and readable.

## 8. Required Learner Decisions

During Sprint-17, the learner must make and explain at least these decisions:

1. Whether an API accepts `&[T]`, `&mut [T]`, or `Vec<T>`.
2. Whether a workflow should use `iter`, `iter_mut`, or `into_iter`.
3. Whether an owned output requires a clone from borrowed data.
4. Whether a closure captures by shared borrow, mutable borrow, or move.
5. Whether an inline closure or named helper function communicates intent better.
6. Whether `match`, `if let`, `let ... else`, or `while let` best expresses the control flow.
7. Whether a loop or iterator pipeline is clearer for a mutation or transformation.
8. Whether `HashSet`, `HashMap`, or `Vec` matches the required behavior.

The Teacher should evaluate the learner's reasoning rather than dictate a design and ask for retrospective justification.

## 9. Checkpoint Sequence

Sprint-17 must proceed checkpoint by checkpoint. The Teacher should pause for questions and source-level review before advancing.

### Checkpoint 1 — Sprint-16 Partial Progress Revalidation Gate

Purpose:

Before new Sprint-17 work begins, test whether the learner can still explain and apply the content recorded as partial Sprint-16 progress.

This checkpoint must be short and diagnostic, not a full re-teaching pass.

The Teacher should use a small set of focused source-reading, prediction, and explanation questions covering:

- `iter`, `iter_mut`, and `into_iter`;
- borrowed and mutable slices;
- owned `Vec<T>` workflows;
- `HashSet` duplicate detection;
- `HashMap` counting or grouping;
- justified cloning from borrowed records;
- loop clarity for mutation-heavy logic;
- iterator item ownership.

Expected learner work:

- explain item types and ownership in small examples;
- predict whether values are borrowed, mutably borrowed, or moved;
- choose a collection and iteration style for a bounded scenario;
- explain one justified clone decision;
- explain when a loop is clearer than an iterator chain.

If gaps appear, the Teacher should provide short targeted reinforcement before advancing. Sprint-17 must not restart Sprint-16 from the beginning.

Checkpoint completion criteria:

- learner explanations are source-specific and coherent;
- learner can apply the concepts in a small bounded example;
- any targeted reinforcement is reviewed;
- the gate result is recorded for Sprint-17 learning validation.

Completing this gate alone does not mark any Rust Core Coverage Matrix topic complete.

### Checkpoint 2 — Closure Consolidation In Project Context

Purpose:

Complete closure learning through project-relevant examples and source-level reasoning.

Teaching and learner work should cover:

- distinguish closure parameters from captured variables;
- predict shared-borrow, mutable-borrow, and move capture;
- explain why a closure binding may need to be mutable;
- connect capture behavior to conceptual `Fn`, `FnMut`, and `FnOnce`;
- use closures inside iterator pipelines;
- compare a closure with a named helper function;
- implement a bounded project transformation that requires an intentional capture or callback choice.

Checkpoint completion criteria:

- learner explains capture behavior before relying on compiler trial and error;
- project work demonstrates a meaningful closure transformation;
- closure-versus-helper-function reasoning is explicit;
- conceptual closure traits are explained through use of captured values, not memorized labels.

### Checkpoint 3 — Pattern Matching Fluency

Purpose:

Make systematic pattern matching the main new Sprint-17 learning focus.

Teaching and learner work should cover:

- use `match` for explicit multi-state handling;
- use `if let` for focused single-pattern handling;
- use `let ... else` for a clear early-exit boundary;
- use `while let` only where repeated matching is natural;
- destructure structs, enums, tuples, and references;
- distinguish refutable and irrefutable patterns;
- use basic match guards;
- preserve exhaustive state handling;
- compare pattern forms for concrete project cases.

Checkpoint completion criteria:

- learner selects pattern forms intentionally;
- learner explains ownership or borrowing caused by patterns;
- state branches remain explicit and readable;
- exhaustive and non-exhaustive behavior is understood;
- pattern matching is used as state modeling and control flow, not syntax display.

### Checkpoint 4 — Integrated Rust Core Fluency Exercise

Purpose:

Integrate Sprint-17 concepts in one bounded project exercise.

The exercise should:

- transform or summarize a collection of domain values;
- use a closure inside an iterator pipeline where it improves clarity;
- use pattern matching for meaningful state handling;
- use `HashSet` or `HashMap` for genuine behavior;
- accept borrowed input and produce owned output where appropriate;
- require at least one explicit clone decision;
- require a loop-versus-iterator tradeoff decision;
- expose behavior through a small public library API;
- remain within the existing bounded lab architecture unless a separate decision changes it.

Checkpoint completion criteria:

- implementation is small and readable;
- all topic areas are integrated for behavioral value;
- learner explains ownership, capture, patterns, collections, and control-flow choices;
- focused tests support the integrated behavior;
- Student Validation is prepared before formal repository validation.

## 10. Student Work Expectations

During authorized execution, the learner should:

- remain the primary implementer;
- participate in the initial source-level project review;
- complete the revalidation gate before new implementation work;
- implement bounded closure, pattern, and integration work;
- explain item ownership, capture, clone, pattern, and collection decisions;
- keep source and public API boundaries small;
- write or adjust focused tests tied to behavior;
- avoid over-engineering or unrelated cleanup;
- identify blocking and non-blocking issues before formal validation.

## 11. Testing Requirements

If Sprint-17 continues `rust_core_fluency_lab`, the recommended final total is:

`6 to 10 focused tests`

The exact count may vary slightly if the learner explains why the behavior boundary requires it.

Tests should cover meaningful behavior such as:

- collection filtering or transformation;
- duplicate or membership behavior;
- pattern-based state handling;
- closure-backed transformation where useful;
- integrated behavior through a public API.

Avoid:

- one test per syntax feature;
- broad test inflation;
- tests for every private helper;
- awkward runtime tests for compiler-enforced ownership, closure, or borrowing rules.

Compiler-enforced properties should also be explained at source level.

## 12. Teaching Requirements

The future Teacher should:

- teach technical content primarily in Chinese;
- introduce important Rust terms as English term plus Chinese professional explanation when first used;
- keep normal teaching density;
- avoid both over-compressed concept dumping and over-fragmented low-value teaching;
- start with short source-reading or reasoning contexts;
- teach or frame the relevant concept before asking focused reasoning questions;
- avoid asking the learner to guess hidden concepts or acceptance criteria;
- avoid repeating unnecessary disclaimers;
- keep examples proportionate to the learning objective;
- preserve the learner as the primary implementer;
- use source-level explanation, prediction, diagnosis, and tradeoff questions;
- pause at checkpoint boundaries for questions and review;
- keep governance validation separate from learning-project validation.

The Teacher may provide targeted examples, test expectations, or small skeletons. Near-final core implementation should not be provided before the learner practices the design and implementation work.

## 13. Student Validation

If Sprint-17 modifies or validates `rust_core_fluency_lab`, the learner must eventually run in `/Users/dumplings/workspace/rust_core_fluency_lab`:

- `cargo fmt --check`
- `cargo check`
- `cargo test`

The learner should also review:

- public API and module boundaries;
- iterator item ownership;
- closure capture and clone decisions;
- pattern exhaustiveness;
- test focus and scope;
- known blocking and non-blocking issues.

Student Validation is not performed during roadmap drafting.

## 14. Codex Repository Validation

Formal Codex Repository Validation is required after meaningful Sprint-17 implementation is complete.

Expected validation target:

`/Users/dumplings/workspace/rust_core_fluency_lab`

Codex should inspect the learning-project source, tests, dependency scope, public API, and repository state and run:

- `cargo fmt --check`
- `cargo check`
- `cargo test`

Codex should verify:

- implementation remains within Sprint-17 scope;
- the revalidation and new work are represented by meaningful source and tests;
- closure, pattern, iterator, and collection work is coherent;
- test coverage is focused;
- no out-of-scope lifetime, smart-pointer, blockchain, async, concurrency, persistence, or broad architecture work was added;
- command results pass;
- blocking and non-blocking findings are distinguished.

Codex Repository Validation must remain separate from governance-repository validation and does not replace Teacher Learning Validation.

## 15. Teacher Learning Validation

Teacher Learning Validation is required before Sprint-17 may close.

The Teacher must verify that the learner can explain:

- iterator item ownership;
- borrowed versus owned collection APIs;
- clone decisions;
- closure parameters and captures;
- shared-borrow, mutable-borrow, and move capture;
- mutable closure bindings;
- conceptual `Fn`, `FnMut`, and `FnOnce`;
- closure versus helper-function choices;
- pattern forms and destructuring;
- refutability, guards, and exhaustiveness;
- loop-versus-iterator tradeoffs;
- integrated use of iterators, closures, patterns, and collection ownership.

Validation should use concrete source, prediction, diagnosis, comparison, and tradeoff questions. Passing tests alone is not sufficient to close Sprint-17.

## 16. Completion Criteria

Sprint-17 may be closed only when all of the following are true:

- the learner explicitly accepted this roadmap before execution began;
- all four checkpoints are completed;
- the Sprint-16 partial-progress revalidation gate is completed;
- closure consolidation is completed and validated;
- pattern matching fluency is completed and validated;
- the integrated exercise is completed;
- project scope remains small and aligned with Stage 2.5;
- tests remain focused and meaningful;
- Student Validation passes if learning-project code is modified or used as completion evidence;
- formal Codex Repository Validation passes or has only explicitly accepted non-blocking notes;
- Teacher Learning Validation passes;
- governance and learning-project validation remain separate;
- explicit non-goals are respected;
- a Sprint-17 closure document is created through the approved governance workflow.

Sprint-17 must not be marked complete solely because code compiles or tests pass.

## 17. Explicit Non-Goals

Sprint-17 excludes:

- deep lifetime reasoning;
- explicit lifetime-annotation projects;
- stack-versus-heap topology;
- `Box<T>`;
- `Rc<T>`;
- `Weak<T>`;
- deep `RefCell<T>` or interior mutability;
- `Deref`;
- `Drop`;
- public error-trait consolidation;
- `Display` or `std::error::Error` as a primary topic;
- blockchain;
- Solana;
- async Rust or Tokio;
- threads or channels;
- `Arc<T>` or `Mutex<T>`;
- RPC, networking, wallets, signing, or account models;
- persistence or file IO;
- CLI framework work;
- broad architecture expansion;
- broad test inflation.

These topics remain assigned to later Stage 2.5 or later Stage 3/4 work unless separately authorized.

## 18. Relationship To Later Stage 2.5 Planning

The accepted planning direction recommends:

1. Sprint-17 — Remaining Rust Core Fluency And Pattern Matching Consolidation
2. Sprint-18 — Lifetimes And Borrowing Topology
3. Sprint-19 — Smart Pointers And Interior Mutability
4. Sprint-20 — Engineering Contract Consolidation

Only Sprint-17 has a roadmap and learner acceptance. Sprint-18, Sprint-19, and Sprint-20 remain planning recommendations only. They are not drafted, scoped, accepted, or authorized.

Sprint-17 does not complete Stage 2.5 and does not authorize Stage 3 transition.

## 19. Authorization Boundary

This roadmap has been accepted by the learner and is ready for future Teacher execution.

Sprint-17 execution has not started. Current active sprint remains None.

The next allowed action is to open a Sprint-17 Teacher execution window under this accepted roadmap.

Recording learner acceptance does not:

- start Sprint-17;
- mark Sprint-17 active before the Teacher execution window begins;
- inspect, validate, or modify `rust_core_fluency_lab`;
- continue, complete, or close Sprint-16;
- create a Sprint-16 or Sprint-17 closure;
- draft or authorize Sprint-18, Sprint-19, or Sprint-20;
- complete Unit 1 or mark any coverage topic complete;
- authorize Stage 3 transition.

Next allowed action: open `Sprint-17 Teacher — Stage 2.5 Remaining Rust Core Fluency And Pattern Matching Consolidation` and begin with Checkpoint 1, the Sprint-16 partial-progress revalidation gate.
