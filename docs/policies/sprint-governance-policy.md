# Sprint Governance Policy

## Purpose

This policy defines sprint design, execution, review, closure, roadmap ownership, and failed-sprint handling.

Use this file for:

- Specification Review;
- sprint roadmap creation or review;
- sprint execution boundary checks;
- sprint closure;
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
-> Sprint Execution
-> Sprint Review / Closure

Specification Review must occur before sprint execution begins.

Purpose:

- verify scope;
- verify deliverables;
- verify sprint size;
- prevent both oversized and undersized sprint design;
- ensure the sprint can produce meaningful capability growth within the approved stage.

## Task Granularity

Avoid both oversized and undersized learning tasks.

Sprint design should optimize for learning throughput, not minimum task size.

A sprint should be bounded enough to avoid long-context drift, but substantial enough to create meaningful capability growth.

Preferred sprint shape:

- one cohesive learning theme;
- two to four connected implementation tasks or implementation artifacts;
- at least one meaningful learner design decision;
- at least one required test addition or test update when code behavior or public API behavior changes;
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
- could reasonably be completed as a small task inside a larger sprint.

When a sprint appears undersized, the Teacher should increase implementation density within the same approved stage and theme instead of expanding into unrelated projects or topics.

For Stage 1: Rust Foundations, increasing implementation density may include:

- adding a closely related implementation step;
- adding or updating tests;
- requiring public API usage through integration tests;
- reinforcing ownership, borrowing, `Result`, module boundaries, visibility, or testing habits through code;
- adding a small end-to-end workflow inside the same project;
- requiring a clearer learner design decision before implementation.

Increasing sprint substance must not be used as justification to jump prematurely into unrelated topics such as blockchain concepts, Solana, Async Rust, Tokio, trait-heavy abstraction, generic-heavy refactor, or large architecture redesign.

## Roadmap Ownership

Sprint roadmap files are repository assets and require clear ownership and approval flow.

Default responsibility:

- Teacher Agents may draft sprint roadmaps.
- Architect Agents may review sprint roadmaps when governance risk, scope risk, stage-alignment risk, or workflow-separation risk exists.
- Codex may create or update sprint roadmap files only after receiving an explicit prompt forwarded by the learner.
- The learner has final human approval authority before roadmap repository updates are accepted.

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
