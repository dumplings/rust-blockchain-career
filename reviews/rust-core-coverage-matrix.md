# Rust Core Coverage Matrix

## 1. Identity And Status

- Document type: Rust Core Coverage Matrix
- Status: Governance planning reference
- Coverage scope: Stage 2 and Stage 2.5 Rust-core coverage ledger
- Current stage, active sprint state, and authorization boundary: see `CONTEXT.md`
- Stage 3 planning may be prepared; this matrix does not authorize Stage 3 learning execution
- Sprint-15: PASS WITH NOTES / CLOSED
- Sprint-16: Execution stopped before completion; partial unvalidated progress; not complete or closed
- Sprint-17: PASS WITH NOTES / CLOSED
- Sprint-18: PASS WITH NOTES / CLOSED
- Sprint-19: PASS WITH NOTES / CLOSED
- Sprint-20: PASS WITH NOTES / CLOSED
- Stage 2.5: PASS WITH NOTES / COMPLETE after formal exit review
- Unit 1 proposal: `roadmaps/archive/stage-2-5-unit-1-rust-core-fluency.md`; approved as drafting basis
- Unit 1 formal roadmap: `roadmaps/archive/sprint-16.md`; partial unvalidated execution evidence; no topic completed under the Sprint-16 boundary
- Remaining-coverage review: `reviews/archive/planning/stage-2-5-remaining-coverage-review.md`; planning artifact; no classification change
- Sprint-17 roadmap and closure: `roadmaps/archive/sprint-17.md` and `reviews/sprint-17-closure.md`; validated durable evidence for Rust Core Fluency topics
- Sprint-18 roadmap and closure: `roadmaps/archive/sprint-18.md` and `reviews/sprint-18-closure.md`; validated durable evidence for ownership, borrowing, and lifetime reasoning
- Sprint-19 roadmap and closure: `roadmaps/archive/sprint-19.md` and `reviews/sprint-19-closure.md`; validated durable evidence for smart pointers, interior mutability, and ownership-topology tradeoffs
- Sprint-20 roadmap and closure: `roadmaps/archive/sprint-20.md` and `reviews/sprint-20-closure.md`; validated durable evidence for engineering-contract reasoning, bounded traits/generics, public APIs, public error ergonomics, and Rust common-concept reinforcement
- Stage 2.5 exit review: `reviews/stage-2-5-exit-review.md`; formal completion decision and deferred/carry-forward placement
- Source audit: `reviews/archive/planning/rust-curriculum-coverage-audit.md`
- Post-midpoint decision: `reviews/archive/planning/stage-2-post-midpoint-review.md`
- Primary external baseline: [The Rust Programming Language](https://doc.rust-lang.org/book/)

This matrix records topic-level governance state after the formal Stage 2.5 exit review. It is not a sprint roadmap, implementation plan, universal mastery ledger, or learning-execution authorization.

## 2. Purpose

This file maps Rust core topic coverage to durable repository evidence, audit classification, priority, recommended handling, validation method, and Stage 3 entry impact.

Future Architects and Teachers should use this matrix with the source audit and
current `CONTEXT.md` instead of reconstructing curriculum coverage from chat
history.

Recommended handling describes the governance treatment that a future approved review should consider. It does not authorize a sprint, implementation task, learning project, or stage transition.

## 3. Classification Legend

### Coverage Classification

- Covered sufficiently for now: durable evidence is adequate for the current point in the curriculum, but later reinforcement may still be appropriate.
- Partially covered; reinforce: meaningful evidence exists, but breadth, depth, transfer, or validation remains incomplete.
- Explicitly deferred: prior roadmap scope deliberately excluded the topic and no later completion superseded that deferral.
- Missing / not planned: no durable coverage evidence or approved future placement was found.
- Not urgent for current job-readiness target: useful material that is not a current transition priority.

### Priority

- P0 blocking before Stage 3: the coverage and validation decision must be resolved before any Stage 3 transition.
- P1 should cover before Stage 3: the topic should be covered or placed in an approved pre-Stage-3 plan.
- P2 can cover during Stage 3/4: the topic may be scheduled during Stage 3 or Stage 4 before the relevant engineering work requires it.
- P3 optional / later: specialist or infrequent material that can be handled when a concrete need appears.

## 4. Coverage Matrix

| Topic | Classification | Priority | Existing evidence | Gap / risk | Recommended handling | Validation method | Stage 3 entry impact |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Cargo and project basics | Covered sufficiently for now | P1 | Fresh projects and repeated `cargo fmt`, `cargo check`, and `cargo test` evidence in `learning-log.md` and Sprint closures. | Broader tooling is tracked separately under Cargo ecosystem practices. | Maintain through normal approved project work. | Successful tool commands plus learner explanation of crate targets and project structure. | No independent block; retain routine evidence. |
| Variables / data types / functions / control flow | Covered sufficiently for now | P1 | Used throughout completed Rust projects; Sprint-20 explicitly validated expression-oriented design, immutable input, mutability boundaries, type choices, control flow, and ownership/borrowing reasoning in a public library API. | Fluency still requires reinforcement in future source reading and domain work. | Maintain through normal approved project work and source-level explanation. | Source-level explanation, contrast exercises, compiler-error reasoning, and Teacher Learning Validation. | Sprint-20 resolves the explicit common-concept reinforcement requirement for the current curriculum point. |
| Ownership / borrowing / moves / references / slices | Covered sufficiently for now | P0 | Stage 1 Exit Assessment PASS; Sprint-13 through Sprint-15 reinforced API-boundary ownership; Sprint-14 directly validated value/reference choices; Sprint-18 validated ownership as resource discipline, borrowing as controlled access, source-level topology tracing, aliasing versus mutation, and reference copy/exclusivity semantics. | Precise owner wording, input/output origin tracing, and source-first borrow-diagnostic triage still need reinforcement. | Maintain through approved Rust work and compare ordinary borrowing with smart-pointer topology when later scope requires it. | Learner explanation, source-level ownership tracing, compiler-error prediction, bounded API repair, and Teacher Learning Validation. | Sprint-18 resolves this P0 topic for the current curriculum point; the exit review confirms no current Stage 3 planning block. |
| Structs / methods / encapsulation | Covered sufficiently for now | P1 | `task_tracker`, `devlog_cli`, `rust_mechanics_lab`, and `rust_engineering_assessment` used private fields, constructors, methods, accessors, and controlled mutation. | Risk is regression rather than missing exposure. | Maintain through future approved project design. | Public API review, invariant reasoning, and focused behavior tests. | No independent block; preserve demonstrated capability. |
| Enums and basic matching | Covered sufficiently for now | P1 | Earlier enum/error modeling plus Sprint-17 validated intentional use of `match`, `if let`, `let ... else`, `while let`, destructuring, guards, and exhaustiveness. | Matching borrowed enum fields without accidentally moving non-`Copy` fields still needs reinforcement. | Maintain through normal source reading and future approved Rust work. | Source review, ownership explanation for borrowed patterns, and focused exhaustive/non-exhaustive matching exercises. | Sprint-17 resolves the current basic-matching coverage requirement; retain reinforcement. |
| Modules / privacy / crates / public APIs | Covered sufficiently for now | P1 | Stage 1 Exit Assessment passed module organization, visibility, crate boundaries, and public API basics; Sprint-20 explicitly validated a crate-root facade, private modules, public types with private fields, and concrete caller-facing behavior. | Public `NormalizedRecord::new` weakens a possible normalized-only invariant and remains a reinforcement note. | Maintain through architecture and public-surface review; narrow constructors when a type promises a validated invariant. | Codex scope/API validation plus learner explanation of `pub`, `pub(crate)`, private items, constructors, and crate boundaries. | Sprint-20 strengthens durable public-contract evidence; no independent block remains for the current curriculum point. |
| Collections and strings | Covered sufficiently for now | P1 | Earlier projects used `Vec`, `String`, `HashMap`, `HashSet`, slices, and entry APIs; Sprint-17 directly validated collection selection, iteration ownership, borrowed-input/owned-output transformations, duplicate detection, counting/grouping, and clone decisions. | `HashSet<T>` versus `HashSet<&T>` semantic choices and automatic iterator fluency still need reinforcement. | Maintain through future approved work and revisit owned-versus-borrowed set elements when a concrete API requires the choice. | Small comparative exercises, ownership explanation, and focused behavior tests. | Sprint-17 resolves the current collection-ownership coverage requirement; retain reinforcement. |
| Error handling | Covered sufficiently for now | P1 | Earlier work established `Result`, `?`, `From`, `map_err`, custom errors, public error kinds, and context-aware boundaries; Sprint-20 validated a public error type and kind, `Display`, `std::error::Error`, kind-versus-message separation, and source-chaining judgment. | Source chaining remains conceptual because the validation-rule error has no lower-level source; the public normalized-record constructor leaves an API-invariant note. | Maintain through real library boundaries and reinforce source chaining when lower-level IO, parse, or external-format errors are wrapped. | Source/API review, error-chain explanation, success/error tests, Codex validation, and Teacher Learning Validation. | Sprint-20 resolves public-error ergonomics for the current curriculum point; this is not permanent mastery. |
| Generics / traits / static dispatch | Covered sufficiently for now | P1 | Sprint-13 introduced a storage trait/generic boundary; Sprint-14 validated bounds, static dispatch, and monomorphization; Sprint-20 validated an internal `NamedInput` trait, private bounded generic helper, concrete public facade, and abstraction tradeoff reasoning. | The one-implementation trait would likely be over-abstraction outside this bounded learning exercise; abstraction heuristics need continued semantic-boundary reinforcement. | Maintain through future concrete-versus-generic design comparisons and require a stable capability reason before adding abstraction. | Design comparison, generic ownership tracing, source-level explanation, focused implementation/tests, and Teacher Learning Validation. | Sprint-20 resolves broader bounded generic/trait reasoning for the current curriculum point. |
| Trait method resolution and trait-in-scope requirements | Partially covered; reinforce | P2 | Prior work established traits as behavior contracts, bounds, and static dispatch. Sprint-22 provided bounded reinforcement through `sha2` / `Digest`, trait-in-scope requirements, method resolution, and method-call versus fully qualified syntax / UFCS discussion and use. Broader external-API fluency remains carry-forward. | External-library usage can hide why an import enables method or associated-function syntax and can turn an unstated Rust prerequisite into domain-learning friction. | Continue just-in-time reinforcement before future dependent external-crate or API work; retain as carry-forward rather than a separate sprint by default. | Source comparison, small compiler-diagnostic exercise, method-call versus fully qualified syntax explanation, and Teacher source-level review. | No Stage 3 entry block, no Rust restart trigger, and no independent blocker by default; reinforce before dependent library use. |
| Lifetimes | Covered sufficiently for now | P0 | Initial `reviews/archive/planning/rust-baseline-assessment.md` recorded basic understanding; Sprint-18 validated input/output reference relationships, bounded elision, meaningful explicit annotations, invalid local-reference escape, compiler diagnostics, and borrowed-versus-owned API tradeoffs. | Lifetime annotations, input names, output origins, and the fact that annotations do not extend runtime value lifetimes still need precise reinforcement. | Maintain through future source reading and approved API design without reopening Sprint-18 or expanding into advanced lifetime syntax by default. | Reference-relationship diagrams, signature explanation, compiler-error diagnosis, bounded API repair, and Teacher Learning Validation. | Sprint-18 resolves this P0 topic for the current curriculum point; the exit review confirms no current Stage 3 planning block. |
| Testing | Covered sufficiently for now | P1 | Unit, integration, workflow, state-transition, persistence, and fake-storage tests exist across completed projects. | Some file/storage paths and public contracts remain lightly tested. | Maintain focused testing tied to learning objectives; avoid broad expansion as filler. | Student Validation, Codex Repository Validation, and learner explanation of what each test proves. | No independent block; preserve focused testing capability. |
| CLI project structure | Partially covered; reinforce | P2 | `wallet_cli` used a thin binary and library-side command workflow; later projects preserved thin `main.rs`. | Environment variables, stderr behavior, full argument tooling, and production CLI ergonomics were deferred. | Place in Stage 3/4 only when an approved project needs a stronger CLI boundary. | End-to-end CLI behavior, library/binary responsibility review, and focused command tests. | No Stage 3 entry block; retain a future placement decision. |
| Closures and iterators | Covered sufficiently for now | P0 | Sprint-17 completed and validated iterator ownership, borrowed and owned collection APIs, closure parameters and captures, mutable closure bindings, conceptual `Fn` / `FnMut` / `FnOnce`, iterator pipelines, helper-versus-closure choices, and loop-versus-iterator tradeoffs. | No `move` closure appears in source, although move capture passed conceptual Teacher validation; iterator-and-closure combinations are understood but not yet automatic. | Maintain through normal approved Rust work and reinforce capture and adapter fluency without reopening Sprint-17. | Learner explanation, source-level ownership tracing, loop-versus-iterator comparison, bounded transformations, and focused tests. | This P0 topic is resolved for the current curriculum point; the exit review confirms no current Stage 3 planning block. |
| Cargo ecosystem practices | Partially covered; reinforce | P2 | `Cargo.toml`, dependency selection, `serde`, and `serde_json` were covered in Sprint-12 onward. | Workspaces, release profiles, documentation, publishing, `cargo clippy`, and wider ecosystem workflow are not durably planned. | Schedule only the job-relevant subset during Stage 3/4 or portfolio preparation. | Tool-use demonstration and explanation of dependency/workspace/release decisions. | No Stage 3 entry block; track for later engineering readiness. |
| `Box<T>` / `Deref` / `Drop` | Covered sufficiently for now | P1 | Sprint-19 validated `Box<T>` owned indirection, custom `Deref<Target = str>`, deref coercion, ownership-chain tracing, and deterministic ownership-end reasoning through explicit `drop` behavior. | No custom `Drop` implementation was created, and the private `BoxedLabel` concept surface produces dead-code warnings in a normal library build. | Maintain through approved Rust work and reinforce cleanup reasoning when a real resource-lifecycle boundary appears. | Concept explanation, ownership tracing, bounded source exercises, focused tests, Codex validation, and Teacher Learning Validation. | Sprint-19 resolves this P1 topic for the current curriculum point; this is not permanent mastery. |
| `Rc<T>` / `Weak<T>` / shared ownership | Covered sufficiently for now | P1 | Sprint-19 validated single-threaded shared ownership, `Rc::clone`, strong counts, `Weak::downgrade`, `Weak::upgrade`, absence handling, non-owning semantics, and bounded cycle-risk reasoning. | Cycle-breaking reasoning is validated through Teacher discussion but remains lightly preserved in project source and tests. | Maintain through future approved ownership-topology work without expanding into production graph design by default. | Ownership-count tracing, cycle/`Weak<T>` explanation, focused behavior tests, Codex validation, and Teacher Learning Validation. | Sprint-19 resolves this P1 topic for the current curriculum point; this is not permanent mastery. |
| `RefCell<T>` / interior mutability | Covered sufficiently for now | P1 | Sprint-14 introduced runtime borrowing through a fake recorder; Sprint-19 validated interior mutability, `Ref` and `RefMut` guards, runtime borrow failure, and preference for ordinary `&mut` when sufficient. | More complex composition with shared ownership remains a future reinforcement topic rather than a current independent blocker. | Maintain through future approved Rust work and require explicit justification whenever interior mutability is chosen. | Source comparison, guard-lifetime explanation, controlled failure tests, design-choice reasoning, Codex validation, and Teacher Learning Validation. | Sprint-19 resolves this P1 topic for the current curriculum point; this is not permanent mastery. |
| Threads / channels / `Mutex<T>` / `Send` / `Sync` | Explicitly deferred | P2 | Sprint-14 excluded threading and concurrency primitives; later work did not supersede the exclusion. | Missing Rust ownership transfer across threads, message passing, shared-state synchronization, and marker-trait reasoning. | Assign before substantial backend or concurrent client work in Stage 3/4. | Thread/channel exercises, synchronization reasoning, compiler diagnostics, and focused tests when authorized. | No Stage 3 entry block; placement must precede work that depends on concurrency. |
| `Arc<T>` / shared-state concurrency | Explicitly deferred | P2 | Sprint-14 and Sprint-15 explicitly excluded `Arc<Mutex<T>>`. | Missing thread-safe shared ownership and the relationship among `Arc`, `Mutex`, `Send`, and `Sync`. | Cover with concurrency before substantial multi-threaded or client/backend work. | Ownership/synchronization diagrams, bounded shared-state exercise, and race-safety explanation. | No Stage 3 entry block; required before dependent Stage 4/backend work. |
| Async / await / futures / runtimes | Explicitly deferred | P2 | Async Rust and Tokio were repeatedly excluded in Stage 1 and Stage 2 roadmaps. | Missing futures, polling, task/runtime boundaries, async borrowing, cancellation, and async error handling. | Assign during Stage 3/4 before approved networking, RPC, or Solana client work needs it. | Async workflow explanation, bounded runtime exercise, compiler/test validation, and source review. | No Stage 3 entry block; required before dependent networking/client work. |
| Trait objects / dynamic dispatch | Explicitly deferred | P2 | Sprint-13 excluded trait-object deep dives; Sprint-14 confirmed no `dyn Trait`. | Missing object safety, vtable/dynamic dispatch tradeoffs, and heterogeneous behavior collections. | Schedule when a Stage 3/4 design provides a real need; compare with enums and static dispatch. | Design comparison, object-safety diagnosis, bounded example, and source-level explanation. | No Stage 3 entry block; retain a future placement decision. |
| Advanced patterns and matching | Covered sufficiently for now | P1 | Sprint-17 directly validated struct, enum, tuple, and borrowed destructuring; refutable and irrefutable patterns; guards; exhaustiveness; and intentional selection among `match`, `if let`, `let ... else`, and `while let`. | Borrowed enum-field matching and binding ownership require continued reinforcement. | Maintain through source reading and future approved project work; reinforce borrowed-pattern ownership when relevant. | Pattern-reading exercises, exhaustive match design, ownership explanation, and bounded behavior tests. | Sprint-17 resolves the current systematic-pattern coverage requirement; retain reinforcement. |
| Unsafe Rust / macros / advanced language features | Not urgent for current job-readiness target | P3 | `serde` derive use provides macro consumption exposure; no substantive unsafe, macro-authoring, advanced-trait, or advanced-type coverage exists. | Specialist APIs may be difficult to read later, but immediate implementation skill is not required. | Treat as reference literacy and add only when a concrete project or dependency requires it. | Documentation-guided explanation and narrowly scoped review or experiment. | No Stage 3 entry block. |

## 5. P0 Status Before Stage 3

The P0 set and current resolution status are:

1. Deeper ownership and borrowing mental model — covered sufficiently for now by Sprint-18
   - aliasing and mutation;
   - moves and reference relationships;
   - indirection and cleanup;
   - owned values versus borrowed views;
   - reference copy semantics;
   - source-level ownership tracing.
2. Explicit lifetime reasoning — covered sufficiently for now by Sprint-18
   - relationships among input and output references;
   - lifetime annotations as relationship descriptions;
   - compiler diagnostics;
   - bounded project use rather than syntax memorization.
3. Closures and iterators - covered sufficiently for now by Sprint-17
   - closure capture, iterator ownership, iterator pipelines, transformation, collection, and loop tradeoffs were validated;
   - source-level `move` closure use and automatic adapter fluency remain reinforcement notes rather than current blockers.

Sprint-17 resolves the closures-and-iterators P0 topic for the current curriculum point. Sprint-18 resolves deeper ownership and borrowing plus explicit lifetime reasoning for the current curriculum point.

All identified P0 Rust-core topics are covered sufficiently for the current curriculum point. This does not imply permanent mastery. The formal exit review records Stage 2.5 as complete with notes; Stage 3 planning remains separate from learning-execution authorization.

## 6. P1 Before Stage 3

Sprint-20 supplies validated evidence for the P1 areas that remained after Sprint-19:

- broader generic and trait design is covered sufficiently for the current curriculum point through a bounded internal capability trait, private generic helper, static dispatch, concrete public facade, and explicit over-abstraction analysis;
- public error traits and library error ergonomics are covered sufficiently for the current curriculum point through a public error type and kind, `Display`, `std::error::Error`, kind-versus-message separation, and source-chaining judgment;
- Rust-specific common concepts received explicit source-level reinforcement through expression, mutability, type, control-flow, ownership, and borrowing reasoning;
- modules, public APIs, testing, and encapsulation capability were preserved and explicitly validated.

Sprint-17 resolves systematic pattern matching and collection ownership behavior for the current curriculum point. Its recorded reinforcement notes do not reopen those topics.

Sprint-18 resolves the previously open P0 ownership, borrowing, and lifetime topics for the current curriculum point. Its reinforcement notes do not reopen those topics.

Sprint-19 resolves smart pointers and deeper interior-mutability reasoning for the current curriculum point. Its source-preservation, warning, and repository-hygiene notes remain reinforcement items and do not reopen those topics.

Sprint-20 resolves the remaining engineering-contract P1 work for the current curriculum point. Its constructor-invariant, source-chaining, test-boundary, abstraction-heuristic, and repository-hygiene notes remain reinforcement items rather than independent blockers.

All identified P0 and P1 pre-Stage-3 topics are covered sufficiently for the current curriculum point. The formal Stage 2.5 exit review evaluated the complete evidence and recorded `PASS WITH NOTES / STAGE 2.5 COMPLETE`. This matrix does not imply permanent mastery or authorize Stage 3 learning execution.

## 7. Stage 2.5 Relationship

`Stage 2.5 — Rust Core Philosophy Bridge` is complete with notes after the formal exit review.

The approved direction may organize:

- ownership topology and Rust systems philosophy;
- stack, heap, allocation, and indirection;
- aliasing, mutation, and cleanup;
- `Box<T>`, `Rc<T>`, `Weak<T>`, and `RefCell<T>`;
- compile-time and runtime borrow checking;
- the conceptual transition toward `Arc<T>`, `Mutex<T>`, `Send`, and `Sync`.

Stage 2.5 does not replace the wider coverage matrix. Sprint-17 supplies validated evidence for closures, iterators, patterns, and collection ownership. Sprint-18 supplies validated evidence for deeper ownership, borrowing, and explicit lifetime reasoning. Sprint-19 supplies validated evidence for smart pointers, interior mutability, and ownership-topology tradeoffs. Sprint-20 supplies validated evidence for bounded trait/generic design, public API and error contracts, and Rust common-concept reinforcement. P2, P3, contextual topics, and ordinary reinforcement items remain carry-forward dependencies under the exit review.

Stage 2.5 is now represented in `roadmaps/master-roadmap.md` as the required high-level bridge before Stage 3. That representation did not itself authorize implementation, Sprint-16, or Stage 3 transition.

`roadmaps/archive/sprint-16.md` formalized the original Unit 1 coverage and validation shape. Sprint-16 produced partial, unvalidated execution evidence before being stopped prior to completion and remains incomplete and unclosed.

Sprint-17 established a separate completion boundary and produced validated evidence for closures and iterators, systematic pattern matching, and collection ownership behavior. It did not complete Sprint-16 or Stage 2.5.

Sprint-18 established a separate completion boundary and produced validated Teacher Learning evidence for deeper ownership, borrowing, and explicit lifetime reasoning without creating a learning project. It did not complete Sprint-16 or Stage 2.5. At that point, smart pointers, deeper `RefCell<T>`, broader traits and generics, public error ergonomics, and engineering-contract consolidation remained future or placement-required Stage 2.5 work.

Sprint-19 established a separate completion boundary and produced validated Student, Codex Repository, and Teacher Learning evidence for smart pointers, deeper `RefCell<T>`, and ownership-topology tradeoffs. It did not complete Sprint-16 or Stage 2.5. At that point, broader traits and generics, public error ergonomics, Rust-specific common-concept reinforcement, and engineering-contract consolidation remained future or placement-required Stage 2.5 work.

Sprint-20 established a separate completion boundary and produced validated Student, Codex Repository, and Teacher Learning evidence for broader bounded trait/generic design, public API contracts, public error ergonomics, and Rust common-concept reinforcement. It did not complete Sprint-16 by implication. The later formal Stage 2.5 exit review evaluated Sprint-17 through Sprint-20 together and recorded bridge completion with notes.

## 8. Matrix Maintenance Rules

- Use local repository evidence as the authoritative source for status changes.
- Do not mark a topic covered merely because syntax appeared incidentally.
- Do not treat one successful sprint as permanent mastery.
- Update classification only after validated learning evidence or an explicit governance decision.
- Record the roadmap, review, learning log, or assessment that supports each status change.
- Keep P2 and P3 topics visible even when they are not current transition blockers.
- Maintain the matrix after the Stage 2 Post-Midpoint Review and review it before any future Stage 3 transition decision.
- Keep governance planning separate from learning-project implementation and validation.

## 9. Exit Status And Authority Boundary

The formal exit decision is owned by `reviews/stage-2-5-exit-review.md`. This matrix records that decision but does not:

- mark Sprint-16 or Unit 1 complete;
- perform learning-project validation or modify any learning project;
- authorize further Master Roadmap changes;
- create, accept, activate, or start a Stage 3 roadmap or sprint;
- authorize Stage 3 learning execution;
- perform learning-project creation, implementation, or curriculum execution in this governance update;
- invalidate completed Sprint-12 through Sprint-15 learning progress;
- modify any learning-project repository.

Sprint-16 execution stopped before completion. Student Validation and Teacher Learning Validation remain incomplete for Sprint-16, and formal Codex Repository Validation was not performed under the Sprint-16 boundary.

Sprint-17 independently completed all four of its checkpoints and all three validation layers. Sprint-17 evidence changes the classifications for closures and iterators, systematic pattern matching, and collection ownership behavior only.

Sprint-18 independently completed all four checkpoints and Teacher Learning Validation. Student Validation and Codex Repository Validation for a learning project were not applicable because no learning-project code or repository was created or modified. Sprint-18 evidence changes the classifications for ownership, borrowing, and lifetimes only.

Sprint-19 independently completed all five checkpoints, Student Validation, Codex Repository Validation, and Teacher Learning Validation. Sprint-19 evidence changes the classifications for smart pointers and interior mutability only.

Sprint-20 independently completed all four checkpoints, Student Validation, Codex Repository Validation, and Teacher Learning Validation. Sprint-20 evidence updates broader traits/generics, public API and error contracts, and Rust common-concept reinforcement for the current curriculum point.

Stage 2.5 is complete with notes. Deferred P2/P3, contextual topics, and ordinary reinforcement remain carry-forward work rather than exit blockers. Sprint lifecycle and execution authorization are owned by `CONTEXT.md`, the sprint governance policy, and explicit learner decisions; this coverage ledger does not authorize Stage 3 learning execution.
