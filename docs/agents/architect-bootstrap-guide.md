# Architect Bootstrap Guide

> Status: Conditional Architect onboarding and narrative support.
>
> - This guide is not the canonical startup-bundle owner. Canonical startup bundles live in `AGENTS.md` Section 10.
> - The portable Architect creation artifact is `docs/agents/architect-standard-prompt.md`.
> - Load this guide only for Architect onboarding, authority ambiguity, governance-system review, failure-mode orientation, or another task-specific need.
> - Do not load this guide by default for routine governance work.
> - `CONTEXT.md` remains authoritative for current state.

## 1. Purpose

This guide explains why the governance system exists and gives a new Architect a compact mental model for operating it.

The repository supports long-term Rust + Blockchain employability through practical capability growth. Governance exists to keep that learning system coherent, transferable, and recoverable across chat resets, model changes, platform migrations, and agent replacement. It is not an end in itself.

Use the canonical sources below for enforceable rules. This guide provides orientation and historical failure context only; it must not override current state, policy, or an approved task.

## 2. Canonical Sources

Use the Canonical Rule Ownership table and Architect / governance startup bundle in `AGENTS.md`. This guide does not maintain another authority map.

Current state comes from `CONTEXT.md`; current actions come from `TODO.md`; historical roadmaps, reviews, handovers, and learning logs are conditional evidence.

## 3. Governance Philosophy

An Architect should use these principles as an orientation lens:

- optimize for learner capability rather than content completion or implementation speed;
- preserve important decisions and evidence in the repository instead of depending on chat memory;
- keep Governance Workflow separate from Learning Workflow;
- require explicit authority for role changes and learning execution;
- prefer small, evidence-driven changes over speculative governance expansion;
- distinguish system-execution failures from learner capability failures;
- treat historical artifacts as evidence, not as current-state authorities.

The normative versions of these principles live in `AGENTS.md` and the relevant policy files.

## 4. Architect Orientation

The Architect handles system-level coherence, not routine teaching or learning-project implementation. During onboarding or a governance-system review, establish:

1. what is currently true and authorized;
2. whether the issue is system governance or local teaching judgment;
3. which canonical file owns the relevant rule or state;
4. whether the problem is isolated or supported by recurring evidence;
5. the smallest durable action that resolves the problem without expanding scope;
6. what downstream prompt or handoff is required.

Detailed Architect responsibilities and restrictions live in `AGENTS.md` and `docs/agents/architect-standard-prompt.md`. Do not restate them as a competing rule set here.

## 5. Failure-Mode Orientation

Sprint-03 remains the clearest historical warning case. Its important system-level failure patterns were:

- teaching mode drift toward excessive guided discovery and architecture discussion;
- insufficient direct reinforcement of the active Rust learning objective;
- drift among Learning Workflow, Governance Workflow, and software-team assumptions;
- governance concerns ending as conversational reflection instead of repository-oriented assets;
- implementation responsibility shifting away from the learner toward Codex;
- recurring observations remaining passive instead of entering governance review.

These were primarily system-execution failures, not learner Rust-knowledge failures. Use them to recognize patterns, then apply the current canonical policies rather than treating this historical summary as an independent rule source.

Detailed historical evidence remains in `reviews/sprint-03-failure-review.md`.

## 6. When To Use This Guide

Use this guide when:

- onboarding a new Architect who needs system rationale and orientation;
- resolving Architect authority or role ambiguity;
- reviewing governance-system coherence or transferability;
- interpreting recurring failure patterns;
- explaining how the canonical governance sources fit together.

Do not use this guide as default input for:

- a routine, already-scoped governance update;
- Teacher sprint execution;
- Codex repository validation;
- sprint closure;
- current-state lookup.

For those workflows, use the matching startup bundle in `AGENTS.md` Section 10.

## 7. Onboarding Continuation

Create a new Architect with `docs/agents/architect-standard-prompt.md`, load the canonical Architect / governance bundle from `AGENTS.md`, and use `CONTEXT.md` for current state. Add this guide only when its narrative or failure-mode context is relevant.

When governance work requires repository action, follow the Governance Workflow and preserve final human review. Sprint execution, role switching, and learning-project implementation remain outside Architect authority unless the learner explicitly authorizes them.
