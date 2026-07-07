# Stage 2.5 — Rust Core Philosophy Bridge

## 1. Specification Identity

- Specification name: `Stage 2.5 — Rust Core Philosophy Bridge`
- Document type: Bridge specification
- Status: Specification / planning document
- Current stage: Stage 2 - Rust Engineering
- Current active sprint: None
- Sprint-15: PASS WITH NOTES / CLOSED
- Sprint-16: Execution stopped before completion; partial unvalidated progress; not complete or closed
- Stage 3 transition: Not authorized
- Source review: `reviews/archive/planning/stage-2-post-midpoint-review.md`
- Coverage reference: `reviews/rust-core-coverage-matrix.md`
- Source audit: `reviews/archive/planning/rust-curriculum-coverage-audit.md`
- Master Roadmap representation: Recorded through a subsequent approved governance update; not execution authorization

This specification defines the governance boundary and recommended structure of the approved Stage 2.5 bridge direction. It is not a sprint roadmap or implementation authorization.

## 2. Purpose

Stage 2.5 bridges Stage 2 Rust Engineering and Stage 3 Blockchain Foundations by consolidating Rust core philosophy, mental models, idiomatic fluency, and job-readiness coverage before blockchain and Solana complexity is introduced.

Stage 2.5 is not merely a collection of syntax topics. It organizes Rust knowledge as a connected engineering model:

- ownership as resource discipline;
- borrowing as controlled access;
- aliasing XOR mutability;
- lifetimes as reference relationships;
- closures and iterator fluency;
- pattern matching fluency;
- smart pointers as ownership-topology tools;
- `RefCell<T>` as a deliberate escape hatch;
- traits and generics as abstraction tradeoffs;
- public API and error boundaries as contracts;
- safety without garbage collection;
- systems mindset before blockchain.

The intended outcome is stronger transfer, explanation, and source-reading capability, not isolated feature completion.

## 3. Governance Status

`Stage 2.5 — Rust Core Philosophy Bridge` is approved as the required bridge direction and planning layer before Stage 3.

Authorization boundary:

- Stage 2.5 is not an executable sprint.
- This specification does not authorize implementation.
- This specification does not start, draft, scope, or authorize Sprint-16.
- This specification does not create a Sprint-16 roadmap.
- This specification itself does not modify `roadmaps/master-roadmap.md`; a subsequent approved governance update now represents Stage 2.5 as the required high-level bridge before Stage 3.
- Master Roadmap representation does not authorize implementation, bridge execution, or sprint planning.
- Any bridge-unit roadmap, sprint roadmap, learning project, or execution requires a separate approved workflow and explicit learner approval.
- A subsequent learner-approved governance update created `roadmaps/archive/sprint-16.md` from Unit 1. Execution later began and was stopped before completion; no Unit 1 completion is recorded.
- Stage 3 transition remains unauthorized.

## 4. Why Stage 2.5 Is Needed

Sprint-12 through Sprint-15 remain valid completed Stage 2 learning progress.

Those sprints established meaningful capability in:

- project and module organization;
- ownership and borrowing in bounded APIs;
- error boundaries;
- testing;
- dependency, JSON, file, and storage boundaries;
- minimal traits, generics, and static dispatch;
- bounded interior mutability;
- source-level engineering tradeoffs.

Sprint-15 is midpoint evidence, not Stage 2 exit evidence. It demonstrates integrated capability inside a bounded project but does not establish general Rust job-readiness.

The Rust curriculum audit recorded `SIGNIFICANT RUST COVERAGE GAPS`.

The Rust Core Coverage Matrix identifies P0 and P1 topics that must be resolved, covered, validated, or durably planned before Stage 3.

A direct transition to Blockchain Foundations would be premature because it would add domain complexity while core Rust mental models and idiomatic fluency remain incomplete.

## 5. P0 Topics Before Stage 3

Stage 2.5 must define coverage and validation handling for all P0 topics.

### 5.1 Deeper Ownership And Borrowing Mental Model

Required coverage boundary:

- ownership as resource discipline;
- borrowing as controlled access;
- aliasing XOR mutability;
- moves and reference relationships;
- owned values versus borrowed views;
- reference copy semantics;
- indirection and cleanup;
- source-level ownership tracing.

The learning standard should connect compiler rules to resource lifetime, API design, mutation rights, and cleanup rather than reduce ownership to memorized move examples.

### 5.2 Explicit Lifetime Reasoning

Required coverage boundary:

- lifetimes as relationships among references;
- input/output reference relationships;
- annotations as relationship descriptions;
- compiler diagnostics;
- invalid-reference reasoning;
- bounded source-level application.

The learning standard should emphasize why references are related and what the compiler must prove, not syntax memorization or artificial annotation-heavy exercises.

### 5.3 Closures And Iterators

Required coverage boundary:

- closure capture and ownership modes;
- iterators as lazy processing abstractions;
- adapter chains;
- loop-versus-iterator tradeoffs;
- transformation and collection;
- idiomatic Rust source-reading fluency.

The learning standard should include both writing and reading iterator/closure code and should connect closure capture to the ownership model.

## 6. P1 Topics Before Stage 3

Stage 2.5 or another explicitly approved pre-Stage-3 plan should cover or place:

- smart pointers: `Box<T>`, `Rc<T>`, `Weak<T>`, `Deref`, and `Drop`;
- deeper `RefCell<T>` and interior mutability reasoning;
- systematic pattern matching;
- collections and ownership behavior;
- broader generic and trait design;
- public error traits and library error ergonomics;
- Rust-specific common concept reinforcement where durable evidence is currently implicit.

P1 planning should preserve demonstrated capability in modules, privacy, public APIs, tests, errors, and bounded project engineering.

P1 coverage should be consolidated into cohesive learning units rather than split into one sprint per Rust book chapter.

## 7. Recommended Bridge Structure

The following bridge structure is recommended. It is not execution authorization and does not decide sprint numbering.

### Bridge Unit 1 — Rust Core Fluency

Primary topics:

- closures;
- iterators;
- pattern matching;
- collections ownership behavior.

Purpose:

Improve idiomatic Rust reading and writing fluency before blockchain complexity.

Expected validation shape:

- source-reading exercises;
- loop-versus-iterator comparison;
- closure capture explanation;
- pattern matching explanation;
- bounded implementation exercises;
- Teacher Learning Validation.

Any code target, project, test count, checkpoint sequence, or completion criterion requires a separately approved roadmap.

### Bridge Unit 2 — Ownership Topology And Lifetimes

Primary topics:

- explicit lifetime reasoning;
- stack versus heap;
- `Box<T>`;
- `Rc<T>`;
- `Weak<T>`;
- `RefCell<T>`;
- `Deref`;
- `Drop`;
- aliasing XOR mutability;
- shared ownership versus borrowing.

Purpose:

Build a deeper ownership and resource-lifecycle model before blockchain, account, and resource-oriented programming.

Expected validation shape:

- ownership diagrams;
- source-level lifetime explanation;
- compiler diagnostic reasoning;
- bounded smart-pointer exercises;
- contrast among ordinary borrowing, shared ownership, and interior mutability;
- Teacher Learning Validation.

Any code target, project, test count, checkpoint sequence, or completion criterion requires a separately approved roadmap.

### Bridge Unit 3 — Engineering Contract Consolidation

Primary topics:

- broader trait and generic design;
- public API as contract;
- public error traits;
- `Display`;
- `std::error::Error`;
- structured error context;
- possible bounded revisit of `rust_engineering_assessment` hardening.

Purpose:

Connect Rust philosophy back to practical engineering and Stage 2 exit readiness.

Expected validation shape:

- public API review;
- error boundary explanation;
- trait/generic tradeoff review;
- focused code hardening only if later approved;
- Codex Repository Validation if code is modified;
- Teacher Learning Validation.

The possible `rust_engineering_assessment` revisit is only a candidate direction. This specification does not select that project, authorize modifications, or require project continuation.

## 8. P2 Placement

The following P2 topics remain visible but are not Stage 3 entry blockers:

- `Arc<T>`;
- `Mutex<T>`;
- `Send`;
- `Sync`;
- threads and channels;
- async, await, and futures;
- trait objects and `dyn Trait`.

These topics should be scheduled before dependent Stage 3 or Stage 4 work such as:

- networking;
- RPC clients;
- Solana client work;
- backend-style work;
- concurrent designs.

P2 placement is a curriculum dependency rule. It does not authorize teaching or implementation.

## 9. Relationship To Sprint-16

Sprint-16 has a learner-accepted formal roadmap at `roadmaps/archive/sprint-16.md`. Execution stopped before completion, and the sprint is not complete or closed.

This specification did not itself decide sprint numbering. A subsequent learner decision selected Unit 1 as Sprint-16 and selected the future `rust_core_fluency_lab` project shape.

The learner accepted the expanded distribution in `reviews/archive/planning/stage-2-5-remaining-coverage-review.md` and later accepted `roadmaps/archive/sprint-17.md`. Sprint-17 is ready for Teacher execution, but execution has not started.

The selected project was created during authorized Sprint-16 execution. This governance update does not inspect, validate, or modify it.

Sprint-17 and Sprint-18 remain future directional units only and require separate approved roadmap workflows.

## 10. Relationship To The Master Roadmap

`roadmaps/master-roadmap.md` now represents Stage 2.5 as the required high-level bridge between Stage 2 and Stage 3 through a separate approved governance update.

This specification did not itself make that roadmap change, and the roadmap representation does not authorize execution.

The Master Roadmap should remain high-level. Topic-level coverage, priority, evidence, validation, and maintenance should remain in:

- `reviews/rust-core-coverage-matrix.md`;
- this bridge specification;
- future approved bridge reviews or roadmaps.

## 11. Preliminary Stage 3 Entry Prerequisites

Before Stage 3 can be authorized:

1. P0 topics must have completed coverage and validation, or an explicit governance decision must explain why a remaining gap is acceptable.
2. P1 topics must be covered or placed into an approved pre-Stage-3 plan.
3. The Rust Core Coverage Matrix must be reviewed and updated with durable evidence.
4. Teacher Learning Validation must confirm that the learner can explain the relevant Rust mental models and tradeoffs.
5. A separate governance review must decide whether Stage 3 entry prerequisites are satisfied.

No Stage 3 transition may occur solely because one bridge unit, assessment, or sprint was completed.

## 12. Recommended Next Governance Actions

1. Open a Sprint-17 Teacher execution window under `roadmaps/archive/sprint-17.md`.
2. Begin with the Sprint-16 partial-progress revalidation gate.
3. Preserve Sprint-16 progress as partial and unvalidated until later validation supports completion credit.
4. Keep Sprint-18, Sprint-19, and Sprint-20 as planning recommendations only.
5. Maintain the Rust Core Coverage Matrix and preserve the Stage 3 transition block.

This section records future planning steps only. It does not continue Sprint-16 or create a new sprint roadmap.

## 13. Explicit Non-Authorization Statement

This specification and the Sprint-16 partial-progress update do not:

- mark Sprint-16 complete or closed;
- create a Sprint-16 closure;
- validate or modify `rust_core_fluency_lab`;
- authorize later Stage 2.5 unit execution;
- perform learning-project creation or modification in this governance update;
- authorize Stage 3 transition;
- authorize further modification of `roadmaps/master-roadmap.md`;
- invalidate Sprint-12, Sprint-13, Sprint-14, or Sprint-15 completion.

Final status: Stage 2.5 is represented in the Master Roadmap as the required bridge before Stage 3. Sprint-16 stopped before completion with partial unvalidated progress. Remaining Unit 1 content returns to future Stage 2.5 planning, and Stage 3 transition remains unauthorized.
