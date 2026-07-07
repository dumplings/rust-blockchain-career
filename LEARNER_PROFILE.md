# Learner Profile

## Purpose

This file is the canonical compact working profile for curriculum and teaching adaptation.
It records stable learner background, demonstrated capability, preferences, and carry-forward learning risks.
It does not own live sprint state, execution authorization, curriculum ordering, or formal coverage status.
Use `CONTEXT.md`, the accepted sprint roadmap, `roadmaps/master-roadmap.md`, and the relevant coverage artifact for those questions.

## Update Rules

- Update after a sprint closure, stage exit, or major evidence-backed correction.
- Record demonstrated capability and explicit learner preferences, not optimistic inference.
- Keep temporary sprint logistics and execution authority out of this file.
- Keep detailed checkpoint evidence in closures, coverage ledgers, and `learning-log.md`.
- Prefer compact synthesis over copying historical narrative.
- Resolve conflicts in favor of the current canonical state or coverage owner.

## Stable Background And Goals

- The learner is an experienced software developer transitioning toward Rust and blockchain work.
- The career goal is job-ready entry-level Rust + Blockchain engineering capability.
- Solana is the intended specialization after the required general blockchain foundations.
- Current Rust capability is approximately B+ as a planning shorthand, not a standardized assessment score.
- Blockchain capability is still beginner-level, with a validated but deliberately narrow local-chain foundation.
- Chinese is the default teaching and discussion language.
- English technical terms should appear inline when they improve source-reading and professional vocabulary.
- English training is secondary to accurate technical assessment unless a sprint explicitly targets it.
- The learner remains the primary author of learning-project implementation.
- The learner prefers direct, reasoned simplification when process structure creates execution burden.
- Historical governance material should not be part of normal learner startup or reading burden.

## Rust Capability Snapshot

### Demonstrated Strengths

- Ownership, borrowing, moves, references, and slices are usable in project work.
- Lifetime relationships are understood well enough for the current curriculum boundary.
- `Result`, error propagation, and domain-oriented error design have been exercised repeatedly.
- Modules, privacy, crates, visibility, and public API boundaries have been applied in multi-file projects.
- Traits, generics, and static dispatch have been used to define meaningful capability boundaries.
- Closures, iterators, pattern matching, and common collection operations are available working tools.
- Smart-pointer and interior-mutability concepts have been covered at the required foundations level.
- Unit and integration testing habits are established, including invalid-path and tamper scenarios.
- The learner can navigate unfamiliar project code and explain implementation tradeoffs.

### Partial Or Just-In-Time Areas

- Precise ownership wording, value-origin tracing, and source-first borrow diagnosis still need reinforcement.
- Trait method resolution and the requirement for a trait to be in scope should be reinforced with external APIs.
- Lifetime annotations should be revisited when input/output origin relationships become less obvious.
- CLI design is only partially covered and should be taught when a real project boundary requires it.
- External crate documentation, dependency versions, and exact API behavior require source-backed verification.
- File, storage, and some public-contract behaviors have received lighter testing than core domain logic.

### Rust Watchlist

- Do not restart Rust foundations broadly; reinforce gaps at the point of use.
- Prefer a stable semantic boundary over abstraction created only to remove repetition.
- Watch for public constructors or APIs that weaken domain invariants.
- Async/await, futures, and runtimes are explicitly deferred and must precede networking, RPC, or Solana clients.
- Advanced macros and `unsafe` are not current prerequisites and should be introduced only when justified.

## Blockchain Capability Snapshot

### Demonstrated Foundation

- A narrow Rust blockchain data model has been implemented and validated.
- Block linking, chain validation, tamper detection, and deterministic local checks are understood.
- Toy-hash limitations and the security purpose of cryptographic hashes can be distinguished.
- SHA-256 integration, exact hashed bytes, and canonical input concerns have been exercised.
- The learner can explain what local validation proves and where it falls short of network consensus.

### Major Gaps Still To Teach

- Transaction roles, signed payloads, and end-to-end transaction validation remain incomplete.
- Private keys, public keys, addresses, wallets, accounts, and signatures need systematic treatment.
- UTXO and account/state models have not yet been compared adequately.
- Nodes, networks, propagation, and consensus remain outside demonstrated capability.
- Trust boundaries and threat models are partial and must accompany each new mechanism.
- Smart-contract and on-chain program fundamentals remain missing.
- Fees, compute or resource limits, and production serialization concerns remain missing or partial.
- Chain-general concepts versus chain-specific design need repeated explicit separation.
- Reading blockchain protocol documentation and source material is not yet a demonstrated independent skill.

### Blockchain Watchlist

- Do not let a working local model imply production-blockchain or consensus readiness.
- Require exact byte and representation reasoning for hashes, signatures, and serialization.
- Keep mechanism, security property, and trust assumption separate in explanations.
- Preserve scenario-based validation, including mutation, invalid input, and wrong-key cases.

## Solana Readiness

- Solana remains a later specialization, not a shortcut around Stage 3 foundations.
- Current readiness is blocked by missing signature, transaction, state-model, program, serialization, and security foundations.
- Networking, async Rust, RPC clients, account ownership, and runtime constraints will require explicit preparation.
- Solana examples should be used only when they clarify an authorized foundation without pulling scope forward.
- This profile never authorizes Stage 4 or Solana execution; live authorization belongs to `CONTEXT.md`.

## Teaching And Density Preferences

- Use Chinese-first explanation with precise English terms embedded inline.
- Begin a bounded topic with a compact prerequisite inventory and an explicit checkpoint contract.
- Explain the concept and security purpose before asking for implementation.
- Keep implementation increments small enough that the learner can reason about every line.
- Use source-backed, locally verified dependency examples instead of relying on remembered APIs.
- Introduce Rust details just in time when they unblock the blockchain concept.
- Validate through concrete scenarios and ask the learner to explain why each case should pass or fail.
- Connect material to job and interview relevance without turning the sprint into trivia practice.
- Make scope, non-goals, required artifacts, and completion evidence explicit before work begins.
- Avoid hidden requirements and unnecessary repetition between the task specification and validation prompt.
- The Sprint-22 pattern of compact preparation, concept-first instruction, bounded implementation, and scenario validation was explicitly preferred.
- Treat that pattern as a reusable default, not a rigid script; adjust density from observed learner performance.

## Validation Profile

- Preserve Student Validation, Codex Repository Validation, and Teacher Learning Validation as separate layers.
- Passing code is necessary evidence but does not by itself demonstrate learning.
- Student self-checks may be concise when they report current commands, results, and scenario reasoning.
- Codex should validate repository state, source behavior, tests, and acceptance criteria without replacing learner implementation.
- Teacher validation should require explanation of design choices, failure cases, and security implications.
- Reference implementations or explicitly waived artifacts must not be counted as learner-authored evidence.
- Record meaningful capability changes in closure and coverage evidence before updating this profile.

## Current Planning Implications

- Consult `CONTEXT.md` before using this profile; this section does not declare a sprint active.
- The next blockchain work should build from hash literacy toward key roles and digital signature verification.
- Rust readiness for that boundary is sufficient with just-in-time support rather than a foundations restart.
- Inventory new crates, APIs, Rust syntax surfaces, protocol concepts, byte strings, `Digest`-like trait methods, and dependency versions before instruction.
- Require explicit valid-signature, wrong-key, modified-message, malformed-input, and representation scenarios where applicable.
- For a narrow signature-verification sprint, use public verification fixtures only; do not introduce key generation, private keys, or signing workflows even in tests unless a later roadmap explicitly authorizes them.
- Keep consensus, networking, wallet architecture, transaction systems, and Solana implementation outside a narrow signature sprint unless separately authorized.
- Continue updating Stage 3 coverage conservatively; a single successful exercise is not permanent mastery.
- Prefer one clear current path over parallel optional tracks that increase startup burden.

## Evidence Pointers

- Live state and authorization: `CONTEXT.md`
- Curriculum ordering and exit criteria: `roadmaps/master-roadmap.md`
- Rust evidence: `reviews/rust-core-coverage-matrix.md`
- Stage 3 evidence: `reviews/stage-3-blockchain-coverage-ledger.md`
- Stage 2.5 exit evidence: `reviews/stage-2-5-exit-review.md`
- Recent demonstrated progression: `reviews/sprint-20-closure.md` through `reviews/sprint-22-closure.md`
- Detailed chronological evidence: `learning-log.md`
- Current evidence navigation: `reviews/INDEX.md`
