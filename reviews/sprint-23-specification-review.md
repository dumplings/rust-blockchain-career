# Sprint-23 Specification Review

## 1. Review Identity

- Review date: 2026-07-07
- Review owner: Architect, with Codex as repository update bridge
- Curriculum stage: Stage 3 — Blockchain Foundations
- Review type: Sprint-23 Specification Review
- Candidate boundary: `Public-Key Roles, Digital Signatures, And Verification Boundaries`
- Review status: PASS WITH NOTES — READY FOR ROADMAP DRAFTING AFTER SEPARATE LEARNER AUTHORIZATION
- Sprint-23 roadmap: Not created
- Learning execution: Not authorized
- Stage 4 / Solana execution: Unauthorized

This review evaluates one candidate Sprint-23 capability boundary. It is not a
sprint roadmap, roadmap acceptance, Teacher start, learning-execution
authorization, or Stage 4 / Solana authorization.

## 2. Evidence Reviewed

Local repository evidence:

- `AGENTS.md`;
- `CONTEXT.md`;
- `docs/policies/lifecycle-policy.md`;
- `docs/policies/learning-execution-policy.md`;
- `docs/policies/repository-validation-policy.md`;
- `templates/specification-review-template.md`;
- `roadmaps/master-roadmap.md`;
- `reviews/post-sprint-22-stage-3-planning-review.md`;
- `reviews/sprint-22-closure.md`;
- `reviews/stage-3-blockchain-coverage-ledger.md`;
- `reviews/rust-core-coverage-matrix.md`;
- `reviews/stage-3-4-external-alignment-audit.md`;
- `reviews/stage-3-repair-direction-decision.md`;
- `reviews/architect-retirement-handover-2026-07-07-post-sprint-22.md`.

Authoritative external baselines:

- [NIST FIPS 186-5 — Digital Signature Standard](https://csrc.nist.gov/pubs/fips/186-5/final);
- [RFC 8032 — Edwards-Curve Digital Signature Algorithm](https://www.rfc-editor.org/rfc/rfc8032.html), including published Ed25519 test vectors;
- [`ed25519-dalek` 2.2.0 rustdoc](https://docs.rs/ed25519-dalek/2.2.0/ed25519_dalek/), including `VerifyingKey`, `Signature`, and `verify_strict`;
- [The Rust Programming Language — Data Types](https://doc.rust-lang.org/book/ch03-02-data-types.html);
- [The Rust Programming Language — Recoverable Errors with `Result`](https://doc.rust-lang.org/book/ch09-02-recoverable-errors-with-result.html);
- [The Rust Programming Language — Traits](https://doc.rust-lang.org/book/ch10-02-traits.html);
- [The Rust Reference — Method Call Expressions](https://doc.rust-lang.org/reference/expressions/method-call-expr.html);
- [Rust by Example — Arrays and Slices](https://doc.rust-lang.org/rust-by-example/primitives/array.html);
- [The Cargo Book — Specifying Dependencies](https://doc.rust-lang.org/cargo/reference/specifying-dependencies.html);
- [`std::convert::TryFrom`](https://doc.rust-lang.org/std/convert/trait.TryFrom.html).

Dependency metadata and API documentation were inspected on 2026-07-07.
The stable docs.rs release identified for `ed25519-dalek` was 2.2.0, while the
3.x line was represented by prereleases such as 3.0.0-rc.1. Version 2.2.0
declares Rust 1.81 as its minimum supported Rust version, and its documented API
contains the bounded verification surface required by this candidate.

Local dependency probe: NOT RUN / PENDING. The local toolchain is Rust 1.95.0,
but `ed25519-dalek` 2.2.0 was not present in the local Cargo registry cache and a
network download would have been required. This does not fail the Specification
Review. Local build and test verification remains mandatory during roadmap
drafting or before execution.

## 3. Current State Confirmation

- Stage 2.5 — Rust Core Philosophy Bridge: PASS WITH NOTES / COMPLETE.
- Current stage: Stage 3 — Blockchain Foundations.
- Stage 3 status: Started but incomplete.
- Sprint-21: PASS WITH NOTES / CLOSED.
- Sprint-22: PASS WITH NOTES / CLOSED.
- Active learning sprint: None.
- Teacher execution window: Closed / inactive.
- Sprint-23: This Specification Review is created by this update only; no
  roadmap, acceptance, Teacher start, or execution authorization exists.
- Stage 4 / Solana execution: Unauthorized.

## 4. Specification Verdict

Verdict: PASS WITH NOTES.

`Public-Key Roles, Digital Signatures, And Verification Boundaries` is a
cohesive, dependency-ordered Stage 3 capability boundary after Sprint-22.
Sprint-22 established the exact-byte, canonical-input, hash-claim, and
reviewed-library foundations needed to reason about signed data without
compressing wallets, accounts, transactions, and chain-specific execution into
the same unit.

This boundary should precede transaction authorization, wallet and custody
work, account/state comparison, realistic state transitions, and later Solana
signer workflows. Roadmap drafting is allowed only after separate explicit
learner authorization.

## 5. Learning Capability Boundary

A future Sprint-23 roadmap should teach and validate:

- conceptual public-key and private-key roles without deriving or implementing
  the underlying mathematics;
- signing versus encryption;
- the exact message bytes, public key, and signature required as verification
  inputs;
- successful verification versus invalid verification as a bounded claim;
- why successful verification does not by itself prove address ownership,
  wallet custody, account authorization, transaction acceptance, consensus, or
  finality;
- how Sprint-22 exact-byte and canonical-input reasoning applies to signed-data
  workflows;
- why reviewed cryptographic libraries and published test vectors are required
  instead of learner-authored primitives;
- how malformed input differs from a well-formed but invalid signature.

Addresses, wallets, custody, accounts, and transactions may appear only as
short boundary comparisons. Such exposure must not be counted as coverage of
those later capabilities.

## 6. Proposed Future Learning Artifact

Recommended roadmap candidate: an offline Rust library lab tentatively named
`signature_verification_lab`.

The candidate lab would verify published Ed25519 signed-message test vectors
and controlled negative cases. It should accept or embed synthetic public test
fixtures, parse bounded byte inputs, call a reviewed verification API, report
parse or verification failure explicitly, and test what changes invalidate the
claim.

The lab must not generate real keys, store private keys, use wallet material,
connect to a network, submit transactions, handle real funds, or implement a
cryptographic primitive. This is a candidate artifact for later roadmap design,
not an accepted project, implementation instruction, or authorization to create
a learning repository.

## 7. Dependency And API Boundary

Preferred teaching dependency candidate:

`ed25519-dalek = "=2.2.0"`

Exact pinning prevents an unreviewed semver update from changing the teaching
API during the sprint. Version 2.2.0 has the required verification-only surface
and is preferable to adopting a 3.x prerelease for this bounded learning unit.

Candidate API surface:

- `VerifyingKey::from_bytes`;
- `Signature::from_bytes` or `Signature::from_slice`, selected according to the
  exact input representation and desired malformed-length boundary;
- `VerifyingKey::verify_strict`;
- `Result`-based public-key parsing, signature parsing, and verification errors.

The future roadmap should distinguish inherent methods from optional
trait-provided verification methods and identify any trait imports before
requiring their use. The bounded artifact should prefer `verify_strict`; it must
not broaden into signing APIs merely to demonstrate a trait.

Signing APIs, random key generation, custody, seed phrases, storage,
networking, wallet crates, and Solana SDKs are outside the candidate dependency
surface. `hex` or `hex-literal` may be used only as an optional fixture helper
when the selected published vectors require it; hex decoding is not a central
learning objective.

Before execution, the roadmap must verify the exact crate version, enabled
features, rustdoc API, local build and test behavior, transitive resolution,
and MSRV/toolchain compatibility. If `ed25519-dalek = "=2.2.0"` is not locally
viable, roadmap work must either select a locally verified alternative or
return to Architect review. It must not silently substitute a different major
or prerelease version.

## 8. Rust Dependency Readiness

Verdict: READY WITH JUST-IN-TIME SUPPORT.

No Rust restart is required. No independent Rust-only blocker exists for this
candidate. Before dependent work, the Teacher or future roadmap must teach or
confirm:

- fixed-size arrays such as `[u8; 32]` and `[u8; 64]` versus borrowed slices
  such as `&[u8]`;
- fallible byte parsing and slice-to-array conversion;
- `Result` handling for malformed public keys, malformed signatures, and
  invalid verification;
- inherent versus trait-provided methods, trait method resolution,
  trait-in-scope requirements, and fully qualified syntax when relevant;
- rustdoc navigation for constructors, parsing methods, verification methods,
  error types, and features;
- exact dependency pinning and feature awareness.

Carry-forward reinforcement:

- ownership and borrowing at byte-slice API boundaries;
- exact byte representation and canonical-input reasoning from Sprint-22;
- focused positive and negative tests;
- narrow public APIs and explicit error boundaries;
- source-backed dependency use and explanation of what each test proves.

## 9. Validation Requirements For A Future Roadmap

The future roadmap must define all three independent validation layers.

### Student Validation

- The learner runs the required formatting, compiler, and test commands.
- The learner explains what each positive and negative test proves and does not
  prove.
- The learner identifies the exact bytes, public key, and signature used by the
  verification call.

### Codex Repository Validation

- Inspect repository state, changed-file scope, dependency declarations and
  resolved versions, compiler status, test status, API usage, secret handling,
  and scope compliance.
- Confirm that no signing, key-generation, wallet, network, transaction, or
  learner-authored cryptographic implementation entered the artifact.

### Teacher Learning Validation

- Validate conceptual public/private-key and signature roles;
- validate signing-versus-encryption reasoning;
- validate interpretation of successful, invalid, and malformed verification
  outcomes;
- validate source and rustdoc navigation;
- validate explanation quality and verification-claim boundaries.

Required negative cases must include at least:

1. altered message;
2. altered signature;
3. altered public key;
4. malformed-length input.

Passing tests alone do not establish learning success. The learner must explain
what a valid signature supports and which identity, authorization, transaction,
network, consensus, and finality checks remain outside that result.

## 10. Explicit Non-Goals

- learner-authored cryptographic algorithms, Ed25519 internals, or curve
  arithmetic;
- private-key generation, randomness, entropy design, custody, secure storage,
  seed phrases, backup, recovery, hardware wallets, HSMs, or KMSs;
- real private keys, real funds, credentials, wallet material, RPC, devnet,
  testnet, or mainnet;
- address derivation or address encoding;
- wallet implementation;
- transaction creation, transaction signing, mempool or admission behavior,
  fees, replay protection, consensus, or finality;
- UTXO or account/state model implementation;
- smart contracts, on-chain programs, Anchor, PDA, CPI, Solana SDK use, or
  Stage 4 execution;
- production-security certification or universal security claims;
- broad serialization, protocol codecs, or binary-format curriculum;
- signing APIs or keypair workflows added only for demonstration convenience.

## 11. External-Baseline And Job-Transfer Quality Gate

Quality-gate verdict: PASS.

- Authoritative source or recognized benchmark: NIST FIPS 186-5, RFC 8032,
  published Ed25519 test vectors, `ed25519-dalek` 2.2.0 rustdoc, and relevant
  official Rust and Cargo documentation.
- Real-world concept or workflow: receive exact message bytes, a claimed public
  key, and a signature; parse them through a reviewed library; verify the
  signature; and interpret the result within a wider identity and authorization
  policy.
- Toy or simplification boundary: offline public fixtures and a small library
  lab, with no private material, signing, network submission, wallet, protocol,
  or production-security claim.
- Transferable engineering capability: read signature specifications and crate
  docs, integrate a reviewed verification API, use published test vectors,
  handle malformed and invalid inputs, and diagnose byte-representation
  mismatch.
- Interview or industry relevance: explain signature roles and distinguish
  cryptographic verification from identity, application authorization,
  transaction acceptance, and consensus.
- Path toward a more realistic artifact or workflow: later apply the verified
  boundary to transaction authorization and signer workflows only after the
  remaining Stage 3 prerequisites are taught and validated.
- Real-world setup or prerequisites: a compatible local Rust toolchain and a
  source-verified pinned dependency; no account, credential, wallet, network, or
  token setup is required.

The candidate avoids low-realism toy-only framing because the lab maps directly
to offline artifact, API-request, signed-message, and blockchain-client
verification boundaries while keeping production secret handling out of scope.

## 12. Roadmap Drafting Requirements

If the learner separately authorizes Sprint-23 roadmap drafting, the roadmap
must:

- teach concept and claim boundaries before code;
- include a compact prerequisite inventory for the crate, API, byte types,
  parsing, traits, fixtures, and toolchain behavior;
- preserve Chinese-first teaching with English technical terminology scaffolded
  inline and controlled for density;
- use a small number of cohesive checkpoints;
- avoid compressing addresses, wallets, custody, accounts, transactions, and
  Solana signer workflows into this sprint;
- record local source-backed dependency, feature, API, MSRV, build, and test
  verification;
- keep the learner as the primary implementer;
- preserve Student Validation, Codex Repository Validation, and Teacher
  Learning Validation;
- require the sprint interview-prep pack unless the learner explicitly waives
  it;
- preserve the external-baseline, safe-fixture, and secret-handling boundaries
  in this review.

## 13. Final Authority Boundary

This update creates only `reviews/sprint-23-specification-review.md` and
synchronizes current governance state.

It does not:

- create or accept a Sprint-23 roadmap;
- accept, activate, or start Sprint-23;
- authorize roadmap drafting without a separate learner decision;
- open a Teacher execution window;
- create or modify a learning project;
- issue checkpoint tasks or begin learning execution;
- change any Stage 3 coverage classification;
- complete Stage 3;
- authorize Stage 4 or Solana execution.

Final Specification Review verdict: PASS WITH NOTES — READY FOR ROADMAP
DRAFTING AFTER SEPARATE LEARNER AUTHORIZATION.

Next possible step: the learner may review this Specification Review and
explicitly authorize Sprint-23 roadmap drafting. No later lifecycle step is
authorized by implication.
