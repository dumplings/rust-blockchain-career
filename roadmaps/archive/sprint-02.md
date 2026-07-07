# Sprint-02: Rust Business Logic Foundations

## Goal

Extend tx_parser from a simple parser into a multi-stage business workflow.

The objective of this sprint is to learn how to expand an existing Rust project while strengthening Rust fundamentals.

This sprint should continue reinforcing:

- Rust project organization
- Result-based error handling
- module boundaries
- business logic separation

The sprint should also introduce a small amount of blockchain-flavored domain modeling without teaching blockchain internals.

---

## Primary Project

tx_parser

---

## Learning Objectives

By the end of this sprint, the learner should understand:

- why parsing and validation are different responsibilities;
- how business rules differ from parsing rules;
- how Result propagates across modules;
- how to design and use ValidationError;
- how to extend an existing Rust project safely.

---

## Domain Model

The Transaction model may evolve from a minimal parser-focused structure toward a more blockchain-inspired structure.

Example direction:

- from
- to
- amount
- nonce

The exact implementation should remain simple.

Do not introduce signatures, cryptography, networking, or blockchain internals.

---

## Required Topics

### Rust Fundamentals

- Result
- ?
- error propagation
- enum-based errors

### Project Organization

- validator.rs
- responsibility boundaries
- dependency direction

### Business Logic

- validation rules
- validation failures
- meaningful error reporting

---

## Deliverables

The project should contain:

- main.rs
- lib.rs
- models.rs
- parser.rs
- validator.rs
- errors.rs

The project should be capable of:

- parsing input
- validating input
- returning validation errors
- returning parse errors

---

## Explicitly Out Of Scope

Do not study:

- Async Rust
- Tokio
- Traits (advanced usage)
- Generics
- Solana
- Anchor
- PDA
- Blockchain internals
- thiserror
- anyhow
- Macro programming

These topics belong to future sprints.

---

## Sprint Completion Criteria

The sprint is complete only if the learner can:

1. Explain why parser and validator are separate modules.
2. Explain ParseError versus ValidationError.
3. Explain Result propagation across modules.
4. Explain when to return Err(...).
5. Explain when and why ? is used.
6. Navigate the expanded codebase confidently.

---

## Teaching Notes

Keep sprint scope intentionally small.

Prefer:

Learn
→ Implement
→ Test
→ Review

Avoid introducing multiple major Rust concepts in the same sprint.

The goal is steady capability growth rather than maximum topic coverage.
