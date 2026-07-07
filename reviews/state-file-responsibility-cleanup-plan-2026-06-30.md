# State File Responsibility Cleanup Plan - 2026-06-30

## 1. Plan Identity

- Plan type: Phase 2A state-file responsibility cleanup plan
- Plan date: 2026-06-30
- Source audit: `reviews/governance-system-optimization-audit-2026-06-30.md`
- Current Sprint-18 state: Accepted / awaiting explicit learner start command
- Sprint-18 execution status: Not started
- Teacher execution window: Not open
- Current governance focus: Governance-system optimization
- Boundary: Planning and migration safety only; no existing file modifications
- Proposed implementation phase: Phase 2B, only after learner review and approval

This plan does not rewrite `CONTEXT.md` or `TODO.md`, start Sprint-18, open a Teacher execution window, or access a learning-project repository.

## 2. Current Problem Summary

`CONTEXT.md` is too long for reliable active-state use. It currently contains 803 lines across 22 major sections. It combines current state with:

- historical sprint summaries;
- detailed learning-project and test results;
- completed milestone history;
- a repository tree already documented in `README.md`;
- a 33-file Teacher startup list;
- reinforcement backlogs;
- old Architect and failure context;
- future system-structure ideas;
- repeated closure and assessment summaries.

The startup list embedded in `CONTEXT.md` currently resolves to 33 files and approximately 13,158 lines. Loading that set before ordinary teaching would make historical state compete with current state and would undermine the role-specific loading guidance in `AGENTS.md`.

`TODO.md` is only 34 lines, but its 32 task items mix:

- seven checked completed items plus one governance-review reminder fulfilled by the current audit and plan;
- active work;
- sprint and stage constraints;
- historical protection rules;
- teaching-process carry-forward notes;
- technical reinforcement backlog;
- repository hygiene;
- governance workflow invariants.

The repository-first model is still necessary. Historical information must remain durable, but durability does not require loading every historical detail at startup or copying it into both current-state files.

The cleanup should reduce active-state duplication while preserving the existing source hierarchy:

- current facts in `CONTEXT.md`;
- concrete current work in `TODO.md`;
- execution contracts in roadmaps;
- outcomes and historical evidence in reviews and `learning-log.md`;
- topic coverage in `reviews/rust-core-coverage-matrix.md`;
- reusable rules in policy files;
- recurring governance issues in `governance/observations.md`.

## 3. Desired File Responsibilities

### `CONTEXT.md`

`CONTEXT.md` should answer:

- what is true now;
- what sprint and lifecycle state is current;
- what transition is allowed next;
- what is explicitly blocked;
- what roadmap, review, coverage, handover, and policy files are authoritative for the current situation;
- what language and learner constraints matter now;
- what risks matter now.

`CONTEXT.md` should not contain:

- full historical sprint summaries;
- old project test counts or command results;
- long startup lists;
- repeated closure details;
- repository structure already in `README.md`;
- long-term topic backlog already in the coverage matrix or sprint closures;
- detailed project histories already in `learning-log.md`;
- future-system notes that are already addressed by a governance review or belong in a human runbook;
- copies of policy rules beyond the minimum current authorization state.

The file should remain sufficient for a new agent to identify current state and select the next relevant files. It should not attempt to carry the entire learning history.

### `TODO.md`

`TODO.md` should answer:

- what concrete actions remain now;
- what each action's completion condition is;
- what work is currently gated by learner approval or another explicit prerequisite.

`TODO.md` should not contain:

- standing policy constraints;
- broad historical protection rules;
- long-term curriculum backlog;
- completed planning history already recorded elsewhere;
- repeated sprint status statements;
- every non-blocking note from prior sprint closures;
- reminders already enforced by policies or accepted roadmaps.

An item should remain only when someone can perform it and determine when it is complete. A current gate may remain as an actionable waiting item when its next transition is explicit.

## 4. `CONTEXT.md` Block Inventory

The line references below describe the file at Phase 2A planning time.

| Current block | Classification | Phase 2B treatment | Durable source or caution |
| --- | --- | --- | --- |
| `Goal` (lines 3-5) | Keep in compact `CONTEXT.md` | Keep as one sentence | Also preserved in `README.md` and `roadmaps/master-roadmap.md` |
| `Current Stage` (lines 7-9) | Shorten and keep | Rename to `Current Stage And Bridge Phase`; state Stage 2 as the program stage and Stage 2.5 as the incomplete required bridge | `roadmaps/master-roadmap.md`; `reviews/stage-2-5-bridge-specification.md` |
| `Current Sprint` (lines 11-19) | Keep in compact `CONTEXT.md` | Preserve one compact lifecycle list for Sprint-16, Sprint-17, and Sprint-18 | `roadmaps/sprint-16.md`; `reviews/sprint-17-closure.md`; `roadmaps/sprint-18.md` |
| `Current Milestone` authorization gate (lines 21-25) | Keep in compact `CONTEXT.md` | Keep the accepted-but-not-started state, no open Teacher window, and explicit learner start requirement | Sprint Execution Start Gate in `docs/policies/lifecycle-policy.md`; `roadmaps/sprint-18.md` |
| `Current Milestone` history and project detail (lines 27-55) | Move to pointer only | Replace with links to latest closure, takeover, specification review, and accepted roadmap | `reviews/sprint-17-closure.md`; latest handover and takeover reports; `reviews/sprint-18-specification-review.md`; `roadmaps/sprint-18.md`; `reviews/sprint-15-closure.md` |
| Curriculum source list (lines 57-77) | Move to pointer only | Retain only active pointers: master roadmap, coverage matrix, Stage 2.5 specification, Sprint-17 closure, Sprint-18 specification review, and Sprint-18 roadmap | The listed source files themselves preserve the chain; older proposal and roadmap links may move to `Historical References` |
| Curriculum audit and Stage 2.5 decision summary (lines 79-85) | Shorten and keep | Preserve the significant-gap decision, incomplete bridge, and Stage 3 block in two or three lines | `reviews/rust-curriculum-coverage-audit.md`; `reviews/stage-2-post-midpoint-review.md`; `roadmaps/master-roadmap.md` |
| Detailed Sprint-16 partial-progress narrative (lines 87-103) | Remove because durable source already exists | Remove from startup state; retain only “incomplete, unclosed, no completion credit” | `roadmaps/sprint-16.md`; `reviews/stage-2-5-remaining-coverage-review.md`; `reviews/sprint-17-closure.md` section 12 |
| Detailed Sprint-17 evidence narrative (lines 105-111) | Remove because durable source already exists | Replace with one closure pointer and current topic-coverage summary | `reviews/sprint-17-closure.md`; `reviews/rust-core-coverage-matrix.md`; `learning-log.md` |
| Remaining coverage and future sprint status (lines 113-119) | Shorten and keep | Preserve unresolved P0/P1 direction, Stage 2.5 incomplete, Sprint-19/20 planning-only, and Stage 3 unauthorized | `reviews/rust-core-coverage-matrix.md`; `roadmaps/sprint-18.md`; `reviews/stage-2-5-bridge-specification.md` |
| Governance policy baseline (lines 121-125) | Move to pointer only | Use one pointer to `AGENTS.md` and relevant policies | `AGENTS.md`; `docs/policies/` |
| Sprint-07 and completed-sprint history (lines 127-165) | Remove because durable source already exists | Keep only a historical-reference pointer for abnormal Sprint-07 and stopped Sprint-16 | `roadmaps/sprint-07.md`; `reviews/sprint-07-attempt-1-failure-review.md`; numbered sprint closures; `learning-log.md` |
| 33-file Teacher startup list (lines 167-205) | Remove because durable source already exists | Remove the cumulative list. Use the role-specific minimum in `AGENTS.md`; Phase 3 may later canonicalize all startup lists | `AGENTS.md` section 10; source audit section 11; this plan section 8 |
| `Current Learning Profile` (lines 207-213) | Shorten and keep | Retain programming background, current Rust/blockchain level, preferred direction, and English constraint in compact bullets | This block contains current learner-specific information and requires caution; `README.md` preserves only the mission, not the full profile |
| Learner approval and runtime density feedback (lines 215-223) | Keep in compact `CONTEXT.md` | Preserve a concise statement that approval is lightweight direction authorization and runtime density feedback is normal | `docs/policies/lifecycle-policy.md`; `docs/policies/learning-execution-policy.md`; `reviews/sprint-18-specification-review.md` |
| `Current Language Requirements` (lines 225-231) | Keep in compact `CONTEXT.md` | Retain concise technical-teaching and governance-output language rules | `docs/policies/learning-execution-policy.md`; current selection remains state-specific |
| `Completed` history (lines 233-268) | Remove because durable source already exists | Remove the chronological checklist | `learning-log.md`; numbered roadmaps and reviews; Stage 1 assessment report |
| `Current Repository Structure` (lines 270-294) | Remove because durable source already exists | Remove | `README.md`; `docs/README.md` |
| `In Progress` status and current focus (lines 296-316) | Shorten and keep; actionable part moves to `TODO.md` | Replace with the current governance-optimization focus, Sprint-18 hold, and one coverage pointer | Current audit; this cleanup plan; `TODO.md`; coverage matrix; policies and closures cited by each historical note |
| `In Progress` project and closure repetition (lines 318-326) | Remove because durable source already exists | Remove | `reviews/sprint-17-closure.md`; `reviews/sprint-15-closure.md`; `roadmaps/sprint-16.md` |
| `Sprint-01 Milestone Summary` (lines 328-342) | Remove because durable source already exists | Remove | `roadmaps/sprint-01.md`; `reviews/sprint-01-review.md`; `learning-log.md` |
| `Sprint-01 Completion` (lines 343-360) | Remove because durable source already exists | Remove | `reviews/sprint-01-review.md`; `learning-log.md` |
| `Sprint-02 Completion` (lines 361-381) | Remove because durable source already exists | Remove | `reviews/sprint-02-review.md`; `learning-log.md` |
| `Sprint-06 Completion` (lines 382-403) | Remove because durable source already exists | Remove | `roadmaps/sprint-06.md`; `reviews/sprint-06-closure.md`; `learning-log.md` |
| `Next Focus` (lines 404-421) | Shorten and keep | Split into `Current Active Governance Focus` and `Next Allowed Transition`; move concrete Phase 2B work to `TODO.md` | Current audit; this cleanup plan; Sprint-18 roadmap and start-gate policies; coverage matrix |
| `Known Risk` (lines 423-432) | Shorten and keep | Retain role/workflow drift, state synchronization, and long-context reliability; omit generic prose | Current audit; latest Architect retirement handover |
| Architect lineage in `Active Governance Context` (lines 434-448) | Move to pointer only | Keep only latest handover and takeover links under `Historical References` | `reviews/architect-retirement-handover-2026-06-30-post-sprint-17.md`; `reviews/architect-takeover-assessment-2026-06-30-post-sprint-17.md` |
| Historical sprint-status sequence (lines 450-510) | Remove because durable source already exists | Remove | Numbered roadmaps and reviews; `learning-log.md`; latest handover |
| Detailed Sprint-08 through Sprint-17 project summaries (lines 512-686) | Remove because durable source already exists | Remove all command counts, API summaries, project paths, and technical detail from active state | Corresponding sprint closures; Stage 1 assessment report; `learning-log.md` |
| Repeated Sprint-07 guard and generic authorization statement (lines 688-700) | Move to pointer only | Keep Sprint-07 only as a historical abnormal-record pointer; use the canonical execution-start rule for current authorization | `roadmaps/sprint-07.md`; Sprint-07 failure review; sprint governance policy |
| `Future System Notes` (lines 702-731) | Move to pointer only | Remove the sample directory tree; retain no active task. Reference the audit's P2 cleanup recommendation if needed | Source audit sections 9, 12, and 13 preserve the YAGNI and later-indexing decision. Exact trigger wording is not otherwise duplicated, so do not delete without retaining the audit pointer |
| `Latest Sprint Closure` (lines 733-753) | Move to pointer only | Replace full summary with one authoritative file link | `reviews/sprint-17-closure.md`; `learning-log.md` |
| `Latest Assessment` (lines 755-782) | Move to pointer only | Replace full summary with one historical file link | `reviews/stage-1-exit-assessment.md`; `learning-log.md` |
| `Active Learning Strategy` (lines 784-803) | Shorten and keep | Retain one sentence: learner implements, Teacher guides and validates learning, Codex supports repository work | `AGENTS.md` role boundaries and workflow separation; `README.md` |

### Block-Level Safety Conclusions

- No current `CONTEXT.md` block should be moved wholesale into `governance/observations.md`.
- The observation queue is for recurring governance issues, not historical storage or curriculum backlog.
- Only concrete current actions should move from `In Progress` or `Next Focus` into `TODO.md`.
- The compact file must state that `reviews/rust-core-coverage-matrix.md` is authoritative for topic coverage only. Its current-sprint wording is not the authority for Sprint-18 lifecycle state; the compact `CONTEXT.md` and accepted Sprint-18 roadmap are.
- Learner profile, current language selection, and the governance-optimization focus require special care because they are current operational state, not merely history.

## 5. `TODO.md` Item Inventory

The table covers every current item in order.

| Item | Current item summary | Classification | Phase 2B action | Durable source |
| ---: | --- | --- | --- | --- |
| 1 | Onboard next Architect | Completed task to remove | Remove | Latest Architect handover and takeover assessment |
| 2 | Prepare Sprint-18 Specification Review | Completed task to remove | Remove | `reviews/sprint-18-specification-review.md` |
| 3 | Prepare Sprint-18 roadmap | Completed task to remove | Remove | `roadmaps/sprint-18.md` |
| 4 | Obtain learner acceptance of Sprint-18 roadmap | Completed task to remove | Remove | Accepted status in `roadmaps/sprint-18.md` and current `CONTEXT.md` |
| 5 | Await explicit learner start command, then startup checklist and Checkpoint 1 | Active task to keep | Keep, but state that governance optimization must finish or be ended before teaching begins | Current `CONTEXT.md`; Sprint-18 roadmap; sprint and Teacher policies |
| 6 | Maintain Rust Core Coverage Matrix before Stage 3 | Active task to keep | Keep as a future gated governance action | `reviews/rust-core-coverage-matrix.md` section 8 |
| 7 | Do not complete or close Sprint-16 | Historical protection to preserve by pointer rather than task | Remove as task; preserve compact status in `CONTEXT.md` | `roadmaps/sprint-16.md`; remaining-coverage review; Sprint-17 closure section 12 |
| 8 | Review and accept Sprint-17 roadmap | Completed task to remove | Remove | `roadmaps/sprint-17.md`; Sprint-17 closure |
| 9 | Complete and close Sprint-17 | Completed task to remove | Remove | `reviews/sprint-17-closure.md` |
| 10 | Record Sprint-17 coverage evidence | Completed task to remove | Remove | Sprint-17 closure; coverage matrix |
| 11 | Keep Sprint-19/20 as planning recommendations | Standing constraint to move to `CONTEXT.md` or roadmap pointer | Remove as task; preserve concise current boundary | Sprint-18 roadmap section 16; remaining-coverage review |
| 12 | Keep Stage 3 unauthorized | Standing constraint to move to `CONTEXT.md` or policy reference | Remove as task; preserve in compact current state | Master roadmap; bridge specification; coverage matrix |
| 13 | Define Stage 3 entry prerequisites | Active task to keep | Keep with a clear “before any Stage 3 transition review” completion condition | Bridge specification section 11; master roadmap; coverage matrix |
| 14 | Plan all remaining ownership, lifetime, smart-pointer, `RefCell`, and contract work | Coverage/backlog item to preserve through coverage matrix | Remove broad task; use matrix and approved sprint planning | Coverage matrix; bridge specification; remaining-coverage review; Sprint-18 roadmap |
| 15 | Preserve Sprint-18 accepted but not started | Duplicate standing constraint | Remove duplicate; item 5 plus compact current state is sufficient | Sprint governance policy; Teacher policy; Sprint-18 roadmap; `CONTEXT.md` |
| 16 | Preserve Teacher direct review plus Codex formal validation model | Standing policy constraint | Remove as task | `AGENTS.md`; Codex collaboration policy; sprint governance policy |
| 17 | Carry forward Sprint-14 teaching-process corrections | Coverage/backlog item already durably recorded | Remove from current tasks | `reviews/sprint-14-closure.md` section 13 and carry-forward notes; Teacher policy contains reusable corrections |
| 18 | Reinforce borrowed enum matching | Coverage/backlog item to preserve through coverage matrix | Remove until selected by approved learning scope | Sprint-17 closure section 8; coverage matrix enum and advanced-pattern rows |
| 19 | Reinforce `HashSet<T>` vs `HashSet<&T>` and iterator/closure fluency | Coverage/backlog item to preserve through coverage matrix | Remove until selected by approved learning scope | Sprint-17 closure section 8; coverage matrix collections and closures rows |
| 20 | Consider tests for untested `rust_core_fluency_lab` transformations | Coverage/backlog item already durably recorded | Remove until a future approved roadmap selects it | Sprint-17 closure section 9 |
| 21 | Review untracked learning-project source and metadata | Repository hygiene task to keep if actionable | Keep as a separately authorized, non-current task; do not access the project during Phase 2B | Sprint-17 closure section 9; latest Architect handover section 6 |
| 22 | Compare ordinary `&mut self` mutation with `RefCell` | Coverage/backlog item to preserve through coverage matrix | Remove until selected by approved learning scope | Sprint-15 closure section 13; coverage matrix `RefCell<T>` row |
| 23 | Reinforce `&T` copy semantics and `&mut T` exclusivity | Coverage/backlog item to preserve through roadmap or matrix | Remove from TODO; Sprint-18 already includes this concept | Sprint-15 closure section 13; Sprint-18 learning objectives and Checkpoint 1; coverage matrix ownership row |
| 24 | Reinforce `&Path` / `PathBuf` analogy | Coverage/backlog item already durably recorded | Remove until selected by approved learning scope | Sprint-15 closure section 13 |
| 25 | Reinforce `HashSet` duplicate detection | Coverage/backlog item already durably recorded | Remove until selected by approved learning scope | Sprint-15 closure section 13; coverage matrix collections row |
| 26 | Revisit stricter persisted-data types | Coverage/backlog item already durably recorded | Remove until selected by approved learning scope | Sprint-15 closure sections 10 and 13 |
| 27 | Add focused file/storage test coverage | Coverage/backlog item to preserve through coverage matrix | Remove until selected by approved learning scope | Sprint-15 closure section 13; coverage matrix testing row |
| 28 | Revisit `Display` and `std::error::Error` | Coverage/backlog item to preserve through coverage matrix | Remove until selected by approved learning scope | Sprint-15 closure section 13; coverage matrix error-handling row |
| 29 | Revisit overflow-safe id generation | Coverage/backlog item already durably recorded | Remove until selected by approved learning scope | Sprint-15 closure sections 10 and 13 |
| 30 | Preserve Sprint-07 as failed/abnormal and uncredited | Historical protection to preserve by pointer rather than task | Remove as task; retain historical reference only | `roadmaps/sprint-07.md`; Sprint-07 Attempt-1 failure review |
| 31 | Keep governance and learning-project validation separate | Standing policy constraint | Remove as task; apply when a validation task exists | `docs/policies/repository-validation-policy.md` section `One Repository Per Validation Prompt`; `AGENTS.md` workflow separation |
| 32 | Ask a future Architect for governance complexity review | Completed task to remove | Remove; this audit and plan fulfill it | Governance optimization audit; this cleanup plan |

### TODO Safety Conclusions

- Every completed item has a durable result file.
- Every reinforcement item is preserved in a closure, the coverage matrix, an accepted roadmap, or more than one of those sources.
- No item requires migration into `governance/observations.md`.
- The observation queue should not become a replacement curriculum backlog.
- The repository-hygiene item is the only current technical-hygiene action worth retaining, and it remains separately gated.

## 6. Proposed Compact `CONTEXT.md` Shape

The following is a planning draft, not a modification to the real file. It targets roughly 80 to 130 lines without making line count a hard policy.

```markdown
# Current Context

## Goal

Become job-ready for entry-level Rust + Blockchain development, prioritizing Solana, general blockchain fundamentals, and broader Rust blockchain engineering in that order.

## Current Stage And Bridge Phase

- Program stage: Stage 2 — Rust Engineering
- Required bridge: Stage 2.5 — Rust Core Philosophy Bridge
- Stage 2.5 status: Incomplete
- Stage 3 transition: Unauthorized

## Current Sprint State

- Active learning sprint: None
- Sprint-16: Stopped before completion; incomplete; unclosed; no completion credit
- Sprint-17: PASS WITH NOTES / CLOSED
- Sprint-18: Accepted / awaiting explicit learner start command
- Sprint-18 execution: Not started
- Teacher execution window: Not open
- Sprint-19 and Sprint-20: Planning recommendations only

## Current Authorization Boundary

Roadmap acceptance does not start execution. Sprint-18 may begin only after an explicit learner command to start Sprint-18 execution or checkpoint work. The Teacher must then complete the startup checklist before Checkpoint 1.

The current governance-optimization work does not constitute a Sprint-18 start command. Sprint-18 teaching must not begin during this governance-optimization window.

## Current Active Governance Focus

- Current focus: Governance-system optimization
- Phase 1 execution-start gate: Complete
- Phase 2A cleanup plan: Complete after this report is accepted
- Next governance action: Learner review and approval decision for Phase 2B
- Phase 2B boundary: Compact `CONTEXT.md` and make `TODO.md` task-only; no roadmap, policy, review, or learning-project changes

## Authoritative Active Files

- Core governance: `AGENTS.md`
- Program stages: `roadmaps/master-roadmap.md`
- Current Sprint-18 contract: `roadmaps/sprint-18.md`
- Sprint-18 scope basis: `reviews/sprint-18-specification-review.md`
- Execution start gate: `docs/policies/lifecycle-policy.md`
- Teacher readiness and authority: `docs/policies/learning-execution-policy.md`
- Topic coverage ledger: `reviews/rust-core-coverage-matrix.md`
- Latest closure: `reviews/sprint-17-closure.md`
- Governance optimization audit: `reviews/governance-system-optimization-audit-2026-06-30.md`
- State cleanup plan: `reviews/state-file-responsibility-cleanup-plan-2026-06-30.md`

The coverage matrix is authoritative for topic coverage. Current sprint lifecycle state remains authoritative here and in the accepted Sprint-18 roadmap.

## Current Coverage State

- Sprint-17 sufficiently covered closures and iterators, systematic pattern matching, and collection ownership for the current curriculum point.
- Remaining P0 blockers include deeper ownership/borrowing mental models and explicit lifetime reasoning.
- Remaining P1 planning includes smart pointers, deeper `RefCell<T>`, broader traits/generics, and public error ergonomics.
- Stage 2.5 remains incomplete; Stage 3 remains blocked.

## Learner Profile And Language Requirements

- Learner: experienced software developer; Rust approximately B+; blockchain beginner
- Technical teaching: Chinese, with English technical terms when useful
- Governance and repository-ready documents: English
- English training: Secondary unless explicitly selected
- Learner approval: Lightweight direction authorization and final human acceptance, not detailed curriculum-quality assurance
- Runtime density feedback: Normal evidence; narrow, reinforce, defer, or split at checkpoint boundaries when needed
- Learner remains the primary learning-project implementer

## Active Risks

- Architect/Teacher role drift
- Governance and learning workflow mixing
- Current-state synchronization drift
- Long-context reliability decline
- Loss of Stage 2.5 coverage visibility during cleanup

## Next Allowed Transition

Current next transition: learner reviews this Phase 2A plan and decides whether to authorize Phase 2B.

Sprint-18 remains blocked during governance optimization. After this governance window ends, a separate explicit learner start command may open the Sprint-18 Teacher execution window; the Teacher startup checklist must then pass before Checkpoint 1.

## Historical References

- Latest Architect handover: `reviews/architect-retirement-handover-2026-06-30-post-sprint-17.md`
- Latest Architect takeover: `reviews/architect-takeover-assessment-2026-06-30-post-sprint-17.md`
- Sprint-16 stopped-state and replanning evidence: `roadmaps/sprint-16.md` and `reviews/stage-2-5-remaining-coverage-review.md`
- Sprint-17 completion evidence: `reviews/sprint-17-closure.md`
- Stage 2.5 specification: `reviews/stage-2-5-bridge-specification.md`
- Chronological history: `learning-log.md`
- Sprint-07 abnormal record: `roadmaps/sprint-07.md` and `reviews/sprint-07-attempt-1-failure-review.md`
- Stage 1 exit evidence: `reviews/stage-1-exit-assessment.md`
```

### Compact-Shape Notes

- The draft intentionally does not reproduce every historical roadmap and closure.
- Historical pointers are conditional navigation aids, not a mandatory startup bundle.
- The draft keeps Sprint-16, Sprint-17, Sprint-18, Stage 2.5, and Stage 3 boundaries explicit.
- The draft makes governance optimization the current focus, preventing accidental teaching during the cleanup window.
- The draft preserves learner approval and runtime density rules because they affect current Sprint-18 execution behavior.

## 7. Proposed Task-Only `TODO.md` Shape

The following is a planning draft, not a modification to the real file.

```markdown
# Current Tasks

- [ ] After learner approval, complete governance optimization Phase 2B by compacting `CONTEXT.md` and making `TODO.md` task-only within the approved plan
- [ ] Keep Sprint-18 accepted but not started throughout the governance-optimization window; after that window, await an explicit learner start command before opening a Teacher execution window
- [ ] Maintain `reviews/rust-core-coverage-matrix.md` before any Stage 3 transition review
- [ ] Define and approve Stage 3 entry prerequisites before any Stage 3 transition decision
- [ ] If still needed and separately authorized, perform a repository-hygiene review for untracked `rust_core_fluency_lab` source and `.DS_Store` / `.idea/` metadata
- [ ] When formal validation is requested, use separate prompts and verdicts for the governance repository and any learning-project repository
```

This shape intentionally excludes:

- completed Sprint-17 and Sprint-18 planning history;
- Sprint-14, Sprint-15, and Sprint-17 reinforcement lists;
- Sprint-07 and Sprint-16 historical guard text already preserved elsewhere;
- general policy reminders without a current action;
- future Sprint-19 and Sprint-20 scope details.

The first item should be removed when Phase 2B completes. The Sprint-18 waiting item should be replaced by an active Teacher execution task only after the learner explicitly ends the governance hold and commands execution to start.

## 8. Startup Load Reduction Proposal

These bundles are recommendations for later startup-policy review. No startup policy file is modified in Phase 2A or proposed Phase 2B.

### Architect / Governance Optimization

Always load:

- `AGENTS.md`;
- compact `CONTEXT.md`;
- task-only `TODO.md`;
- `docs/policies/lifecycle-policy.md`;
- the audit, plan, or governance decision that defines the current task;
- files explicitly authorized for inspection or modification.

Conditionally load:

- master roadmap and coverage matrix for stage or curriculum decisions;
- sprint governance policy for lifecycle changes;
- Codex and language policies when preparing repository updates;
- latest handover/takeover when onboarding or resolving authority ambiguity;
- observations only when the task concerns recurring governance issues.

Do not load by default:

- full `learning-log.md`;
- all historical sprint roadmaps and closures;
- Teacher execution policy when no teaching boundary is under review;
- human runbooks and templates unrelated to the task;
- old Architect handovers superseded by the latest handover.

### Teacher Sprint Execution

Always load:

- `AGENTS.md`;
- compact `CONTEXT.md`;
- accepted current sprint roadmap;
- `docs/policies/learning-execution-policy.md`;
- `docs/policies/lifecycle-policy.md`;
- `docs/policies/learning-execution-policy.md`;
- the learner message that explicitly starts execution.

Conditionally load:

- current Specification Review for scope rationale;
- latest relevant closure or handover for carry-forward evidence;
- coverage matrix when the roadmap has coverage-ledger obligations;
- Codex collaboration policy when generating a formal validation prompt;
- master roadmap when stage alignment is uncertain.

Do not load by default:

- Stage 1 roadmaps and assessments;
- unrelated historical sprint files;
- full learning log;
- Architect startup documents;
- governance observations without a current issue.

### Sprint Closure

Always load:

- `AGENTS.md`;
- compact `CONTEXT.md`;
- accepted sprint roadmap;
- Student Validation evidence;
- Codex Repository Validation report;
- Teacher execution and sprint governance policies;
- sprint review template.

Conditionally load:

- coverage matrix when closure changes topic classification;
- Codex policy when validation scope needs clarification;
- previous closure when explicit comparison is required;
- language policy when output requirements are uncertain.

Do not load by default:

- all prior closures;
- all historical roadmaps;
- old handovers;
- full learning log;
- unrelated governance observations.

### Codex Repository Validation

Always load:

- the explicit validation prompt;
- `AGENTS.md`;
- `docs/policies/repository-validation-policy.md`;
- the target repository or authorized files;
- relevant roadmap, specification, or acceptance criteria.

Conditionally load:

- compact `CONTEXT.md` when current lifecycle or repository boundaries affect validation;
- sprint policy for lifecycle compliance;
- language policy when creating a repository-ready report;
- current closure draft when validating closure synchronization.

Do not load by default:

- unrelated repositories;
- all governance history;
- full learning log;
- old sprint roadmaps and reviews;
- Teacher or Architect startup material unrelated to validation.

### Governance Update

Always load:

- `AGENTS.md`;
- compact `CONTEXT.md`;
- task-only `TODO.md` when current actions change;
- governance lifecycle policy;
- Codex collaboration policy;
- language policy;
- the approved governance decision and exact target files.

Conditionally load:

- sprint policy for lifecycle changes;
- master roadmap for stage-structure changes;
- coverage matrix for curriculum-state changes;
- observations for recurring issue lifecycle changes;
- relevant handover, audit, failure review, or closure.

Do not load by default:

- every policy file;
- all roadmaps and reviews;
- full learning log;
- learning-project code;
- templates and runbooks unrelated to the update.

## 9. Migration Safety Checklist

Phase 2B should not begin until the learner approves this plan or an amended version.

Before editing:

- [ ] Capture `git status` and hashes for all existing dirty and untracked governance files.
- [ ] Record line counts for `CONTEXT.md` and `TODO.md`; current Phase 2A counts are 803 and 34 lines.
- [ ] Confirm the approved Phase 2B target files.
- [ ] Confirm that the governance-optimization window remains active and Sprint-18 teaching remains blocked.

While editing `CONTEXT.md`:

- [ ] Confirm every removed block has the durable source named in section 4.
- [ ] Preserve Sprint-18 accepted / awaiting explicit learner start command.
- [ ] Preserve that Sprint-18 execution has not begun and no Teacher execution window is open.
- [ ] Preserve the explicit learner start command gate and Teacher startup checklist sequence.
- [ ] Preserve Sprint-16 incomplete, unclosed, and without completion credit.
- [ ] Preserve Sprint-17 PASS WITH NOTES / CLOSED.
- [ ] Preserve Stage 2.5 incomplete.
- [ ] Preserve Stage 3 unauthorized.
- [ ] Preserve learner approval as lightweight direction authorization rather than detailed curriculum QA.
- [ ] Preserve runtime density feedback as normal and actionable.
- [ ] Preserve governance optimization as the current Architect focus.
- [ ] Preserve that Sprint-18 teaching must not start during the governance-optimization window.
- [ ] Preserve current language requirements and learner-primary implementation.
- [ ] Label the coverage matrix as a topic ledger, not current sprint lifecycle authority.

While editing `TODO.md`:

- [ ] Confirm every removed item is completed, moved, duplicated, policy-owned, or durably preserved in the source named in section 5.
- [ ] Keep only tasks with a clear actor, prerequisite, and completion condition.
- [ ] Do not copy the reinforcement backlog into `CONTEXT.md`.
- [ ] Do not copy the reinforcement backlog into `governance/observations.md`.
- [ ] Keep the repository-hygiene task separately gated and do not access the learning project during Phase 2B.

After editing:

- [ ] Report line counts before and after for both files.
- [ ] Run `git diff --check`.
- [ ] Run a repository-wide trailing-whitespace check.
- [ ] Run a conflict-marker check.
- [ ] Review the complete diff for unique-information loss.
- [ ] Verify only approved Phase 2B files changed relative to the captured baseline.
- [ ] Confirm no policy, roadmap, review, template, runbook, or learning-project file was modified.
- [ ] Confirm Sprint-18 remains accepted but not started.
- [ ] Confirm no learning-project repository was accessed.

## 10. Recommended Phase 2B Scope

Phase 2B should modify exactly:

- `CONTEXT.md`;
- `TODO.md`.

Phase 2B should not modify:

- `governance/observations.md`;
- `AGENTS.md`;
- policy files;
- roadmaps;
- reviews;
- `README.md`;
- `learning-log.md`;
- templates;
- runbooks;
- learning-project repositories.

No current TODO item qualifies as a new governance observation. Updating `governance/observations.md` would create an unnecessary third migration target and risk turning the observation queue into a backlog.

If Phase 2B discovers genuinely unique information without a durable source, implementation should stop and report the blocker rather than expanding scope automatically. Startup-policy consolidation belongs to the later Phase 3 workflow, not Phase 2B.

## 11. Risks

### Unique Information Loss

The largest risk is deleting a block that appears repetitive but contains the only copy of a learner preference, current authorization boundary, or migration trigger. Learner profile, language, runtime density, and current governance focus require direct preservation.

### Excessive Compression

`CONTEXT.md` could become too terse for a new agent to identify the correct roadmap, closure, coverage ledger, or handover. The compact file needs explicit active pointers and historical navigation without reproducing historical content.

### Moving History Into `TODO.md`

The cleanup must not solve `CONTEXT.md` size by moving history or standing rules into `TODO.md`. The task file should remain an action queue.

### Observation Queue Pollution

`governance/observations.md` explicitly rejects general brainstorming and backlog. Moving reinforcement or cleanup ideas there would recreate the same problem in another file.

### Sprint-18 Boundary Regression

Compression could accidentally weaken “accepted but not started,” omit the explicit start gate, or imply that Teacher execution follows Phase 2B automatically. The authorization boundary must remain explicit.

### Stage 2.5 Visibility Loss

Removing detailed coverage prose could make remaining P0 and P1 work invisible. The compact state must retain a concise coverage summary and a direct pointer to the coverage matrix and bridge specification.

### Stale Historical Status In Referenced Files

Some historical or planning files include status wording that predates Sprint-18 acceptance. The compact `CONTEXT.md` must be explicit that it and the accepted Sprint-18 roadmap control current lifecycle state, while the coverage matrix controls topic coverage.

### Dirty-Worktree Attribution

The repository already contains modified and untracked governance work. Phase 2B must compare hashes and status against a captured baseline so existing changes are not incorrectly attributed to the cleanup.

## 12. Final Recommendation

Phase 2B should proceed after learner review and explicit approval of this plan.

The proposed cleanup is behavior-preserving because:

- current lifecycle, authorization, stage, language, learner, and risk state remains in compact `CONTEXT.md`;
- every removed historical block has a durable repository source;
- every removed TODO item is completed, duplicated, policy-owned, or preserved in a roadmap, review, closure, coverage ledger, failure record, or learning log;
- no current item needs migration into the governance observation queue;
- Phase 2B can remain limited to two files;
- startup-policy consolidation is deferred to Phase 3.

Recommended decision: Approve Phase 2B as a narrow rewrite of `CONTEXT.md` and `TODO.md` only, using sections 6, 7, and 9 as the implementation contract. Do not start Sprint-18 during that work.
