# Sprint-23 — Public-Key Roles, Digital Signatures, And Verification Boundaries

## 1. Identity And Status

- Sprint: Sprint-23
- Title: Public-Key Roles, Digital Signatures, And Verification Boundaries
- Stage: Stage 3 — Blockchain Foundations
- Status: ACCEPTED / NOT STARTED / NOT ACTIVE
- Specification Review: `reviews/sprint-23-specification-review.md`
- Dependency probe: PASS — `ed25519-dalek = "=2.2.0"` locally verified for the roadmap's bounded verification surface
- Roadmap owner: Architect draft after explicit learner authorization
- Teacher execution: Not authorized
- Learning project: `signature_verification_lab`; candidate only; not created
- Stage 4 / Solana execution: Unauthorized

This accepted roadmap records the Sprint-23 execution contract. Acceptance does
not start Sprint-23, open a Teacher execution window, create the candidate
project, authorize checkpoint work, or create execution authority.

## 2. Authorization Boundary

The roadmap has been accepted. Roadmap acceptance does not:

- activate or start Sprint-23;
- open a Teacher execution window;
- create or modify a learning project;
- authorize checkpoint instruction or learner implementation work;
- authorize creation of `signature_verification_lab`;
- complete Stage 3;
- authorize Stage 4 or Solana execution.

The learner has accepted this roadmap. Sprint-23 remains not started until the
learner gives a separate explicit Teacher-window or sprint-execution start
command under the Sprint Execution Start Gate.

## 3. Sprint Purpose And Stage Alignment

Sprint-23 should establish a precise, source-backed foundation for public-key
roles, digital signatures, and verification claims. By closure, the learner
should be able to explain and apply:

- public-key and private-key roles at a conceptual level;
- digital signature verification;
- signing versus encryption;
- the exact message bytes, public key, and signature used as verification
  inputs;
- valid, invalid, and malformed verification outcomes;
- what a valid signature supports as a claim and what it does not prove;
- why signature verification is not by itself address ownership, wallet
  custody, account authorization, transaction acceptance, consensus, or
  finality;
- how Sprint-22 exact-byte and canonical-input reasoning carries into
  signed-data workflows;
- why reviewed cryptographic libraries and published test vectors replace
  learner-authored cryptographic primitives.

This scope belongs in Stage 3 because signature literacy is a prerequisite for
later transaction authorization, wallet and custody boundaries, account/state
comparison, realistic state transitions, and Solana signer workflows. Those
later topics are dependency context, not Sprint-23 execution scope.

## 4. Evidence And Coverage Gap

This roadmap is based on:

- `reviews/sprint-23-specification-review.md`;
- `reviews/post-sprint-22-stage-3-planning-review.md`;
- `reviews/sprint-22-closure.md`;
- `reviews/stage-3-blockchain-coverage-ledger.md`;
- `reviews/rust-core-coverage-matrix.md`;
- `reviews/stage-3-4-external-alignment-audit.md`;
- `roadmaps/master-roadmap.md`.

Sprint-22 provides durable exact-byte, canonical-input, hash-boundary, and
reviewed-library evidence. The Stage 3 ledger still records keys, addresses,
wallets, accounts, and signatures as missing or not yet durably covered.
Sprint-23 narrows that broad gap to public/private-key roles, signature
verification, and verification boundaries. It does not change a coverage
classification before validated learning and closure evidence exists.

## 5. External Baseline And Job-Transfer Target

1. **Authoritative source or recognized benchmark:**
   [NIST FIPS 186-5 — Digital Signature Standard](https://csrc.nist.gov/pubs/fips/186-5/final),
   [RFC 8032 — Edwards-Curve Digital Signature Algorithm](https://www.rfc-editor.org/rfc/rfc8032.html)
   and its Ed25519 test vectors,
   [`ed25519-dalek` 2.2.0 rustdoc](https://docs.rs/ed25519-dalek/2.2.0/ed25519_dalek/),
   and official Rust documentation for arrays and slices, `Result`, traits,
   method resolution, and Cargo dependency requirements.
2. **Real-world concept or workflow:** receive exact message bytes, a claimed
   public key, and a signature; parse them through a reviewed API; verify the
   signature; and interpret the result within a wider identity and
   authorization policy.
3. **Toy or simplification boundary:** use public RFC test fixtures in an
   offline library lab. Do not use private material, signing, wallet state,
   network submission, transaction processing, or production-security claims.
4. **Transferable engineering capability:** read a signature specification and
   crate rustdoc, integrate a reviewed verification API, use published test
   vectors, handle malformed and invalid inputs, and diagnose byte-
   representation mismatch.
5. **Interview or industry relevance:** explain public/private-key and signature
   roles, signing versus encryption, verification inputs, invalid versus
   malformed input, and the boundary between cryptographic verification and
   identity, authorization, transaction, and consensus claims.
6. **Path toward a more realistic artifact or workflow:** later Stage 3 units
   may apply this boundary to transaction authorization and signer workflows
   after wallet/custody, account/state, transaction-lifecycle, and security
   prerequisites are taught and validated.
7. **Real-world setup or prerequisites:** a compatible local Rust toolchain and
   the pinned, source-verified dependency. No account, wallet, credential,
   network, token, or real-funds setup is required.

Secret-handling boundary: no private key, seed phrase, wallet material,
credential, API secret, or real-funds information may be pasted into Teacher,
Architect, or Codex chat or committed to any repository.

## 6. Dependency Probe Record

The temporary probe at `/tmp/sprint23-ed25519-probe-20260707` passed before
roadmap drafting.

- Declared dependency: `ed25519-dalek = "=2.2.0"`.
- Resolved dependency: `ed25519-dalek 2.2.0`.
- Commands passed: `cargo fmt --check`, `cargo check`, `cargo test`,
  `cargo tree -e features -i ed25519-dalek`, `rustc --version`, and dependency
  inspection in `Cargo.toml` and `Cargo.lock`.
- Tests: four passed, including the RFC 8032 valid vector, altered-message
  rejection, malformed-signature-length rejection, and trait-provided
  verification behavior.
- Explicit feature flags: none required for this verification-only path.
- Default features observed: `alloc`, `std`, `fast`, and `zeroize`.
- `VerifyingKey::verify_strict`: inherent method; no trait import required.
- Trait-provided `verify`: requires `ed25519_dalek::Verifier` in scope.
- Toolchain: Rust 1.95.0; compatible with the crate's Rust 1.81 MSRV.

The probe is dependency evidence only. It is not a learning project, learner
implementation, or Sprint-23 execution evidence.

## 7. Compact Prerequisite Inventory

Before requiring dependent work, the Teacher must teach or confirm this compact
inventory.

### Teach Before Use

- public-key and private-key conceptual roles;
- digital signature purpose and verification workflow;
- signing versus encryption;
- exact message bytes and representation boundaries;
- Ed25519 as the selected reviewed algorithm, without curve mathematics;
- RFC 8032 test-vector structure and the role of public fixtures;
- what valid, invalid, and malformed outcomes mean and do not mean;
- safe handling: public fixtures only, with no private or wallet material.

### Just-In-Time Support

- `ed25519-dalek` 2.2.0 and rustdoc navigation;
- `[u8; 32]`, `[u8; 64]`, and `&[u8]`;
- fallible byte parsing and slice-to-array conversion;
- `Result` and error classification for malformed and invalid inputs;
- inherent methods, trait method resolution, trait-in-scope requirements, and
  UFCS where relevant;
- Cargo exact-version pinning and feature awareness;
- ownership and borrowing at byte-slice API boundaries;
- focused positive and negative tests.

This inventory is setup and teaching support, not a prerequisite examination or
a separate Rust sprint. No Rust restart is required.

## 8. Learning Project Candidate

- Candidate name: `signature_verification_lab`
- Candidate type: fresh offline Rust library crate
- Expected future path: `/Users/dumplings/workspace/signature_verification_lab`
- Current state: not created

The project must not be created until Sprint-23 execution is explicitly started
after roadmap acceptance. This roadmap neither creates nor authorizes the
project.

Candidate artifact boundaries:

- library-only or library-first;
- no CLI unless separately justified as a tiny wrapper after library behavior
  is stable and without changing sprint scope;
- public RFC or equivalent reviewed test fixtures only;
- verify a valid vector and controlled negative cases;
- no real keys or wallet material;
- no key generation or signing workflow;
- no address derivation;
- no network, RPC, devnet, testnet, or mainnet;
- no transaction submission;
- no Solana SDK;
- no learner-authored cryptographic primitive.

## 9. Proposed Public API Shape

This section is roadmap guidance, not final implementation code.

The future lab should likely expose:

- one narrow verification function that receives explicit message, public-key,
  and signature bytes;
- typed or explicit parse errors for malformed public-key and signature inputs;
- a result or error boundary that distinguishes malformed input from a
  well-formed invalid signature;
- a narrow public surface that does not expose signing or key-management APIs;
- tests whose names and assertions make the claim boundary visible.

Exact type and error names remain learner design decisions within the accepted
roadmap boundary. The Teacher should explain the contract and review criteria
without providing a near-final implementation first.

## 10. Checkpoint Plan

### Checkpoint 1 — Concept Boundary: Keys, Signatures, And Verification Claims

Teaching targets:

- teach public/private-key roles and signing versus encryption;
- identify exact message, public-key, and signature inputs;
- distinguish successful verification, invalid verification, and malformed
  input;
- separate signature verification from addresses, wallets, custody, accounts,
  transactions, consensus, and finality.

Learner evidence:

- explain the verification workflow in their own words;
- classify several claims as supported or unsupported by a valid signature;
- identify the additional identity or authorization policy required by a
  realistic application.

The Teacher must confirm stable conceptual reasoning before source or code work.

### Checkpoint 2 — Source And Dependency Reading

Teaching targets:

- read the relevant RFC 8032 test-vector structure;
- navigate `ed25519-dalek` 2.2.0 rustdoc for `VerifyingKey`, `Signature`,
  parsing, and `verify_strict`;
- confirm the exact dependency pin, default features, API surface, toolchain
  compatibility, and recorded dependency probe;
- teach arrays, slices, fallible parsing, `Result`, and trait method resolution
  as needed;
- distinguish inherent `verify_strict` from trait-provided `verify`.

Learner evidence:

- locate and explain the relevant specification and rustdoc entries;
- identify which inputs have fixed lengths and where conversion may fail;
- explain why the dependency is pinned and why no signing feature is needed.

### Checkpoint 3 — Minimal Verification Lab

Implementation boundary after explicit execution start:

- learner creates the fresh library crate;
- declare `ed25519-dalek = "=2.2.0"` without silently substituting another
  version;
- implement a narrow verification function using a published public RFC 8032
  vector;
- distinguish malformed public-key or signature input from a well-formed
  invalid signature;
- add tests for the valid vector and malformed-length parsing;
- keep the learner as the primary implementer.

No key generation, signing, wallet, address, network, transaction, or Solana
SDK work is permitted.

### Checkpoint 4 — Negative Cases And Claim Boundaries

Required controlled cases:

1. altered message;
2. altered signature;
3. altered public key;
4. malformed-length input.

Learner evidence:

- implement focused tests for all four cases;
- explain why altered but well-formed data differs from malformed input;
- identify exactly which bytes changed;
- explain what each failure demonstrates and what it does not prove;
- diagnose at least one representation-mismatch scenario.

### Checkpoint 5 — Review, Job Transfer, And Interview Preparation

Required work:

- complete source-level review of API, errors, dependency use, and tests;
- map the lab to real offline verification workflows;
- explain external-baseline and job-transfer relevance;
- complete current Student Validation;
- prepare and complete Codex Repository Validation;
- complete Teacher Learning Validation;
- create the sprint interview-prep pack unless the learner explicitly waives
  it;
- preserve remaining Stage 3 gaps without claiming wallet, account,
  transaction, consensus, or Solana coverage.

## 11. Validation Requirements

### Student Validation

The learner must report current PASS/FAIL results after the final code change
for:

- `cargo fmt --check`;
- `cargo check`;
- `cargo test`.

The learner must also explain:

- what the positive vector test demonstrates;
- what each altered-input test demonstrates;
- malformed versus well-formed invalid input;
- the exact message, public key, and signature bytes;
- what successful verification proves and does not prove.

### Codex Repository Validation

Validation target:

`/Users/dumplings/workspace/signature_verification_lab`

This must be a separate one-repository validation prompt. Codex should inspect:

- changed files and repository status;
- `Cargo.toml` and `Cargo.lock` dependency versions;
- enabled dependency features;
- source and tests;
- compiler and test results;
- public API and error boundaries;
- use of public fixtures only;
- absence of secrets, signing, key generation, wallet, address, network, RPC,
  transaction, Solana, and learner-authored cryptographic code;
- scope compliance.

Codex should independently run:

- `cargo fmt --check`;
- `cargo check`;
- `cargo test`.

### Teacher Learning Validation

Teacher validation must verify:

- conceptual public/private-key and signature roles;
- signing versus encryption;
- identification of exact message, public key, and signature inputs;
- valid versus invalid versus malformed outcomes;
- cryptographic verification claim boundaries;
- rustdoc and source navigation;
- representation-mismatch diagnosis;
- job-transfer explanation.

Passing tests or Codex validation alone does not establish learning success.

## 12. Explicit Non-Goals

Sprint-23 must not include:

- learner-authored cryptographic algorithms, Ed25519 internals, or curve
  arithmetic;
- private-key generation, randomness, entropy design, custody, secure storage,
  seed phrases, backup, recovery, hardware wallets, HSMs, or KMSs;
- real private keys, real funds, credentials, wallet material, RPC, devnet,
  testnet, or mainnet;
- address derivation or address encoding;
- wallet implementation;
- transaction creation, transaction signing, fees, replay protection, mempool
  or admission behavior, consensus, or finality;
- UTXO or account/state implementation;
- smart contracts, on-chain programs, Anchor, PDA, CPI, Solana SDK use, or
  Stage 4 execution;
- production-security certification or universal security claims;
- broad serialization or protocol codecs;
- signing APIs or keypair workflows added only for demonstration convenience;
- modification of `mini_blockchain` or `crypto_hash_literacy_lab`;
- treating brief comparison context as completed coverage of later topics.

## 13. Teaching Requirements

- Conduct technical teaching in Chinese.
- Scaffold every English technical term inline in Chinese on first checkpoint
  use and control terminology density.
- Teach concept, mental model, workflow, boundaries, common mistakes, and
  acceptance criteria before learner implementation.
- Present the compact prerequisite inventory before dependent work.
- Keep the learner as the primary implementer.
- Use official definitions, RFC material, rustdoc, and locally verified
  dependency behavior.
- Distinguish official documentation, local inference, local build/test
  verification, and version-sensitive behavior.
- Teacher-provided tests or small examples may support learning, but the Teacher
  must not provide a near-final core implementation first.
- Pause and review at checkpoint boundaries before progressing.
- Preserve the three independent validation layers.

## 14. Interview-Prep Pack Requirement

Before normal closure, the Teacher must provide:

`interview-prep/sprints/sprint-23-public-key-roles-digital-signatures-and-verification-boundaries.md`

unless the learner explicitly waives it.

The pack must be written in Chinese and cover:

- public/private-key roles;
- signing versus encryption;
- message, public-key, and signature inputs;
- valid, invalid, and malformed distinctions;
- verification claim boundaries;
- reviewed-library use;
- published test vectors;
- common misconceptions.

Each question must use concise `考点` lookup tags and a separate `回答示例`
section with interview-ready wording, following the Teacher execution policy.

## 15. Acceptance And Completion Criteria

### Roadmap Acceptance Criteria

The learner should accept this roadmap only after confirming that:

1. the dependency probe PASS is recorded;
2. the scope remains public-key roles, signature verification, and claim
   boundaries;
3. wallet, account, transaction, consensus, and Solana execution remain out of
   scope;
4. the checkpoint sequence is small and concept-first;
5. the candidate artifact is offline, bounded, and uses public fixtures only;
6. all three validation layers are explicit;
7. all non-goals and secret-handling boundaries are preserved.

### Sprint Completion Criteria

If later explicitly started, Sprint-23 may close only when:

1. all five checkpoints are completed;
2. the learner remains the primary implementer;
3. the valid RFC vector and all required negative cases are implemented and
   explained;
4. Student Validation passes after the final code change;
5. Codex Repository Validation passes or passes with notes and has no blocking
   finding;
6. Teacher Learning Validation passes or passes with notes;
7. the interview-prep pack exists or the learner's waiver is recorded;
8. scope and secret-handling boundaries remain compliant;
9. closure records capability growth and remaining Stage 3 gaps without
   implying later-topic coverage or Stage 4 authorization.

## 16. Risks And Controls

- **Vocabulary compression:** do not combine keys, addresses, wallets,
  accounts, and signatures into one shallow unit; keep later concepts as brief
  boundary comparisons only.
- **Code before claims:** Checkpoint 1 must stabilize verification meaning before
  dependency or implementation work.
- **Hidden Rust prerequisites:** use the compact inventory and teach arrays,
  slices, parsing, `Result`, traits, and rustdoc navigation just in time.
- **API drift:** preserve exact version `=2.2.0`; any dependency change requires
  new local verification and scope review.
- **Signing-scope drift:** use verification APIs only; do not add key generation
  or signing for convenience.
- **Fixture confusion:** use public test vectors and identify exact message,
  key, and signature bytes.
- **Test-only success:** require learner explanation and Teacher validation;
  passing code does not prove conceptual understanding.
- **Security overclaim:** distinguish cryptographic verification from identity,
  authorization, transaction acceptance, consensus, finality, and production
  security.

## 17. Final Roadmap Boundary

Roadmap status: ACCEPTED / NOT STARTED / NOT ACTIVE.

This roadmap does not start learning execution, create the candidate project,
open a Teacher execution window, issue checkpoint work, complete Stage 3, or
authorize Stage 4 / Solana execution.

The next possible learner decision is an explicit Teacher-window or
sprint-execution start command. Execution still requires the Sprint Execution
Start Gate; roadmap acceptance alone does not start Sprint-23.
