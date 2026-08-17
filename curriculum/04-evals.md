# Track: Evals

**Source lessons** (`ai-engineering-from-scratch`): Phase 11 lesson 10
(Evaluation & Testing); Phase 5 lesson 27 (LLM Evaluation: RAGAS, DeepEval,
G-Eval); Phase 14 lesson 30 (Eval-Driven Agent Development) once you're
also in the Agents track.

The track most self-taught AI engineers skip — and the one that separates
"I made a demo" from "I made something reliable enough to charge for."

## Tier 1 — Understand
- Why "it looked good when I tried it" isn't evidence of anything at scale.
- The difference between a golden dataset (known right answers) and
  LLM-as-judge evaluation, and the failure modes of each.
- Precision/recall-style thinking applied to LLM outputs (not just accuracy).
- Regression testing for prompts: why a prompt change that fixes one case
  can silently break three others.

## Tier 2 — Build
- Build a small golden dataset (20-50 examples) for a real task and a script
  that scores a prompt/pipeline against it automatically.
- Use that eval to compare two versions of the same prompt/pipeline and show
  a measurable difference — not a guess.

## Tier 3 — Ship
- Wire evals into an actual pipeline (yours or a client's) so that changes
  get scored before they go live, not after something breaks.

## Signals you're stuck at tier 1
Every "is this good?" question gets answered by re-reading the output
yourself instead of running a test.
