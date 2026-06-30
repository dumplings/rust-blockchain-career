# Sprint Governance Policy

## Purpose

This policy defines sprint design, execution, review, closure, roadmap ownership, learning density, project continuation, and failed-sprint handling.

Use this file for:

- Specification Review;
- sprint roadmap creation or review;
- sprint execution boundary checks;
- sprint closure;
- learning-density and project-continuation decisions;
- failed or discarded sprint attempts;
- current-state synchronization.

## Sprint-Based Learning

Learning progress is organized around sprints rather than calendar weeks.

A sprint ends when its learning objectives and required validation layers are completed.

Sprint duration may vary depending on:

- learning speed;
- project complexity;
- personal schedule.

Progress is measured by outcomes and capability growth, not elapsed time.

## Sprint Lifecycle

Preferred lifecycle:

Sprint Review
-> Specification Review
-> Sprint Roadmap
-> Roadmap Acceptance / Accepted But Not Started
-> Explicit Learner Start Command
-> Sprint Execution
-> Sprint Review / Closure

Specification Review must occur before sprint execution begins.

Purpose:

- verify scope;
- verify deliverables;
- verify sprint size;
- verify learning density;
- evaluate project continuation when the same project has been used across multiple sprints;
- prevent both oversized and undersized sprint design;
- ensure the sprint can produce meaningful capability growth within the approved stage.

## Sprint Workflow Contracts

Each sprint phase should have a clear purpose, owner, decision boundary, and output.

Agents may use judgment inside these boundaries, but they should not leave the learner to infer missing workflow steps or translate informal recommendations into operational requests.

### Specification Review

Purpose:
Evaluate the next candidate sprint before roadmap creation or execution.

Primary owner:
Teacher, with Architect review when scope, stage alignment, workflow separation, or governance consistency is uncertain.

Required work:

- confirm the current stage, active sprint state, and any prior outcome relevant to the candidate direction;
- use current state, curriculum progress, and stage-relevant coverage artifacts as the continuity baseline;
- load a previous roadmap, closure, failure review, handover, or learning log only when candidate scope, unresolved coverage, project continuation, or authority ambiguity requires that evidence;
- identify the candidate sprint direction;
- explain why the direction fits the current stage and long-term roadmap;
- assess expected learning density, not only sprint size;
- when continuing an existing learning project, assess the remaining project learning value;
- define proposed scope and explicit non-goals;
- identify expected learner implementation work;
- identify required tests, validation layers, and repository validation targets;
- surface risks, ambiguities, and decisions needed before roadmap creation;
- state whether execution is authorized, not authorized, or awaiting learner / Architect approval.

Required output:
A Specification Review report or cross-agent action request that is complete enough for the learner to forward without reconstructing missing context.

A Specification Review recommendation does not authorize sprint execution by itself.

### Sprint Roadmap

Purpose:
Convert an approved sprint direction into an executable learning plan.

Primary owner:
Teacher, with Architect review when governance risk exists.

Required work:

- define sprint identity, objective, stage alignment, scope, and non-goals;
- define how the sprint maintains sufficient learning density;
- define checkpoint sequence and expected learner decisions;
- define implementation artifacts and testing requirements;
- define Student Validation, Codex Repository Validation, and Teacher Learning Validation requirements;
- define completion criteria.

Required output:
A roadmap draft or repository-ready roadmap update prompt.

Roadmap creation or repository update requires learner approval.

### Sprint Execution Start Gate

Roadmap acceptance creates an accepted-but-not-started state by default.

Accepted-but-not-started is not active sprint execution. Sprint execution begins only after the learner gives an explicit command to start execution or checkpoint work.

Valid explicit start commands include:

- “Start Sprint-18 execution now.”
- “Begin Teacher mode now.”
- “Start Checkpoint 1 now.”
- equivalent clear learner wording.

The learner may combine roadmap acceptance and execution start in one message only when the message unambiguously states both decisions.

None of the following authorizes execution by itself:

- accepting a roadmap;
- creating or updating roadmap or current-state files;
- placing execution in `TODO.md` as the next task;
- writing “next permitted action” or equivalent readiness wording;
- completing the Teacher startup checklist.

Without an explicit learner start command, an agent may summarize readiness and ask whether the learner wants to begin. The agent must not start teaching, issue checkpoint work, or treat the sprint as active.

This gate applies especially when an agent would switch from Architect / governance mode into Teacher / learning execution mode. Existing role boundaries in `AGENTS.md` remain authoritative.

### Sprint Execution

Purpose:
Teach and validate the approved roadmap through checkpoint-based learning.

Primary owner:
Teacher for teaching and validation; learner for implementation.

Required work:

- confirm that the Sprint Execution Start Gate has been satisfied;
- teach the checkpoint concept and implementation boundary;
- keep the learner as the primary implementer;
- review source-level work before moving on when the checkpoint requires it;
- keep scope aligned with the approved roadmap;
- generate Codex validation prompts when formal repository validation is required.

Required output:
Checkpoint instructions, learner tasks, review feedback, validation prompts, and learning validation decisions as needed.

### Sprint Closure

Purpose:
Decide whether the sprint counts as completed learning progress and preserve the outcome.

Primary owner:
Teacher, with Codex repository validation and learner review.

Required work:

- confirm Student Validation;
- confirm Codex Repository Validation;
- complete Teacher Learning Validation;
- record completed work, capability growth, remaining gaps, scope compliance, and governance lessons;
- identify recommended next actions without authorizing the next sprint by implication.

Required output:
A closure package or sprint review that is repository-ready when the sprint outcome should be preserved.

### State Synchronization

Purpose:
Keep current-state files aligned with durable sprint outcomes.

Primary owner:
Teacher or Architect for deciding what needs synchronization; Codex for repository updates when prompted by the learner.

Required work:

- identify which current-state files would mislead future agents if left unchanged;
- keep state updates scoped to meaningful milestones;
- avoid mixing governance repository updates with separate learning-project validation.

Required output:
A complete Codex prompt when repository updates are required.

## Sprint Size, Learning Density, And Project Continuation

Avoid both oversized and undersized learning tasks.

Sprint design should optimize for learning throughput, not minimum task size.

Sprint size and learning density are related but separate.

A sprint should be bounded enough to avoid long-context drift, but substantial enough to create meaningful capability growth.

Learning density means the sprint contains enough meaningful concepts, implementation work, design decisions, and explanation requirements to justify a dedicated learning cycle.

A sprint may be somewhat larger when its theme is cohesive, its non-goals are clear, and it prevents a learning thread from being split into multiple low-density follow-up sprints.

Preferred sprint shape:

- one cohesive learning theme;
- two to four connected implementation tasks or implementation artifacts;
- at least one meaningful learner design decision;
- at least one required test addition or test update when code behavior or public API behavior changes;
- one clear explanation or design-reasoning target;
- one final validation cycle.

Preferred workflow:

Learn
-> Implement
-> Test
-> Review

before introducing unrelated major topics.

A sprint is likely undersized if it:

- contains only a tiny mechanical code change;
- requires little or no teaching;
- includes no meaningful learner decision;
- adds no new test or test update when behavior or public API expectations changed;
- ends with mostly review or discussion and very little implementation;
- continues an existing project with only isolated cleanup, style polish, or small test adjustments;
- could reasonably be completed as a small task inside a larger sprint.

When a sprint appears undersized, the Teacher should increase learning density within the same approved stage and theme instead of expanding into unrelated projects or topics.

For Stage 1: Rust Foundations, increasing learning density may include:

- adding a closely related implementation step;
- adding or updating tests;
- requiring public API usage through integration tests;
- reinforcing ownership, borrowing, `Result`, module boundaries, visibility, or testing habits through code;
- adding a small end-to-end workflow inside the same project;
- requiring a clearer learner design decision before implementation.

Increasing sprint substance must not be used as justification to jump prematurely into unrelated topics such as blockchain concepts, Solana, Async Rust, Tokio, trait-heavy abstraction, generic-heavy refactor, or large architecture redesign.

Tests may support learning density, but test expansion should not be used as filler. When the learner has explicitly lower priority for testing workload, tests should validate the sprint's core contract without becoming the main learning burden.

## Project Continuation And Exhaustion

When the same learning project has been used across multiple sprints, the next Specification Review should assess whether continuing the project still creates meaningful learning value.

Continuing the same project is appropriate when:

- high-value concepts remain unpracticed or weak;
- the next work reinforces the active stage objective;
- the project still supports meaningful learner implementation and design decisions;
- the remaining work can be organized as a cohesive sprint rather than scattered cleanup.

The Teacher should recommend a final consolidation sprint when:

- several related remaining issues can be resolved together;
- continuing the project one more time would produce meaningful capability growth;
- splitting the remaining issues would create low-density follow-up sprints;
- the project is close to exhausting its value for the current stage.

The Teacher should recommend leaving the project when:

- remaining work is mostly polish, small isolated fixes, broad test expansion, or feature accumulation;
- continuing would mainly preserve momentum rather than teach a meaningful capability;
- a new project, stage exit assessment, or stage transition would produce better learning density;
- the project has already served its role for the current stage.

After a project is declared sufficiently exhausted for a stage, future sprints should not continue it by default.

Revisiting an exhausted project requires an explicit new high-value reason, such as a stage-appropriate assessment finding, a new stage objective, or a clearly justified integration need.

## Roadmap Ownership

Sprint roadmap files are repository assets and require clear ownership and approval flow.

Default responsibility:

- Teacher Agents may draft sprint roadmaps.
- Architect Agents may review sprint roadmaps when governance risk, scope risk, stage-alignment risk, or workflow-separation risk exists.
- Codex may create or update sprint roadmap files only after receiving an explicit prompt forwarded by the learner.
- The learner has final human approval authority before roadmap repository updates are accepted.

### Learner Approval And Roadmap Quality Responsibility

The learner has final human authority over repository updates, roadmap acceptance, and sprint start. These are distinct decisions unless the learner's message unambiguously combines them.

Roadmap acceptance by itself creates the accepted-but-not-started state defined by the Sprint Execution Start Gate. It does not authorize sprint execution.

Learner approval does not require the learner to perform detailed curriculum-design quality assurance or independently detect whether a roadmap is too dense, too broad, poorly sequenced, or pedagogically miscalibrated.

Teacher and Architect agents remain responsible for:

- scope calibration;
- learning density;
- stage alignment;
- checkpoint boundaries and sequencing;
- implementation and testing expectations;
- validation design.

The learner may provide lightweight direction confirmation rather than reviewing every roadmap detail.

If overload, underload, or miscalibration becomes visible only during execution, treat that as normal learning-system feedback. The Teacher should adjust at a checkpoint boundary through narrowing, reinforcement, deferral, or splitting, and should request a governance decision when the required change would materially alter accepted sprint scope.

Approval must not be used to shift responsibility for roadmap-quality problems onto the learner.

A Teacher-generated roadmap draft or Codex prompt does not by itself mean the roadmap has been approved for repository creation.

Preferred workflow:

Teacher Agent
-> Roadmap Draft
-> Learner and/or Architect Review and Approval
-> Teacher or Architect Codex Prompt
-> Learner Forwards Prompt to Codex
-> Codex Repository Update
-> Learner Review and Commit

The Architect should not become the default sprint roadmap author during normal learning execution.

The Architect should intervene when roadmap scope, stage alignment, workflow separation, or governance consistency is uncertain.

## Sprint Closure

Sprint closure should preserve:

- sprint status;
- completed objectives;
- unfinished objectives;
- capability growth;
- remaining bottlenecks;
- validation results;
- governance lessons;
- recommended next actions.

A normal sprint closure should record the three validation layers:

1. Student Validation
2. Codex Repository Validation
3. Teacher Learning Validation

Closure packages are repository assets and should be written in English by default.

## Failed Or Discarded Sprint Attempts

If a sprint attempt is stopped due to teaching execution failure, the failed attempt must not automatically count as completed learning progress.

The system should distinguish among:

- completed sprint;
- failed sprint attempt;
- discarded learning progress;
- retry or replacement sprint.

A failed teaching attempt that stops a sprint, discards learning progress, triggers governance review, or requires Teacher replacement should produce a failure review or handover report.

Learning-project code from a failed attempt may be kept, discarded, or reused later, but it must not be counted as official completed learning progress unless formally revalidated.

Do not automatically reopen a failed or terminated sprint.

A future sprint should define a new scope rather than copying a failed sprint attempt.

## State Synchronization

Meaningful sprint or governance milestones may require updates to:

- `CONTEXT.md`;
- `TODO.md`;
- `learning-log.md`;
- `roadmaps/*`;
- `reviews/*`;
- `governance/observations.md`;
- templates or docs when reusable process assets change.

Avoid updating governance files for every study session.

Update current-state files when outdated state would mislead future agents.
