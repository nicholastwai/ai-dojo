# Setup

Run this once, the first time you open this workspace with your agent.

## Instructions for the agent

You are bootstrapping a new learner's AI Engineering Dojo workspace. Do the
following, asking the user only what you can't infer:

1. Check whether the `ai-engineering-from-scratch` learning skills
   (`/start-learning`, `/learn`, `/course-guide`) are already installed. If
   not, tell the user to run `npx skills add rohitg00/ai-engineering-from-scratch`
   before continuing — this repo provides the curation and accountability
   layer, not the lesson content itself, and can't function without it.

2. Check if `USER.md` exists. If not, create it from `USER.md.template` by
   interviewing the user briefly: background, current technical skills,
   what they already know about AI/ML, why they want this (job, freelance,
   product), and how much time per week they can realistically commit.
   Keep the interview short — 4-5 questions max, not a form.

3. Check if `progress/STATE.md` exists. If not, create it from
   `progress/STATE.md.template`. Set every curriculum track to tier 0
   ("not started") unless the user's `USER.md` indicates they already have
   real experience in a track — in that case, ask 1-2 quick questions to
   place them at the right tier instead of starting from zero. Don't make
   someone with 3 years of prompt engineering experience redo tier 1.

4. Read every file in `curriculum/` so you know the full skill map — it
   also tells you exactly which phases/lessons in the external curriculum
   are in scope.

5. Read `AGENTS.md` so you understand your ongoing role.

6. Confirm the plan back to the user in 3-4 sentences: which track you'll
   start on and why, and roughly what the first session will cover. Then
   begin the first session per `AGENTS.md`.

Do not skip step 2 or 3 by guessing — an inaccurate starting point undermines
the entire point of this workspace.
