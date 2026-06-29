# Stage 2.5 Unit 1 — Rust Core Fluency

## 1. Proposal Identity

- Document type: Bridge-unit roadmap proposal
- Status: Approved as the drafting basis for `roadmaps/sprint-16.md`; superseded as the active roadmap
- Current stage: Stage 2.5 — Rust Core Philosophy Bridge (proposal placement only)
- Durable active repository stage at drafting: Stage 2 — Rust Engineering
- Current sprint: None active
- Sprint-15: PASS WITH NOTES / CLOSED
- Sprint-16: Execution stopped before completion; partial unvalidated progress; not complete or closed
- Sprint-17: PASS WITH NOTES / CLOSED under a separate completion boundary
- Execution status: No current execution
- Stage 3 transition: Not authorized
- Source specification: `reviews/stage-2-5-bridge-specification.md`
- Coverage reference: `reviews/rust-core-coverage-matrix.md`

This document records the source proposal that the learner approved as the basis for `roadmaps/sprint-16.md`. Sprint-16 execution later began and was stopped before completion. The formal roadmap remains the authoritative Sprint-16 scope record. Sprint-17 later established a separate completion boundary and independently validated the Rust Core Fluency topic group. This supports topic-level coverage for closures and iterators, systematic pattern matching, and collection ownership behavior, but it does not complete Sprint-16, the original Unit 1 execution boundary, or Stage 2.5.

## 2. Purpose

Unit 1 focuses on Rust core fluency before deeper ownership topology and lifetime work and before blockchain-specific complexity.

Its primary purpose is to improve idiomatic Rust reading, reasoning, and writing through:

- closures;
- iterators;
- pattern matching;
- collection ownership behavior.

The intended progression is from “can complete guided bounded projects” toward “can read, reason about, and write more ordinary idiomatic Rust.”

This unit should connect syntax to ownership behavior, API choices, control flow, and readability. It should not become passive chapter completion or a survey of disconnected Rust features.

## 3. Stage 2.5 Alignment

This proposal addresses the Rust Core Fluency portion of `Stage 2.5 — Rust Core Philosophy Bridge`.

At proposal time, it directly responded to coverage matrix findings that:

- closures and iterators are a P0 gap;
- systematic pattern matching is a P1 gap;
- collection selection, borrowing, mutation, and transformation need P1 reinforcement.

Sprint-17 later supplied validated evidence for these Rust Core Fluency topics, and the coverage matrix now records them as covered sufficiently for the current curriculum point. Remaining Stage 2.5 work is unchanged by this proposal document.

Unit 1 does not complete all Stage 2.5 requirements. In particular, it does not complete explicit lifetime reasoning, ownership topology, smart pointers, deeper interior mutability, or engineering-contract consolidation.

At proposal time, completion of a future authorized Unit 1 was expected to prepare the learner for Unit 2 — Ownership Topology And Lifetimes. It would not by itself have authorized Unit 2 or Stage 3.

## 4. Proposed Learning Outcomes

After future authorized execution and validation, the learner should be able to:

1. Read closure-heavy and iterator-heavy Rust without treating adapter chains as opaque syntax.
2. Explain how shared borrowing, mutable borrowing, and ownership transfer affect closure capture.
3. Explain the conceptual difference among `Fn`, `FnMut`, and `FnOnce` without implementing advanced closure traits.
4. Choose intentionally among `iter`, `iter_mut`, and `into_iter` based on ownership and mutation needs.
5. Read and construct bounded iterator pipelines using common adapters and `collect`.
6. Compare loops and iterator pipelines using clarity, ownership, control-flow, and maintainability tradeoffs.
7. Use patterns to destructure structs, enums, tuples, and references.
8. Explain refutable versus irrefutable patterns and why exhaustive matching matters.
9. Make borrow-versus-own choices around `Vec`, `String`, slices, `HashMap`, and `HashSet`.
10. Explain collection mutation and transformation behavior at source level.

## 5. Proposed Topic Scope

### 5.1 Closures

Proposed coverage:

- closure syntax and parameter inference;
- capture by shared borrow, mutable borrow, or move;
- `move` closures at a bounded conceptual level;
- `Fn`, `FnMut`, and `FnOnce` as behavior determined by how captured values are used;
- ownership and borrowing inside closures;
- closures passed to iterator adapters;
- when a closure is clearer than a small named helper function;
- when a named helper function communicates intent better;
- reading closure-heavy code and tracing captured state.

The unit should teach capture behavior through concrete source examples and prediction. It should not require manual implementation of the closure traits or advanced generic callback APIs.

### 5.2 Iterators

Proposed coverage:

- iterators as lazy processing abstractions;
- the distinction among `iter`, `iter_mut`, and `into_iter`;
- common adapters including `map`, `filter`, `find`, `any`, and `all`;
- transformation and collection through `collect`;
- ownership and borrowing through iterator pipelines;
- mutation through iterator items where appropriate;
- loop-versus-iterator tradeoffs;
- when iterator style improves clarity and composability;
- when a loop is clearer because state, early exits, or branching would make a chain obscure;
- reading adapter chains from source input to final consumer.

Examples should preserve the lazy-versus-consuming distinction and should require the learner to identify the item type and ownership state at important pipeline steps.

### 5.3 Pattern Matching

Proposed coverage:

- `match`;
- `if let`;
- `while let` where repeated refutable matching provides a natural example;
- `let ... else` for early-exit validation where appropriate;
- destructuring structs, enums, tuples, and references;
- refutable and irrefutable patterns;
- basic match guards;
- exhaustive thinking;
- using explicit variants and branches to represent valid and invalid states;
- choosing among `match`, `if let`, and `let ... else` based on intent.

The unit should emphasize pattern matching as a control-flow and state-modeling tool, not as syntax memorization.

### 5.4 Collection Ownership Behavior

Proposed coverage:

- `Vec<T>` ownership, borrowing, slicing, and mutation;
- `String` versus `&str` at API boundaries;
- slices as borrowed views;
- `HashMap<K, V>` lookup, entry-oriented mutation, and transformation;
- `HashSet<T>` membership and duplicate detection;
- borrow-versus-own choices around collection APIs;
- mutation during iteration and the borrowing constraints it creates;
- transforming one collection shape into another;
- selecting a collection based on behavior rather than habit;
- explaining when cloning is necessary, avoidable, or an acceptable tradeoff.

Collection work should reinforce ownership reasoning without expanding into a broad algorithms or data-structures course.

## 6. Teaching And Learning Model

Future execution should preserve the project-driven learning model.

Each checkpoint should normally use this sequence:

1. Introduce a short problem or source-reading context.
2. Introduce only the concepts needed to reason about that context.
3. Ask the learner to predict ownership, control flow, or output behavior.
4. Use a small bounded implementation or rewrite exercise.
5. Require source-level explanation and tradeoff comparison.
6. Record Teacher Learning Validation evidence before advancing.

Teaching requirements:

- technical teaching should be primarily in Chinese under the current language policy;
- professional terminology should remain precise and stable;
- validation questions should test reasoning, consequence, contrast, and diagnosis rather than recall;
- code examples should follow a clear problem or context;
- the learner should receive meaningful thinking time before hints or solutions;
- examples should be incremental rather than a near-final implementation;
- tests should validate meaningful behavior and must not be used as filler;
- the unit should not be divided into one mini-sprint per Rust Book chapter.

## 7. Proposed Checkpoints

### Checkpoint 1 — Iterator And Collection Reading

Focus:

- read ordinary loops and equivalent iterator pipelines;
- compare readability and control flow;
- distinguish `iter`, `iter_mut`, and `into_iter`;
- trace item types, borrowing, mutation, and ownership transfer;
- transform bounded `Vec`, slice, `HashMap`, and `HashSet` inputs.

Proposed learner work:

- annotate what each loop or adapter consumes and produces;
- rewrite selected loops into iterator form;
- rewrite selected dense iterator chains into clearer loops;
- explain why one version is preferable for the specific case;
- implement a few bounded collection transformations.

Validation focus:

- the learner explains ownership behavior rather than only producing equivalent output;
- the learner recognizes iterator laziness and the role of consumers such as `collect`, `find`, `any`, or `all`;
- the learner can defend a loop-versus-iterator choice.

### Checkpoint 2 — Closure Capture And Transformation

Focus:

- closure syntax and inference;
- shared-borrow, mutable-borrow, and move capture;
- closures inside iterator adapters;
- conceptual `Fn`, `FnMut`, and `FnOnce` behavior;
- closure versus helper-function choices.

Proposed learner work:

- predict capture behavior in concrete examples;
- diagnose bounded borrow or move errors involving closures;
- use closures in collection filtering and transformation;
- explain how closure behavior constrains repeated calls;
- compare an inline closure with a named helper function.

Validation focus:

- the learner connects closure behavior to ownership of captured values;
- the learner can explain whether a closure may be called repeatedly or consumes captured state when called;
- the learner can read closure-heavy code without relying on trial and error alone.

### Checkpoint 3 — Pattern Matching Fluency

Focus:

- `match`, `if let`, and `let ... else`;
- `while let` only where it gives a natural repeated-matching example;
- destructuring structs, enums, tuples, and references;
- refutability, guards, and exhaustive matching;
- matching as explicit state modeling.

Proposed learner work:

- read and explain nested but bounded patterns;
- replace branch-heavy code with an appropriate pattern form;
- identify missing or overly broad branches;
- use destructuring to expose only the data needed by a branch;
- compare `match`, `if let`, and `let ... else` for a concrete problem.

Validation focus:

- the learner explains why the selected pattern form communicates intent;
- the learner identifies exhaustive and non-exhaustive state handling;
- the learner can reason about borrowing or moves caused by a pattern.

### Checkpoint 4 — Integrated Fluency Exercise

Focus:

- combine iterators, closures, pattern matching, and collection ownership;
- solve one small bounded domain problem;
- preserve clarity rather than maximizing feature density;
- explain ownership and control-flow tradeoffs.

Proposed learner work:

- transform a collection of domain values into a filtered or grouped result;
- use pattern matching to make state branches explicit;
- use closures and iterator adapters where they improve clarity;
- retain loops where they express the logic more clearly;
- use `HashSet` for a genuine membership or duplicate-detection requirement;
- explain API inputs and outputs as owned values or borrowed views;
- identify at least one valid alternative design and its tradeoff.

Validation focus:

- the learner integrates the topics without being given a complete solution shape;
- the implementation remains small and readable;
- explanations cover capture, iteration mode, matching, collection choice, and ownership boundaries;
- passing tests are supporting evidence, not a substitute for explanation.

## 8. Candidate Exercise And Repository Shapes

The following options record the proposal-stage alternatives. A subsequent learner decision selected Option A for the formal Sprint-16 roadmap, and the project was created during authorized execution.

### Option A — New `rust_core_fluency_lab` Library Crate

Possible domain shape:

- a small collection of tagged activity or event records;
- filtering and transforming records;
- grouping or indexing selected values;
- explicit enum-state handling;
- duplicate detection with `HashSet`;
- borrowed query inputs and owned output summaries.

Proposed repository name:

`rust_core_fluency_lab`

Proposed file layout:

- `Cargo.toml`;
- `src/lib.rs`;
- `src/model.rs`;
- `src/transform.rs`;
- `tests/fluency.rs`, only if public-boundary integration tests add value.

Proposed test range:

`6 to 8 focused tests`

Tests should cover meaningful transformations, state branches, duplicate handling, and ownership-visible API behavior. They should not test every adapter or pattern individually.

### Option B — Bounded Existing-Project Extension

A small extension of an existing learning project may be considered only after the learner selects the project and explicitly approves its modification.

Any such extension should:

- add one cohesive fluency-oriented workflow rather than unrelated exercises;
- avoid changing the original project's completed-learning record;
- define its file changes and test range in the accepted execution roadmap;
- remain subject to separate learning-project validation.

No existing project was selected. Option B was not carried into the formal Sprint-16 roadmap.

## 9. Future Validation Proposal

No learning validation or repository validation is executed by creating this draft.

If execution is later approved, proposed Student Validation should include:

- `cargo fmt --check`;
- `cargo check`;
- `cargo test`;
- review of iterator item and ownership behavior;
- review of whether pattern branches are explicit and exhaustive where required;
- identification of known blocking and non-blocking issues.

Proposed Teacher Learning Validation should confirm that the learner can:

1. Explain the ownership differences among `iter`, `iter_mut`, and `into_iter`.
2. Explain concrete closure capture behavior and the relevant conceptual `Fn`, `FnMut`, or `FnOnce` constraint.
3. Read and explain iterator pipelines from source collection to consumer.
4. Choose between loops and iterator chains using tradeoff reasoning.
5. Use patterns to destructure enums, structs, tuples, and references.
6. Explain refutability, exhaustiveness, and basic guard behavior.
7. Explain how collection ownership affects API design.
8. Explain mutation and borrowing constraints during collection iteration.
9. Defend collection selection and any cloning decisions.
10. Integrate the topics in a bounded exercise without relying on a supplied near-final answer.

Codex Repository Validation should occur only if future approved execution modifies a real learning-project repository. That validation must be separate from governance-repository validation and should check scope, source, tests, and required commands without replacing Teacher Learning Validation.

## 10. Proposed Completion Criteria

If execution is separately approved, Unit 1 should be considered complete only when:

- all four checkpoints are completed;
- the learner demonstrates both source-reading and implementation fluency;
- the learner explains ownership behavior in iterator and closure examples;
- the learner uses and explains systematic pattern matching;
- collection choices and borrow-versus-own boundaries are intentional;
- loop-versus-iterator choices are justified by clarity and behavior;
- tests, if code is authorized, remain focused and tied to the learning contract;
- Student Validation passes for any modified learning repository;
- required Codex Repository Validation passes or has only explicitly accepted non-blocking notes;
- Teacher Learning Validation passes;
- explicit non-goals remain respected.

These criteria are a proposal. They do not create an active completion contract until the roadmap is accepted for execution.

## 11. Explicit Non-Goals

Unit 1 excludes:

- Stage 3 blockchain concepts;
- Solana;
- async Rust or Tokio;
- threads or channels;
- `Arc<T>` or `Mutex<T>`;
- deep lifetime coverage;
- smart-pointer topology involving `Box<T>`, `Rc<T>`, `Weak<T>`, or `RefCell<T>` beyond incidental references needed to read code;
- trait objects or `dyn Trait`;
- unsafe Rust;
- macro authoring;
- large framework design;
- production CLI tooling such as `clap`;
- one mini-sprint per Rust Book chapter;
- broad test expansion or tests used as filler.

These topics belong to later bridge units or later stages unless separately approved.

## 12. Relationship To Unit 2

Unit 1 should establish enough closure, iterator, pattern, and collection fluency that Unit 2 can focus on ownership topology and lifetimes without simultaneously teaching ordinary Rust control-flow idioms from scratch.

Unit 2 remains only a recommended bridge direction in the source specification. This proposal does not draft, scope, or authorize Unit 2.

## 13. Relationship To Sprint-16

This proposal file is not the formal Sprint-16 roadmap.

The learner subsequently approved Unit 1 as Sprint-16 and authorized creation of the formal roadmap at `roadmaps/sprint-16.md`.

Sprint-16 execution stopped before completion. Sprint-16 is not complete or closed, and its progress remains partial and unvalidated.

The learner accepted the expanded distribution in `reviews/stage-2-5-remaining-coverage-review.md` and later completed Sprint-17 with PASS WITH NOTES. Sprint-17 evidence belongs to its separate completion boundary and does not change Sprint-16 completion state or retroactively complete the original Unit 1 execution boundary.

The existing `/Users/dumplings/workspace/rust_core_fluency_lab` project is not inspected, validated, or modified by this governance update.

## 14. Explicit Non-Authorization Statement

This proposal synchronization does not:

- mark Sprint-16 complete or closed;
- create a Sprint-16 closure;
- validate or modify the learning project;
- mark Unit 1 complete;
- authorize Unit 2;
- complete Stage 2.5;
- authorize Stage 3 transition;
- modify any learning-project repository.

Final proposal status: Approved as the drafting basis and superseded by `roadmaps/sprint-16.md`. Sprint-16 stopped before completion with partial unvalidated progress. Sprint-17 later validated the Rust Core Fluency topic group separately; Stage 2.5 remains incomplete.
