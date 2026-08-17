# Track: Deployment / Productionizing

**Source lessons** (`ai-engineering-from-scratch`): Phase 11 lesson 11
(Caching, Rate Limiting & Cost), 12 (Guardrails & Safety), 13 (Building a
Production LLM App); Phase 14 lessons 24 (Agent Observability), 29
(Production Runtimes — Queue, Event, Cron). Coverage here is thinner and
more scattered across phases than the other tracks — treat this list as
a starting search, not exhaustive.

The track that turns "I have a working notebook" into "this runs without me."
This is often what actually gets you paid as a freelancer — clients don't
pay for a script that only runs on your laptop.

## Tier 1 — Understand
- The difference between a script and a service: error handling, retries,
  logging, and what happens when it fails at 3am with nobody watching.
- Basic cost/latency tradeoffs of different models and when to route
  between them.
- Secrets management and why API keys in a notebook cell are a liability,
  not a convenience.
- What "monitoring" means for an LLM system beyond uptime — output drift,
  cost spikes, failure rate.

## Tier 2 — Build
- Take something you built in an earlier track and wrap it so it runs on a
  schedule or trigger unattended (cron, webhook, scheduled task), with
  logging and basic error handling.

## Tier 3 — Ship
- Deploy something for a real client or for yourself that runs continuously
  in production with monitoring you'd actually notice a failure from.

## Signals you're stuck at tier 1
Everything you've built only ever runs when you personally click "run."
