# Sprint-22 Specification Review

## Review Identity

- Proposed sprint: Sprint-22 — Cryptographic Hash Literacy And Tamper Evidence
- Stage: Stage 3 — Blockchain Foundations
- Primary project: None selected; concept-first unit with a possible bounded `crypto_hash_literacy_lab`
- Review owner: Architect
- Review date: 2026-07-04
- Review status: COMPLETE / AWAITING LEARNER DECISION ON ROADMAP DRAFTING
- Roadmap status: Not created / not authorized
- Execution status: Not accepted / not active / not authorized

This Specification Review evaluates the Architect-selected first Stage 3 repair boundary. It is not a Sprint-22 roadmap and does not authorize project creation, Teacher execution, or learning work.

## Current State

- Stage 2.5 — Rust Core Philosophy Bridge: PASS WITH NOTES / COMPLETE
- Current stage: Stage 3 — Blockchain Foundations
- Sprint-21 — Mini Blockchain Data Model And Validation: PASS WITH NOTES / CLOSED
- Active learning sprint: None
- Teacher execution window: Closed / inactive
- Accepted external-alignment baseline: `reviews/stage-3-4-external-alignment-audit.md`
- Accepted initial Stage 3 coverage ledger: `reviews/stage-3-blockchain-coverage-ledger.md`
- Selected Stage 3 repair boundary: Cryptographic hash literacy, tamper evidence, and security boundary reasoning
- Sprint-22 roadmap: Does not exist
- Stage 4 / Solana execution: Unauthorized

Sprint-16 remains stopped before completion, incomplete, unclosed, and without completion credit. No failed or historical sprint boundary is changed by this review.

## Documents Reviewed

- `AGENTS.md`
- `CONTEXT.md`
- `TODO.md`
- `roadmaps/master-roadmap.md`
- `reviews/stage-3-repair-direction-decision.md`
- `reviews/stage-3-4-external-alignment-audit.md`
- `reviews/stage-3-blockchain-coverage-ledger.md`
- `reviews/sprint-21-closure.md`
- `roadmaps/sprint-21.md`
- `docs/policies/lifecycle-policy.md`
- `docs/policies/learning-execution-policy.md`
- `templates/specification-review-template.md`
- `learning-log.md`

## Proposed Direction

Sprint-22 should be concept-first with a small bounded Rust lab only after the core concepts are taught and explained. This is a concept-plus-small-lab recommendation with concept-first ordering, not an implementation-heavy sprint.

The conceptual boundary should establish:

- deterministic toy hash versus cryptographic hash;
- preimage resistance;
- second-preimage resistance;
- collision resistance;
- tamper evidence versus tamper prevention;
- hash linkage as a detection mechanism, not authorization or consensus;
- canonical representation and the danger of ambiguous serialization;
- why reviewed libraries and standard protocols are used instead of custom primitives;
- how Sprint-21's toy hash maps to real blockchain integrity boundaries;
- how this knowledge prepares later keys, signatures, wallets, transaction authorization, consensus, and Solana work.

After the learner can explain those boundaries, a small Rust exercise may use an established hash library or published test vectors to compare inputs, recompute digests, expose ambiguous encoding, or verify tamper-detection behavior. The exercise must consume a primitive through a library; it must not implement one.

The possible lab name is `crypto_hash_literacy_lab`. This review does not select, create, or authorize that project. The later roadmap decision may instead choose a written concept artifact plus bounded source-reading exercises if that produces sufficient durable evidence with less implementation distraction.

## Learning Density And Project Continuation

The direction has sufficient learning density without production-blockchain work because it combines:

- three distinct security properties and their threat boundaries;
- comparison of deterministic and cryptographic hashing;
- tamper evidence, prevention, authentication, and authorization distinctions;
- canonical representation and verification-boundary reasoning;
- official-source reading;
- application to Sprint-21's toy hash;
- safe dependency-use judgment;
- interview-style explanation and misconception correction;
- optional bounded code or test-vector evidence.

Sprint-22 should not continue `mini_blockchain` as its primary project. The existing project has already produced its intended data-model and local-validation evidence. Extending it risks disguising the conceptual repair as feature work or production hardening.

A new small lab has learning value only if it remains subordinate to the concept objectives. It should be selected in a later roadmap only when it materially improves transfer through canonical-input, digest-verification, or test-vector practice. The lab should not become a general cryptography project.

## Stage Alignment

The direction fits Stage 3 because cryptographic hash literacy is required to explain block linkage, tamper evidence, transaction identifiers, integrity claims, and later trust assumptions. It directly repairs a gap identified by Sprint-21 closure and the accepted Stage 3 ledger.

The sprint must not advance into Stage 4. Solana accounts, programs, instructions, PDA, CPI, Anchor, RPC, devnet, testnet, wallets, and signer implementation remain outside this review.

The sprint also must not absorb later Stage 3 units on keys and signatures, transaction authorization, nodes and networking, consensus, finality, or smart-contract execution.

## External Baseline And Job-Transfer Target

- Authoritative source or recognized benchmark: `reviews/stage-3-4-external-alignment-audit.md`; [Bitcoin Block Chain Guide](https://developer.bitcoin.org/devguide/block_chain.html); [Ethereum Blocks](https://ethereum.org/developers/docs/blocks/); [Solana Core Concepts](https://solana.com/docs/core) for later dependency context only; current official documentation for any library or published test vector selected by a future roadmap.
- Real-world concept or workflow: cryptographic hash linkage, tamper-evidence verification, content-derived identifiers or commitment-style reasoning, canonical inputs, and the security boundary around blockchain data integrity.
- Toy or simplification boundary: no primitive implementation, production security claim, wallet or signature implementation, network, consensus, production blockchain, or Solana execution.
- Transferable engineering capability: explain hash security properties precisely, reject false security claims, use source-backed terminology, reason about canonical inputs, select reviewed dependencies, and identify what digest verification does and does not prove.
- Interview or industry relevance: answer junior to mid-level questions about hash properties, collision risk, tamper detection, canonical serialization, custom-crypto risk, and the difference among integrity, authentication, authorization, and consensus.
- Path toward a more realistic artifact or workflow: a later signed-message or transaction-authorization unit, a transaction-lifecycle unit, source-backed protocol data work, and later Solana account and transaction readiness.
- Real-world setup or prerequisites, if applicable: no account registration, API token, devnet or testnet access, RPC endpoint, wallet, faucet, test token, private key, seed phrase, or external platform permission is required. If a future roadmap selects an established library or official test vector, setup should remain local and non-secret.

Secret-handling boundary: the learner must never paste private keys, seed phrases, real-funds credentials, API secrets, or sensitive tokens into Teacher, Architect, or Codex chat or commit them to a repository. Sprint-22 does not require any secret.

## Proposed Scope

In scope:

- source-backed teaching of cryptographic hash purpose and limits;
- deterministic toy hash versus cryptographic hash;
- preimage, second-preimage, and collision resistance at interview-usable depth;
- clear attacker-goal and security-property distinctions;
- tamper evidence versus tamper prevention;
- integrity versus authentication, authorization, and consensus;
- canonical representation, ambiguous concatenation, and verification-input boundaries;
- analysis of Sprint-21's toy hash and previous-hash linkage;
- safe use of reviewed standard libraries and protocols;
- small written comparison, diagram, scenario, test-vector, or bounded Rust exercise when it strengthens understanding;
- Student Validation appropriate to the selected artifact boundary;
- Codex Repository Validation when a persistent artifact or lab is used as completion evidence;
- Teacher Learning Validation centered on explanation, application, and boundary reasoning;
- a sprint-specific Chinese interview-prep pack before closure unless the learner explicitly waives it.

Out of scope:

- implementing SHA-256 or any cryptographic primitive;
- designing a custom hash function;
- production cryptography or production security claims;
- wallet private-key handling or key management;
- seed phrases;
- real signatures or transaction authorization implementation;
- devnet, testnet, RPC, networking, or consensus implementation;
- Solana program development;
- Anchor, PDA, or CPI;
- extending `mini_blockchain` into a production blockchain;
- broad data-serialization, wallet, transaction, consensus, or Solana coverage beyond the minimum context required to explain the hash boundary.

## Expected Learner Work

The learner should:

- explain the three hash properties in their own words and distinguish the attacker goal for each;
- compare Sprint-21's toy hash with a cryptographic hash without claiming that either hash linkage prevents modification;
- explain why tamper evidence is not tamper prevention, authentication, authorization, or consensus;
- identify at least one ambiguous representation and propose a canonical alternative;
- inspect and cite the selected official or recognized source material;
- explain why implementing a custom primitive is unsafe and how a reviewed library should be evaluated and used;
- analyze realistic boundary scenarios rather than repeat definitions;
- produce a durable written artifact, and, only if later approved, a small bounded Rust lab or test-vector exercise;
- prepare for Teacher validation and the required interview-prep pack.

The learner remains the primary author of any learning artifact or optional lab.

## Expected Tests And Validation

Required validation layers:

1. Student Validation
2. Codex Repository Validation when a repository artifact or lab is used
3. Teacher Learning Validation

### Student Validation Without Code

If the accepted roadmap selects no code, Student Validation should confirm that the learner-authored durable artifact:

- cites the selected sources;
- distinguishes the three hash properties;
- distinguishes tamper evidence from prevention, authentication, authorization, and consensus;
- explains the canonical-representation risk;
- maps Sprint-21's toy hash to its real security limitations;
- answers the assigned scenario or misconception checks;
- has been self-reviewed for technical accuracy and unclear wording.

No `cargo` commands should be required when no Rust project is created or modified.

### Student Validation With A Small Lab

If a later roadmap selects a Rust lab, Student Validation should include concise pass/fail reporting for:

- `cargo fmt --check`;
- `cargo check`;
- `cargo test`;
- any roadmap-specific test-vector or behavior check.

### Codex Repository Validation

For a written-only artifact, Codex should inspect:

- artifact presence and scope;
- source links and terminology;
- internal consistency of the property distinctions;
- toy-versus-real and security-claim boundaries;
- canonical-representation examples;
- Markdown and repository hygiene.

For a small lab, Codex should additionally inspect:

- dependency and public API boundaries;
- absence of learner-authored primitive implementation;
- explicit input representation;
- focused tests or published test-vector use;
- absence of secrets and prohibited scope;
- formatter, compiler, test, warning, and repository status evidence.

Codex validation should not be represented as proof of learner understanding.

### Teacher Learning Validation

Teacher validation should occur only after the concepts have been taught and practiced. It should use scenario-based explanation rather than definition recitation. The learner should be asked to:

- identify which security property a concrete attack challenges and explain why;
- explain what a changed or unchanged digest proves and does not prove;
- diagnose an ambiguous-input example;
- correct a false claim such as "hash linkage prevents tampering";
- explain why a standard library does not remove the need to define canonical inputs and verification boundaries;
- relate the result to Sprint-21 and to later signatures or consensus without being assessed on those later topics.

Questions should be introduced only after the relevant instruction. The Teacher should accept precise reasoning in the learner's own words and should not turn terminology recall into the primary assessment.

### Minimum Durable Coverage Evidence

To move `Cryptographic hash literacy` from `Missing / not yet covered` to `Partially covered; deepen`, evidence must include:

- a persistent learner-authored explanation or comparison artifact;
- correct distinction among the three required security properties;
- correct tamper-evidence and canonical-input reasoning;
- explicit mapping to Sprint-21's toy boundary;
- completed Teacher Learning Validation.

To classify the topic as `Covered sufficiently for current boundary`, the same evidence should also demonstrate transfer through multiple unfamiliar scenarios and either a bounded library/test-vector exercise or an equivalently strong applied verification artifact. Any classification change requires a later closure or explicit governance update; this review changes no ledger classification.

Repository validation target:

- the governance or learning-artifact repository selected by a future roadmap;
- optional candidate project root only if `crypto_hash_literacy_lab` is later approved and created.

## Interview-Prep Pack Requirement

Before normal Sprint-22 closure, the Teacher must create or coordinate creation of:

`interview-prep/sprints/sprint-22-cryptographic-hash-literacy-and-tamper-evidence.md`

unless the learner explicitly waives it.

The pack should follow `docs/policies/learning-execution-policy.md`, remain entirely in Chinese, use the required difficulty labels and `考点：...` answer prefix, and cover realistic hash-property, tamper-evidence, canonical-input, custom-crypto, and security-boundary questions. At least two questions should target misconceptions such as collision resistance versus preimage resistance or tamper evidence versus prevention.

The closure should reference the pack path rather than embed the pack.

## Required Review Questions And Decisions

### 1. Recommended Sprint Shape

Decision: Concept-first plus a small bounded Rust lab is preferred, with concept teaching and learner explanation completed before code. Pure concept-first remains an acceptable fallback if a durable written and scenario-based artifact can provide equivalent applied evidence. Implementation-heavy is rejected.

### 2. Minimum Durable Evidence

Decision: Use the persistent explanation, property distinctions, tamper/canonical-input analysis, Sprint-21 mapping, Teacher validation, and applied transfer boundary defined above. A later closure or governance update owns the ledger classification change.

### 3. Student Validation With Little Or No Code

Decision: Validate the completeness, sources, distinctions, scenarios, and self-review of the learner-authored artifact. Do not invent `cargo` requirements when no code exists.

### 4. Codex Validation Target

Decision: Inspect the written artifact when no lab exists; inspect both artifact and lab when a lab is later authorized. Validate repository evidence and scope, not learner understanding.

### 5. Teacher Validation Without Memorization

Decision: Teach first, then use unfamiliar scenarios, false-claim correction, comparison, and input-boundary diagnosis. Do not make definition recall the primary assessment.

### 6. Avoiding Sprint-21's Concept-Before-Implementation Problem

Decision: Require concept explanation, source-backed definitions, mental models, boundaries, learner questions, and learner explanation before any optional library or code exercise.

### 7. Interview-Transfer Value

Decision: Require precise professional vocabulary, junior-to-mid interview scenarios, security-claim correction, design-boundary explanation, and a durable interview-prep pack.

### 8. Interview-Prep Pack

Decision: Require the sprint-specific pack at the path above before normal closure unless explicitly waived. Do not backfill Sprint-21 through this review.

## Risks And Ambiguities

- Definitions may be memorized without the learner recognizing distinct attacker goals.
- "Cryptographic" may be misheard as "secure in every context."
- Hashing may be conflated with encryption, signing, authentication, authorization, or consensus.
- Canonical representation may expand into a broad serialization sprint.
- A Rust lab may dominate the concept-first objective.
- A selected library or test vector may become outdated or poorly sourced.
- Sprint-21 comparison may drift into unauthorized project hardening.
- Later signature or consensus concepts may be assessed before they are taught.
- The sprint may become too small if it contains definitions only and no applied scenario or artifact.

These risks should be controlled through source-backed teaching, scenario practice, a strict optional-lab boundary, and explicit non-goals.

## Decisions Needed

Before roadmap creation:

1. The learner should accept, revise, or reject this Specification Review.
2. The learner or Architect should confirm whether the roadmap should require the small Rust lab or allow a written applied artifact instead.
3. If a lab is selected, the roadmap should name the established library or official test-vector source and keep setup local and non-secret.
4. The roadmap should define the exact learner-authored artifact, checkpoint sequence, and validation boundary.
5. Separate learner authorization is required before Codex creates a Sprint-22 roadmap.

No decision above authorizes learning execution.

## Recommended Next Action

The learner and Architect should review this Specification Review and decide whether Sprint-22 roadmap drafting is authorized and whether the preferred small-lab evidence is required or optional.

If roadmap drafting is separately authorized, the Teacher should draft a bounded concept-first roadmap that preserves this review's dependency order, external baseline, positive job-transfer target, validation branches, interview-prep requirement, and non-goals.

## Authorization Status

- Review only: Yes
- Stage 3 repair direction selected: Yes
- Sprint-22 Specification Review created: Yes
- Sprint-22 roadmap creation authorized by this review: No
- Sprint-22 roadmap created: No
- Sprint-22 accepted or active: No
- Sprint-22 execution authorized: No
- Teacher execution window authorized: No
- Learning-project creation or modification authorized: No
- Stage 4 / Solana execution authorized: No

Specification Review does not authorize sprint execution by itself.

## Language Note

This Specification Review is a repository-oriented governance artifact and is written in English. Any future learner-facing teaching and assessment should remain Chinese-first under the language policy. The sprint interview-prep pack is a separate Chinese learner self-study asset.
