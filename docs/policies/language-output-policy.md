# Language And Output Policy

## Purpose

This policy defines language expectations and output categories for the learning system.

The goal is to support effective learning while keeping repository assets interoperable across ChatGPT, Codex, Claude, Gemini, and future agents.

## Documentation Language

Governance documents should be written in English whenever practical.

This includes:

- `README.md`;
- `AGENTS.md`;
- `CONTEXT.md`;
- `TODO.md`;
- roadmap documents;
- review documents;
- handover documents;
- reusable templates;
- policy documents.

Reason:

Governance files are intended to be maintained by multiple AI systems over time. English improves cross-agent interoperability.

## Learning Notes Language

Learning notes may be written in:

- Chinese;
- English;
- mixed Chinese and English.

Use whichever language maximizes learning effectiveness.

Technical terminology should remain in English whenever useful.

Examples:

- Ownership
- Borrowing
- Lifetime
- Trait
- Iterator
- Async
- Tokio
- UTXO
- PDA
- Account Model

Learning effectiveness is more important than language purity.

Do not translate technical concepts merely for consistency.

## Teaching And Assessment Language

Language should follow the learning objective.

Do not introduce English requirements unless English itself is the skill being trained.

Examples:

- When assessing Rust knowledge, evaluate Rust knowledge.
- When assessing blockchain understanding, evaluate blockchain understanding.
- When practicing English communication, evaluate English communication.

Avoid mixing technical assessment and language assessment unless explicitly requested.

Current language requirements should be checked in `CONTEXT.md` before teaching begins.

Current language requirements are recorded in `CONTEXT.md`. When `CONTEXT.md` requires Chinese technical teaching:

- technical learning must be conducted primarily in Chinese;
- technical terminology should remain in English when useful;
- English training is a secondary objective and should not interfere with technical evaluation.

Teachers must conduct instruction primarily in Chinese unless English communication is an explicit sprint objective.

Teaching language is not a matter of teacher preference.

English training should be intentional rather than accidental.

## Output Classification

### Teaching Content

Purpose:
Direct instruction during learning execution.

Language:
Chinese.

Repository Asset:
Usually no.

### Teacher Learner Discussion

Purpose:
Clarification, feedback, short learning interaction.

Language:
Chinese.

Repository Asset:
No.

### Governance Documents

Purpose:
Persistent repository governance.

Examples:

- `AGENTS.md`;
- `CONTEXT.md`;
- `roadmaps/master-roadmap.md`;
- `governance/observations.md`;
- policy documents.

Language:
English.

Repository Asset:
Yes.

### Codex Prompts

Purpose:
Executable prompts sent to Codex.

Language:
English.

Repository Asset:
Optional.

### Takeover Assessment Reports

Purpose:
Agent takeover validation.

Language:
English.

Repository Asset:
Recommended.

### Specification Review Reports

Purpose:
Sprint specification review before roadmap creation.

Language:
English.

Repository Asset:
Recommended.

### Sprint Roadmaps

Purpose:
Sprint scope, milestones, deliverables, completion criteria.

Language:
English.

Repository Asset:
Yes.

### Sprint Reviews And Closure Packages

Purpose:
Sprint completion, validation, handover.

Language:
English.

Repository Asset:
Yes.

### Failure Reviews

Purpose:
Document failed or terminated sprint execution.

Language:
English.

Repository Asset:
Yes.

## Cross-Agent Prompt Language

When an agent produces a prompt intended to be copied by the learner to another agent, the prompt should be written in English by default.

This applies to prompts for:

- Codex;
- Teacher Agents;
- Architect Agents;
- Review Agents;
- Takeover Agents;
- future AI agents participating in the learning system.

Learner-facing explanation before or after the prompt may be written in Chinese when that improves clarity.

Repository-ready assets should remain English by default.

Examples include:

- sprint roadmaps;
- specification review reports;
- sprint review or closure packages;
- failure reviews;
- governance update requests;
- Codex repository update prompts.

The goal is cross-agent interoperability without forcing all learner-facing discussion into English.

## Interaction Efficiency

Default communication style:

- concise;
- direct;
- action-oriented.

When recommending next steps, Teachers should provide:

- decision;
- rationale;
- next action.

Avoid:

- repeated justification;
- excessive hedging;
- unnecessary philosophical discussion;
- repeatedly revisiting previously accepted decisions.

If governance review is not being requested, Teachers should prefer execution over extended discussion.

The learner may interrupt and request deeper analysis when needed.
