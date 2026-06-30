# Language And Output Policy

## Purpose

This policy separates learner-facing conversation language from persistent artifact language.

The default model is:

- communicate with the learner in Chinese;
- preserve repository governance and cross-agent artifacts in English;
- keep professional technical terminology in English when useful.

An output's structure does not determine its language. A structured takeover verdict written in a browser chat is still learner-facing conversation unless the agent is explicitly asked to produce a repository-ready report.

## Default Language Matrix

| Output | Default language | Repository asset |
| --- | --- | --- |
| Learner-facing Teacher conversation | Chinese | No |
| Learner-facing Architect conversation | Chinese | No |
| Learner-facing Codex explanation | Chinese | No |
| Technical teaching and technical assessment | Chinese | Usually no |
| Learning notes | Chinese, English, or mixed | Optional |
| Repository-ready governance document | English | Yes |
| Sprint roadmap, closure, failure review, or handover | English | Yes |
| Repository-ready takeover assessment | English | Recommended |
| Cross-agent prompt, including Codex prompt | English | Optional |

The learner may explicitly request another language for a specific conversation or artifact.

## Learner-Facing Conversation

All browser-based Teacher and Architect windows should conduct learner-facing conversation in Chinese by default.

This includes:

- startup and takeover responses;
- readiness reports;
- governance discussion;
- decisions and recommendations explained to the learner;
- clarification and follow-up questions;
- checkpoint teaching and feedback;
- summaries of Codex repository evidence.

English labels such as `READY`, `ACCEPT`, `PASS`, `BLOCKED`, or technical terms may remain in English, but their explanation should be in Chinese.

Do not switch learner-facing conversation to English merely because:

- the attached repository files are written in English;
- the output uses a formal heading or verdict;
- the topic is governance;
- the agent is producing a structured response;
- a cross-agent prompt will be included later in the response.

## Teaching And Assessment

Technical teaching and assessment must be conducted primarily in Chinese unless English communication is an explicit learning objective.

Important professional terminology should be introduced using:

`English professional term (Chinese professional translation)`

After introduction, the English term may be used alone when clear. Do not force awkward translations.

Technical knowledge and English ability must not be assessed together unless the sprint explicitly includes English training.

## Learning Notes

Learning notes may use Chinese, English, or mixed language according to learning effectiveness. Technical terminology may remain in English.

## Persistent Repository Assets

Repository-ready governance assets should be written in English by default for cross-agent interoperability.

This includes:

- `README.md`, `AGENTS.md`, `CONTEXT.md`, and `TODO.md`;
- policies, templates, and runbooks when their established format requires it;
- Master Roadmap and sprint roadmaps;
- specification reviews;
- sprint closures and failure reviews;
- governance decisions and observations;
- handovers;
- formal takeover assessment documents intended for repository storage.

A browser takeover response is not automatically a repository-ready takeover assessment. If the learner later asks to persist it, produce the repository asset in English while continuing the surrounding conversation in Chinese.

## Cross-Agent Prompts

Prompts intended for Teacher, Architect, Codex, Review Agent, or another AI role should be written in English by default.

Learner-facing explanation before or after the prompt should remain in Chinese. A response may therefore contain Chinese discussion plus an English copy-ready prompt.

## Current Requirements

Check `CONTEXT.md` for current learner-specific overrides, teaching language, terminology expectations, and English-training objectives.

In the absence of an explicit override:

- learner-facing conversation is Chinese;
- repository-ready governance assets are English;
- cross-agent prompts are English;
- technical terminology may remain in English.

## Interaction Efficiency

Communication should remain concise, direct, and action-oriented. Language selection must not create duplicated bilingual reports unless the learner explicitly requests both versions.
