# Sprint-01: Rust Project Foundations

## Goal

Deliver `tx_parser v0.1`.

The purpose of this sprint is not to learn isolated Rust concepts.

The purpose is to build a small but complete Rust project and understand how Rust projects are organized.

---

## Primary Project

tx_parser v0.1

---

## Learning Objectives

By the end of this sprint, the learner should understand:

- project structure;
- crate boundaries;
- module organization;
- Result-based error handling;
- basic testing workflow;
- project-level reasoning.

---

## Required Topics

### Project Structure

- main.rs
- lib.rs
- modules
- use
- pub

### Error Handling

- Result
- ?
- custom errors
- errors.rs

### Data Modeling

- structs
- serde
- serde_json

### Testing

- unit tests
- cargo test

---

## Deliverables

The project should contain:

- main.rs
- lib.rs
- models.rs
- parser.rs
- errors.rs
- tests

The project should:

- compile successfully;
- parse valid input;
- return meaningful errors;
- include tests;
- include a README.

---

## Explicitly Out of Scope

Do not study:

- Tokio
- Async Rust
- Solana
- Anchor
- PDA
- Blockchain internals

These topics belong to later sprints.

---

## Sprint Completion Criteria

The sprint is complete only if the learner can:

1. Explain the project structure.
2. Explain module boundaries.
3. Explain error propagation.
4. Explain why Result is used.
5. Navigate the codebase without confusion.
6. Pass all tests.

---

## Progress

Completed:

- Created project module structure;
- Implemented Transaction model;
- Implemented ParseError;
- Implemented JSON parsing using serde_json;
- Implemented error conversion using map_err;
- Implemented main.rs integration;
- Added first successful unit test;
- Verified cargo check, cargo run, and cargo test workflows.

Current Focus:

- Error-path testing;
- Project organization reasoning;
- Module boundary understanding.
