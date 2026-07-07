# Sprint-22 Roadmap — Cryptographic Hash Literacy And Tamper Evidence

## 1. Sprint Identity And Lifecycle Status

* Sprint: Sprint-22
* Title: Cryptographic Hash Literacy And Tamper Evidence
* Stage: Stage 3 — Blockchain Foundations
* Candidate project: `crypto_hash_literacy_lab`
* Lifecycle status: ACCEPTED / NOT STARTED / NOT ACTIVE
* Execution status: UNAUTHORIZED
* Teacher window: Not open

This accepted roadmap records the Sprint-22 execution contract. Acceptance does not
activate or start Sprint-22, open a Teacher window, or authorize creation of the
candidate project.

### Drafting Authority And Ownership Boundary

This roadmap was drafted through an exceptional Architect-authorized intervention
for Stage 3 repair, external-alignment risk, toy-project realism risk, and
job-transfer calibration after Sprint-21. It does not change the normal ownership
rule: Teacher Agents remain the default pedagogical authors of ordinary sprint
specifications and roadmaps. Future normal sprint drafting returns to that default,
with Architect review only when governance, scope, stage alignment, or workflow
separation is uncertain.

## 2. Objective And Stage Alignment

Sprint-22 develops cryptographic hash literacy and tamper-evidence reasoning at a
junior-to-mid interview-usable depth. It repairs the conceptual gap exposed by
Sprint-21 without reopening Sprint-21 or expanding `mini_blockchain`.

By closure, the learner should be able to explain and apply:

* deterministic toy hash versus cryptographic hash;
* preimage resistance, second-preimage resistance, and collision resistance;
* tamper evidence versus tamper prevention;
* integrity versus authentication, authorization, and consensus;
* canonical representation and ambiguous-input risks;
* why reviewed libraries and protocols are used instead of custom primitives;
* what Sprint-21's toy hash and previous-hash linkage demonstrated and did not
  demonstrate.

This objective belongs in Stage 3 because precise hash and integrity reasoning is a
prerequisite for later work on keys, signatures, transaction authorization,
consensus, and Solana. Those later subjects are dependency context, not Sprint-22
execution scope.

## 3. Evidence And Coverage Gap

The roadmap is based on:

* `reviews/stage-3-repair-direction-decision.md`;
* `reviews/sprint-22-specification-review.md`;
* `reviews/stage-3-4-external-alignment-audit.md`;
* `reviews/stage-3-blockchain-coverage-ledger.md`;
* `reviews/sprint-21-closure.md`.

Sprint-21 provides durable evidence for deterministic content-dependent toy
hashing, previous-hash linkage, local recomputation, and basic tamper detection. It
does not establish cryptographic hash properties, canonical protocol inputs,
adversarial security guarantees, authentication, authorization, consensus, or
production security.

The Stage 3 ledger therefore keeps cryptographic hash literacy as missing and hash
and tamper detection as partial. This roadmap does not change either classification;
only later validated evidence and closure or an explicit governance update may do
so.

## 4. Learning Shape And Density

Required shape:

`concept-first -> applied reasoning -> small bounded Rust lab -> scenario transfer -> final validation`

The small lab is required by this roadmap because it provides bounded applied
evidence without turning the sprint into implementation-heavy cryptography work.
A pure written replacement is allowed only through an Architect-approved roadmap
revision before execution. Such a replacement must preserve equivalent applied
verification, unfamiliar-scenario transfer, and all three validation layers.

The sprint has sufficient density through three distinct attacker-goal properties,
security-boundary comparison, canonical-input analysis, source reading, a focused
library-use lab, unfamiliar scenarios, Sprint-21 mapping, and interview transfer.
Code remains subordinate to conceptual understanding.

## 5. Required Scope

The sprint includes:

1. Source-backed cryptographic hash concepts and limits.
2. Deterministic toy hash versus cryptographic hash comparison.
3. Preimage, second-preimage, and collision resistance at conceptual and applied
   scenario depth.
4. Tamper evidence versus tamper prevention.
5. Integrity versus authentication, authorization, and consensus.
6. Canonical representation, ambiguous concatenation, and verification-input
   boundaries.
7. Analysis of Sprint-21's toy hash and hash-linkage boundary.
8. Safe use of an established reviewed hash library without primitive
   implementation.
9. A learner-authored lab README or equivalent artifact that records sources,
   claims, limitations, examples, and Sprint-21 mapping.
10. Focused Rust tests that preserve the lab's intended learning behavior.
11. Scenario-based Teacher validation and a sprint-specific interview-prep pack.

## 6. Explicit Non-Goals

Sprint-22 must not include:

* implementation of SHA-256 or any cryptographic primitive;
* design of a custom hash function;
* production cryptography or production-security claims;
* private keys, seed phrases, real signatures, wallets, or custody workflows;
* devnet, testnet, RPC, networking, or consensus implementation;
* Anchor, PDA, CPI, Solana programs, or other Stage 4 execution;
* extension or modification of `mini_blockchain`;
* a broad serialization, cryptography, transaction, or blockchain project;
* keys, signature authorization, nodes, finality, or smart-contract execution as
  assessed learning objectives.

## 7. External baseline and job-transfer target

1. **Authoritative source or recognized benchmark:** the accepted
   `reviews/stage-3-4-external-alignment-audit.md`, the
   [Bitcoin Block Chain Guide](https://developer.bitcoin.org/devguide/block_chain.html),
   [Ethereum Blocks](https://ethereum.org/developers/docs/blocks/), and current
   official documentation for the selected Rust hash library. Solana Core Concepts
   is later dependency context only.
2. **Real-world concept or workflow:** cryptographic hash linkage, content-integrity
   checks, digest verification, canonical input construction, and precise security
   claim boundaries.
3. **Toy or simplification boundary:** the lab uses controlled local inputs and one
   reviewed primitive through a library. It is not a protocol, authenticated
   message flow, consensus system, wallet, or production security design.
4. **Transferable engineering capability:** reason about attacker goals, select and
   consume a reviewed dependency, define unambiguous verification inputs, test
   integrity behavior, and reject unsupported security claims.
5. **Interview or industry relevance:** explain hash properties, collision risk,
   tamper evidence, canonical representation, custom-crypto risk, and the
   distinctions among integrity, authentication, authorization, and consensus.
6. **Path toward a more realistic artifact or workflow:** later Stage 3 units may
   add signed-message or transaction-authorization work, protocol data, replicated
   validation, and consensus concepts before Stage 4 Solana account and transaction
   workflows.
7. **Real-world setup or prerequisites:** no account registration, API token,
   devnet or testnet, RPC endpoint, wallet, faucet, test token, private key, seed
   phrase, or platform permission is required. Setup is limited to the local Rust
   toolchain and the selected library dependency.

Secret-handling boundary: Sprint-22 requires no secret. Private keys, seed phrases,
real-funds credentials, API secrets, and sensitive tokens must never be pasted into
Teacher, Architect, or Codex chat or committed to any repository.

## 8. Candidate Lab And Dependency Boundary

The later authorized execution should create a small Rust library project named
`crypto_hash_literacy_lab`. This roadmap task does not create it.

The lab should use the RustCrypto `sha2` crate as the established ecosystem choice
for SHA-256 consumption. No exact version is fixed in this roadmap; before project
creation, the Teacher or Codex must confirm the current maintained release and
official documentation, then allow Cargo to record the resolved version in
`Cargo.lock`. If that dependency is no longer suitable, changing it requires a
documented Teacher/Codex confirmation that preserves the same scope and reviewed-
library boundary.

Before Checkpoint 3 implementation, the Teacher must briefly surface and teach or
confirm the support concepts needed by this lab:

* the role of the `sha2` crate and the `Sha256` type;
* the `Digest` trait, why it must be imported even when code does not write
  `Digest::...`, and the minimal trait-method-resolution rule involved;
* inherent methods versus trait-provided methods, associated functions supplied by
  a trait, and recognizing “trait is implemented but not in scope” diagnostics;
* method-call syntax and UFCS (fully qualified syntax) such as
  `<Sha256 as Digest>::new()` as an explanatory comparison, not required ceremony;
* byte values, byte strings, byte slices, the `b"..."` literal, UTF-8 strings versus
  bytes, and `.as_bytes()`;
* the purpose and boundary of hexadecimal digest formatting.

This is bounded just-in-time Rust reinforcement, not a new cryptography or advanced-
traits unit. It is not an independent Sprint-22 blocker unless the missing knowledge
prevents the learner from completing the accepted lab boundary.

The lab should remain small:

* accept explicit byte inputs and compute SHA-256 digests through the library;
* compare identical and deliberately changed inputs;
* verify an expected digest match and mismatch;
* demonstrate that naive concatenation can map fields such as `("ab", "c")` and
  `("a", "bc")` to the same input bytes;
* demonstrate one bounded canonical alternative, such as length-prefixed fields,
  that keeps those logical inputs distinct;
* preserve the intended behavior with focused tests;
* keep the public API and error boundary simple;
* document that digest comparison alone proves neither origin, authenticity,
  authorization, consensus, nor overall production security.

The canonical-input exercise teaches representation boundaries; it must not expand
into a general serialization framework.

## 9. Checkpoint Sequence

### Checkpoint 1 — Deterministic And Cryptographic Hashes

Teaching targets:

* introduce deterministic hashing and cryptographic hashing with source-backed
  definitions;
* teach the attacker goal behind preimage, second-preimage, and collision
  resistance;
* distinguish the three properties through examples rather than definition recall;
* compare those properties with Sprint-21's toy deterministic hash.

Learner evidence and decision:

* explain each property in their own words;
* classify several concrete attacker goals and justify the classification;
* decide which claims about Sprint-21 are supported and which are not.

The Teacher must address learner questions and confirm stable reasoning before
Checkpoint 2.

### Checkpoint 2 — Tamper Evidence And Canonical Inputs

Teaching targets:

* explain tamper evidence versus tamper prevention;
* distinguish integrity from authentication, authorization, and consensus;
* show why verification depends on an agreed, unambiguous input representation;
* analyze ambiguous concatenation and one bounded canonical encoding approach;
* correct false claims such as “hash linkage prevents tampering.”

Learner evidence and decision:

* diagnose at least one ambiguous representation;
* propose and justify a bounded canonical alternative;
* state what digest equality, inequality, and recomputation prove and do not prove.

The Teacher must address learner questions and confirm the concept-first gate before
any lab implementation is assigned.

### Checkpoint 3 — Small Rust Hash Literacy Lab

Implementation boundary:

* create `crypto_hash_literacy_lab` only after Sprint-22 execution is separately
  authorized;
* confirm the current `sha2` dependency source before adding it;
* complete the bounded support-concept setup in Section 8 before requiring library
  use;
* implement only the minimal digest, comparison or verification, and canonical-
  input behavior required by Section 8;
* add a concise learner-authored README or equivalent artifact with source links,
  security boundaries, the ambiguous-input example, and Sprint-21 mapping;
* add focused tests for deterministic output, a tiny input change, expected digest
  match and mismatch, naive-representation ambiguity, and canonical separation.

Learner decisions:

* choose controlled input examples and explain why they reveal the target behavior;
* choose a minimal canonical representation and explain its boundary;
* choose a simple API or error shape without introducing unnecessary abstraction.

Review must confirm that no learner-authored primitive or unsupported security claim
has entered the lab.

### Checkpoint 4 — Scenario And Interview Transfer

The learner should:

* classify unfamiliar attacks by the challenged security property;
* correct false claims about digest changes, collision resistance, hash linkage, and
  tamper prevention;
* diagnose a new ambiguous-input scenario;
* explain why a reviewed library does not define canonical inputs or the caller's
  verification boundary;
* map the lab and concepts back to Sprint-21 without hardening or modifying that
  project;
* explain where Bitcoin or Ethereum hash linkage provides a real reference and why
  later signatures, consensus, and Solana add different mechanisms.

Future signatures and consensus may be named as boundaries but must not be assessed
as if they were taught in Sprint-22.

### Checkpoint 5 — Final Validation And Interview Preparation

Required work:

* complete current Student Validation after the final code change;
* complete formal Codex Repository Validation;
* complete scenario-based Teacher Learning Validation;
* resolve blocking findings while preserving the sprint's non-goals;
* provide the interview-prep pack or record the learner's explicit waiver;
* prepare closure evidence without changing the Stage 3 ledger before validation.

## 10. Required Tests

The lab should contain focused tests for:

* identical byte input producing the same digest;
* a tiny controlled input change producing a different observed digest;
* expected digest verification success;
* changed-input or changed-expected-digest verification failure;
* two logical field sequences producing identical bytes under naive concatenation;
* the same logical field sequences producing distinct bytes and observed digests
  under the selected canonical representation.

The tests demonstrate controlled observed behavior. They do not prove universal
collision absence, authorization, authenticity, consensus, or production security.

## 11. Student Validation

The learner should report concise PASS/FAIL results for:

* `cargo fmt --check`;
* `cargo check`;
* `cargo test`.

The learner should also self-check that they can, without definition-only
memorization:

* distinguish the three security properties and their attacker goals;
* explain tamper evidence versus prevention;
* distinguish integrity from authentication, authorization, and consensus;
* diagnose the lab's ambiguous-input example;
* explain the limits of the reviewed library and Sprint-21's toy hash.

## 12. Codex Repository Validation

Codex should inspect the later-created lab repository, including:

* source, tests, `Cargo.toml`, `Cargo.lock`, README or equivalent learner artifact,
  and repository status;
* dependency choice and its documented source;
* absence of learner-authored cryptographic primitive implementation;
* explicit canonical and ambiguous input examples;
* focused tests and simple public API or error boundaries;
* absence of secrets and all prohibited scope;
* repository hygiene.

Codex should independently run:

* `cargo fmt --check`;
* `cargo check`;
* `cargo test`.

The report should distinguish blocking findings from non-blocking notes and state
scope compliance. Codex validation establishes repository evidence only; it must not
be represented as proof of learner understanding.

## 13. Teacher Learning Validation

Teacher validation must occur after teaching and use unfamiliar scenarios rather
than definition-only memorization. The learner should be asked to:

* identify which security property a concrete attack challenges and explain why;
* explain what changed or unchanged digest output proves and does not prove;
* diagnose an ambiguous input representation;
* correct a false claim such as “hash linkage prevents tampering”;
* explain why a reviewed library does not remove the need for canonical inputs and
  clear verification boundaries;
* map the lesson back to Sprint-21 without being assessed on future signatures or
  consensus.

Teacher Learning Validation may pass with notes when the learner's applied reasoning
is sufficient for the current boundary and any weakness is explicitly recorded for
reinforcement. Codex PASS does not imply Teacher Learning Validation PASS.

## 14. Interview-Prep Pack

Before normal closure, the Teacher must provide:

`interview-prep/sprints/sprint-22-cryptographic-hash-literacy-and-tamper-evidence.md`

unless the learner explicitly waives it.

The pack must follow `docs/policies/learning-execution-policy.md`: it must be entirely
in Chinese, use realistic junior-to-mid questions, label each question `初级`,
`初中级`, or `中级`, and begin every answer with `考点：...`. It should use 8–12
questions by default, mix concept, tradeoff, engineering-practice, misconception,
and project-explanation prompts, and include at least two misconception or boundary
questions. The Sprint-22 closure should reference the pack path rather than embed
the pack.

## 15. Completion Criteria

Sprint-22 may close only when:

1. Concept checkpoints have been taught, learner questions have been addressed, and
   the concept-before-code gate was respected.
2. The learner demonstrates hash-property, canonical-input, and tamper-evidence
   reasoning in their own words across unfamiliar scenarios.
3. The small lab is learner-implemented and validated, unless an Architect-approved
   roadmap revision replaced it with equivalent applied evidence before execution.
4. Student Validation passes.
5. Codex Repository Validation passes or passes with notes and no blocking finding
   remains.
6. Teacher Learning Validation passes or passes with notes.
7. The interview-prep pack is provided or explicitly waived by the learner.
8. The README or equivalent durable learner artifact records sources, boundaries,
   canonical-input reasoning, and Sprint-21 mapping.
9. Non-goals remain respected and no secret is introduced.
10. Closure records remaining gaps and owns any proposed Stage 3 ledger update.

## 16. Sprint-Specific Risks And Controls

* **Definition memorization:** require attacker-goal classification and unfamiliar
  scenarios.
* **“Cryptographic” treated as universally secure:** require explicit input,
  verification, authentication, authorization, and consensus boundaries.
* **Lab dominance:** do not assign code until Checkpoints 1 and 2 are stable; keep
  the API and tests bounded.
* **Canonicalization scope expansion:** use one small ambiguous example and one
  bounded canonical alternative only.
* **Dependency drift:** confirm current maintained library documentation before
  project creation without expanding into dependency research.
* **Sprint-21 reopening:** use it only as a contrast case; never modify it.
* **Premature future-topic assessment:** signatures, consensus, and Solana remain
  context only.

## 17. Acceptance And Execution Boundary

The next permitted learning action is a separate explicit learner command to start
Sprint-22 execution in an authorized Teacher window.

Sprint-22 remains accepted-but-not-started until the learner gives an explicit
execution-start command in an authorized Teacher window under
`docs/policies/lifecycle-policy.md`. Until that start command and Teacher
authorization exist:

* do not create `crypto_hash_literacy_lab`;
* do not start Checkpoint 1 or issue learning work;
* do not modify `mini_blockchain` or any learning-project source;
* do not mark Sprint-22 active or execution authorized;
* do not update the Stage 3 ledger as though learning occurred;
* do not authorize Stage 4 or Solana execution.
