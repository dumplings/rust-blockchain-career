# Sprint-18 — Lifetimes And Borrowing Topology

## 1. Sprint Identity

- Sprint number: Sprint-18
- Sprint title: `Lifetimes And Borrowing Topology`
- Sprint status: Accepted / awaiting explicit learner start command
- Execution status: Not started
- Authorization status: Roadmap accepted by learner; execution requires an explicit learner start command; this repository update does not start learning execution; learning-project creation remains pending a future authorized Teacher execution window
- Current active sprint: None
- Stage relationship: Stage 2.5 — Rust Core Philosophy Bridge
- Stage 2.5 status: Incomplete
- Sprint-17: PASS WITH NOTES / CLOSED
- Sprint-16: Stopped before completion; incomplete; unclosed; no completion credit
- Stage 3 transition: Not authorized
- Source Specification Review: `reviews/sprint-18-specification-review.md`
- Coverage reference: `reviews/rust-core-coverage-matrix.md`
- Candidate learning project: `rust_lifetime_topology_lab`
- Candidate project path: `/Users/dumplings/workspace/rust_lifetime_topology_lab`
- Project status: Not created by this roadmap draft

The learner accepted this roadmap for Sprint-18. Acceptance confirms the roadmap direction and creates an accepted-but-not-started state. A Teacher execution window may open only after an explicit learner command to start Sprint-18 execution or checkpoint work; the Teacher startup checklist must then be completed before Checkpoint 1.

Recording acceptance does not start Sprint-18 through this repository update and does not create or modify any learning project. No Teacher execution window is open. Candidate learning-project creation remains pending an explicit learner start command and the future Teacher execution window.

## 2. Sprint Purpose

Sprint-18 is intended to address the remaining P0 Stage 2.5 blockers:

- deeper ownership and borrowing mental models;
- explicit lifetime reasoning.

The sprint should teach lifetimes through concrete ownership, borrowing, and reference relationships rather than through syntax memorization or artificial annotation drills.

Sprint-18 should connect:

- ownership to resource responsibility;
- borrowing to controlled access;
- aliasing rules to mutation rights;
- reference validity to input/output API relationships;
- lifetime annotations to relationships the compiler must verify.

Smart-pointer topology remains deferred to later Stage 2.5 work.

## 3. Stage Alignment And Learning Density

Sprint-17 supplied durable evidence for closures and iterators, systematic pattern matching, and collection ownership behavior. The next Stage 2.5 need is the deeper ownership and lifetime boundary that remains P0 before Stage 3.

This sprint should occur before smart-pointer and engineering-contract consolidation because the learner first needs a clear model of ordinary ownership, borrowing, references, and lifetime relationships. Later work can then compare ordinary borrowing with smart-pointer ownership topologies without teaching both models simultaneously.

The topic is high value but has a high overload risk. Ownership topology and lifetimes can expand into advanced annotations, smart pointers, compiler theory, or contrived examples if scope is not actively controlled.

Runtime density controls are required:

- pause at every checkpoint boundary;
- ask for pace, density, overload, and underload feedback;
- narrow, reinforce, defer, or split material when runtime evidence requires it;
- do not force completion of an overloaded checkpoint sequence;
- treat runtime density adjustment as normal teaching feedback, not learner failure;
- do not treat learner roadmap approval as detailed curriculum-quality assurance;
- surface a governance decision when an adjustment would materially change accepted sprint scope.

The preferred sprint shape is three required checkpoints plus one conditional integrated checkpoint.

## 4. Learning Objectives

By the end of an authorized Sprint-18 execution, the learner should be able to:

1. Explain ownership as resource discipline.
2. Explain borrowing as controlled access.
3. Explain aliasing XOR mutability.
4. Trace moves, references, borrowed views, and owned values in bounded Rust source.
5. Explain why `&T` is `Copy` while `&mut T` is not `Copy` because it represents exclusive mutable access.
6. Explain lifetimes as relationships among references.
7. Explain input/output reference relationships in function signatures.
8. Explain lifetime annotations as relationship descriptions rather than runtime duration controls.
9. Explain bounded lifetime elision behavior.
10. Diagnose simple lifetime-related compiler errors.
11. Choose owned output versus borrowed output based on validity and API design.
12. Explain when returning a reference is valid and when owned output is required.
13. Repair a small invalid-reference API by changing ownership or reference relationships.
14. Explain the tradeoffs among borrowing, cloning, and transferring ownership for a bounded API.

## 5. Required Scope

Sprint-18 must cover:

- ownership topology source reading;
- value, owner, and reference diagrams or equivalent explanation exercises;
- ownership transfer and moved-value reasoning;
- owned values versus borrowed views;
- borrowed input versus borrowed output;
- borrowed input versus owned output;
- reference copy semantics;
- shared-borrow versus mutable-borrow constraints;
- aliasing and mutation rights;
- input/output reference relationships;
- returning references tied to valid input data;
- invalid local-reference escape;
- lifetime elision at a bounded conceptual level;
- explicit lifetime annotations only when they clarify a real reference relationship;
- lifetime annotations as compiler-checked relationship descriptions;
- simple lifetime-related compiler diagnostic reasoning;
- small implementation exercises that expose reference validity and API choices;
- source-level comparison of a borrowed-output API with an owned-output alternative.

Basic indirection and cleanup concepts may appear only where needed to explain ordinary values and references.

## 6. Explicit Non-Goals

Sprint-18 excludes:

- full smart-pointer topology;
- `Rc<T>`;
- `Weak<T>`;
- deep `RefCell<T>`;
- `Deref`;
- `Drop`;
- broad `Box<T>` coverage, except a tiny explanatory contrast if needed;
- async Rust;
- threads or concurrency;
- blockchain;
- Solana;
- persistence or file IO as a primary topic;
- broad architecture expansion;
- public error-trait consolidation;
- trait objects or dynamic dispatch;
- advanced lifetime bounds;
- higher-ranked trait bounds;
- self-referential structure design;
- artificial lifetime-annotation drills detached from real reference relationships.

The Teacher should explicitly defer excluded topics instead of expanding the sprint when they arise.

## 7. Required Learner Decisions

During authorized execution, the learner should make and explain at least these decisions:

1. Whether a function should return borrowed data or owned data.
2. Whether an input should be `T`, `&T`, `&mut T`, `&[T]`, or an owned collection.
3. Whether a returned reference can validly relate to an input reference.
4. Whether cloning is necessary to produce valid owned output.
5. Whether an API should expose a borrowed view or own the result.
6. How mutation requirements affect borrowing and aliasing design.
7. Whether a compiler lifetime diagnostic is caused by invalid reference escape, an ambiguous relationship, or conflicting borrow rights.
8. Whether explicit lifetime annotations add necessary relationship information or merely restate elision.
9. Whether a small API should be repaired by changing ownership, changing its return type, or clarifying its reference relationships.

The Teacher should evaluate the reasoning behind these choices rather than dictate an API and ask for retrospective justification.

## 8. Checkpoint Sequence

Sprint-18 should proceed checkpoint by checkpoint. The Teacher must pause for learner questions, source-level review, and density feedback before advancing.

### Checkpoint 1 — Ownership And Borrowing Topology

Purpose:

Build a clear resource-and-access mental model before introducing lifetime annotations.

Required teaching and learner work:

- read small source examples and trace owners, moves, and references;
- use diagrams or precise verbal traces for value/reference relationships;
- distinguish owned values from borrowed views;
- compare shared and mutable borrow rights;
- explain aliasing XOR mutability;
- explain why `&T` is `Copy` and why `&mut T` preserves exclusivity instead;
- compare `T`, `&T`, `&mut T`, slices, and owned collections in bounded APIs.

Checkpoint completion criteria:

- learner explanations identify owners and access rights correctly;
- move and borrow consequences are predicted before compiler trial and error;
- reference copy semantics and mutable-reference exclusivity are coherent;
- checkpoint density is acceptable or adjusted before progress.

### Checkpoint 2 — Lifetimes As Reference Relationships

Purpose:

Connect reference validity to function signatures and returned references.

Required teaching and learner work:

- analyze signatures with one or more input references;
- identify which input a returned reference may validly relate to;
- explain lifetime elision at a bounded conceptual level;
- add explicit annotations only when they communicate a necessary relationship;
- explain why annotations do not extend a value's runtime lifetime;
- compare returning a borrowed reference with returning an owned result;
- diagnose invalid local-reference escape conceptually.

Checkpoint completion criteria:

- learner explains reference relationships rather than reciting annotation syntax;
- learner distinguishes elided from explicit relationships;
- returned-reference validity is reasoned from source ownership;
- borrowed-output and owned-output alternatives are compared coherently;
- checkpoint density is reviewed before progress.

### Checkpoint 3 — Compiler Diagnostics And Small Implementation Exercises

Purpose:

Apply the mental model to compiler feedback and bounded API repair.

Required teaching and learner work:

- diagnose simple invalid reference-return examples;
- distinguish invalid escape, ambiguous relationships, and conflicting borrow rights;
- repair small APIs by changing ownership or reference relationships;
- compare borrowed-output and owned-output designs;
- use minimal explicit lifetimes where justified;
- implement small functions that expose meaningful reference-validity decisions.

Checkpoint completion criteria:

- diagnostics are explained through ownership and reference relationships;
- repairs solve the semantic problem rather than silence the compiler mechanically;
- explicit annotations remain minimal and meaningful;
- learner can justify borrowing, ownership, or cloning choices;
- the Teacher determines with the learner whether Checkpoint 4 density remains appropriate.

### Checkpoint 4 — Integrated Bounded Exercise And Validation

Status:

Conditional on acceptable density after Checkpoints 1 through 3.

Purpose:

Integrate source reading, API design, lifetime reasoning, and validation without expanding into smart-pointer topology.

Possible exercise boundary:

- select records from borrowed input and return valid borrowed views;
- produce owned summaries from borrowed input;
- compare a borrowed-output API with an owned-output API;
- explain why an invalid reference-return alternative cannot compile;
- add a small number of focused behavior tests if code is created.

Checkpoint completion criteria:

- exercise remains bounded and readable;
- ownership and lifetime relationships are explained source-first;
- borrowed and owned API choices are justified;
- Student Validation is prepared if code exists;
- integrated work does not introduce excluded topics.

Checkpoint 4 may be reduced, deferred, or split into later approved work if earlier checkpoints already consume the sprint's appropriate learning density. Such adjustment is not learner failure.

## 9. Candidate Project / Exercise Shape

Preferred candidate if project-based execution is later authorized:

- project: `rust_lifetime_topology_lab`;
- path: `/Users/dumplings/workspace/rust_lifetime_topology_lab`;
- crate shape: small Rust library crate;
- dependency boundary: standard library only unless a later approved roadmap amendment says otherwise.

The project does not exist as a result of this roadmap draft and must not be created before separate execution authorization.

Candidate domain behaviors should make borrowed views and owned outputs natural, for example:

- selecting records from a borrowed collection;
- returning references tied to input records;
- producing owned summaries from borrowed input;
- comparing valid and invalid reference-return APIs;
- performing controlled mutation through an appropriate mutable borrow.

A future accepted roadmap execution may instead use source reading plus several small exercises without a dedicated project if that better controls learning density.

Do not continue `rust_core_fluency_lab` by default. That project served Sprint-17's Rust Core Fluency scope. Reuse requires a specific high-value justification and a separate approved decision.

## 10. Testing Requirements

If code is created during later authorized execution, use a small number of focused tests.

Recommended final range:

`4 to 7 focused tests`

Tests should cover observable behavior such as:

- selecting the expected borrowed view where testable through behavior;
- producing the expected owned output from borrowed input;
- controlled mutation behavior when appropriate;
- relevant empty, missing, or boundary cases;
- integrated public behavior if a small library API is created.

Avoid:

- one test per lifetime syntax form;
- broad test inflation;
- awkward runtime tests for compiler-enforced invalid-reference behavior;
- tests used as substitutes for ownership or lifetime explanation.

Compiler-enforced lifetime behavior should be explained at source level.

## 11. Student Validation

If code is created or modified during authorized execution, the learner should run in the learning-project repository:

- `cargo fmt --check`
- `cargo check`
- `cargo test`

The learner should also review:

- ownership and reference relationships;
- borrowed versus owned return choices;
- lifetime relationships expressed by signatures;
- explicit annotation necessity;
- known blocking and non-blocking issues;
- scope and non-goal compliance.

Student Validation is not performed during roadmap drafting.

## 12. Codex Repository Validation

Formal Codex Repository Validation is required if a learning project is created or modified.

Expected validation target if the candidate project is later selected and created:

`/Users/dumplings/workspace/rust_lifetime_topology_lab`

Codex should verify:

- implementation remains within Sprint-18's ownership-and-lifetime scope;
- no smart-pointer, async, concurrency, blockchain, persistence, or broad architecture expansion exists;
- source and public API choices express coherent ownership and reference relationships;
- compiler and test commands pass;
- tests remain focused;
- blocking and non-blocking findings are distinguished.

Governance-repository validation and learning-project validation must remain separate.

## 13. Teacher Learning Validation

Teacher Learning Validation is required before Sprint-18 can close.

The Teacher must validate that the learner can explain:

- ownership and borrowing topology;
- ownership as resource discipline;
- borrowing as controlled access;
- aliasing XOR mutability;
- reference copy semantics;
- shared versus mutable borrow rights;
- input/output reference relationships;
- lifetime elision and explicit annotations;
- why lifetime annotations do not extend value lifetime;
- simple compiler lifetime diagnostics;
- borrowed-output versus owned-output API tradeoffs;
- ownership, borrowing, or cloning choices in the final bounded work.

Validation should use source reading, diagrams or precise relationship traces, prediction, diagnosis, comparison, and tradeoff questions.

Passing compiler checks or tests is not enough.

## 14. Completion Criteria

Sprint-18 may be closed only when:

- this roadmap has been accepted before execution;
- the learner explicitly commanded Sprint-18 execution or checkpoint work to start;
- the Teacher startup checklist was completed before Checkpoint 1;
- Sprint-18 execution began under this accepted roadmap;
- Checkpoints 1 through 3 are completed;
- Checkpoint 4 is completed or explicitly narrowed, deferred, or split through an approved density adjustment;
- Student Validation passes if code is created or modified;
- Codex Repository Validation passes or returns only explicitly accepted non-blocking notes if a learning project is created or modified;
- Teacher Learning Validation passes;
- scope remains within the approved P0 ownership-and-lifetime boundary;
- smart-pointer topology remains deferred;
- explicit non-goals remain respected;
- Sprint-16 remains incomplete and unclosed;
- Stage 2.5 remains incomplete unless a separate later governance decision changes that state;
- Stage 3 transition remains unauthorized;
- a Sprint-18 closure document is created through the approved governance workflow.

Sprint-18 must not be marked complete solely because code compiles or tests pass.

## 15. Runtime Density Adjustment

The learner is not responsible for detecting roadmap density problems before execution.

Overload or underload discovered during teaching and implementation is normal learning-system feedback. It does not indicate learner failure and does not mean the learner accepted responsibility for roadmap-quality problems by approving the sprint.

Checkpoint boundaries are the required adjustment points. The Teacher should:

- pause and identify the density problem;
- preserve the central P0 learning objective;
- narrow or reinforce current material when possible;
- defer excluded or lower-priority material;
- split work into later approved scope when needed;
- record the adjustment for later validation and closure.

If an adjustment materially changes the accepted roadmap, the Teacher or Architect should surface a governance decision rather than silently rewriting the sprint during execution.

Density adjustment must not be used to introduce smart-pointer topology or unrelated scope.

## 16. Relationship To Later Stage 2.5 Planning

Current later recommendations are:

1. Sprint-19 — Smart Pointers And Interior Mutability
2. Sprint-20 — Engineering Contract Consolidation

These are planning recommendations only. They are not drafted, scoped, accepted, started, or authorized.

Sprint-18 does not complete Stage 2.5. A later governance review must evaluate remaining P0 / P1 coverage and Stage 3 entry prerequisites.

## 17. Authorization Boundary

This roadmap has been accepted by the learner and is awaiting an explicit learner start command.

Roadmap acceptance does not start execution. Sprint-18 remains accepted but not started until the learner gives an explicit command to start Sprint-18 execution or checkpoint work.

Creating or accepting this file does not:

- start Sprint-18;
- start Sprint-18 execution through this repository update;
- create or modify `/Users/dumplings/workspace/rust_lifetime_topology_lab`;
- create or modify any learning-project repository;
- perform Student, Codex, or Teacher learning-project execution through this repository update;
- complete or close Sprint-16;
- create a Sprint-16 closure;
- complete Stage 2.5;
- authorize Stage 3 transition;
- draft, accept, or authorize Sprint-19 or Sprint-20.

Next transition: await an explicit learner start command. After that command, open a Sprint-18 Teacher execution window, complete the Teacher startup checklist for current state, authority, scope, language, workflow boundaries, and learner-primary implementation, then begin with Checkpoint 1 only. Sprint-18 is not active until that execution window begins.
