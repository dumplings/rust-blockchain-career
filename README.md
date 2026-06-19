# Rust Blockchain Career

A personal learning repository for transitioning into Rust + Blockchain development.

## Goal

Become job-ready for entry-level Rust + Blockchain development within 60 days.

Primary direction:

1. Solana development;
2. General blockchain fundamentals;
3. Broader Rust blockchain ecosystem.

## Repository Role

This repository is the source of truth for my Rust + Blockchain learning system.

It is designed for both humans and AI agents.

Chat history is temporary.
This repository is persistent.

## Structure

```text
docs/        Durable policies, agent startup docs, and human runbooks
notes/        Study notes and topic summaries
roadmaps/     Learning roadmaps and sprint plans
reviews/      Sprint reviews and progress evaluations
templates/    Reusable templates for logs, notes, specification reviews, sprint reviews, and handovers
assets/       Images, diagrams, screenshots, and exported materials
```

## Projects

Learning projects are maintained as separate repositories when appropriate.

Planned or existing projects:

- `tx_parser`
- `wallet_cli`
- `mini_blockchain`
- `solana_counter`

## For Humans

This repository records:

- learning goals;
- current progress;
- study notes;
- sprint reviews;
- roadmap documents;
- AI collaboration rules;
- handover materials.

The goal is not only to learn Rust and blockchain, but also to preserve reusable learning assets over time.

## For AI Agents

Before helping with this project, read these files first:

1. `README.md` — understand what this repository is;
2. `AGENTS.md` — understand the core system principles and policy map;
3. `CONTEXT.md` — understand the current learning state;
4. `TODO.md` — understand the current sprint tasks;
5. `learning-log.md` — understand recent progress.

Then read the role-specific policy documents referenced by `AGENTS.md`.

Do not rely only on chat history.

The local repository is the source of truth.
ChatGPT Project files are readable copies and may be outdated.

## Handover Protocol

When a new AI agent takes over this learning system, it should:

1. Read `README.md`, `AGENTS.md`, `CONTEXT.md`, `TODO.md`, and `learning-log.md`;
2. Read the policy documents relevant to its role;
3. Identify the current sprint and current bottleneck;
4. Avoid redesigning the whole system unless necessary;
5. Continue from the existing roadmap and learning assets;
6. Update files after important learning sessions or sprint reviews.

The purpose of this system is to make the learning process transferable across different chats, models, agents, and tools.
