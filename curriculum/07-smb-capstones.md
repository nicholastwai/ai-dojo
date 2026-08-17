# Track 7: SMB Capstones (Go-to-Market)

## Default to automation, not agents

Say this bluntly because it cuts against the rest of this repo's framing:
**most SMB problems don't need an agent.** They need a reliable, boring,
deterministic workflow with an LLM doing one narrow thing inside it — and
that's usually cheaper to build, cheaper to run, and far easier for a
non-technical business owner to trust. The market data backs this up
directly: one automation firm estimates roughly 80% of real revenue-unlocking
wins for small businesses come from automation, not agents, and prices the
two very differently — automation in the $200-2,000/month range, agents
$1,500-10,000+/month plus setup and ongoing tuning. Even vendors who sell
agents make the same point: agents are a decision layer on top of automation,
not a replacement for it, and the businesses seeing real results use
automation for what's predictable and reach for agent-style autonomy only
where genuine judgment is needed. The failure mode is well documented too —
a fully autonomous "agent" given a vague goal and no guardrails is how you
get a business's AI receptionist hallucinating and handing out unauthorized
discounts, not how you get a happy client.

**Practical rule for every archetype below:** default to the simplest thing
that reliably works — a workflow tool (n8n, Make, Zapier) or a plain script
triggering one or two well-scoped LLM calls, wrapped in the human-approval
step. Only escalate to something that actually plans and chains multiple
tool calls autonomously (a real "agent" per Track 3's definition) if the
task has genuine variability a fixed workflow can't handle. This is also
just faster to ship — for someone optimizing for speed to cashflow, a
working n8n workflow this week beats a custom agent framework next month,
and it's what most SMB clients actually need and can afford.

Not a content gap — `ai-engineering-from-scratch` has real capstones (Phase
19 alone is 85 lessons: 17 end-to-end products plus 9 deep-build tracks,
20-40 hours each, plus phase-ending capstones in 13 and 14). Use those; they're
legitimate evidence of technical range. What they don't do is point at a
specific external business's actual problem or end with an outreach motion —
they prove you can build a complete system, not that a real business is
better off because you built it for them. That's what this track adds.
One more gap worth naming: the source curriculum is agent-shaped throughout
(that's its whole subject), so its capstones will pull you toward "build an
agent" by default — this track's job includes pulling back toward "does
this actually need to be an agent" before you start.

This is not a seventh skill — it's where you point the first six at a real
business problem. Everything here assumes you've reached at least "build"
tier on Agents & tool use and Evals. A capstone is a project scoped so that
a small business could actually use it, which makes it double as an outreach
piece: "I built this for a business like yours" opens far more doors than
"I'm available for AI work."

**If your target is specific enough to name real projects** — a particular
business model, a particular employer type, a particular market — copy
`ACTIVE-BUILDS.md.template` to `ACTIVE-BUILDS.md` (gitignored, yours) and
replace this generic menu with 2-4 named projects mapped tightly to that
target, each with its own gap analysis. That file, once it exists, becomes
the plan; this menu is the fallback for when the target isn't that specific
yet.

## Converting a Phase 19 capstone into an SMB capstone

This is the actual bridge, and the mapping below is now confirmed against
the source repo's `ROADMAP.md` directly (not inferred from search snippets)
— verify against `/course-guide` yourself before starting, since the repo
adds lessons over time, but as of this writing these are real project
titles at real paths.

**Two of the 17 end-to-end products are already close to SMB-shaped —
start here if one fits, since it's retargeting, not a rebuild:**
- **[Production RAG Chatbot (Regulated Vertical)](https://github.com/rohitg00/ai-engineering-from-scratch/blob/main/phases/19-capstone-projects/08-production-rag-chatbot)**
  (project 08) — built explicitly for a regulated vertical. Near-direct fit
  for the knowledge-base support archetype, especially with a
  healthcare/insurance background.
- **[Multimodal Document QA (Vision-First)](https://github.com/rohitg00/ai-engineering-from-scratch/blob/main/phases/19-capstone-projects/04-multimodal-document-qa)**
  (project 04) — close fit for the back-office document workflow archetype.

**Everything else is real, useful scaffolding shaped around a different
surface use case — retarget the mechanism, not the premise:**
- **Inbox triage / lead qualification** ← the "Agent harness" deep-build
  track (lessons 20-29: loop contract, tool registry, function dispatcher,
  plan-execute, verification gates, sandboxing, eval harness,
  observability). Built around a coding-agent example — the infrastructure
  transfers, the example doesn't.
- **Knowledge-base support agent** ← the RAG deep-build track (lessons
  64-69: chunking strategies compared, hybrid retrieval, cross-encoder
  reranking, query rewriting, RAG evaluation, end-to-end system) — more
  rigorous than the single RAG lesson in Phase 11, and its own eval lesson
  (68) is a better source for this than the generic "Eval harness" track.
- **Recurring report generator** ← the "Auto research" deep-build track
  (lessons 50-57), with a real caveat: it's shaped around scientific-paper
  workflow (hypothesis generator, literature retrieval, paper writer), not
  business reporting. Expect to retarget harder here than the other tracks.
- **Back-office document workflow** ← Phase 12's document/diagram
  understanding lessons (22, 23), or project 04 above as a stronger base.
- **Content-ops pipeline** ← Phase 14's multi-agent orchestration lessons
  (25, 28) or the Multi-Agent Software Engineering Team capstone (project
  10), retargeted from code review to content review.

**Not a good source for this track's Evals work despite the name:** the
"Eval harness" deep-build track (lessons 70-75) is coding-benchmark shaped
— task specs, code-exec metrics, leaderboards. Use the RAG deep-build's own
eval lesson (68) or Phase 11 lesson 10 instead for business-facing evals.


Once you've picked one, do these five things — in order, none skippable —
to turn the technical build into an actual SMB capstone:

1. **Kill the sample data.** Nearly every lesson exercise ships with clean,
   synthetic, or public sample data. Replace it with a real business's
   actual (messy) data before anything else — this alone surfaces most of
   the real problems a demo never hits.
2. **Add the human-approval step if it's missing.** Lesson capstones
   optimize for technical completeness (does the system work end to end),
   not for "would a business owner trust this unsupervised." Draft-then-approve
   is what makes it deployable, not a nice-to-have.
3. **Replace the lesson's benchmark with a business-scoped eval.** The
   source curriculum's own eval (if any) measures the lesson's learning
   objective. Build a 20-30 example eval set from the actual business's
   real cases per `curriculum/04-evals.md` — that's a different, harder
   benchmark than "does the code run."
4. **Find one real business, even unpaid, even a friend's.** This is the
   step people skip because it's the uncomfortable one. Nothing below
   counts as "ship" tier without it.
5. **Get the before/after number.** Time saved, error rate, response time
   — whatever the business actually cares about. This number is the whole
   outreach asset; the code is not.

## Why SMBs specifically

Small and mid-sized businesses can't hire in-house AI teams, so they
assemble a stack of narrow tools that each do one well-defined job — and
most of what they need is reliable automation, not autonomous agents (see
above). That's still the exact shape of work a freelancer can win: one
repetitive, rule-heavy, clear-input/clear-output task, automated well,
priced accordingly. The winning pattern is almost always **supervised
first** — draft, a human approves — expanding autonomy only once it's been
reliably right for weeks, if it ever needs to. Build that human-in-the-loop
checkpoint into every capstone; it's what makes a business trust it.

## Tiers for this track

- **Understand** — you can look at a business and identify the single
  highest-ROI, lowest-risk task to automate, and explain why the others are
  worse first bets.
- **Build** — you've built one capstone below end-to-end against realistic
  (even if synthetic) data, with an eval harness and a human-approval step.
- **Ship** — a real business (even one, even unpaid at first) is actually
  using it, and you have a before/after number.

## Capstone archetypes

Pick by which is closest to a business you can actually reach. Each now
states its **default build** (automation-first) and the **escalation
condition** — the specific reason you'd need real agent autonomy instead.

1. **Inbox triage & draft-reply.** *Default:* a workflow tool watches the
   inbox, an LLM call classifies the message (lead / support / vendor /
   spam) and drafts a reply, queued for one-click approval — no autonomous
   planning needed, this is classify-then-template. *Escalate to an agent
   only if:* replies genuinely require multi-step research (checking order
   status across systems, for instance) before a draft is possible. High-ROI
   either way because email is where small teams drown. Eval: misclassification
   rate and how often a draft ships unedited.

2. **Lead qualification & CRM updater.** *Default:* a workflow scores
   inbound leads against a fixed rubric via one LLM call and writes the
   summary + next action into the CRM — deterministic scoring, not agentic
   decision-making. *Escalate only if:* qualification genuinely requires
   the system to decide *which* enrichment sources to check based on what
   it finds, not just run a fixed set. Eval: does the score agree with what
   a human would have decided?

3. **Recurring report generator.** *Default:* a scheduled workflow pulls
   from the data source (sales, accounting, ads, analytics) and one LLM
   call turns the numbers into a plain-language summary — genuinely just
   automation with a writing step. *Escalate only if:* the business needs
   the system to decide *what to investigate further* based on what it
   finds, not just report on fixed metrics. Eval: are the called-out
   changes the ones a human analyst would flag?

4. **Knowledge-base support agent (RAG).** *Default:* still mostly
   deterministic — retrieve, ground, answer, cite, escalate when confidence
   is low. The "agent" framing here is really a RAG pipeline with a
   fallback rule, not autonomous planning. Eval: faithfulness (answer
   grounded in a real doc) and correct escalation on out-of-scope questions.

5. **Content-ops pipeline.** *Default:* a fixed workflow — research step,
   draft step, brand-voice edit step — each a single LLM call in sequence,
   not agents deciding the sequence themselves. *Escalate only if:* content
   type genuinely varies enough that the steps needed differ per piece.
   Note the real bar regardless: generic AI content is now a liability, so
   the differentiator is capturing a specific business's voice and facts,
   not volume. Eval: how much editing a draft needs before it's publishable.

6. **Back-office document workflow.** *Default:* deterministic extraction
   pipeline — OCR/parse, extract structured fields, validate against rules,
   route — flagging anything ambiguous for a human. This is close to pure
   automation almost by definition; genuine agentic judgment is rarely
   needed here. Eval: field-extraction accuracy and false-confidence rate
   on messy inputs.

## The outreach move

Once one capstone is at "ship" tier (even for a friend's business):
- Write it up as a short case study — the problem, what you built, the
  before/after number. The number is the whole point.
- That case study, not a resume, is your outreach. Approach businesses that
  look like the one you built for.
- A caution that matches reality: **fix the data first.** An agent wired to
  a messy, out-of-date system just automates the mess. Part of the paid work
  is often cleaning the inputs before automating — say so, and scope for it.

## Signals you're stuck at "understand"
You have a favorite archetype in theory but haven't built one against real
(or realistic) data, and haven't talked to a single business about their
actual bottleneck.
