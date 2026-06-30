# Rust Core Coverage Matrix

## 1. Identity And Status

- Document type: Rust Core Coverage Matrix
- Status: Governance planning reference
- Current stage: Stage 2 - Rust Engineering
- Current sprint: None
- Sprint-15: PASS WITH NOTES / CLOSED
- Sprint-16: Execution stopped before completion; partial unvalidated progress; not complete or closed
- Sprint-17: PASS WITH NOTES / CLOSED
- Stage 2.5: Required bridge before Stage 3; partially completed and still in progress at the curriculum level
- Unit 1 proposal: `roadmaps/stage-2-5-unit-1-rust-core-fluency.md`; approved as drafting basis
- Unit 1 formal roadmap: `roadmaps/sprint-16.md`; partial unvalidated execution evidence; no topic completed under the Sprint-16 boundary
- Remaining-coverage review: `reviews/stage-2-5-remaining-coverage-review.md`; planning artifact; no classification change
- Sprint-17 roadmap and closure: `roadmaps/sprint-17.md` and `reviews/sprint-17-closure.md`; validated durable evidence for Rust Core Fluency topics
- Source audit: `reviews/rust-curriculum-coverage-audit.md`
- Post-midpoint decision: `reviews/stage-2-post-midpoint-review.md`
- Primary external baseline: [The Rust Programming Language](https://doc.rust-lang.org/book/)

This matrix records topic-level governance state for Stage 2.5 decisions after Sprint-17 closure. It is not a sprint roadmap, implementation plan, or stage authorization.

## 2. Purpose

This file maps Rust core topic coverage to durable repository evidence, audit classification, priority, recommended handling, validation method, and Stage 3 entry impact.

Future Architects and Teachers should use this matrix with the source audit, current `CONTEXT.md`, and `TODO.md` instead of reconstructing curriculum coverage from chat history.

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
| Variables / data types / functions / control flow | Partially covered; reinforce | P1 | Used throughout all completed Rust projects. | Usage is largely implicit; no durable assessment maps Rust-specific expression, mutability, type, and control-flow semantics. | Include explicit coverage or evidence review in the approved pre-Stage-3 plan. | Source-level explanation, small contrast exercises, and compiler-error reasoning. | Must be covered or explicitly planned before Stage 3. |
| Ownership / borrowing / moves / references / slices | Partially covered; reinforce | P0 | Stage 1 Exit Assessment PASS; Sprint-13 through Sprint-15 reinforced API-boundary ownership; Sprint-14 directly validated value/reference choices. | Mental-model depth remains weak around reference copy semantics, aliasing, indirection, mutation, and cleanup topology. | The approved Stage 2.5 bridge direction must assign explicit mental-model reinforcement and transfer validation through a separate specification. | Learner explanation, source-level ownership tracing, compiler-error prediction, bounded code exercises, and Teacher Learning Validation. | Blocks Stage 3 decision until coverage and validation handling are approved. |
| Structs / methods / encapsulation | Covered sufficiently for now | P1 | `task_tracker`, `devlog_cli`, `rust_mechanics_lab`, and `rust_engineering_assessment` used private fields, constructors, methods, accessors, and controlled mutation. | Risk is regression rather than missing exposure. | Maintain through future approved project design. | Public API review, invariant reasoning, and focused behavior tests. | No independent block; preserve demonstrated capability. |
| Enums and basic matching | Covered sufficiently for now | P1 | Earlier enum/error modeling plus Sprint-17 validated intentional use of `match`, `if let`, `let ... else`, `while let`, destructuring, guards, and exhaustiveness. | Matching borrowed enum fields without accidentally moving non-`Copy` fields still needs reinforcement. | Maintain through normal source reading and future approved Rust work. | Source review, ownership explanation for borrowed patterns, and focused exhaustive/non-exhaustive matching exercises. | Sprint-17 resolves the current basic-matching coverage requirement; retain reinforcement. |
| Modules / privacy / crates / public APIs | Covered sufficiently for now | P1 | Stage 1 Exit Assessment explicitly passed module organization, visibility, crate boundaries, and public API basics; later sprints reinforced crate facades. | Later projects must preserve rather than assume the capability. | Maintain through architecture and public-surface review. | Codex scope/API validation plus learner explanation of `pub`, `pub(crate)`, private items, and crate boundaries. | No independent block; retain evidence in future work. |
| Collections and strings | Covered sufficiently for now | P1 | Earlier projects used `Vec`, `String`, `HashMap`, `HashSet`, slices, and entry APIs; Sprint-17 directly validated collection selection, iteration ownership, borrowed-input/owned-output transformations, duplicate detection, counting/grouping, and clone decisions. | `HashSet<T>` versus `HashSet<&T>` semantic choices and automatic iterator fluency still need reinforcement. | Maintain through future approved work and revisit owned-versus-borrowed set elements when a concrete API requires the choice. | Small comparative exercises, ownership explanation, and focused behavior tests. | Sprint-17 resolves the current collection-ownership coverage requirement; retain reinforcement. |
| Error handling | Covered sufficiently for now | P1 | Strong evidence for `Result`, `?`, `From`, `map_err`, custom errors, public error kinds, and context-aware boundaries. | `Display`, `std::error::Error`, structured context, and library error ergonomics remain incomplete. | Maintain current capability and add the recorded public-error ergonomics reinforcement. | Source/API review, error-chain explanation, success/error tests, and Teacher Learning Validation. | Public-error ergonomics should be covered or planned before Stage 3. |
| Generics / traits / static dispatch | Partially covered; reinforce | P1 | Sprint-13 introduced a minimal storage trait/generic boundary; Sprint-14 validated bounds, static dispatch, and monomorphization; Sprint-15 assessed practical judgment. | Evidence is limited to small behavior traits and functions; broader type/method design and tradeoffs remain weak. | Assign broader but bounded generic/trait reasoning in the approved pre-Stage-3 plan. | Design comparison, generic ownership tracing, source-level explanation, and focused implementation/tests when authorized. | Must be covered or explicitly planned before Stage 3. |
| Lifetimes | Explicitly deferred | P0 | Initial `reviews/rust-baseline-assessment.md` recorded basic understanding; Sprint-14 and Sprint-15 explicitly excluded deep lifetime work. | No later project-level validation shows explicit lifetime relationships or annotation reasoning. | The approved Stage 2.5 bridge direction must assign explicit lifetime coverage and validation through a separate specification. | Reference-relationship diagrams, signature explanation, compiler-error diagnosis, and bounded lifetime exercises. | Blocks Stage 3 decision until coverage and validation handling are approved. |
| Testing | Covered sufficiently for now | P1 | Unit, integration, workflow, state-transition, persistence, and fake-storage tests exist across completed projects. | Some file/storage paths and public contracts remain lightly tested. | Maintain focused testing tied to learning objectives; avoid broad expansion as filler. | Student Validation, Codex Repository Validation, and learner explanation of what each test proves. | No independent block; preserve focused testing capability. |
| CLI project structure | Partially covered; reinforce | P2 | `wallet_cli` used a thin binary and library-side command workflow; later projects preserved thin `main.rs`. | Environment variables, stderr behavior, full argument tooling, and production CLI ergonomics were deferred. | Place in Stage 3/4 only when an approved project needs a stronger CLI boundary. | End-to-end CLI behavior, library/binary responsibility review, and focused command tests. | No Stage 3 entry block; retain a future placement decision. |
| Closures and iterators | Covered sufficiently for now | P0 | Sprint-17 completed and validated iterator ownership, borrowed and owned collection APIs, closure parameters and captures, mutable closure bindings, conceptual `Fn` / `FnMut` / `FnOnce`, iterator pipelines, helper-versus-closure choices, and loop-versus-iterator tradeoffs. | No `move` closure appears in source, although move capture passed conceptual Teacher validation; iterator-and-closure combinations are understood but not yet automatic. | Maintain through normal approved Rust work and reinforce capture and adapter fluency without reopening Sprint-17. | Learner explanation, source-level ownership tracing, loop-versus-iterator comparison, bounded transformations, and focused tests. | The closures/iterators P0 topic is resolved for the current curriculum point; deeper ownership and lifetime P0 topics still block Stage 3. |
| Cargo ecosystem practices | Partially covered; reinforce | P2 | `Cargo.toml`, dependency selection, `serde`, and `serde_json` were covered in Sprint-12 onward. | Workspaces, release profiles, documentation, publishing, `cargo clippy`, and wider ecosystem workflow are not durably planned. | Schedule only the job-relevant subset during Stage 3/4 or portfolio preparation. | Tool-use demonstration and explanation of dependency/workspace/release decisions. | No Stage 3 entry block; track for later engineering readiness. |
| `Box<T>` / `Deref` / `Drop` | Missing / not planned | P1 | No durable coverage evidence or assigned plan was found. | Missing heap indirection, recursive-type, deref coercion, and deterministic cleanup mental models. | Include in an approved pre-Stage-3 smart-pointer and ownership-topology plan. | Concept explanation, memory/ownership diagrams, bounded exercises, and source-level review. | Must be covered or explicitly planned before Stage 3. |
| `Rc<T>` / `Weak<T>` / shared ownership | Explicitly deferred | P1 | Sprint-14 and Sprint-15 excluded `Rc<RefCell<T>>`; no `Weak<T>` evidence exists. | Missing single-threaded shared ownership, cycle risk, and non-owning references. | Include with smart-pointer topology before Stage 3; keep reference-cycle scope bounded. | Ownership-count tracing, cycle/`Weak<T>` explanation, bounded exercises, and tests when authorized. | Must be covered or explicitly planned before Stage 3. |
| `RefCell<T>` / interior mutability | Partially covered; reinforce | P1 | Sprint-14 validated a fake recorder using runtime borrow checking; Sprint-15 and `TODO.md` preserve reinforcement needs. | Initial explanation required correction; comparison with ordinary `&mut self`, runtime borrow failure, and composition with shared ownership remain incomplete. | Reinforce with explicit contrast and boundary reasoning in the approved pre-Stage-3 plan. | Source comparison, borrow-guard explanation, scenario selection, and focused tests. | Must be covered or explicitly planned before Stage 3. |
| Threads / channels / `Mutex<T>` / `Send` / `Sync` | Explicitly deferred | P2 | Sprint-14 excluded threading and concurrency primitives; later work did not supersede the exclusion. | Missing Rust ownership transfer across threads, message passing, shared-state synchronization, and marker-trait reasoning. | Assign before substantial backend or concurrent client work in Stage 3/4. | Thread/channel exercises, synchronization reasoning, compiler diagnostics, and focused tests when authorized. | No Stage 3 entry block; placement must precede work that depends on concurrency. |
| `Arc<T>` / shared-state concurrency | Explicitly deferred | P2 | Sprint-14 and Sprint-15 explicitly excluded `Arc<Mutex<T>>`. | Missing thread-safe shared ownership and the relationship among `Arc`, `Mutex`, `Send`, and `Sync`. | Cover with concurrency before substantial multi-threaded or client/backend work. | Ownership/synchronization diagrams, bounded shared-state exercise, and race-safety explanation. | No Stage 3 entry block; required before dependent Stage 4/backend work. |
| Async / await / futures / runtimes | Explicitly deferred | P2 | Async Rust and Tokio were repeatedly excluded in Stage 1 and Stage 2 roadmaps. | Missing futures, polling, task/runtime boundaries, async borrowing, cancellation, and async error handling. | Assign during Stage 3/4 before approved networking, RPC, or Solana client work needs it. | Async workflow explanation, bounded runtime exercise, compiler/test validation, and source review. | No Stage 3 entry block; required before dependent networking/client work. |
| Trait objects / dynamic dispatch | Explicitly deferred | P2 | Sprint-13 excluded trait-object deep dives; Sprint-14 confirmed no `dyn Trait`. | Missing object safety, vtable/dynamic dispatch tradeoffs, and heterogeneous behavior collections. | Schedule when a Stage 3/4 design provides a real need; compare with enums and static dispatch. | Design comparison, object-safety diagnosis, bounded example, and source-level explanation. | No Stage 3 entry block; retain a future placement decision. |
| Advanced patterns and matching | Covered sufficiently for now | P1 | Sprint-17 directly validated struct, enum, tuple, and borrowed destructuring; refutable and irrefutable patterns; guards; exhaustiveness; and intentional selection among `match`, `if let`, `let ... else`, and `while let`. | Borrowed enum-field matching and binding ownership require continued reinforcement. | Maintain through source reading and future approved project work; reinforce borrowed-pattern ownership when relevant. | Pattern-reading exercises, exhaustive match design, ownership explanation, and bounded behavior tests. | Sprint-17 resolves the current systematic-pattern coverage requirement; retain reinforcement. |
| Unsafe Rust / macros / advanced language features | Not urgent for current job-readiness target | P3 | `serde` derive use provides macro consumption exposure; no substantive unsafe, macro-authoring, advanced-trait, or advanced-type coverage exists. | Specialist APIs may be difficult to read later, but immediate implementation skill is not required. | Treat as reference literacy and add only when a concrete project or dependency requires it. | Documentation-guided explanation and narrowly scoped review or experiment. | No Stage 3 entry block. |

## 5. P0 Status Before Stage 3

The P0 set and current resolution status are:

1. Deeper ownership and borrowing mental model
   - aliasing and mutation;
   - moves and reference relationships;
   - indirection and cleanup;
   - owned values versus borrowed views;
   - reference copy semantics;
   - source-level ownership tracing.
2. Explicit lifetime reasoning
   - relationships among input and output references;
   - lifetime annotations as relationship descriptions;
   - compiler diagnostics;
   - bounded project use rather than syntax memorization.
3. Closures and iterators - covered sufficiently for now by Sprint-17
   - closure capture, iterator ownership, iterator pipelines, transformation, collection, and loop tradeoffs were validated;
   - source-level `move` closure use and automatic adapter fluency remain reinforcement notes rather than current blockers.

Sprint-17 resolves the closures-and-iterators P0 topic for the current curriculum point. Deeper ownership and borrowing plus explicit lifetime reasoning remain unresolved P0 blockers. No Stage 3 transition is authorized.

## 6. P1 Before Stage 3

The following P1 areas should be covered or placed in an approved pre-Stage-3 plan:

- smart pointers: `Box<T>`, `Rc<T>`, `Weak<T>`, `Deref`, and `Drop`;
- deeper `RefCell<T>` and interior mutability reasoning;
- broader generic and trait design;
- public error traits and library error ergonomics;
- Rust-specific common concept reinforcement where durable evidence is currently implicit;
- continued preservation of modules, APIs, testing, and encapsulation capability.

Sprint-17 resolves systematic pattern matching and collection ownership behavior for the current curriculum point. Their recorded reinforcement notes do not reopen Sprint-17 or replace the remaining P1 work above.

P1 planning should consolidate related concepts into cohesive learning units. It should not create one sprint per Rust book chapter or use tests as filler.

The Stage 2 Post-Midpoint Review approved Stage 2.5 as the bridge direction and planning layer for P1 organization. A separate specification or roadmap-review proposal is still required before implementation or sprint planning.

## 7. Stage 2.5 Relationship

`Stage 2.5 — Rust Core Philosophy Bridge` is approved as the required bridge direction and planning layer before Stage 3.

The approved direction may organize:

- ownership topology and Rust systems philosophy;
- stack, heap, allocation, and indirection;
- aliasing, mutation, and cleanup;
- `Box<T>`, `Rc<T>`, `Weak<T>`, and `RefCell<T>`;
- compile-time and runtime borrow checking;
- the conceptual transition toward `Arc<T>`, `Mutex<T>`, `Send`, and `Sync`.

Stage 2.5 does not replace the wider coverage matrix. Sprint-17 now supplies validated placement and evidence for closures, iterators, patterns, and collection ownership. Generic/trait breadth, errors, Cargo practices, concurrency, async, and other unresolved topics retain their matrix classifications and placement requirements.

Stage 2.5 is now represented in `roadmaps/master-roadmap.md` as the required high-level bridge before Stage 3. That representation did not itself authorize implementation, Sprint-16, or Stage 3 transition.

`roadmaps/sprint-16.md` formalized the original Unit 1 coverage and validation shape. Sprint-16 produced partial, unvalidated execution evidence before being stopped prior to completion and remains incomplete and unclosed.

Sprint-17 established a separate completion boundary and produced validated evidence for closures and iterators, systematic pattern matching, and collection ownership behavior. It did not complete Sprint-16 or Stage 2.5. Deeper ownership and borrowing, explicit lifetimes, smart pointers, deeper `RefCell<T>`, and engineering-contract consolidation remain future Stage 2.5 work.

## 8. Matrix Maintenance Rules

- Use local repository evidence as the authoritative source for status changes.
- Do not mark a topic covered merely because syntax appeared incidentally.
- Do not treat one successful sprint as permanent mastery.
- Update classification only after validated learning evidence or an explicit governance decision.
- Record the roadmap, review, learning log, or assessment that supports each status change.
- Keep P2 and P3 topics visible even when they are not current transition blockers.
- Maintain the matrix after the Stage 2 Post-Midpoint Review and review it before any future Stage 3 transition decision.
- Keep governance planning separate from learning-project implementation and validation.

## 9. Explicit Non-Authorization Statement

This matrix and the Sprint-17 closure synchronization do not:

- mark Sprint-16 or Unit 1 complete;
- perform learning-project validation or modify `rust_core_fluency_lab`;
- authorize later Stage 2.5 units;
- authorize further Master Roadmap changes;
- authorize Stage 3 transition;
- perform learning-project creation, implementation, or curriculum execution in this governance update;
- invalidate completed Sprint-12 through Sprint-15 learning progress;
- modify any learning-project repository.

Sprint-16 execution stopped before completion. Student Validation and Teacher Learning Validation remain incomplete for Sprint-16, and formal Codex Repository Validation was not performed under the Sprint-16 boundary.

Sprint-17 independently completed all four of its checkpoints and all three validation layers. Sprint-17 evidence changes the classifications for closures and iterators, systematic pattern matching, and collection ownership behavior only.

Stage 2.5 remains incomplete based on the unresolved coverage recorded above. Sprint lifecycle and transition authorization are owned by `CONTEXT.md`, the sprint governance policy, and any accepted current roadmap; this coverage ledger does not define or synchronize those states.
