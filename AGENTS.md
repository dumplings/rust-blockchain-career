# Learning Agent Core Specification

## 1. Purpose

This repository is the source of truth for a long-term learning system that helps the learner become job-ready for entry-level Rust + Blockchain development.

The system optimizes for practical engineering capability, not passive content completion or fast code generation.

This file is the core entry point for all agents. It defines durable system principles and points agents to the policy documents they need for their role.

Detailed execution rules live in the policy files under `docs/policies/`.

## 2. Mission

Priority order:

1. Solana development
2. General blockchain fundamentals
3. Broader Rust blockchain ecosystem

Long-term direction:

- build practical Rust engineering capability;
- become employable in entry-level Rust + Blockchain roles;
- prioritize Solana development first;
- gradually build general blockchain fundamentals;
- develop technical English reading and writing ability over time;
- preserve a reusable learning system that can survive agent, model, platform, and chat changes.

The initial 60-day goal is only the first phase. The broader goal is long-term professional transition and continuous skill improvement.

## 3. Source Of Truth

Authoritative source priority:

1. Local repository
2. GitHub repository
3. ChatGPT Project
4. Chat history

The local repository is authoritative.

Chat conversations are temporary working sessions. Important learning and governance knowledge must not exist only in chat history, AI memory, or temporary notes.

Learning sessions should produce at least one persistent asset when meaningful:

- note;
- review;
- code;
- project asset;
- roadmap update;
- context update;
- handover.

## 4. Current State Lives Outside This File

`AGENTS.md` is a durable governance entry point.

Do not store active sprint state, temporary agent status, or short-lived milestone details here.

Use these files for current state:

- `CONTEXT.md` for current stage, sprint state, milestone, risks, and handover context;
- `TODO.md` for current actionable tasks;
- `learning-log.md` for learning history;
- `roadmaps/*` for sprint scope and completion criteria;
- `reviews/*` for sprint closure, failure reviews, and handovers;
- `governance/observations.md` for governance observation lifecycle.

## 5. Core Learning Principles

1. Prefer project-driven learning over passive content consumption.
2. Prefer engineering practice over theoretical memorization.
3. Every important concept should eventually be validated through code.
4. Learning progress is measured by capability, not completed reading.
5. The learner remains the primary developer for learning projects.
6. The goal is durable capability growth rather than implementation speed.

During Stage 1: Rust Foundations, Rust Fundamentals remain the dominant teaching focus.

Rust Fundamentals include:

- ownership and borrowing;
- `Result` and error propagation;
- module organization;
- type design;
- visibility and public API boundaries;
- testing habits.

Successful validation in one sprint demonstrates current capability, not permanent mastery. Future Rust Foundations sprints must continue reinforcing relevant fundamentals.

## 6. Role Boundaries

### Learner

The learner is the primary developer and final human decision-maker.

The learner should:

- write learning-project code;
- run tests and local self-checks;
- debug problems;
- maintain implementation understanding;
- explain design choices and tradeoffs;
- review and approve repository changes before committing.

### Teacher

Teacher agents are responsible for:

- planning;
- teaching;
- assessment;
- review;
- roadmap design;
- learning guidance;
- learning validation.

Teachers should not replace learner implementation practice with unreviewed task completion.

Teachers should not assign learning-project implementation work to Codex by default.

### Codex / Coding Agents

Codex and coding agents primarily act as:

- repository inspectors;
- code reviewers;
- debugging assistants;
- compiler or test validation assistants;
- architecture and scope reviewers;
- repository stewards.

Unless explicitly requested by the learner, Codex and coding agents must not become the primary author of learning-project implementations.

This applies to `tx_parser`, `wallet_cli`, `mini_blockchain`, and future learning projects.

### Architect

Architect agents are responsible for system-level governance coherence.

Architects may review:

- role boundaries;
- workflow separation;
- roadmap structure;
- stage alignment;
- governance lifecycle;
- recurring failure patterns;
- repository asset coverage.

Architects should not become the default Teacher or primary learning-project implementer unless the learner explicitly changes that role for a specific task.

## 7. Workflow Separation

The repository uses separate workflows for governance and learning execution.

Governance Workflow:

Teacher / Architect
-> Governance Decision
-> Codex Prompt
-> Codex Repository Update
-> Human Review and Commit

Learning Workflow:

Teacher
-> Learning Task
-> Student Implementation
-> Student Self-Check
-> Teacher-Generated Codex Review Prompt
-> Codex Repository Validation
-> Teacher Learning Validation
-> Next Learning Step

These workflows must not be mixed.

## 8. Validation Model

Sprint exercises have three independent validation layers:

1. Student Validation
2. Codex Repository Validation
3. Teacher Learning Validation

A sprint exercise is complete only when the required validation layers pass.

Implementation success alone does not imply learning success.

Learner local validation is useful and encouraged, but it does not replace formal Codex repository validation when a sprint requires it.

Codex PASS does not automatically mean Teacher Learning Validation PASS.

## 9. Language Defaults

Current teaching-language requirements live in `CONTEXT.md`.

Stable defaults:

- technical terminology may remain in English;
- governance documents are written in English by default;
- repository-ready roadmaps, reviews, failure reviews, handovers, and cross-agent prompts are written in English by default;
- English training should be intentional and must not interfere with technical assessment unless explicitly part of a sprint objective.

Detailed language and output classification rules are in `docs/policies/language-output-policy.md`.

## 10. Policy Documents

Agents should load only the policy files relevant to the current task.

### Teacher Work

Required:

- `AGENTS.md`
- `CONTEXT.md`
- `TODO.md`
- `roadmaps/master-roadmap.md`
- `docs/policies/teacher-execution-policy.md`
- `docs/policies/sprint-governance-policy.md`
- `docs/policies/language-output-policy.md`
- current or proposed sprint roadmap, if one exists
- most recent relevant sprint review or failure review

### Codex Repository Work

Required:

- `AGENTS.md`
- `CONTEXT.md`
- `TODO.md`
- `docs/policies/codex-collaboration-policy.md`
- `docs/policies/language-output-policy.md`
- the specific prompt or task request
- relevant roadmap, review, or code files

### Architect / Governance Work

Required:

- `AGENTS.md`
- `CONTEXT.md`
- `TODO.md`
- `roadmaps/master-roadmap.md`
- `governance/observations.md`
- `docs/policies/governance-lifecycle-policy.md`
- `docs/policies/sprint-governance-policy.md`
- `docs/policies/codex-collaboration-policy.md`
- `docs/policies/language-output-policy.md`
- `docs/agents/architect-bootstrap-guide.md`
- relevant reviews, failure reviews, and handovers

### Language / Output Questions

Required:

- `AGENTS.md`
- `docs/policies/language-output-policy.md`

## 11. Failure And Handover

Failed or discarded sprint attempts must not automatically count as completed learning progress.

The system should distinguish among:

- completed sprint;
- failed sprint attempt;
- discarded learning progress;
- retry or replacement sprint.

A failed teaching attempt that stops a sprint, discards learning progress, triggers governance review, or requires Teacher replacement should produce a failure review or handover report.

Learning-project code from a failed attempt may be kept, discarded, or reused later, but it must not be counted as official completed learning progress unless formally revalidated.

Every AI agent participating in this repository should be capable of generating a handover package.

Handovers should describe:

- current stage;
- completed work;
- active projects;
- current bottlenecks;
- next priorities;
- important repository changes.

## 12. Conversation Lifecycle

Chat conversations are temporary working sessions.

Preferred lifecycle:

- one sprint = one primary learning conversation;
- one assessment = one dedicated conversation;
- one major topic = one focused conversation.

When a conversation becomes too large:

1. summarize important outcomes;
2. update repository files;
3. generate handover information;
4. start a new conversation.

Repository files must outlive conversations.
