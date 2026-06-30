# Master Roadmap

## Learning Goal

Become employable as a Rust + Blockchain Junior Developer.

The roadmap is capability-based rather than calendar-based.

The system's Solana-first priority describes the intended specialization, not permission to skip prerequisites. The curriculum deliberately places Blockchain Foundations before Solana Development so later Solana work rests on general blockchain understanding.

---

## Stage Overview

Stage 1:
Rust Foundations

Stage 2:
Rust Engineering

Stage 2.5:
Rust Core Philosophy Bridge

Stage 3:
Blockchain Foundations

Stage 4:
Solana Development

Stage 5:
Remote Job Preparation

---

## Stage Objectives

### Stage 1: Rust Foundations

Purpose:

Build durable Rust language and small-project foundations.

Major capabilities:

- ownership and borrowing;
- Result-based error handling;
- module organization;
- crate boundaries;
- public API basics;
- testing habits;
- small Rust project navigation.

Expected outcomes:

- learner can build and explain small Rust projects;
- learner can reason about Rust errors and module boundaries;
- learner can maintain Rust Fundamentals while adding new project concepts.

### Stage 2: Rust Engineering

Purpose:

Develop practical Rust engineering capability beyond small foundation projects.

Major capabilities:

- larger project organization;
- trait and generic usage;
- dependency management;
- CLI workflows;
- file and data handling;
- integration testing;
- maintainable error design.

Expected outcomes:

- learner can extend and maintain larger Rust projects;
- learner can make engineering tradeoffs;
- learner can use Rust tools and libraries with confidence.

### Stage 2.5: Rust Core Philosophy Bridge

Purpose:

Consolidate Rust's deeper philosophy, mental models, idiomatic fluency, and job-readiness coverage before blockchain-specific complexity.

Major capabilities:

- ownership as resource discipline;
- borrowing as controlled access;
- aliasing XOR mutability;
- explicit lifetime reasoning;
- closures and iterator fluency;
- pattern matching fluency;
- smart pointers as ownership-topology tools;
- `RefCell<T>` and interior mutability as deliberate escape hatches;
- traits and generics as abstraction tradeoffs;
- public API and error boundaries as contracts;
- systems mindset before blockchain.

Expected outcomes:

- learner can explain and apply core Rust mental models beyond isolated syntax;
- learner can read and write more idiomatic Rust involving closures, iterators, patterns, lifetimes, and ownership topology;
- learner can reason about smart pointers and interior mutability as design tools;
- learner is better prepared to learn blockchain and Solana concepts without stacking them on shallow Rust foundations.

### Stage 3: Blockchain Foundations

Purpose:

Build general blockchain understanding before deep Solana development.

Major capabilities:

- transaction concepts;
- account and wallet basics;
- blocks and chains;
- consensus overview;
- smart contract basics;
- blockchain data modeling;
- security-oriented thinking.

Expected outcomes:

- learner can explain core blockchain concepts;
- learner can connect blockchain concepts to Rust data structures and workflows;
- learner can reason about simple blockchain-inspired systems.

### Stage 4: Solana Development

Purpose:

Develop practical Solana development capability.

Major capabilities:

- Solana account model;
- programs and instructions;
- PDA concepts;
- Anchor basics;
- client interaction;
- testing Solana programs;
- reading Solana documentation.

Expected outcomes:

- learner can build and explain small Solana projects;
- learner can reason about account ownership, instruction flow, and program state;
- learner can prepare for entry-level Solana engineering tasks.

### Stage 5: Remote Job Preparation

Purpose:

Convert technical capability into employability.

Major capabilities:

- portfolio project presentation;
- technical writing;
- interview explanation;
- GitHub readiness;
- remote collaboration habits;
- English technical communication practice.

Expected outcomes:

- learner can present projects clearly;
- learner can explain technical decisions in interviews;
- learner can apply for junior Rust + Blockchain roles with credible artifacts.

---

## Stage Exit Criteria

### Stage 1: Rust Foundations

Complete this stage only when the learner can:

1. Explain ownership and borrowing in project context.
2. Use Result and error propagation intentionally.
3. Organize small Rust projects with clear module boundaries.
4. Explain crate boundaries and public API basics.
5. Write and run meaningful tests.
6. Navigate and modify small Rust projects without confusion.

### Stage 2: Rust Engineering

Complete this stage only when the learner can:

1. Extend a larger Rust project safely.
2. Use traits and generics in practical engineering contexts.
3. Design maintainable error boundaries.
4. Use dependencies and tooling appropriately.
5. Write integration tests for meaningful workflows.
6. Explain engineering tradeoffs in Rust project design.

### Stage 2.5: Rust Core Philosophy Bridge

Complete this bridge only when the learner can:

1. Explain deeper ownership and borrowing models, including aliasing versus mutation, ownership transfer, borrowed views, indirection, cleanup, and reference copy semantics.
2. Explain lifetimes as relationships among references and reason through simple lifetime-related compiler diagnostics.
3. Use and explain closures and iterators, including capture behavior, lazy processing, adapter chains, and loop-versus-iterator tradeoffs.
4. Use and explain systematic pattern matching for ordinary Rust code.
5. Explain smart pointers such as `Box<T>`, `Rc<T>`, `Weak<T>`, `RefCell<T>`, `Deref`, and `Drop` as ownership-topology and resource-lifecycle tools.
6. Explain when interior mutability is justified and when ordinary `&mut` design is preferable.
7. Explain how traits, generics, public APIs, and public error boundaries express engineering contracts and tradeoffs.
8. Demonstrate enough Rust core fluency for Stage 3 Blockchain Foundations to start without major Rust fundamentals risk.

### Stage 3: Blockchain Foundations

Complete this stage only when the learner can:

1. Explain basic transaction, wallet, block, and chain concepts.
2. Model simple blockchain concepts in Rust.
3. Explain the difference between general blockchain concepts and chain-specific implementation details.
4. Reason about simple security and trust assumptions.
5. Connect blockchain data flow to practical code.

### Stage 4: Solana Development

Complete this stage only when the learner can:

1. Explain the Solana account model.
2. Build and test small Solana programs.
3. Explain instructions, accounts, and program state.
4. Use Anchor for basic Solana workflows.
5. Read Solana documentation and apply it to project work.
6. Debug common beginner Solana development issues.

### Stage 5: Remote Job Preparation

Complete this stage only when the learner can:

1. Present portfolio projects clearly.
2. Explain project architecture and tradeoffs.
3. Write concise technical summaries.
4. Discuss Rust and blockchain work in interview settings.
5. Demonstrate remote collaboration readiness.
6. Apply for junior Rust + Blockchain roles with credible repository evidence.

---

## Sprint Relationship

Stages contain multiple sprints. Sprint design, review, and acceptance ownership follows `docs/policies/sprint-governance-policy.md`.

Teachers may not change stage ordering.

Teachers must align sprint objectives with the current stage.

Sprint roadmaps should define local scope, deliverables, and completion criteria.

Sprint roadmaps must not override the active stage objective.

Stage 2.5 is a required bridge between Stage 2 Rust Engineering and Stage 3 Blockchain Foundations.

Stage 2.5 may contain one or more separately approved bridge units, sprints, or assessments. Its representation in this roadmap does not authorize any of them.

Topic-level coverage and recommended bridge structure remain in:

- `reviews/rust-core-coverage-matrix.md`;
- `reviews/stage-2-5-bridge-specification.md`.

Any bridge-unit or sprint roadmap requires a separate approved workflow.

---

## Governance Notes

The Master Roadmap has higher authority than sprint roadmaps.

Sprint planning must align with the active stage.

Stage progression is based on capability, not calendar time.

Do not advance stages only because a sprint ended.

Stage 3 must not begin until the Stage 2.5 exit criteria are satisfied or a separate governance decision explicitly accepts any remaining gap.

Current sprint and execution authorization are owned by `CONTEXT.md` and the sprint governance policy, not by this curriculum roadmap.

Do not use this roadmap to create timelines or estimate sprint counts.
