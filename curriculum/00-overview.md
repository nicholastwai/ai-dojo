# Curriculum Overview

This repo does not contain its own lessons. Technical content comes from
[`ai-engineering-from-scratch`](https://github.com/rohitg00/ai-engineering-from-scratch)
— an open, actively maintained, 503-lesson curriculum, credited in full in
the main README. This file exists to do the thing that curriculum doesn't:
say which of its 503 lessons are actually in scope for this track, and hold
a bar (the tier system) that its own lesson quizzes don't enforce.

| Tier | Name | Definition |
|---|---|---|
| 1 | Understand | You can explain it correctly, from scratch, without notes, including *why* it works and when it fails. |
| 2 | Build | You've built a working example yourself — not copy-pasted — and can modify it without help. |
| 3 | Ship | You've used it in something a real user (even one person) actually relies on. |

## One-time setup

Install the external curriculum's agent skills once, from inside this repo:

```
npx skills add rohitg00/ai-engineering-from-scratch
```

This adds `/start-learning`, `/learn`, and `/course-guide <topic>` to your
agent. `/start-learning` runs a placement quiz — take it. With a data
science / ML background, expect to place well past Phase 0-3 (setup, math
foundations, ML fundamentals, deep learning core); don't manually skip
without taking the quiz, since it calibrates more precisely than a guess.

## In-scope phases

Only these phases are relevant to this track. Everything else in the
source curriculum is real, good material — just not on the path to
AI/LLM engineering and agent freelance work, and pulling from it is how
tutorial hell happens.

| Phase | Why it's in scope |
|---|---|
| **11 — LLM Engineering** | Prompt engineering, RAG, LoRA fine-tuning, function calling, evals, guardrails, MCP. Core material for tracks 1, 2, 4, 5. |
| **13 — Tools & Protocols** | MCP and A2A in depth — the interop layer agents actually run on. Core material for track 3. |
| **14 — Agent Engineering** | The agent loop, memory, planning, every major framework, production runtimes, eval-driven agent development, multi-session handoff. The single most relevant phase to this track's goal — core material for tracks 3, 6, 7. |
| **5 — NLP** *(selectively)* | Only: chunking strategies for RAG, LLM evaluation frameworks (RAGAS/DeepEval). Not the other 27 lessons. |
| **19 — Capstone Projects** *(selectively)* | 17 end-to-end products + 9 deep-build tracks (confirmed via ROADMAP.md). Two products (Production RAG Chatbot for a regulated vertical, Multimodal Document QA) are close to SMB-shaped as-is; the rest are strong technical scaffolding built around developer/research use cases — see `curriculum/07-smb-capstones.md` for the specific mapping. Don't work this phase front-to-back; go in with a target archetype already chosen. |

**Explicitly out of scope** unless a specific real project needs it: Phase
4 (Computer Vision), Phase 6 (Speech & Audio), Phase 8 (Generative AI —
image/video/3D), Phase 9 (Reinforcement Learning), Phase 12 (Multimodal /
embodied VLAs). These are excellent, but going through them "for
completeness" is the tutorial-hell trap this repo exists to prevent.

## How a lesson maps to a tier

- **Understand** = the source lesson's own "Concept" + "Build It" beats,
  completed, including its quiz.
- **Build** = **not** the source lesson's own exercise. It's using what
  the lesson taught on something from `USER.md` — a real project, not the
  lesson's toy example.
- **Ship** = that real thing is actually used by someone other than you.

## Tracks

Each track below still owns its own tier definitions and real-project
framing (see `curriculum/01` through `07`) — those are this repo's
contribution. Track content maps to the in-scope phases above; tracks 1-2
mostly draw from Phase 11, track 3 from Phases 13-14, track 4 from Phase 11
+ selected Phase 5, track 5 has thinner source coverage (fine-tuning gets
one lesson in Phase 11 — go deeper only if a project needs it), track 6 is
thin in the source curriculum too (most "production" content is folded
into Phase 14's later lessons), and track 7 is different in kind rather
than missing from the source: Phase 19's 17 end-to-end capstones (plus
phase-ending capstones in 13 and 14) prove technical range on complete
systems, but none are framed around a specific external business's
problem or paired with outreach — track 7 supplies that framing, using
whichever source capstone fits as the technical build.

1. **Prompt engineering** — foundational, fast to reach tier 3, underpins everything else.
2. **RAG (retrieval-augmented generation)** — grounding LLMs in real data.
3. **Agents & tool use** — the highest-leverage skill for freelance/consulting work right now.
4. **Evals** — the skill that separates people who ship reliable systems from people who ship demos.
5. **Fine-tuning** — narrower, useful, not always necessary — good to reach tier 1-2 and go deeper only if a project needs it.
6. **Deployment / productionizing** — turning a working notebook into something that runs unattended.
7. **SMB capstones (go-to-market)** — not a new skill; where you point the first six at a real business problem, producing a portfolio piece that doubles as freelance outreach. Gated behind reaching "build" tier on Agents and Evals.

## Principle: depth over breadth

It is better to have tracks 1-3 at tier 3 and tracks 4-6 at tier 1 than to
have all six tracks at tier 1. Employers and clients pay for tier 3.
