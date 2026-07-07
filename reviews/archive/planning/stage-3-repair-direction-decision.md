# Stage 3 Repair-Direction Decision

## 1. Decision Identity

- Decision date: 2026-07-04
- Decision owner: Architect, under learner-delegated curriculum-direction authority
- Curriculum stage: Stage 3 — Blockchain Foundations
- Decision type: Stage 3 repair-direction and first unresolved capability-boundary selection
- Decision status: ACCEPTED
- Selected boundary: Cryptographic hash literacy, tamper evidence, and security boundary reasoning
- Candidate next review: Sprint-22 — Cryptographic Hash Literacy And Tamper Evidence

This decision selects the first Stage 3 repair boundary after the accepted external-alignment audit. It preserves historical closed-sprint outcomes while allowing future Stage 3 and Stage 4 direction to be restructured around stronger external alignment and job transfer.

## 2. Current State And Authorization Boundary

- Stage 2.5 — Rust Core Philosophy Bridge: PASS WITH NOTES / COMPLETE
- Stage 3 — Blockchain Foundations: Started
- Sprint-21 — Mini Blockchain Data Model And Validation: PASS WITH NOTES / CLOSED
- Active learning sprint: None
- Teacher execution window: Closed / inactive
- Sprint-22 roadmap: Does not exist
- Sprint-22 acceptance, activation, and execution: Unauthorized
- Stage 4 / Solana execution: Unauthorized

This decision authorizes creation of a Sprint-22 Specification Review only. It does not authorize a Sprint-22 roadmap, roadmap acceptance, sprint execution, a Teacher window, or learning-project work.

## 3. Evidence Reviewed

The decision used:

- `AGENTS.md`;
- `CONTEXT.md`;
- `TODO.md`;
- `roadmaps/master-roadmap.md`;
- `reviews/archive/planning/stage-3-4-external-alignment-audit.md`;
- `reviews/stage-3-blockchain-coverage-ledger.md`;
- `reviews/sprint-21-closure.md`;
- `roadmaps/archive/sprint-21.md`;
- `docs/policies/lifecycle-policy.md`;
- `docs/policies/learning-execution-policy.md`;
- `templates/specification-review-template.md`;
- `learning-log.md`.

## 4. Accepted Planning Baseline

The following remain accepted and authoritative for Stage 3 repair planning:

- `reviews/archive/planning/stage-3-4-external-alignment-audit.md` — accepted Stage 3 / Stage 4 external-alignment planning baseline;
- `reviews/stage-3-blockchain-coverage-ledger.md` — accepted initial Stage 3 blockchain coverage ledger.

The Stage 3 ledger remains stage-specific and separate from `reviews/rust-core-coverage-matrix.md`.

## 5. Selected Repair Direction

The Architect selects this first unresolved capability boundary:

`Cryptographic hash literacy, tamper evidence, and security boundary reasoning`

The candidate sprint direction is:

`Sprint-22 — Cryptographic Hash Literacy And Tamper Evidence`

The unit should be concept-first. It should establish source-backed vocabulary, mental models, security properties, limitations, and verification boundaries before any optional bounded code exercise.

The direction includes:

- deterministic toy hash versus cryptographic hash;
- preimage resistance;
- second-preimage resistance;
- collision resistance;
- tamper evidence versus tamper prevention;
- canonical representation and ambiguous-input risks;
- standard reviewed libraries and protocols versus learner-authored primitives;
- mapping Sprint-21's toy hash to real hash-linkage limitations;
- professional and interview-ready explanation of security claims.

## 6. Dependency-Order Rationale

This boundary is selected before keys, signatures, transaction authorization, consensus, or Solana because:

1. Hash functions are a foundational dependency for transaction identifiers, block linkage, commitments, address derivation contexts, signing workflows, and integrity checks.
2. The learner needs to distinguish deterministic output from cryptographic security before later systems use hashes inside stronger authorization or consensus claims.
3. Signature teaching without hash literacy would stack key, signing, encoding, and authorization concepts on an unresolved security primitive boundary.
4. Consensus teaching would add distributed agreement, adversarial nodes, forks, and finality before the learner can precisely explain the local integrity claim already introduced in Sprint-21.
5. Solana transactions, recent blockhashes, signatures, accounts, and program workflows should be introduced only after their chain-general prerequisites are stable.
6. A concept-first repair directly addresses Sprint-21's concept-before-implementation gap without reopening or invalidating the completed sprint.

This ordering does not claim that hash functions alone provide blockchain security. It creates the prerequisite language needed to explain what later signature, authorization, consensus, and protocol mechanisms add.

## 7. Sprint-21 Relationship

Sprint-21 remains PASS WITH NOTES / CLOSED.

Sprint-21 provides useful validated evidence for:

- deterministic content-dependent toy hashing;
- previous-hash linkage;
- local recomputation and validation;
- basic tamper-detection tests;
- recognition that the toy hash is not production cryptography and local validation is not consensus.

Sprint-21 does not establish durable cryptographic security understanding. It did not validate cryptographic hash properties, canonical protocol encoding, adversarial security claims, signatures, authorization, replicated validation, consensus, or production security.

Sprint-22 should use Sprint-21 as a contrast case and source of questions. It should not continue `mini_blockchain` as a production-blockchain expansion.

## 8. Explicit Non-Goals

The selected repair direction does not include:

- Solana execution;
- Anchor;
- PDA or CPI;
- wallet private-key or seed-phrase handling;
- wallet key management;
- real signatures or transaction authorization implementation;
- devnet or testnet access;
- RPC or networking;
- consensus implementation;
- learner-authored SHA-256 or any other cryptographic primitive;
- production cryptography or production security claims;
- production blockchain expansion;
- modification of `mini_blockchain`;
- compression of other missing Stage 3 coverage into Sprint-22.

These non-goals bound the candidate direction. A later Specification Review must also state the positive external baseline and job-transfer target.

## 9. Expected Next Process

1. Create and review `reviews/archive/planning/sprint-22-specification-review.md`.
2. Decide whether the concept-first unit should remain artifact-based or include a small bounded Rust lab using an established library or official test vectors.
3. Decide the minimum durable Student, Codex, and Teacher validation evidence.
4. If the Specification Review is accepted, request separate authorization before drafting a Sprint-22 roadmap.
5. If a roadmap is later drafted, require separate learner acceptance and an explicit execution-start command before any Teacher work.

The Specification Review may be created by this governance update. No later process step is authorized by implication.

## 10. Non-Authorization Statement

This decision does not:

- create a Sprint-22 roadmap;
- accept, activate, or start Sprint-22;
- authorize a Teacher execution window;
- create or modify a learning project;
- modify `mini_blockchain`;
- change Sprint-21's verdict or validated scope;
- mark cryptographic hash literacy covered in the Stage 3 ledger;
- mark Stage 3 complete;
- authorize Stage 4 or Solana execution;
- authorize private-key, seed-phrase, real-funds, API-secret, or sensitive-token handling;
- modify governance policy.

Final decision: select cryptographic hash literacy, tamper evidence, and security boundary reasoning as the first Stage 3 repair boundary, and authorize only a Sprint-22 Specification Review.
