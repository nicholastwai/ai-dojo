# Track: Fine-tuning

**Source lesson** (`ai-engineering-from-scratch`): Phase 11 lesson 08
(Fine-Tuning with LoRA & QLoRA). This is genuinely thin coverage relative
to the rest of the source curriculum's depth on fine-tuning at the
pretraining level (Phase 10 has much more, e.g. instruction tuning, RLHF,
DPO) — those are out of scope here unless a project specifically needs
that depth; this track cares about applied fine-tuning, not training LLMs
from scratch.

Narrower and lower-priority than the other tracks for most freelance/
consulting work — prompting, RAG, and agents solve the majority of real
client problems. Worth reaching tier 1-2; go to tier 3 only if a specific
project genuinely needs it.

## Tier 1 — Understand
- When fine-tuning is the right tool vs when better prompting/RAG solves it
  more cheaply (this is the most commonly skipped judgment call).
- Full fine-tuning vs parameter-efficient methods (LoRA/QLoRA) at a
  conceptual level — what's actually being updated and why the
  efficient methods work almost as well for far less cost.
- What a training dataset for fine-tuning needs to look like, and why
  dataset quality matters more than model choice.

## Tier 2 — Build
- Fine-tune a small open model on a narrow, well-defined task (e.g. a
  specific output format or tone) and compare its performance against a
  well-prompted base model on the same eval set from the Evals track.

## Tier 3 — Ship
- Only pursue this tier if a real project's cost, latency, or quality
  requirements genuinely can't be met by prompting/RAG alone — fine-tune
  and deploy a model into that project.

## Signals you're stuck at tier 1
Reaching for fine-tuning as the default answer instead of the fallback.
