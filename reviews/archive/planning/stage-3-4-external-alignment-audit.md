# Stage 3 / Stage 4 External Curriculum Alignment Audit

## 1. Review Identity And Purpose

- Review date: 2026-07-04
- Review type: Curriculum coverage and external-alignment audit
- Status: ACCEPTED PLANNING BASELINE
- Curriculum scope: Stage 3 — Blockchain Foundations and Stage 4 — Solana Development preparation
- Trigger: Sprint-21 closure and learner concern about toy-project realism and job transfer
- Local evidence authority: `AGENTS.md`, current state, accepted roadmaps, closures, policies, and coverage artifacts
- External-source verification: Available and completed against the sources listed below
- Final verdict: ALIGNMENT GAP CONFIRMED / STAGE 3 REPAIR DECISION REQUIRED BEFORE SPRINT-22 PLANNING

This audit evaluates whether the current Stage 3 and Stage 4 direction is sufficiently anchored to recognized technical sources and practical Rust + Blockchain / Solana employability. It preserves all historical closed-sprint outcomes while allowing future curriculum direction to be restructured.

The Master Roadmap remains directionally valid: general blockchain foundations should precede deeper Solana development. Its current Stage 3 and Stage 4 descriptions are not detailed enough, by themselves, to guarantee external coverage, practical transfer, or job readiness.

## 2. Current State And Authorization Boundary

- Stage 2.5 — Rust Core Philosophy Bridge: PASS WITH NOTES / COMPLETE
- Current curriculum stage: Stage 3 — Blockchain Foundations
- Sprint-21: PASS WITH NOTES / CLOSED
- Active learning sprint: None
- Teacher execution window: Closed / inactive
- Sprint-22 roadmap: Does not exist
- Sprint-22 planning and execution: Paused pending selection of the Stage 3 repair direction and first unresolved capability boundary
- Stage 4 / Solana execution: Unauthorized

This audit does not create, draft, accept, activate, or start Sprint-22. It does not authorize a Teacher window, learning-project work, Stage 4, or Solana execution.

## 3. Evidence And External Baselines

### Local Evidence

The audit inspected:

- `AGENTS.md`;
- `CONTEXT.md`;
- `TODO.md`;
- `roadmaps/master-roadmap.md`;
- `roadmaps/archive/sprint-21.md`;
- `reviews/sprint-21-closure.md`;
- `reviews/stage-2-5-exit-review.md`;
- `reviews/rust-core-coverage-matrix.md`;
- `reviews/archive/planning/rust-curriculum-coverage-audit.md`;
- `reviews/archive/planning/stage-2-5-bridge-specification.md`;
- `docs/policies/lifecycle-policy.md`;
- `docs/policies/learning-execution-policy.md`;
- `docs/policies/lifecycle-policy.md`;
- `learning-log.md`;
- existing Stage 3, blockchain, Solana, and roadmap-template references in the repository.

No existing Stage 3 blockchain external-alignment audit, Stage 3 coverage ledger, or Stage 4 Solana official-docs curriculum map was found before this update. The Rust curriculum has a TRPL-based audit and coverage matrix; Stage 3 and Stage 4 did not have an equivalent domain baseline.

### Externally Verified Sources

The following sources were inspected live on 2026-07-04:

| Source | Curriculum signal used by this audit |
| --- | --- |
| [Solana Core Concepts](https://solana.com/docs/core) | Orders accounts, programs, instructions, transactions, fees, PDAs, and CPIs as dependent concepts. |
| [Solana Rust SDK](https://solana.com/docs/clients/official/rust) | Connects Rust work to RPC clients, transaction and account types, signers, signatures, program crates, interfaces, and key management. |
| [Ethereum Accounts](https://ethereum.org/developers/docs/accounts/) | Connects accounts to key pairs, signatures, nonce, balance, contract code, storage, and wallet boundaries. |
| [Ethereum Transactions](https://ethereum.org/developers/docs/transactions/) | Provides a real signed-transaction and network-processing reference. |
| [Ethereum Blocks](https://ethereum.org/developers/docs/blocks/) | Connects transactions, cryptographic block linkage, synchronized state, validators, and consensus. |
| [Ethereum Smart Contracts](https://ethereum.org/developers/docs/smart-contracts/) | Connects code, state, transactions, execution, limitations, and composability. |
| [Bitcoin Developer Guides](https://developer.bitcoin.org/devguide/) | Organizes block chain, transactions, contracts, wallets, payment processing, operating modes, P2P networking, and mining. |
| [Bitcoin Block Chain Guide](https://developer.bitcoin.org/devguide/block_chain.html) | Connects hashes, transaction history, UTXOs, validation, consensus rules, and proof of work. |
| [Bitcoin Transactions Guide](https://developer.bitcoin.org/devguide/transactions.html) | Connects inputs, outputs, keys, signatures, scripts, fees, and transaction lifecycle. |
| [Bitcoin Wallets Guide](https://developer.bitcoin.org/devguide/wallets.html) | Separates key distribution, signing, network interaction, custody, and wallet operating models. |
| [Anchor Documentation](https://www.anchor-lang.com/docs) | Maps Solana application work to program structure, account constraints, PDA, CPI, clients, testing, custom errors, security footguns, and verifiable builds. |

These sources are reference baselines, not a requirement to copy another ecosystem's implementation details into Solana training. Bitcoin and Ethereum material should support chain-general comparison; Solana and Anchor sources should anchor later specialization.

## 4. Stage 3 External-Alignment Analysis

The Master Roadmap names transactions, accounts, wallets, blocks, chains, consensus, smart contracts, data modeling, and security-oriented thinking. This is directionally aligned with recognized foundational material.

The current Stage 3 plan is insufficiently specified in five ways:

1. It does not define a source-backed concept coverage boundary.
2. It does not order concepts by dependency, such as hash literacy before tamper claims, keys before signatures, or local validation before consensus comparison.
3. It does not require comparison among UTXO, account/state, and Solana account models at the appropriate abstraction level.
4. It does not define how conceptual knowledge will progress into realistic engineering artifacts.
5. It does not define positive job-transfer or interview-relevance evidence.

Stage 3 should not become an exhaustive survey of Bitcoin and Ethereum. It should use them as concrete reference systems to teach general concepts and tradeoffs before identifying how Solana differs.

Required Stage 3 coverage should include:

- transaction lifecycle, authorization, replay protection, fees, and state effects;
- blocks, state history, hash linkage, and tamper evidence;
- cryptographic hash properties and limits;
- private keys, public keys, addresses, digital signatures, wallets, and custody boundaries;
- UTXO and account/state models at comparison level;
- local validation, replicated validation, consensus, finality, nodes, and network assumptions;
- smart contracts or on-chain programs as deterministic state-transition logic;
- trust assumptions, threat models, and security boundaries;
- chain-general concepts versus chain-specific implementation details;
- documentation reading and professional explanation of tradeoffs.

## 5. Stage 4 Solana External-Alignment Analysis

The Master Roadmap names the Solana account model, programs, instructions, PDAs, Anchor, client interaction, testing, and documentation reading. Those are valid high-level goals.

The current roadmap does not yet provide a verified dependency map covering:

- accounts, ownership, executable programs, and separate data accounts;
- instructions, account metadata, transaction messages, signatures, recent blockhashes, fees, and atomic execution;
- native Rust program structure and the Solana program crate boundary;
- PDA derivation, signer semantics, and ownership constraints;
- CPI privilege propagation and composability;
- serialization, account space, state migration, and compatibility concerns;
- Rust client and JSON-RPC workflows;
- signer abstraction and key-management boundaries;
- local validator or equivalent test environments, program tests, and client integration tests;
- Anchor account constraints, IDLs, clients, testing, custom errors, security footguns, and verifiable builds;
- compute, transaction-size, account, and fee constraints;
- debugging, deployment, documentation navigation, and project explanation.

Stage 4 planning should be mapped now at a high level so Stage 3 can place prerequisites correctly. This mapping is planning evidence only and does not authorize Solana instruction or implementation.

## 6. Master Roadmap Comparison

| Dimension | Current roadmap | External baseline implication | Finding |
| --- | --- | --- | --- |
| Stage order | Rust, blockchain foundations, then Solana | General concepts should precede chain-specific development | Aligned |
| Transactions | Named at Stage 3 and Stage 4 | Requires lifecycle, authorization, fees, state effects, and real data-model comparison | Under-specified |
| Wallets and accounts | Named at Stage 3 | Requires keys, signatures, custody, wallet/account separation, and multiple state models | Under-specified |
| Blocks and chains | Named at Stage 3 | Requires cryptographic linkage, replicated validation, nodes, consensus, and finality | Under-specified |
| Smart contracts / programs | Named at both stages | Requires deterministic execution, state ownership, transaction invocation, testing, and security | Under-specified |
| Security | General security-oriented thinking | Requires explicit hash, signature, trust, threat, custody, and program-security placement | Material gap |
| Practical development | Small projects and client interaction | Requires source-backed progression from models to real libraries, RPC, programs, tests, and debugging | Material gap |
| Job transfer | Employability is the mission | Future roadmaps do not have an explicit positive transfer target | Governance-planning gap |

No Master Roadmap rewrite is required before the learner and Architect decide the repair direction. The immediate need is a Stage 3 coverage and sequencing decision, not automatic expansion of every high-level stage bullet.

## 7. Sprint-21 Job-Transfer And Toy-Boundary Assessment

Sprint-21 remains valid completed learning progress. It produced useful evidence for Rust domain modeling, invariant design, explicit errors, deterministic testing, block linkage, local validation, and tamper-detection behavior.

Its job-transfer value is bounded:

| Sprint-21 toy boundary | Real-world concept not yet established |
| --- | --- |
| Sender and receiver strings | Key ownership, addresses, signature authorization, custody, and replay protection |
| Deterministic toy hash | Cryptographic hash properties, canonical encoding, collision resistance, and security assumptions |
| In-memory block vector | Replicated state, persistence, node roles, propagation, forks, and finality |
| `validate_chain()` | Protocol validation, adversarial inputs, consensus rules, and agreement across nodes |
| Local append workflow | Transaction admission, execution, fees, ordering, block production, and state transition |
| General README limitations | Source-backed comparison with real blockchain systems |

The project should not be retroactively expanded into a production blockchain. Its correct role is an introductory modeling artifact whose limitations now inform the next curriculum decision.

The low-realism concern is therefore valid without making Sprint-21 a failure. The issue is insufficient progression and conceptual anchoring around the toy artifact, not the use of a toy artifact by itself.

## 8. Non-Goals Risk Assessment

Non-goals are necessary for sequencing, overload prevention, and stage control. They become harmful when they dominate roadmap design without an equally explicit statement of what real capability the bounded exercise transfers toward.

Sprint-21 excluded real cryptography, signatures, wallet key management, networking, consensus implementation, Solana, RPC, serialization, and production design. Those exclusions were defensible individually for an introductory sprint. Collectively, without an external baseline and realism path, they left the learner with a model that was easier to validate than to connect to professional blockchain work.

Future planning should retain bounded non-goals while requiring:

- a positive capability target;
- a named real-world analogue;
- an explicit toy-versus-real boundary;
- a follow-on realism path;
- evidence that the selected work advances Stage 3 exit or Stage 4 readiness.

## 9. Positive Job-Transfer Requirements For Future Roadmaps

Future Stage 3 and Stage 4 roadmaps should include one compact section named:

`External baseline and job-transfer target`

That section should identify:

1. the authoritative source or recognized benchmark used;
2. the real system concept represented by the exercise;
3. the toy or simplification boundary;
4. the transferable engineering capability being practiced;
5. the interview or industry relevance;
6. the path to a more realistic artifact or workflow;
7. real-world setup or prerequisite preparation when applicable.

This should be one concise roadmap field, not four duplicated governance sections. The accepted follow-up governance update added the field to the sprint-roadmap content standard and Specification Review template.

## 10. Recommended Stage 3 Learning Sequence

This is a curriculum sequence recommendation, not a sprint plan.

### Phase A — Concept-First Security And State Foundations

- system participants, value/state, and trust boundaries;
- cryptographic hash literacy and tamper evidence;
- keys, addresses, digital signatures, wallets, and custody;
- transaction authorization, lifecycle, fees, nonce or UTXO replay/double-spend controls;
- local validation versus replicated validation, consensus, and finality.

### Phase B — Protocol And State-Model Comparison

- block and transaction relationships;
- UTXO versus account/state models;
- nodes, propagation, mempool or admission concepts, block production, and forks at overview level;
- smart contracts or on-chain programs as state-transition systems;
- Bitcoin, Ethereum, and Solana as comparison anchors without broad ecosystem detours.

### Phase C — Bounded Realistic Engineering

- parse or model source-backed transaction and state structures;
- use established cryptographic libraries rather than invent primitives;
- verify signatures or signed-message workflows in a safe educational boundary;
- model deterministic state transitions, authorization failures, replay resistance, and explicit errors;
- use serialization, test vectors, fixtures, or documented protocol data when they improve realism;
- preserve professional API, invariant, error, test, and repository standards.

### Phase D — Stage 3 Consolidation

- explain trust and security assumptions;
- compare chain-general concepts with chain-specific choices;
- read and apply official documentation;
- review realistic failure cases and threat boundaries;
- produce an artifact and explanation suitable for portfolio or interview discussion.

The sequence must be split into cohesive future units. It must not be compressed into one overloaded sprint.

## 11. Recommended Stage 4 Preparation Sequence

This is a high-level preparation map only.

1. Confirm Stage 3 prerequisites: accounts/state, transactions, signatures, hashes, validation, trust, and smart-contract basics.
2. Learn the Solana execution model: accounts, owners, programs, instructions, transactions, fees, and atomicity.
3. Build and test a minimal native Rust Solana program with explicit account and error boundaries.
4. Add client/RPC transaction construction, signer handling, confirmation, and failure diagnosis.
5. Learn PDAs and CPIs after accounts, programs, and instructions are stable.
6. Introduce Anchor after the learner can explain the native concepts Anchor abstracts.
7. Add serialization, account sizing, constraints, testing layers, security review, compute limits, and upgrade or compatibility reasoning.
8. Complete a realistic bounded project with documentation, tests, debugging evidence, and professional review.

Deferred Rust topics such as async, concurrency, workspaces, binary layout, and Borsh should be scheduled before dependent Solana work, not front-loaded without a concrete dependency.

## 12. Cryptography-Literacy Placement Decision

Cryptography literacy is required in Stage 3 before wallet, signature, security-sensitive transaction, or Solana-specific execution work.

Required literacy includes:

- cryptographic hash versus ordinary deterministic hash or checksum;
- preimage resistance, second-preimage resistance, and collision resistance at conceptual level;
- canonical input representation and domain-separation awareness;
- public/private key roles;
- digital signing versus encryption;
- signature verification and transaction authorization;
- key generation, randomness, custody, and secret-handling boundaries;
- why standard reviewed libraries and protocols must be used instead of learner-authored cryptographic primitives.

This decision requires concept and safe library-use literacy. It does not require implementing cryptographic primitives.

## 13. Sprint-22 Decision

Sprint-22 remains paused.

Before any Sprint-22 Specification Review or roadmap drafting:

1. a Stage 3 repair direction and first unresolved capability boundary should be selected from this accepted audit and ledger;
2. the positive job-transfer and external-baseline requirement should be applied to the candidate unit;
3. the normal Specification Review and roadmap authorization workflow should then be followed.

If Sprint-22 is later selected as the first repair unit, it should be concept-first unless a subsequent evidence-based review establishes that a different first unit better resolves the ledger. This recommendation does not draft Sprint-22.

## 14. Recommended Repository Follow-Up

After human review, consider a separately authorized update to:

- confirm or revise the classifications in `reviews/stage-3-blockchain-coverage-ledger.md`;
- update `roadmaps/master-roadmap.md` only if the audit reveals a high-level stage capability or exit-criterion omission;
- prepare a Stage 3 repair Specification Review only after the audit decision;
- create a more detailed Stage 4 official-docs coverage map before Stage 4 authorization.

No new broad policy is required now. The immediate defect is missing curriculum evidence and sequencing, not absence of another governance layer.

## 15. Non-Authorization Statement

This audit does not:

- create, draft, accept, activate, or start Sprint-22;
- authorize a Teacher execution window;
- authorize learning-project creation or modification;
- reopen or change Sprint-21's PASS WITH NOTES / CLOSED verdict;
- mark Stage 3 complete;
- authorize Stage 4 or Solana execution;
- convert all missing topics into one sprint;
- replace the Rust Core Coverage Matrix with a universal ledger;
- modify sprint-governance or Teacher-execution policy;
- require implementation of cryptographic primitives.

Final decision: accept this audit as the Stage 3 / Stage 4 external-alignment planning baseline, preserve Sprint-21 as bounded validated progress, keep Sprint-22 planning paused, and decide the Stage 3 repair direction before further roadmap work.
