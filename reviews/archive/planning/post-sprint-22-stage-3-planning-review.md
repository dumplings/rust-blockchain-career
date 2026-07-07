# Post-Sprint-22 Stage 3 Planning Review

## 1. Review Identity

- Review date: 2026-07-07
- Review owner: Codex, acting as the local repository review and planning bridge
- Curriculum stage: Stage 3 — Blockchain Foundations
- Review type: Post-Sprint-22 dependency-order and readiness review
- Review status: COMPLETE — RECOMMENDATION ONLY
- Recommended next capability boundary: Public-key roles, digital signatures, and verification boundaries
- Sprint-23 roadmap: Not created
- Learning execution: Not authorized
- Stage 4 / Solana execution: Unauthorized

This document records a planning recommendation. It is not a Specification
Review, sprint roadmap, roadmap acceptance, Teacher start, learning-execution
authorization, or Stage 4 transition decision.

## 2. Evidence Reviewed

Repository evidence:

- `AGENTS.md`;
- `CONTEXT.md`;
- `TODO.md`;
- `learning-log.md`;
- `roadmaps/master-roadmap.md`;
- `reviews/sprint-22-closure.md`;
- `reviews/stage-3-blockchain-coverage-ledger.md`;
- `reviews/rust-core-coverage-matrix.md`;
- `reviews/archive/planning/stage-3-4-external-alignment-audit.md`;
- `reviews/archive/planning/stage-3-repair-direction-decision.md`;
- `docs/policies/lifecycle-policy.md`;
- `docs/policies/learning-execution-policy.md`;
- `docs/policies/lifecycle-policy.md`;
- `docs/policies/repository-validation-policy.md`;
- `templates/specification-review-template.md`.

Authoritative or recognized external baselines:

- [NIST FIPS 186-5 — Digital Signature Standard](https://csrc.nist.gov/pubs/fips/186-5/final);
- [RFC 8032 — Edwards-Curve Digital Signature Algorithm](https://www.rfc-editor.org/rfc/rfc8032.html);
- [Bitcoin Developer Reference — Transactions](https://developer.bitcoin.org/reference/transactions.html);
- [Bitcoin Developer Guide — Wallets](https://developer.bitcoin.org/devguide/wallets.html);
- [Ethereum.org — Ethereum accounts](https://ethereum.org/developers/docs/accounts/);
- [Ethereum.org — Transactions](https://ethereum.org/developers/docs/transactions/);
- [Solana documentation — Transaction Structure](https://solana.com/docs/core/transactions/transaction-structure).

Rust readiness sources:

- [The Rust Programming Language — Data Types](https://doc.rust-lang.org/book/ch03-02-data-types.html);
- [The Rust Programming Language — Recoverable Errors with `Result`](https://doc.rust-lang.org/book/ch09-02-recoverable-errors-with-result.html);
- [The Rust Programming Language — Traits](https://doc.rust-lang.org/book/ch10-02-traits.html);
- [The Rust Reference — Method Call Expressions](https://doc.rust-lang.org/reference/expressions/method-call-expr.html);
- [Rust by Example — Arrays and Slices](https://doc.rust-lang.org/rust-by-example/primitives/array.html);
- [The Cargo Book — Specifying Dependencies](https://doc.rust-lang.org/cargo/reference/specifying-dependencies.html);
- [The Cargo Book — Features](https://doc.rust-lang.org/cargo/reference/features.html);
- [`std::convert::TryFrom`](https://doc.rust-lang.org/std/convert/trait.TryFrom.html).

No cryptographic Rust dependency is selected by this review. Exact crate,
version, feature, trait-import, and API review therefore belongs in a later,
separately authorized Specification Review. This avoids turning readiness
analysis into premature roadmap or implementation design.

## 3. Current State Confirmation

- Stage 2.5 — Rust Core Philosophy Bridge: PASS WITH NOTES / COMPLETE.
- Current stage: Stage 3 — Blockchain Foundations.
- Sprint-21: PASS WITH NOTES / CLOSED.
- Sprint-22: PASS WITH NOTES / CLOSED.
- Active learning sprint: None.
- Teacher execution window: Closed / inactive.
- Stage 3: Started but incomplete.
- Sprint-23: A candidate capability direction is recommended by this review,
  but no direction is accepted and no Specification Review, roadmap,
  acceptance, or execution authorization exists.
- Stage 4 / Solana execution: Unauthorized.

Sprint-22 validated its narrow hash-literacy boundary. It did not validate
keys, signatures, transaction authorization, wallets, accounts, consensus, or
Solana readiness.

## 4. Remaining Stage 3 Gaps

The current ledger still records these partially covered areas:

- transaction concepts and lifecycle;
- block and chain concepts beyond the in-memory toy model;
- local validation versus replicated validation, consensus, and finality;
- trust assumptions and threat models;
- deterministic state transitions and protocol invariants;
- serialization, canonical representation, and protocol data;
- security-oriented thinking;
- chain-general versus chain-specific distinctions.

The ledger records these areas as missing or not yet durably covered:

- keys, addresses, wallets, accounts, and signatures;
- UTXO versus account/state models;
- nodes, networking, and propagation;
- smart-contract or on-chain-program basics;
- fees and resource constraints;
- blockchain official-documentation application;
- Solana-readiness prerequisites.

These gaps must remain separate dependency-ordered planning units. They should
not be compressed into one sprint.

## 5. Review Of The Architect Hypothesis

The hypothesis `keys / addresses / wallets / accounts / signatures` is
directionally correct but too broad for one cohesive next boundary.

- Public/private key roles and digital signatures form one cryptographic and
  verification capability.
- An address is a protocol-specific identifier or representation. It is not
  universally identical to a public key.
- A wallet is a key-management, signing, monitoring, and user-workflow
  boundary, not merely a key pair.
- An account is a protocol state-model concept. Bitcoin, Ethereum, and Solana
  do not use one interchangeable account abstraction.
- Custody, key generation, backup, recovery, and production secret handling
  add substantial security and operational scope.

Combining all five terms would risk shallow vocabulary coverage, chain-model
conflation, unsafe secret-handling exercises, and insufficient scenario-based
validation. The next unit should establish the signature foundation first.

## 6. Recommended Next Capability Boundary

Recommended direction:

`Public-Key Roles, Digital Signatures, And Verification Boundaries`

The conceptual core should include:

- asymmetric public/private key roles without deriving or implementing the
  underlying mathematics;
- signing versus encryption;
- the exact message bytes, signature, and public key required for verification;
- what successful and failed verification support as claims;
- why verification does not by itself establish public-key identity, broad
  application authorization, account permission, consensus, or transaction
  acceptance;
- how Sprint-22 canonical-input and hash boundaries carry into signed-data
  workflows;
- why reviewed implementations and source-backed test vectors must replace
  learner-authored cryptographic primitives.

Addresses, wallets, custody, and accounts may appear only as short boundary
comparisons that explain what the recommended unit does not yet establish.
They should not be assessed as covered by that exposure.

If a later Specification Review selects an applied artifact, the safest
candidate is an offline, bounded signed-message verification lab using an
established library and published test vectors. A valid vector plus controlled
message, signature, and public-key changes can test claim boundaries without
real funds, network access, or learner-authored cryptography. This is a
planning option, not an authorized project or implementation decision.

## 7. External Baseline And Job-Transfer Quality Gate

### Authoritative Baseline

NIST FIPS 186-5 supplies the general digital-signature standard and distinguishes
signature verification from the additional assurance needed to bind a public
key to a claimed signer. RFC 8032 supplies an inspectable EdDSA definition,
verification procedure, security considerations, and published Ed25519 test
vectors. Official Bitcoin and Ethereum documentation supplies real transaction,
key, signature, account, and wallet context. Official Solana transaction
documentation is a later dependency anchor showing that signatures authorize a
serialized transaction message and interact with account keys; it is not an
authorization to teach Solana execution now.

### Real-World Workflow

The real workflow is to receive or construct exact message bytes, obtain the
claimed public key and signature, call a reviewed verification API, handle
malformed or invalid inputs explicitly, and interpret the result within the
application's identity and authorization policy. This is the same core boundary
encountered in signed messages, transaction authorization, API request signing,
artifact verification, and blockchain clients.

### Toy Or Simplification Boundary

A future bounded lab may use public test vectors or synthetic offline fixtures.
It must not use real wallet material, real funds, production credentials,
network submission, custom cryptographic primitives, or production-security
claims. It demonstrates library use and verification reasoning, not secure key
generation, custody, identity infrastructure, wallet engineering, or protocol
authorization.

### Concrete Job Transfer

After a successful future unit, the learner should be able to:

- explain public/private key and signature roles in an interview without
  confusing signing with encryption;
- read an official signature specification and a Rust crate's rustdoc;
- integrate a reviewed verification API with explicit parse and error handling;
- use published test vectors and controlled negative cases;
- identify the exact bytes being verified and diagnose representation mismatch;
- state what a valid signature proves and what application-level identity,
  authorization, transaction, and consensus checks remain.

This is concrete junior-to-mid Rust/blockchain work rather than generic
cryptography exposure.

### Dependency Order

The boundary should follow Sprint-22 because signature systems depend on precise
byte representation, hashing context, integrity claims, and reviewed-library
discipline. It should precede transaction authorization, wallet/custody design,
address derivation, account/state comparison, realistic state transitions, and
Stage 4 signer workflows.

### Explicitly Out Of Scope

- learner-authored cryptographic algorithms or curve arithmetic;
- production key generation, entropy design, or random-number engineering;
- seed phrases, backups, recovery, hardware wallets, HSMs, KMSs, or custody
  operations;
- real private keys, real funds, credentials, network submission, RPC, devnet,
  or testnet;
- full address derivation or encoding;
- wallet implementation;
- UTXO, Ethereum account/state, or Solana account implementation;
- transaction lifecycle, fees, replay prevention, mempool/admission, consensus,
  or finality;
- smart contracts, on-chain programs, Anchor, PDA, CPI, or Stage 4 execution;
- production-security certification or universal security claims.

Quality-gate result: PASS FOR FURTHER SPECIFICATION REVIEW. The recommended
boundary has a concrete external baseline, realistic workflow, honest toy
boundary, job-transfer capability, dependency rationale, and explicit non-goals.
This result does not accept a sprint direction or authorize roadmap creation.

## 8. Bounded Rust Dependency-Readiness Audit

### Must Teach Before Sprint

No independent Rust topic currently requires a new Rust-only sprint or a full
Rust restart. All identified P0 and P1 pre-Stage-3 topics remain sufficiently
covered for the current curriculum point.

Before dependent execution, a future Specification Review must nevertheless
select and verify the exact library version, Cargo features, rustdoc API,
required trait imports, accepted key/signature input forms, error behavior, and
local build/test evidence. This is a dependency-evidence prerequisite, not a
new Rust curriculum block.

### Just-In-Time Checkpoint Support

- fixed-size arrays such as `[u8; N]` versus borrowed slices such as `&[u8]`;
- fallible slice-to-array or decoded-byte conversion through `TryFrom` or an
  equivalent dependency API;
- `Result`-based handling for malformed public keys, malformed signatures,
  fixture decoding, and verification failure;
- inherent methods versus trait-provided methods, trait imports, and compiler
  hints for method resolution;
- Cargo dependency version requirements and only the selected feature flags;
- rustdoc navigation for constructors, parsing, verification methods, error
  types, and feature-gated APIs;
- hex or other fixture decoding only if the selected published vectors require
  it.

### Carry-Forward Reinforcement

- ownership and borrowing at byte-slice API boundaries;
- exact byte input, UTF-8 boundaries, and canonical representation from
  Sprint-22;
- enums, `Result`, `?`, custom error boundaries, and focused negative tests;
- module visibility, narrow public APIs, and learner explanation of what each
  test proves;
- trait method resolution and trait-in-scope requirements;
- source-backed dependency usage, version labeling, and local verification.

### Future Only

- cryptographically secure random-number generation and production key
  generation;
- zeroization, protected memory, secure storage, key rotation, backup, recovery,
  and custody implementation;
- broad binary serialization, Borsh, protocol codecs, and address encodings;
- async Rust, RPC, networking, transaction submission, and client runtimes;
- concurrency, hardware-signing integration, and production wallet architecture;
- chain-specific SDK and Solana account/program types.

Audit result: READY WITH JUST-IN-TIME SUPPORT. The likely Rust surface is
bounded, maps to already covered foundations, and does not justify reopening
Rust training. Exact dependency behavior remains intentionally unresolved until
a separately authorized Specification Review selects a crate and verifies its
current documentation and local behavior.

## 9. Sprint-22 Teaching-Pattern Carry-Forward

A future Specification Review should preserve the successful Sprint-22 pattern
without copying its roadmap mechanically:

1. compact prerequisite inventory;
2. Chinese-first explanation with English technical terms scaffolded inline;
3. concept-first sequencing;
4. bounded implementation only after claim boundaries are stable;
5. source-backed and locally verified dependency examples;
6. just-in-time Rust reinforcement;
7. scenario-based validation, including altered message, signature, and public
   key cases;
8. explicit job-transfer and interview relevance.

## 10. Recommended Next Governance Action

The learner or Architect should review and either accept, revise, or reject the
recommended capability boundary. If it is accepted, the next separately
authorized artifact should be a Sprint-23 Specification Review that resolves
the exact learning density, dependency and test-vector choice, learner artifact,
validation layers, and safe secret-handling boundary.

No Sprint-23 Specification Review or roadmap is created by this document. No
sprint is accepted or active. No Teacher window, learning-project work, Stage 4,
or Solana execution is authorized.

## 11. Final Planning Verdict

Planning review verdict: COMPLETE — RECOMMEND
`Public-Key Roles, Digital Signatures, And Verification Boundaries` as the next
cohesive Stage 3 capability boundary for human or Architect review.

Authorization verdict: NO EXECUTION AUTHORIZED.
