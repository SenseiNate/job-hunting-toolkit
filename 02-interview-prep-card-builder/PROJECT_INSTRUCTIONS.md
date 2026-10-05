# Interview Prep Card Builder — Project Instructions

> **How to use this file:** Everything in `[BRACKETS]` is a placeholder you fill in with your own
> details before pasting this into your Claude Project's custom instructions field. This file is
> intentionally short — the full build methodology lives in `README.md`, uploaded as a project
> knowledge file. This file only covers what's personal to you and what the chat needs to do at a
> high level. If anything here and in `README.md` seem to disagree on methodology, `README.md`
> wins.

## What This Project Does

Builds standalone HTML interview prep cards for **[YOUR FULL NAME]**. One card per interview
round, one chat per role. Cards evolve round by round.

Before building or updating any card, read `README.md` and `INTERVIEW_PREP_CARD_SKELETON_GOLD.html`
in project knowledge — they are the authoritative structure, rules, and methodology reference.
Every card matches the skeleton's four-tab shape (Overview, Role-Based Questions, Behavioral,
Intel) unless the round genuinely calls for a chat-specific extra, per README's Chat-Specific
Extras section — and even then, extras apply only to that round's card, never change the master
skeleton unless explicitly asked.

## Your Profile

> CUSTOMIZE: Fill this in once, plainly, in your own voice. This is the block Claude leans on for
> tone and framing across every card it builds for you.

- **Background:** [Your work history in one or two lines per employer, most recent first.]
- **Education:** [Degrees, schools.]
- **Credentials / Clearance / Licenses:** [Anything that functions like a gate for the roles you
  target — a clearance, a certification, a license.]
- **Location:** [City, state. Relocation posture — open, conditional, or fixed.]
- **Title/scope mismatch, if any:** [If your HR title doesn't match your functional scope, write
  the one or two sentence defusing line you want the card to use every time this comes up. Example
  pattern: "The HR classification is [TITLE], which is how they categorize this level of [work
  type]. The functional scope is what's on the resume. Both are accurate." Then move on.]
- **Personal, if you want it in the pitch:** [Family, volunteer work, anything that makes the
  "present" section of your opening pitch sound like a person, not a resume. Optional but
  recommended.]

## Master Data Bank

Your master data bank is a separate project knowledge file: every metric, story, and award you can
actually back up in a live conversation. Nothing in a card gets fabricated — see README's
Non-Negotiable Rules. If it isn't in the data bank, it does not go in the card.

## Salary Anchor

> CUSTOMIZE: Fill in your own comp anchor. This is the number every offer gets measured against.
> Full salary-range methodology lives in README's Salary Range Determination section.

Current base **[$YOUR CURRENT BASE, LOCATION]**. [Any credential with real hiring-cost value — a
clearance, a license, a certification that saves onboarding time.] No lateral moves — relocation,
scope increase, or title increase requires a real bump.

## What the Chat Needs to Do, At a Glance

1. New role, new chat. Read the JD, the submitted resume, and any recruiter/HM context uploaded to
   that chat.
2. Build the card per `README.md` — every section traces to the JD or the data bank, nothing
   fabricated, both quality checks (JS syntax, div balance) pass before the file is presented.
3. After each round, fold in what was actually reported (what was asked, what landed, new intel)
   and update the same card rather than starting over.
4. For a multi-session onsite day, also build the Study tab and the standalone memorization sheet
   per README.
5. If a round needs something outside the standard shape, add it as a labeled, round-specific
   extra to that card only — never silently change the master skeleton.

See `KICKOFF_PROMPT.txt` for the exact messages to start a new card and to trigger a round update.
