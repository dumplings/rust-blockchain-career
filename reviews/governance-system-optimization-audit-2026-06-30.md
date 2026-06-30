# Governance System Optimization Audit - 2026-06-30

## 1. Audit Identity

- Audit type: Repository-wide governance system optimization audit
- Audit date: 2026-06-30
- Trigger: Architect-to-Teacher role-switch drift after Sprint-18 roadmap acceptance
- Broader concern: Governance process complexity, repeated multi-file updates, state duplication, and startup-load growth
- Current sprint state: Sprint-18 accepted but not started
- Current stage state: Stage 2 / Stage 2.5 bridge work
- Stage 3 transition: Unauthorized
- Audit boundary: Diagnosis and optimization planning only; no policy, roadmap, current-state, learning-log, template, or learning-project changes
- Governance repository: `/Users/dumplings/workspace/rust-blockchain-career`

The audit treats the local repository as authoritative. It does not continue Sprint-18 teaching, start Sprint-18 execution, or count the drifted Checkpoint 1 interaction as Sprint-18 learning execution.

## 2. Incident Summary

The triggering sequence was:

1. The Sprint-18 roadmap was accepted as pending execution start.
2. Sprint-18 execution had not begun, no Teacher execution window had been explicitly opened, and no learning project had been created.
3. The assistant was operating as Architect / governance support.
4. The assistant incorrectly switched into Teacher execution and began Checkpoint 1 without an explicit learner command to start Sprint-18 or change roles.
5. The learner challenged the role switch.
6. The learner did not cause the error. Roadmap acceptance was not an instruction to begin teaching in the same interaction.

The attempted teaching does not count as Sprint-18 execution, Student Validation, Teacher Learning Validation, roadmap progress, or Stage 2.5 completion evidence. Sprint-18 remains accepted but not started.

## 3. Repository Inventory

### Inventory Method

The audit used repository-local inspection only:

- `rg --files` and `find` for the repository tree;
- `wc -l` for file and directory size;
- Markdown heading extraction for every roadmap, review, policy, agent document, template, runbook, and note;
- full-content review of the core state files, all policies, Architect startup documents, the human runbook, templates, relevant failure reviews and handovers, and the Stage 2.5 / Sprint-16 / Sprint-17 / Sprint-18 chain;
- `git status`, `git diff`, and Git history touch counts for state, scope, and churn evidence;
- targeted searches for role-switch, execution-start, authorization, startup-load, state-synchronization, and supersession wording.

No learning-project repository was inspected.

### Inventory At Audit Start

The repository contained 69 Markdown files, plus `.gitignore`, totaling 20,229 Markdown lines before this audit report was created.

| Category | File count | Approximate lines | Purpose |
| --- | ---: | ---: | --- |
| Root governance and current state | 5 Markdown files | 2,212 | `README.md`, `AGENTS.md`, `CONTEXT.md`, `TODO.md`, and `learning-log.md` |
| `docs/` | 9 | 2,495 | Five policies, two Architect startup documents, one human runbook, and one directory index |
| `roadmaps/` | 20 | 8,877 | Master roadmap, 17 numbered sprint records, one assessment specification, and one Stage 2.5 unit proposal |
| `reviews/` | 28 | 6,018 | Sprint outcomes, failures, assessments, audits, stage reviews, handovers, takeover, and Sprint-18 specification review |
| `governance/` | 1 | 268 | Governance observation queue |
| `templates/` | 5 | 348 | Daily log, note, handover, specification review, and sprint review templates |
| `notes/` | 1 | 11 | Sprint-01 note |
| `assets/` | 0 | 0 | Empty asset directory |

`.DS_Store` files exist at the repository root and under `docs/`; they are ignored metadata, not governance assets. `.gitignore` covers `.DS_Store`, `.idea`, `.vscode`, and `temp`.

### Roadmap And Review Counts

`roadmaps/` contains:

- one master roadmap;
- 17 numbered sprint roadmap or abnormal-record files: Sprint-01, Sprint-02, and Sprint-04 through Sprint-18;
- one Stage 1 exit-assessment specification;
- one Stage 2.5 Unit 1 proposal.

`reviews/` contains:

- 17 sprint-specific review, closure, failure, or specification-review files;
- four Architect handover or takeover files;
- seven baseline, coverage, stage, assessment, or bridge review files.

The file count is not inherently excessive. Most files preserve distinct decisions or evidence. The risk comes from loading too many of them during normal startup and from copying current state into historical artifacts.

### Unusually Large Files

The largest active or frequently referenced files are:

- `roadmaps/sprint-15.md`: 993 lines;
- `learning-log.md`: 985 lines;
- `CONTEXT.md`: 801 lines;
- `roadmaps/sprint-13.md`: 791 lines;
- `roadmaps/sprint-14.md`: 747 lines;
- `roadmaps/sprint-12.md`: 696 lines;
- `roadmaps/sprint-09.md`: 672 lines;
- `docs/runbooks/system-operator-manual-zh.md`: 599 lines;
- `roadmaps/sprint-16.md`: 570 lines;
- `roadmaps/sprint-17.md`: 516 lines;
- `roadmaps/sprint-18.md`: 431 lines.

Large historical roadmaps are acceptable when loaded conditionally. They become a startup problem when `CONTEXT.md` asks a Teacher to read many of them together.

### High-Churn Files

Git history shows that churn is concentrated in the active core:

- `CONTEXT.md`: touched by 26 commits;
- `TODO.md`: touched by 24 commits;
- `learning-log.md`: touched by 21 commits;
- `AGENTS.md`: touched by 20 commits;
- `governance/observations.md`: touched by 6 commits.

`CONTEXT.md` and `TODO.md` are expected to change. Their churn becomes risky when they repeat history, policy constraints, and detailed sprint records instead of remaining compact current-state surfaces.

### Pre-Existing Worktree State

The audit began with these pre-existing changes:

- modified: `CONTEXT.md`;
- modified: `TODO.md`;
- modified: `docs/policies/sprint-governance-policy.md`;
- modified: `docs/policies/teacher-execution-policy.md`;
- untracked: `reviews/architect-takeover-assessment-2026-06-30-post-sprint-17.md`;
- untracked: `reviews/sprint-18-specification-review.md`;
- untracked: `roadmaps/sprint-18.md`.

These files were treated as the current local source of truth and were not changed by this audit.

## 4. Current Governance Architecture Assessment

### Current Architecture

The repository uses a sensible layered architecture:

- `AGENTS.md` is the durable entry point and role-boundary map.
- `CONTEXT.md` is intended to hold current stage, sprint, milestone, risk, and handover state.
- `TODO.md` is intended to hold current actionable work.
- `docs/policies/` contains reusable role and workflow rules.
- `roadmaps/` contains stage and sprint planning contracts.
- `reviews/` contains completed decisions, evidence, audits, closures, failures, and handovers.
- `governance/observations.md` is the governance issue lifecycle queue.
- `templates/` and `docs/runbooks/` support repeatable reporting and human operation.
- `learning-log.md` preserves chronological learning history.

This division is conceptually sound. It supports transferability across chats, models, agents, and platforms. Repository-first durability remains necessary.

### Necessary Complexity

The following complexity is justified:

- separate current state, reusable policy, execution contract, and completed evidence;
- distinct Student Validation, Codex Repository Validation, and Teacher Learning Validation;
- separate learning-project and governance-repository validation;
- durable failure, stop, closure, and handover evidence;
- stage-level coverage planning before a Stage 3 transition;
- explicit role boundaries among Learner, Teacher, Codex, and Architect;
- historical artifacts that allow future agents to reconstruct why a decision was made.

Removing these distinctions would reduce durability and make the system more dependent on chat memory.

### Avoidable Complexity

The avoidable complexity is concentrated in four areas:

1. Current sprint and authorization state is repeated across `CONTEXT.md`, `TODO.md`, roadmaps, reviews, handovers, and planning documents.
2. Historical files are sometimes edited to carry later current state, which mixes an event record with a living status document.
3. Startup file lists are repeated in `AGENTS.md`, `CONTEXT.md`, `README.md`, Architect documents, and the runbook with different scopes.
4. Standing constraints and historical reinforcement notes are kept in active state and task files.

The architecture does not need replacement. It needs stricter responsibility boundaries and a smaller active working set.

## 5. Root Cause Analysis Of Role-Switch Drift

### Cause Assessment

| Possible cause | Assessment | Evidence |
| --- | --- | --- |
| Assistant execution error | Primary cause | The assistant changed from Architect / governance mode to Teacher execution without learner authorization. |
| Missing explicit role rule | Not the primary gap | `AGENTS.md` already says Architects must not become the default Teacher unless the learner explicitly changes the role for a specific task. The Architect standard prompt also says not to start normal teaching unless explicitly asked to switch roles. |
| Unclear existing role rule | Minor contributor at most | The rule is explicit and repeated. The problem was failure to obey it, not inability to find it. |
| Missing execution-start protocol | Material gap | No canonical rule states that an accepted roadmap remains blocked until a later explicit learner start command, unless the learner's acceptance message itself clearly includes the start command. |
| Conflicting current state | No direct conflict in the active Sprint-18 state | `CONTEXT.md`, `TODO.md`, and `roadmaps/sprint-18.md` all say accepted but not started. |
| Ambiguous action wording | Material contributor | The roadmap says acceptance permits a future Teacher execution window after the startup checklist, and its final “next permitted action” is to open that window and begin Checkpoint 1. `TODO.md` presents starting Sprint-18 as the next unchecked action. |
| Process fragmentation | Contributing factor | Role rules, startup checks, authorization wording, and next actions are spread across several files. |
| Context length | Risk multiplier, not primary cause | The active Teacher reading list in `CONTEXT.md` names 33 files totaling 13,114 lines, about 65% of all repository Markdown at audit start. |
| Roadmap acceptance wording | Contributing factor | “Accepted,” “authorized,” “ready,” “pending execution,” and “next permitted action” are used close together without one formal lifecycle transition rule. |
| Lack of a hard execution-start gate | Material design weakness | The Teacher startup checklist verifies state and scope but does not explicitly verify a learner start command or role transition. |

### Explicit Answers

Was this primarily context exhaustion?

No. Long context and excessive startup load increase drift probability, but the current state and role restriction were explicit. Context pressure is a system risk multiplier, not a sufficient explanation for this incident.

Was this primarily assistant execution drift?

Yes. The assistant violated an existing role boundary and acted on a queued next task without confirming authority to change roles or start execution.

Did governance wording or workflow design contribute?

Yes. The system distinguishes accepted from started in prose but does not define a single hard transition gate. The unchecked `TODO.md` item and roadmap “next permitted action” can be misread as immediately executable by the current agent.

Is adding a rule sufficient?

No. A narrow execution-start rule is required for immediate prevention, but the active-state and startup-load design should also be simplified. Adding more warnings to every file would treat the symptom while increasing fragmentation.

## 6. Rule Gap Versus Patch Analysis

| Proposed response | Classification | Decision |
| --- | --- | --- |
| “Architect / governance mode must not automatically become Teacher execution mode.” | Existing rule already covers it; a clarification may improve enforcement | Do not create a second independent role rule. Link the existing role boundary to the sprint execution-start gate. |
| “Teacher execution requires an explicit learner start command.” | Missing rule that should be added | Add one canonical execution-start transition rule. Allow acceptance and start in one message only when the learner explicitly requests both. |
| “A passed Teacher startup checklist authorizes execution.” | Unclear existing assumption that should be rejected | The checklist verifies readiness; it must not create authorization. Add learner-start verification to the checklist. |
| “Accepted / pending execution start” as a formal lifecycle state | Clarification of existing state | Standardize it as one canonical state, such as `accepted_not_started`, with one allowed next transition. |
| Repeating “does not start execution” in every roadmap section, review, task, and handover | Patch compensating for an over-complex workflow | Avoid. Keep the rule canonical and keep current state in one active-state surface. |
| Requiring agents to reread all historical roadmaps and reviews before execution | Unnecessary and counterproductive | Existing current-state and relevant-artifact rules are enough if the active state is compact and reliable. |
| Adding another standalone role-switch policy file | Better solved by simplifying state flow | Do not add a sixth policy for this issue. The lifecycle belongs in the sprint policy, with a short Teacher-policy cross-reference. |

Applied to the proposed sentence as a whole:

- the Architect-to-Teacher boundary is an enforcement clarification of an existing rule;
- the explicit learner start command is a genuinely missing transition rule;
- the safest implementation is one canonical execution-start protocol, not repeated warning text across the repository.

## 7. Sprint Planning Workflow Complexity Review

### Actual Sprint-18 Preparation Chain

| Step | Classification | Assessment |
| --- | --- | --- |
| Post-Sprint-17 Architect takeover assessment | Necessary only after handover or agent replacement | It was justified by the controlled Architect retirement and long-context reliability concern. It should not be a normal sprint-opening step. |
| Sprint-18 Specification Review | Necessary and should remain separate for this case | Sprint-18 introduced a new P0 topic group with high overload risk, so a separate scope decision was justified. Routine continuation sprints may use a lighter review package. |
| Learner-approval and runtime-density policy clarification | Useful but can be batched | The learner feedback was reusable and deserved governance treatment. It should remain an exceptional policy update, not a standard sprint-preparation phase. The approved policy update can be batched into one reviewed governance pass. |
| Sprint-18 roadmap draft | Necessary and should remain separate from execution | The roadmap is the execution contract. Drafting should not itself change active sprint state. |
| Learner roadmap acceptance | Necessary and should remain separate from execution start | Acceptance should create `accepted_not_started`, not `active`. A learner may explicitly accept and start in one message, but that must be unambiguous. |
| Roadmap acceptance synchronization | Useful but can be batched | One milestone update to the roadmap status, compact current state, and next task is enough. |
| Repeated `CONTEXT.md` / `TODO.md` updates during planning | Redundant or too fine-grained | Intermediate recommendations, drafts, and confirmations do not each need active-state synchronization. Update after a meaningful state transition. |
| Accepted-but-not-started state | Necessary and should remain separate | It protects the learner from automatic execution. It should appear once as canonical current state rather than in many repeated paragraphs. |
| Teacher startup checklist | Necessary and should remain separate at execution start | It belongs at the Teacher execution boundary. It must verify the explicit start command and current role, not merely language and scope. |

### Overall Assessment

The Sprint-18 chain was unusually long because it combined:

- a controlled Architect replacement;
- Stage 2.5 curriculum planning;
- learner feedback requiring a reusable policy clarification;
- a new high-risk P0 sprint direction;
- roadmap drafting and acceptance.

That does not mean every step was unnecessary. The problem is that exceptional takeover and governance steps became entangled with the normal sprint-opening path, while current-state synchronization repeated the same status in multiple locations.

A normal future sprint should usually require:

1. a scoped Specification Review, which may be lightweight for routine continuation;
2. one roadmap draft and learner acceptance;
3. one acceptance-state synchronization;
4. a later explicit learner execution-start command;
5. the Teacher startup checklist and checkpoint execution.

It should not require a takeover assessment, policy change, historical file refresh, or full repository chronology load unless the situation specifically demands them.

## 8. `CONTEXT.md` And `TODO.md` Responsibility Audit

### `CONTEXT.md`

`CONTEXT.md` is too long for its intended current-state role.

At 801 lines, it currently mixes:

- current stage and sprint state;
- milestone and authorization state;
- curriculum coverage history;
- completed sprint history;
- detailed learning-project summaries;
- startup reading instructions;
- repository structure;
- current work and future focus;
- special historical failure rules;
- full Sprint-08 through Sprint-17 implementation summaries;
- future system restructuring notes;
- latest closure and assessment summaries;
- language and learner profile information.

This mixture increases drift risk because a future agent must distinguish current instructions from historical explanation inside one large mutable file.

`CONTEXT.md` should retain:

- current program stage and current bridge phase as separate fields;
- current sprint lifecycle state;
- current milestone;
- explicit execution authorization state;
- one next permitted transition and its required actor;
- active blockers and current risks;
- current teaching and governance language;
- concise learner operating constraints that materially affect the next action;
- pointers to the active roadmap, latest closure, current coverage ledger, and latest relevant handover.

The following should leave active startup load:

- detailed Sprint-01, Sprint-02, Sprint-06, and later project summaries already preserved in closures and `learning-log.md`;
- the full completed-sprint checklist;
- old project command and test counts;
- historical handover narratives;
- old stage-assessment detail;
- repository structure already documented in `README.md`;
- future directory-restructuring ideas;
- the 33-file Teacher startup list;
- repeated Sprint-16, Sprint-17, Sprint-18, and Stage 3 status paragraphs.

Those records should remain in reviews, handovers, roadmaps, the coverage matrix, and `learning-log.md`, referenced by path when relevant.

### `TODO.md`

`TODO.md` is only 34 lines, but it is not currently task-only. It contains:

- completed preparation tasks;
- the immediate Sprint-18 start task;
- standing prohibitions;
- curriculum coverage obligations;
- reinforcement topics from old sprint closures;
- repository-hygiene ideas;
- long-term Stage 3 prerequisites;
- validation workflow invariants.

Examples such as “Keep Stage 3 transition unauthorized,” “Preserve Sprint-07,” and “Keep governance repository validation and learning-project validation separate” are state or policy, not executable tasks.

`TODO.md` should retain only actionable work with a clear completion condition. Completed planning items should be removed after their outcome is preserved elsewhere. Standing constraints should live in policy or current state. Topic reinforcement should live in the coverage matrix or relevant closure, with only the currently selected reinforcement task copied into `TODO.md`.

### Responsibility Verdict

- `CONTEXT.md` should answer: What is true now, what is blocked, and what transition is allowed next?
- `TODO.md` should answer: What concrete actions remain now?
- reviews and handovers should answer: What happened and why?
- `learning-log.md` should answer: What learning occurred over time?
- roadmaps should answer: What is the accepted execution contract?
- policies should answer: What reusable rules apply?

## 9. Roadmaps And Stage 2.5 File Proliferation Review

### Purpose Separation

The Stage 2.5 artifact chain mostly serves distinct purposes:

| Artifact | Distinct purpose | Current assessment |
| --- | --- | --- |
| `reviews/rust-curriculum-coverage-audit.md` | Diagnoses curriculum and job-readiness gaps | Distinct historical audit |
| `reviews/rust-core-coverage-matrix.md` | Living topic-level coverage ledger | Necessary active planning reference |
| `reviews/stage-2-post-midpoint-review.md` | Governance decision to require a bridge before Stage 3 | Distinct historical decision |
| `reviews/stage-2-5-bridge-specification.md` | Stage-level bridge purpose, coverage, and entry prerequisites | Distinct durable specification, but it contains stale current-action text |
| `roadmaps/stage-2-5-unit-1-rust-core-fluency.md` | Source proposal for Unit 1 | Superseded by `roadmaps/sprint-16.md`; already labeled as superseded |
| `roadmaps/sprint-16.md` | Accepted Sprint-16 execution contract | Necessary, but later status and partial-progress material blur roadmap and stop record responsibilities |
| `reviews/stage-2-5-remaining-coverage-review.md` | Replanning after Sprint-16 stopped | Distinct historical planning decision; already labeled historical |
| `roadmaps/sprint-17.md` | Accepted Sprint-17 execution contract | Distinct historical roadmap |
| `reviews/sprint-17-closure.md` | Sprint-17 completion and evidence | Distinct authoritative closure |
| `reviews/sprint-18-specification-review.md` | Sprint-18 direction and scope decision | Distinct current planning input |
| `roadmaps/sprint-18.md` | Accepted Sprint-18 execution contract | Distinct current roadmap |

Stage 2.5 therefore created mostly necessary planning artifacts rather than arbitrary file proliferation.

### Actual Proliferation Risk

The risk is not the existence of the files. It is that some planning and historical files are synchronized forward with later current state while others are not.

For example:

- the Unit 1 proposal clearly says it is superseded;
- the remaining-coverage review clearly says it is historical;
- the bridge specification still contains a “Recommended Next Governance Actions” section saying to open Sprint-17 and describing Sprint-17 as not started, even though Sprint-17 is closed;
- `roadmaps/sprint-16.md` has become both the original contract and a later partial-progress status record;
- current Sprint-16 and Stage 3 warnings are repeated across many later artifacts.

This creates a synchronization problem that cannot be solved reliably by updating every historical file after every milestone.

### Recommended Treatment

- Do not delete or broadly rename Stage 2.5 artifacts now.
- Do not load historical proposals, old roadmaps, or old reviews during normal Teacher execution unless the current roadmap explicitly depends on them.
- Preserve historical artifacts as “as-of” records.
- Add a short status or supersession banner only where a historical file can reasonably be mistaken for current authority.
- Stop copying later current state into old roadmaps and reviews.
- Use `CONTEXT.md` and the coverage matrix as the active pointers.
- Defer directory archival or broad index creation until after Stage 2.5, when the full bridge history can be classified without moving active files.

File count alone is not a defect. Ambiguous authority and unnecessary startup loading are the defects.

## 10. Policy File Complexity Review

### Responsibility Separation

The five policy files have valid primary responsibilities:

- `teacher-execution-policy.md`: instruction, checkpoints, review, startup readiness, and Teacher Learning Validation;
- `sprint-governance-policy.md`: sprint lifecycle, roadmap ownership, scope, execution, closure, and state synchronization;
- `codex-collaboration-policy.md`: Codex boundaries, prompts, and repository validation;
- `language-output-policy.md`: language and output classification;
- `governance-lifecycle-policy.md`: governance review, observations, updates, handovers, and cross-agent action requests.

The five-file policy split is reasonable. A broad merge is not recommended.

### Overlap And Duplication

The policies total 1,295 lines. Important overlap includes:

- workflow separation in `AGENTS.md`, sprint policy, governance policy, Codex policy, Architect documents, and the runbook;
- validation-layer explanations in `AGENTS.md`, sprint policy, Teacher policy, Codex policy, and every recent roadmap;
- learner-primary implementation boundaries in `AGENTS.md`, Teacher policy, Codex policy, Architect documents, and the runbook;
- Prompt Responsibility in governance policy, Codex policy, Architect documents, and the runbook;
- state synchronization in both sprint and governance policies;
- learner approval and runtime density in both sprint and Teacher policies;
- role boundaries in `AGENTS.md`, governance policy, Architect bootstrap, Architect standard prompt, and the runbook.

Some repetition is purposeful because each role needs a local operational view. The problem is that normative ownership is not always obvious.

### Recommended Canonical Ownership

- `AGENTS.md`: durable role boundaries and policy map.
- Sprint policy: lifecycle states, acceptance, explicit execution start, stop, closure, and state synchronization.
- Teacher policy: teaching behavior and readiness checks after execution has been authorized.
- Codex policy: repository modification and validation mechanics.
- Governance policy: observations, governance updates, handovers, and general cross-agent requests.
- Language policy: language only.

Other files should summarize and link instead of restating complete rules.

### Critical-Rule Scatter Risk

There is a real risk that agents miss critical rules because:

- startup requirements appear in several files;
- the Architect role boundary is explicit, but the sprint execution-start gate is absent;
- the Teacher checklist is separated from roadmap acceptance wording;
- `CONTEXT.md` contains its own 33-file Teacher startup list that is much broader than the role-specific list in `AGENTS.md`;
- `README.md` tells all agents to read `learning-log.md`, while `AGENTS.md` promotes role-specific loading;
- the Architect standard prompt requires the human runbook and the standard prompt itself, even though those largely duplicate material already supplied to the agent.

The answer is canonical ownership and cross-reference, not another policy layer.

## 11. Startup Load Review

### Current Load

The current startup model is too large and internally inconsistent.

The most severe example is the Teacher list in `CONTEXT.md`: 33 files and 13,114 lines before execution. That list includes Stage 1 assessment files, Sprint-11 through Sprint-18 roadmaps and reviews, several Stage 2.5 planning artifacts, the coverage audit and matrix, the latest handover and takeover assessment, and the full learning log.

This defeats the “load only relevant policies” principle in `AGENTS.md` and makes historical status wording compete with current state.

### Always-Required Core

For any repository-facing role:

- `AGENTS.md`;
- a compact `CONTEXT.md`;
- the user's current task or prompt.

`TODO.md` should be required when the role is selecting or updating current work, but not necessarily for a narrowly scoped validation prompt.

### Conditional Role Bundles

#### Architect Takeover

Always load:

- `AGENTS.md`;
- compact `CONTEXT.md`;
- `TODO.md`;
- `roadmaps/master-roadmap.md`;
- `governance/observations.md`;
- governance lifecycle policy;
- sprint governance policy;
- latest relevant handover or takeover report.

Load conditionally:

- Codex policy when preparing repository action;
- language policy when producing repository assets;
- current coverage ledger for curriculum or stage decisions;
- current or proposed roadmap and latest relevant closure;
- failure review only when its failure pattern is relevant.

The human runbook and canonical Architect prompt should not both be mandatory reading after the Architect has already been created from that prompt.

#### Teacher Sprint Execution

Always load:

- `AGENTS.md`;
- compact `CONTEXT.md`;
- accepted current sprint roadmap;
- Teacher execution policy;
- sprint governance policy;
- language policy.

Load conditionally:

- latest closure or handover when the roadmap depends on carry-forward evidence;
- coverage matrix when the sprint has explicit coverage-ledger obligations;
- Codex policy when generating formal validation prompts;
- master roadmap when stage alignment is uncertain, not for every checkpoint.

#### Sprint Closure

Load:

- current sprint roadmap;
- Student Validation and Codex validation evidence;
- Teacher policy and sprint policy;
- sprint review template;
- compact current state;
- coverage matrix only if closure changes coverage classification.

Historical roadmaps from unrelated sprints are not required.

#### Governance Update

Load:

- `AGENTS.md`;
- compact `CONTEXT.md`;
- governance lifecycle policy;
- Codex policy;
- only the policy, state, review, roadmap, or observation files affected by the decision;
- master roadmap only if stage structure or ordering is affected.

#### Codex Validation

Load:

- the explicit validation prompt;
- `AGENTS.md`;
- Codex policy;
- target roadmap or acceptance criteria;
- target repository files.

Load `CONTEXT.md`, language policy, or governance history only when the validation scope requires them.

### Startup Verdict

Role-specific startup bundles should replace cumulative historical reading lists. `CONTEXT.md` should point to a small canonical active set. Historical roadmaps, reviews, learning logs, and failure records should be conditional evidence, not default context.

## 12. Minimal Optimization Recommendations

### P0 - Drift Prevention

| Recommendation | Target file(s) | Expected benefit | Risk of change | Change type |
| --- | --- | --- | --- | --- |
| Add one canonical Sprint Execution Start Gate: roadmap acceptance creates `accepted_not_started`; execution begins only after an explicit learner start command, unless the same learner message explicitly both accepts and starts | `docs/policies/sprint-governance-policy.md`; short cross-reference in `docs/policies/teacher-execution-policy.md` | Prevents roadmap acceptance, TODO ordering, or checklist completion from being treated as implicit execution authority | Low; wording must allow an intentional combined accept-and-start command | Rule addition |
| Tie the existing Architect role boundary to the execution gate: an Architect may recommend or hand off the next Teacher action but may not perform it without an explicit role switch | `AGENTS.md` or its existing role-boundary section; `docs/agents/architect-standard-prompt.md` only if a matching operational sentence is needed | Converts an existing principle into an enforceable transition condition without inventing a new role model | Low; avoid duplicating the full rule in multiple files | Rule clarification |
| Extend the Teacher startup checklist with “explicit learner start command verified” and “current agent is authorized to act as Teacher” | `docs/policies/teacher-execution-policy.md` | Makes readiness checking include authority, not only state, scope, language, and learner-primary implementation | Low | Rule clarification |
| Normalize current Sprint-18 wording after the rule is approved so the only next transition is “await explicit learner start”; do not phrase starting as an executable task for the current Architect | `CONTEXT.md`, `TODO.md`, `roadmaps/sprint-18.md` | Removes the immediate ambiguity that contributed to this incident | Medium because three current files must remain semantically aligned | Workflow simplification |

### P1 - Complexity Reduction

| Recommendation | Target file(s) | Expected benefit | Risk of change | Change type |
| --- | --- | --- | --- | --- |
| Reduce `CONTEXT.md` to current state, current risks, language, learner constraints, one next transition, and active pointers | `CONTEXT.md`; historical content remains in existing reviews, roadmaps, handovers, and `learning-log.md` | Reduces startup load and makes current authority obvious | Medium; careless removal could lose a unique fact, so every removed block needs a destination or existing durable source | Documentation cleanup |
| Make `TODO.md` task-only; remove completed preparation items, standing prohibitions, policy invariants, and the long reinforcement backlog | `TODO.md`; use `reviews/rust-core-coverage-matrix.md` and relevant closures as durable topic sources | Makes the next action queue operational and prevents constraints from masquerading as tasks | Low to medium; ensure no unique reinforcement item is lost | Workflow simplification |
| Define one canonical role-based startup matrix and replace other startup lists with references | `AGENTS.md`, `README.md`, `CONTEXT.md`, `docs/agents/architect-standard-prompt.md`, `docs/runbooks/system-operator-manual-zh.md`, relevant policy introductions | Removes contradictory and cumulative required-file lists; avoids the current 33-file Teacher startup load | Medium; bundles must retain conditional escalation paths | Workflow simplification |
| Batch state synchronization at meaningful transitions: draft, acceptance, start, stop, and closure; do not update active state for every discussion step | `docs/policies/sprint-governance-policy.md`, `docs/policies/governance-lifecycle-policy.md`, relevant templates | Reduces repeated `CONTEXT.md` / `TODO.md` edits and partial synchronization | Low | Workflow simplification |
| Treat roadmaps and reviews as as-of artifacts; stop synchronizing later current state into every historical file | Sprint and governance policies; confusing Stage 2.5 artifacts may receive a one-time status banner after approval | Prevents historical/current mixtures and eliminates an impossible all-files synchronization obligation | Medium; agents must know where current state now lives | Rule clarification |
| Separate “current program stage” from “active bridge phase” in the compact state model | `CONTEXT.md`, sprint lifecycle terminology in `docs/policies/sprint-governance-policy.md` | Removes inconsistent descriptions of Stage 2 versus Stage 2.5 without changing roadmap ordering | Low | Rule clarification |

### P2 - Future Cleanup

| Recommendation | Target file(s) | Expected benefit | Risk of change | Change type |
| --- | --- | --- | --- | --- |
| After Stage 2.5, evaluate lightweight `roadmaps/` and `reviews/` indexes or archive groupings that mark active, historical, and superseded artifacts | Possible `roadmaps/README.md`, `reviews/README.md`, or an approved archive structure | Improves discovery without deleting evidence | Medium to high; renames can break links and indexes can become another synchronization surface | Documentation cleanup |
| Shorten overlapping Architect bootstrap material so the bootstrap guide owns role explanation and the standard prompt owns launch instructions | `docs/agents/architect-bootstrap-guide.md`, `docs/agents/architect-standard-prompt.md`, human runbook references | Reduces duplicated role and startup content | Medium; the startup prompt must remain portable when used outside the repository | Documentation cleanup |
| Add a review trigger, not a hard failure threshold, for oversized active-state files or startup bundles | `docs/policies/governance-lifecycle-policy.md` if later approved | Detects future active-state growth before it reaches the current scale | Low if advisory; high if turned into bureaucratic line-count compliance | Rule addition |
| Consider a concise sprint-roadmap template after the current bridge, with policies referenced instead of restated | `templates/`, only after separate review | Reduces repeated validation, role, and non-authorization boilerplate in future roadmaps | Medium; over-compression could hide sprint-specific requirements | Documentation cleanup |

## 13. Proposed Implementation Plan

### Phase 1 - Immediate P0 Role-Switch And Execution-Start Clarification

Timing: Do now only after learner approval of a focused governance update.

Scope:

1. Add the canonical execution-start gate to the sprint policy.
2. Add authority verification to the Teacher startup checklist.
3. Cross-reference the existing Architect role boundary instead of creating a new policy.
4. Normalize current Sprint-18 state and next-action wording.
5. Confirm Sprint-18 remains accepted but not started after the update.

This phase should be a small reviewed change. It must not start Sprint-18.

### Phase 2 - State-File Responsibility Cleanup Proposal

Timing: Later, after Phase 1 is accepted, and only after the learner reviews a proposed compact state shape.

Scope:

1. Produce a before/after responsibility map for `CONTEXT.md` and `TODO.md`.
2. Verify that every historical block being removed already exists in a roadmap, review, handover, coverage ledger, or learning log.
3. Rewrite `CONTEXT.md` as compact current state and active pointers.
4. Rewrite `TODO.md` as current actionable work only.

This phase is the largest behavior-preserving cleanup and should not be bundled with policy redesign beyond the approved P0 gate.

### Phase 3 - Startup-Load Simplification

Timing: After the compact state files are stable and with learner approval.

Scope:

1. Define role-specific bundles in one canonical location.
2. Replace duplicate startup lists with references.
3. Keep historical and failure evidence conditional.
4. Test the bundles against Architect takeover, Teacher execution, closure, governance update, and Codex validation scenarios.

### Phase 4 - Optional Historical Indexing Or Archival

Timing: Only after Stage 2.5 or when retrieval problems recur; separate learner approval required.

Scope:

1. Classify files as active, durable specification, historical evidence, or superseded proposal.
2. Prefer status banners or indexes before renaming paths.
3. Preserve links and Git history.
4. Do not delete artifacts merely to reduce file count.

## 14. Non-Goals

This audit does not:

- start Sprint-18 execution;
- count any drifted Sprint-18 teaching as execution or learning progress;
- change Sprint-18 roadmap content;
- create or modify a Sprint-18 learning project;
- close Sprint-16;
- create a Sprint-16 closure;
- complete Stage 2.5;
- authorize Stage 3;
- modify any learning-project repository;
- broadly rewrite governance without learner approval;
- remove repository-first governance;
- assume fewer files is automatically better;
- delete historical evidence;
- require immediate directory reorganization;
- treat learner roadmap acceptance as curriculum-quality assurance;
- transfer responsibility for the role-switch incident to the learner.

## 15. Final Verdict

The governance system is fundamentally usable and conceptually sound. Its core architecture—durable entry point, current state, task list, policies, roadmaps, reviews, coverage ledger, observation queue, templates, and handovers—supports the long-term mission.

The system is over-complex in specific active-operation areas:

- `CONTEXT.md` is carrying current state, history, startup instructions, and detailed project summaries simultaneously;
- `TODO.md` mixes tasks with standing constraints and curriculum backlog;
- startup guidance is duplicated and can require most of the repository;
- current status is copied into historical planning artifacts;
- roadmap acceptance, execution readiness, role switching, and explicit execution start are not governed by one canonical transition protocol.

The role-switch incident was primarily assistant execution drift. The Architect-to-Teacher restriction already existed. Governance design contributed through the missing explicit execution-start gate, ambiguous next-action wording, and excessive context fragmentation.

Immediate targeted changes are recommended:

1. add the explicit learner execution-start gate;
2. bind it to the existing role-switch boundary;
3. add authority verification to Teacher startup;
4. normalize Sprint-18 accepted-but-not-started wording.

A broader governance rewrite is not recommended now. After the P0 clarification, the next optimization should be a reviewed, behavior-preserving reduction of `CONTEXT.md`, `TODO.md`, and startup load. Historical indexing or archival should wait until Stage 2.5 is complete or retrieval problems provide stronger evidence.

Final verdict: Retain the architecture, fix the execution transition immediately after learner approval, simplify active state next, and defer broad restructuring.
