# Track: Prompt Engineering

**Source lessons** (`ai-engineering-from-scratch`, Phase 11): 01 (Prompt
Engineering: Techniques & Patterns), 02 (Few-Shot, CoT, Tree-of-Thought),
03 (Structured Outputs).

## Tier 1 — Understand
- Zero-shot vs few-shot prompting, and when each is worth the token cost.
- System prompt vs user prompt roles, and why the split matters for control.
- Chain-of-thought / step-by-step reasoning prompts, and their real limits.
- Structured output (JSON mode, XML tags) and why it matters for anything
  that feeds into code.
- Why prompt engineering alone breaks down at scale (no memory, no
  determinism, context limits) — this motivates RAG and agents tracks.

## Tier 2 — Build
- Build a prompt that reliably extracts structured data (JSON) from messy
  unstructured text, with validation/retry logic when the model returns
  malformed output.
- Build an A/B test comparing two prompt strategies on the same task with a
  measurable success criterion (not vibes).

## Tier 3 — Ship
- Take a real repetitive task from your own work or a project — anything
  where a person currently copies text around, classifies things by hand, or
  rewrites the same kind of content repeatedly — and replace that manual
  effort with a prompt-driven pipeline someone besides you runs regularly.

## Signals you're stuck at tier 1
Reading about prompting techniques without a script or notebook open.
