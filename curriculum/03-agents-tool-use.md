# Track: Agents & Tool Use

This is the highest-leverage *technical* skill for freelance/consulting
work — knowing how tool calls and the agent loop actually work is what lets
you build anything from a one-step LLM-in-a-workflow to a fully autonomous
system. That said: understanding agents doesn't mean every client
deliverable should be one. See `curriculum/07-smb-capstones.md` for the
business-side judgment call — most SMB work should default to deterministic
automation with an LLM call inside it, and only escalate to real agent
autonomy when the task genuinely needs it. This track teaches the full
capability; track 7 teaches when to actually reach for it.

**Source lessons** (`ai-engineering-from-scratch`, use `/course-guide` to
jump to any of these): Phase 13 lessons 01 (The Tool Interface) and 02
(Function Calling Deep Dive); Phase 14 lessons 01 (The Agent Loop), 06
(Tool Use and Function Calling), 07-09 (memory), 26 (Failure Modes — Why
Agents Break), 27 (Prompt Injection and the PVE Defense), 28 (Orchestration
Patterns), 30 (Eval-Driven Agent Development). Phase 14 alone has 42
lessons — these are the ones in scope; the rest (specific framework deep
dives, the later "workbench" sub-track) are worth returning to only once
tier 2 is solid here.

## Tier 1 — Understand
- What a "tool call" actually is: the model outputs structured intent, your
  code executes it, the result goes back into context. The model never
  executes anything itself.
- The agent loop: observe → decide → act → observe result → repeat.
- **The judgment call that matters most in practice: when is a fixed
  workflow with an LLM call inside it enough, versus when does the task
  genuinely need the loop above — the system deciding its own next step,
  not just executing a predetermined one?** Most tasks that feel like they
  need "an agent" are actually classify-then-act or extract-then-route —
  deterministic. Real agent autonomy earns its complexity and cost only
  when the next step genuinely can't be predetermined.
- Why agents need guardrails: unbounded loops, cost control, permission
  scoping (what should this agent never be allowed to do unsupervised).
- Single-agent vs multi-agent/orchestration, and why multi-agent adds
  complexity that's often not worth it for a given task.

## Tier 2 — Build
- Build an agent with at least two real tools (not toy functions — e.g. an
  API call and a file/database write) that completes a multi-step task
  without you manually chaining the steps.
- Add one guardrail deliberately (max iterations, cost cap, or a
  human-approval step before a destructive action) and test that it works.
- As a companion exercise, not a substitute: build the same task's
  simplest deterministic version (a fixed workflow, one or two LLM calls,
  no autonomous loop) and compare — cost, latency, reliability, and how
  much harder the agent version was to get right for the same outcome.
  Knowing the honest tradeoff is part of this tier.

## Tier 3 — Ship
- Deploy an agent that runs on a schedule or trigger, unattended, and
  produces something you or a client actually relies on — e.g. a recurring
  report that pulls from an API and writes a summary, or a workflow that
  watches for an event and takes a multi-step action in response.

## Signals you're stuck at tier 1
You've read about LangGraph/CrewAI but haven't shipped anything that runs
without you babysitting it. The opposite signal is worth watching for too:
reaching for an agent framework by default without asking whether the task
actually needed one — that's not depth, it's the tutorial-hell trap wearing
a more sophisticated costume.
