# AI Engineering Dojo

<p align="center">
  <img src="assets/dojo-banner.png" width="100%" alt="AI Dojo banner — pixel art of a temple gate signed 「AI Dojo 人工智能道场」, a straw-hatted traveler climbing the steps, autumn maples and a waterfall in misty mountains, beside a hanging scroll reading 刻意练习 · 精益求精 (deliberate practice, ever-refining)">
</p>

A files-first accountability and curation layer for becoming a competent AI
engineer through deliberate, project-based practice — taught by whatever AI
agent/harness you already use (Claude Code, Cursor, a self-hosted agent,
ChatGPT with file access, etc).

## Built on top of `ai-engineering-from-scratch`

This repo does not contain its own lessons. The technical curriculum is
[`ai-engineering-from-scratch`](https://github.com/rohitg00/ai-engineering-from-scratch)
— a free, open, 503-lesson curriculum covering AI/ML from the math up. It's
excellent, and it's not this repo's to reinvent.

What this repo adds on top of it:
- **Scope.** 503 lessons across 20 phases is comprehensive to the point of
  being a full ML curriculum. `curriculum/00-overview.md` says exactly
  which ~90 lessons matter for AI/LLM engineering and agent work, and which
  phases to skip unless a specific project needs them.
- **A ship-tier bar the source curriculum doesn't have.** Its lessons end
  with a quiz and a reusable artifact. This repo doesn't count that as
  done — "build" and "ship" tier require using what you learned on
  something real (see `curriculum/00-overview.md`).
- **Accountability across sessions.** A dashboard, a progress file, and an
  agent instructed to hold the line on the tier system rather than let
  finished lessons pass as finished skills.

If you want the deepest possible AI/ML education with no scoping, go
straight to `ai-engineering-from-scratch` — it's the better resource for
that. This repo is for people who already know they want AI/LLM engineering
and agent work specifically, and want the surrounding structure to actually
finish, not just consume, the relevant parts of it.

## The idea

Most AI learning fails for one of two reasons:
1. **Breadth without depth** — endless tutorials, no shipped projects.
2. **No continuity** — every chat starts from zero, so there's no sense of
   progress and no accountability.

Even a curriculum as good as `ai-engineering-from-scratch` doesn't fix
either of these on its own — nothing stops you from working phase to phase
"for completeness" and never shipping, and nothing carries a sense of
progress or stakes between sessions. This repo is a set of markdown files
that fix that:
- who you are and what you already know (`USER.md`)
- what "done" looks like for each core skill, and which external lessons
  teach it (`curriculum/`)
- where you currently stand and what happened last session (`progress/STATE.md`)
- what you've actually shipped (`projects/LOG.md`)

Point an agent at this repo, tell it to read `AGENTS.md`, and it becomes a
tutor that routes you to the right external lessons, picks up exactly where
you left off, and refuses to let "finished the lesson" count as "built
something real."

## Quick start

1. Clone this repo (or use it as a GitHub template).
2. Run `npx skills add rohitg00/ai-engineering-from-scratch` to install the
   source curriculum's agent skills — this repo can't teach without them.
3. Copy `USER.md.template` → `USER.md` and fill in your background/goals.
4. Copy `progress/STATE.md.template` → `progress/STATE.md`.
5. Open the repo in your agent of choice and say:
   > "Read AGENTS.md and USER.md, then start our first session."
6. At the end of every session, the agent updates `progress/STATE.md` and
   (when relevant) logs a project in `projects/LOG.md`.
7. Next time — different day, fresh chat, doesn't matter — say
   "continue my AI engineering track" and it reads the files and picks up
   exactly where you left off.

## The progress dashboard

`index.html` is a self-contained visual dashboard — belt-style progress bars
for each track, a computed rank (white belt → sensei), your streak, and a
session log. The agent updates the data inside it every session, in sync
with `progress/STATE.md`.

- **Local:** just double-click `index.html`. It works offline with no server
  and no build step — the data lives in a `<script type="application/json">`
  block inside the file.
- **Live link (optional):** the repo drops onto GitHub Pages or Vercel
  unchanged if you ever want a shareable URL. No config required.

## How the curriculum works

Each file in `curriculum/` is one core competency (prompt engineering, RAG,
agents/tool use, evals, fine-tuning, deployment, SMB capstones) and points
to the specific lessons in `ai-engineering-from-scratch` that teach it.
Each has three tiers — and only tier 2 and 3 are this repo's own bar, not
the source curriculum's:

- **Understand** — the mapped external lesson, completed, quiz included.
- **Build** — you've used what it taught on something real, not the
  lesson's own toy exercise.
- **Ship** — you've used it in a real project someone other than you could use.

The agent's job is to never let a finished external lesson count as more
than tier 1. Lessons get you to understand. Tier 3 is what makes you
employable/freelanceable.

## Why files instead of a database or app

Any agent that can read a folder can use this — no API, no hosting, no
lock-in. It's also just... auditable. You can open `progress/STATE.md` and
see your own trajectory in plain English.

## Note on the seventh track

Tracks 1-6 are skills. Track 7 (SMB capstones) is different — it's where you
aim the first six at a real business problem to produce a portfolio piece
that doubles as freelance outreach. It's gated behind reaching "build" tier
on Agents and Evals, because a capstone without those isn't shippable.
