# Sprint-18 Specification Review - Lifetimes And Borrowing Topology

## 1. Review Identity

- Sprint candidate: Sprint-18
- Candidate direction: `Lifetimes And Borrowing Topology`
- Report type: Specification Review
- Review result: Recommend proceeding to roadmap drafting only after learner direction confirmation
- Current active sprint: None
- Sprint-17: PASS WITH NOTES / CLOSED
- Sprint-16: Stopped before completion; incomplete; unclosed; no completion credit
- Stage 2.5: Incomplete
- Stage 3 transition: Unauthorized
- Roadmap status: No Sprint-18 roadmap exists
- Execution status: Not authorized

This report evaluates whether `Lifetimes And Borrowing Topology` is an appropriate next Stage 2.5 direction. It is not a sprint roadmap and does not authorize roadmap creation, learning-project work, Sprint-18 execution, or Stage 3 transition.

## 2. Source State And Evidence

The durable governance baseline establishes that:

- Sprint-17 completed and closed with PASS WITH NOTES;
- Sprint-17 independently validated closures and iterators, systematic pattern matching, and collection ownership behavior sufficiently for the current curriculum point;
- Sprint-16 remains incomplete and unclosed under its original execution boundary;
- Sprint-17 Checkpoint 1 does not grant Sprint-16 completion credit;
- Stage 2.5 remains incomplete;
- no learning sprint is active;
- Sprint-18, Sprint-19, and Sprint-20 remain planning recommendations only;
- Stage 3 transition remains unauthorized.

The Rust Core Coverage Matrix identifies the remaining P0 blockers as:

- deeper ownership and borrowing mental models;
- explicit lifetime reasoning.

Important P1 work remains after those P0 topics:

- smart pointers;
- deeper `RefCell<T>` and interior mutability;
- broader generics and traits;
- public error traits and library error ergonomics.

Sprint-18 should address the remaining P0 boundary without absorbing the later P1 smart-pointer and engineering-contract work.

## 3. Learner Feedback Incorporated

The learner clarified that they usually do not perform detailed review of learning plans and do not consider themself responsible for full curriculum-design quality assurance.

The learner can provide direction confirmation and final human authorization. The learner may notice that a plan is overloaded only after teaching and implementation begin, then request an adjustment based on actual learning experience.

This feedback changes Sprint-18 design expectations:

- roadmap and checkpoint design must include explicit density-control boundaries;
- the Teacher must treat runtime pace, overload, and underload feedback as actionable evidence;
- checkpoint scope must be adjustable without classifying the learner as failing;
- an overloaded checkpoint may be narrowed, reinforced, deferred, or split while preserving the central learning objective;
- learner approval must not transfer responsibility for scope quality or pedagogical calibration from Teacher and Architect agents to the learner.

Learner approval remains final human authorization. It may be lightweight direction confirmation rather than detailed review of every roadmap decision.

## 4. Candidate Direction Assessment

Decision: `Lifetimes And Borrowing Topology` is appropriate as the next Stage 2.5 direction, with strict scope control.

The candidate directly addresses the two remaining P0 areas:

1. deeper ownership and borrowing mental models;
2. explicit lifetime reasoning.

These topics are closely related: lifetime reasoning becomes clearer when references are understood as controlled access to owned resources, and ownership topology becomes more concrete when the learner traces which references must remain valid across function boundaries.

Sprint-18 should not become a broad smart-pointer sprint. `Rc<T>`, `Weak<T>`, deeper `RefCell<T>`, `Deref`, `Drop`, and ownership-count topology belong to the later smart-pointer direction unless a future roadmap justifies a tiny contrast needed to explain the P0 material.

## 5. Recommended Sprint-18 Scope

Recommended coverage:

- ownership as resource discipline;
- borrowing as controlled access;
- aliasing XOR mutability;
- moves and reference relationships;
- owned values versus borrowed views;
- reference copy semantics;
- basic indirection and cleanup concepts only where needed to explain references;
- lifetimes as relationships among references;
- input-reference and output-reference relationships;
- lifetime annotations as descriptions of reference relationships, not runtime duration controls;
- simple lifetime-related compiler diagnostic reasoning;
- source-level ownership and reference tracing;
- bounded source-reading exercises;
- small implementation exercises that expose reference relationships without artificial annotation volume.

The sprint should emphasize mental models, source reading, prediction, and explanation rather than lifetime syntax memorization.

## 6. Recommended Non-Goals

Sprint-18 should explicitly exclude:

- full smart-pointer topology;
- `Rc<T>`;
- `Weak<T>`;
- deep `RefCell<T>`;
- `Deref`;
- `Drop`;
- broad `Box<T>` coverage, except an optional tiny explanatory contrast if necessary;
- async Rust;
- threads or concurrency;
- blockchain;
- Solana;
- persistence or file IO as a primary topic;
- broad architecture expansion;
- public error-trait consolidation;
- trait objects or dynamic dispatch.

These exclusions prevent a focused P0 sprint from becoming a combined ownership, smart-pointer, concurrency, and engineering-contract unit.

## 7. Learning Density Assessment

The candidate direction is high value but carries a high overload risk because ownership topology and lifetime reasoning can quickly expand into compiler theory, smart pointers, advanced signatures, and artificial annotation exercises.

Recommendation:

- use a normally sized sprint with three or four checkpoints;
- keep each checkpoint centered on one connected mental-model boundary;
- pause at every checkpoint boundary for pace and density feedback;
- narrow, defer, split, or reinforce material when the learner reports overload;
- permit the sprint to become narrower during execution without treating the learner as failing;
- defer smart-pointer material to Sprint-19 unless a tiny contrast is necessary for the current explanation.

Runtime density adjustment is part of responsible teaching execution. Learner roadmap approval is not evidence that every density tradeoff was reviewed or accepted by the learner in advance.

## 8. Recommended Checkpoint Shape

Recommended high-level sequence:

1. Checkpoint 1 - Ownership and borrowing topology through source reading, value/reference tracing, and diagrams.
2. Checkpoint 2 - Lifetimes as reference relationships in function signatures and returned references.
3. Checkpoint 3 - Compiler diagnostic reasoning and small lifetime-focused implementation exercises.
4. Checkpoint 4 - Integrated bounded exercise and validation, only if the earlier checkpoint density remains acceptable.

This sequence is planning guidance only. Exact teaching content, learner tasks, examples, artifacts, tests, adjustment gates, and completion criteria belong in a future Sprint-18 roadmap.

Checkpoint 4 may be reduced, deferred, or split if runtime evidence shows that the first three checkpoints already consume the sprint's appropriate learning density.

## 9. Project / Exercise Recommendation

Do not automatically continue `rust_core_fluency_lab`.

That project served Sprint-17's iterator, closure, pattern, and collection-fluency scope. Continuing it by default would risk preserving project momentum rather than selecting the clearest lifetime-learning surface.

A future roadmap may choose either:

- a fresh small `rust_lifetime_topology_lab`; or
- source reading plus several small exercises without a large new project.

The choice should depend on which option provides clearer ownership and lifetime relationships at normal learning density. A future roadmap may reuse `rust_core_fluency_lab` only if it identifies a specific high-value reason and explains why reuse is clearer than a fresh bounded surface.

This Specification Review does not select, create, inspect, or modify a learning project.

## 10. Validation Shape

### Student Validation

If code is created or modified, the learner should perform appropriate local self-checks and review the intended ownership and lifetime relationships.

### Codex Repository Validation

Formal Codex Repository Validation is required if a learning project is created or modified. It should verify source scope, compiler and test status, public boundaries when relevant, and exclusion of unapproved smart-pointer or architecture expansion.

### Teacher Learning Validation

Teacher Learning Validation is required and should verify that the learner can explain:

- ownership relationships;
- borrowing rights and mutation constraints;
- reference validity relationships;
- input/output lifetime relationships;
- what lifetime annotations communicate;
- relevant compiler diagnostics;
- design and tradeoff choices.

Passing compiler checks or tests is not sufficient evidence of lifetime understanding.

## 11. Risks

- overloading Sprint-18 with smart-pointer topology;
- turning lifetime learning into syntax memorization;
- using contrived annotations without a real reference relationship;
- asking the learner to infer hidden ownership or lifetime rules;
- relying on learner roadmap review to catch density problems before execution;
- forcing completion after runtime overload becomes visible;
- reopening Sprint-16 or granting it completion credit;
- treating Sprint-17 as completion of Stage 2.5;
- moving toward Stage 3 before remaining P0 / P1 requirements are resolved.

## 12. Recommendation

Recommend proceeding to a Sprint-18 roadmap draft for `Lifetimes And Borrowing Topology` with the narrowed P0 scope defined in this review.

The learner should first confirm this candidate direction. Roadmap drafting or creation still requires a separate authorized workflow.

This Specification Review does not authorize Sprint-18 execution.

## 13. Explicit Non-Authorization Statement

This review does not:

- create `roadmaps/sprint-18.md`;
- authorize Sprint-18 execution;
- authorize learning-project creation or modification;
- authorize Stage 3 transition;
- complete Stage 2.5;
- complete or close Sprint-16;
- create a Sprint-16 closure;
- modify any learning-project repository.

Final review decision: recommend `Lifetimes And Borrowing Topology` as the Sprint-18 roadmap direction, subject to learner direction confirmation and a separate roadmap workflow. Sprint-18 remains unauthorized.
