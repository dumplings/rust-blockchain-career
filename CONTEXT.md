# Current Context

## Goal

Build practical Rust and blockchain engineering capability for entry-level
employment, with Solana as the primary specialization after prerequisite Rust
and blockchain foundations.

## Current Stage And Sprint

- Stage 2.5 — Rust Core Philosophy Bridge: `PASS WITH NOTES / COMPLETE`
- Current stage: Stage 3 — Blockchain Foundations
- Stage 3 status: Started but incomplete
- Sprint-22: `PASS WITH NOTES / CLOSED`
- Active learning sprint: None
- Sprint-23 roadmap: `roadmaps/sprint-23.md`
- Sprint-23 state: `ACCEPTED / NOT STARTED / NOT ACTIVE`
- Canonical lifecycle state: `ACCEPTED_WAITING_START`
- Sprint-23 dependency probe: PASS for `ed25519-dalek = "=2.2.0"`
- Teacher execution window: Closed / inactive
- Sprint-23 candidate project: `signature_verification_lab`; not created
- Stage 4 / Solana execution: Unauthorized

## Current Authorization Boundary

The learner accepted the Sprint-23 roadmap. Acceptance does not start execution,
authorize checkpoint work, open a Teacher window, create the candidate project,
complete Stage 3, or authorize Stage 4 / Solana work.

No learning execution is currently authorized. `signature_verification_lab` may
be created only after Sprint-23 enters `ACTIVE` under the lifecycle policy.

## Next Allowed Action

The learner may explicitly start Sprint-23 in an authorized Teacher execution
context. Do not infer execution authority from roadmap acceptance, this next
action, repository updates, or startup preparation.

An execution-start message sent to an Architect does not convert that governance
window into a Teacher window. The learner must explicitly authorize a Teacher
role switch in that window or start a separate Teacher window, and the Teacher
Startup Checklist must pass before instruction.

## Operational Carry-Forward

- Conduct teaching in Chinese first and scaffold English technical terms inline
  with controlled terminology density.
- Inventory new crates, tools, APIs, protocol concepts, Rust syntax surfaces, and
  support concepts before requiring their use.
- Keep the learner as the primary implementer.
- Preserve Student Validation, Codex Repository Validation, and Teacher Learning
  Validation as separate layers.
- Reinforce trait method resolution and trait-in-scope requirements when external
  APIs depend on them.
- Prevent wallet, account, transaction, signing, network, and Solana scope drift
  during Sprint-23.
- Stage 4 and Solana execution remain unauthorized.

## Active Risks

- Role drift from Architect or Codex into Teacher execution.
- Treating roadmap acceptance or next-action wording as execution authority.
- Hidden prerequisites or excessive English terminology during Chinese teaching.
- Expanding Sprint-23 into wallet, transaction, network, account, signing, or
  Solana implementation.
- Treating narrow validated coverage as permanent mastery or Stage 3 completion.
- Reintroducing duplicated state or rules into roadmaps, reviews, prompts, or
  evidence files.

## Essential Evidence

- Accepted current roadmap: `roadmaps/sprint-23.md`
- Current Specification Review: `reviews/sprint-23-specification-review.md`
- Latest completed sprint evidence: `reviews/sprint-22-closure.md`
- Current Stage 3 ledger: `reviews/stage-3-blockchain-coverage-ledger.md`
- Current Rust matrix: `reviews/rust-core-coverage-matrix.md`
- Stage 2.5 exit decision: `reviews/stage-2-5-exit-review.md`
- Evidence navigation: `reviews/INDEX.md`

Historical roadmaps, reviews, handovers, and `learning-log.md` are conditional
evidence. They are not live-state authorities or default startup inputs.

## Learner Preferences

- Background: Experienced software developer
- Rust level: Approximately B+
- Blockchain level: Beginner
- Learner-facing language: Chinese
- Technical terminology: English is allowed with inline Chinese explanation
- Repository-ready governance language: English
- English training: Secondary unless explicitly selected as a sprint objective
- Implementation boundary: Learner remains the primary learning-project developer
