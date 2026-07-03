# Sprint-21 Roadmap — Mini Blockchain Data Model And Validation

## 1. Sprint Identity And Status

* Sprint: Sprint-21
* Title: Mini Blockchain Data Model And Validation
* Stage: Stage 3 — Blockchain Foundations
* Status: ACCEPTED / NOT STARTED / NOT ACTIVE
* Learning project: Not created by this roadmap
* Execution status: Not authorized

This accepted roadmap records the Sprint-21 scope. It does not create a learning project, authorize Stage 3 execution, or start Teacher checkpoint work.

## 2. Stage Alignment

Stage 3 focuses on general blockchain understanding before deeper Solana development.

This sprint introduces blockchain foundations through Rust data modeling and simple validation. It deliberately keeps the learner at the general blockchain layer before introducing Solana-specific concepts such as programs, PDAs, Anchor, RPC clients, or the Solana account model.

The central implementation flow is:

`Transaction -> Block -> Blockchain -> validate_chain()`

## 3. Objective

By the end of this sprint, the learner should be able to:

* explain basic transaction, block, chain, and genesis block concepts;
* model a toy blockchain data flow in Rust;
* explain how previous-hash linkage creates a tamper-detection mechanism;
* implement simple validation rules for transactions, blocks, and chains;
* distinguish toy local validation from real decentralized consensus;
* explain why this sprint is not a production blockchain implementation.

## 4. Scope

Core scope:

1. `Transaction` model

   * Minimal fields such as sender, receiver, amount, nonce, memo, or transaction id.
   * Basic validation such as positive amount and distinct sender / receiver.
   * Constructor or validation boundary that clearly states whether the returned value is already valid.

2. `Block` model

   * Height or index.
   * List of transactions.
   * Previous hash.
   * Current hash.
   * Deterministic toy hash representation.

3. `Blockchain` model

   * Genesis block.
   * Append workflow.
   * Chain validation workflow.
   * Append-only mental model.

4. Toy hash linkage

   * Deterministic and testable.
   * Clearly documented as not production cryptography.

5. Simple validation rules

   * Transaction validity.
   * Block height continuity.
   * Previous hash match.
   * Recomputed block hash match.
   * Optional duplicate transaction detection if it does not overload the sprint.

6. Conceptual blockchain framing

   * Wallet and account basics at a general conceptual level.
   * Consensus motivation at explanation level.
   * Smart contract basics at conceptual level only.
   * Security and trust assumptions for toy versus real systems.

## 5. Explicit Non-Goals

This sprint does not include:

* Solana program development;
* Anchor;
* PDA;
* Solana account model deep dive;
* RPC client work;
* async Rust / Tokio;
* networking;
* Borsh or binary serialization deep dive;
* cryptographic implementation beyond toy hash representation;
* production-grade blockchain design;
* wallet key management;
* real digital signatures;
* token economics;
* full consensus algorithm implementation.

Account balance updates are not mandatory core scope. They are deferred by default and may be introduced only as an optional stretch exercise if the accepted roadmap scope remains stable and the learner explicitly agrees at a checkpoint boundary.

## 6. Learning Density Rationale

This sprint has enough density for a dedicated learning cycle because it combines:

* a new domain model;
* multiple linked Rust data structures;
* constructor and invariant design;
* validation workflows;
* meaningful tests;
* domain explanation requirements;
* security and trust-boundary reasoning.

The sprint remains bounded because it avoids Solana-specific development, networking, async Rust, real cryptography, token economics, and full consensus implementation.

## 7. Expected Learner Implementation Work

The learner is expected to be the primary implementer of a new small Rust learning project after execution is explicitly authorized.

Tentative project shape:

* A small Rust library project, tentatively named `mini_blockchain`.
* A thin or absent binary target unless the accepted roadmap revision explicitly adds one.
* Core logic in library modules.
* Focused tests for behavior and validation rules.

Expected implementation work:

* Define `Transaction`, `Block`, and `Blockchain` types.
* Define a validation error type, preferably enum-based.
* Implement transaction validation.
* Implement block construction and toy hash recomputation.
* Implement genesis block creation.
* Implement block append workflow.
* Implement `validate_chain()` or equivalent.
* Add focused tests for success and failure paths.
* Explain how each Rust type maps to a blockchain concept.

## 8. Checkpoint Sequence

### Checkpoint 1 — Transaction Model And Validation Boundary

Purpose:

Introduce transaction basics and establish the first validated data boundary.

Expected work:

* Design a minimal `Transaction` type.
* Decide whether `Transaction::new` returns a validated transaction or whether validation is separate.
* Represent ordinary invalid input with `Result`, not `panic`.
* Add tests for valid and invalid transactions.

Rust reinforcement:

* Public constructor invariant design.
* Enum-based validation errors if appropriate.
* Panic-versus-`Result` discipline.

### Checkpoint 2 — Block Model And Toy Hash Linkage

Purpose:

Model how blocks group transactions and link to prior chain state.

Expected work:

* Design a `Block` type with height, transactions, previous hash, and current hash.
* Implement deterministic toy hash calculation.
* Ensure block hash depends on the relevant block contents.
* Add tests showing that changed block contents affect recomputed validation.

Rust reinforcement:

* Private fields and constructor boundaries.
* Borrowed accessors versus owned output choices.
* Precise reference-origin explanation for validation helpers.

### Checkpoint 3 — Blockchain Genesis, Append, And Validation

Purpose:

Build the minimal chain workflow.

Expected work:

* Define `Blockchain`.
* Create a genesis block.
* Implement append behavior.
* Implement `validate_chain()` or equivalent.
* Validate height continuity, previous hash match, transaction validity, and recomputed block hash.
* Add tests for valid chain, tampered block, wrong previous hash, and invalid transaction.

Rust reinforcement:

* Iterator and closure fluency during chain traversal.
* Borrowed enum matching if validation errors are inspected in tests.
* Clear ownership choices for stored transactions and blocks.

### Checkpoint 4 — Trust Boundaries, Optional Duplicate Detection, And Final Review

Purpose:

Connect the toy implementation to real blockchain concepts without expanding into Stage 4.

Expected work:

* Explain wallet/account concepts at a general level.
* Explain why consensus is needed but not implemented.
* Explain why toy hash validation is not production security.
* Optionally add duplicate transaction detection if the core model is stable and the Teacher decides the sprint still has safe capacity.
* Complete final tests and validation package.

Rust reinforcement:

* `HashSet<T>` versus `HashSet<&T>` only if duplicate detection is included.
* Avoid forcing custom `Drop` or `source()` chaining unless a real lower-level error appears.

## 9. Required Tests

The implementation should include focused tests for:

* valid transaction creation or validation;
* invalid transaction rejection;
* valid chain validation;
* tampered block detection;
* wrong previous hash detection;
* recomputed hash mismatch detection;
* invalid transaction inside a block;
* optional duplicate transaction detection if included.

Tests should validate the sprint’s core contract without becoming a broad testing expansion exercise.

## 10. Student Validation

Student Validation requires the learner to run and report:

* `cargo fmt`
* `cargo check`
* `cargo test`

The learner should also explain:

* what each core type represents in blockchain terms;
* what each major validation rule protects;
* why the toy hash is not production cryptography;
* why local validation is not the same as consensus;
* where ordinary invalid input is handled with `Result`.

## 11. Codex Repository Validation

Codex Repository Validation should inspect the learning project after implementation and report:

* files inspected;
* whether `cargo fmt`, `cargo check`, and `cargo test` pass;
* whether the implementation stays within Sprint-21 scope;
* whether prohibited non-goals are absent;
* whether the code models `Transaction -> Block -> Blockchain -> validate_chain()`;
* whether validation tests cover the required success and failure cases;
* whether constructor and validation boundaries are clear;
* whether learner-primary implementation appears preserved;
* any blocking or non-blocking issues.

Codex should not implement missing core learning-project code unless explicitly authorized by the learner for a narrow repository-maintenance purpose.

## 12. Teacher Learning Validation

Teacher Learning Validation should verify that the learner can:

* explain transactions, blocks, chain linkage, and genesis block;
* explain how previous hash linkage supports tamper detection;
* explain the validation rules in the implemented code;
* distinguish toy validation from real consensus;
* distinguish general blockchain concepts from Solana-specific implementation details;
* explain public constructor and invariant choices;
* explain why `Result` is used for ordinary invalid input;
* reason about the relevant Rust ownership and borrowing choices in the code.

A Codex PASS does not automatically imply Teacher Learning Validation PASS.

## 13. Completion Criteria

Sprint-21 may be closed only when:

1. The accepted roadmap scope is implemented without prohibited scope expansion.
2. Student Validation passes.
3. Codex Repository Validation passes or all blocking issues are resolved.
4. Teacher Learning Validation passes.
5. The learner can explain the implemented blockchain model and its limitations.
6. Remaining risks and deferrals are recorded in the closure package.

## 14. Risks And Deferrals

Risks:

* Scope drift into Solana-specific development.
* Treating toy hash linkage as real cryptographic security.
* Overbuilding account balances, wallets, signatures, networking, or consensus.
* Allowing tests to become filler rather than focused validation.
* Reopening Stage 2.5 Rust review instead of using natural reinforcement.

Deferred topics:

* Solana account model.
* Solana programs and instructions.
* Anchor.
* PDA.
* RPC and async client work.
* Real key management and digital signatures.
* Borsh and binary layout.
* Full consensus implementation.
* Production security design.
* Custom `Drop` practice unless a real resource lifecycle appears.
* `source()` chaining unless real lower-level error wrapping appears.

## 15. Explicit Execution Boundary

This accepted roadmap does not authorize execution.

Execution may begin only after:

1. the learner accepts the roadmap;
2. repository state is updated if required;
3. the learner gives an explicit execution-start command;
4. an authorized Teacher execution window begins;
5. the Teacher verifies the startup checklist required by the Teacher execution policy.

Until then:

* do not create the learning project;
* do not start Checkpoint 1;
* do not assign implementation work;
* do not treat Sprint-21 as active.
