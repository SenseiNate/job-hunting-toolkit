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
Every card matches the skeleton's seven-tab shape (Overview, Resume Stories, JD Question Stories, Extra Stories, Technical
Knowledge, Values if the company publishes real named values/principles, Intel) unless the round
genuinely calls for a chat-specific extra, per README's Chat-Specific Extras section — and even
then, extras apply only to that round's card, never change the master skeleton unless explicitly
asked. Every resume bullet actually submitted must be defended by a story (the Resume Map,
README's primary coverage mechanism, backed up by the JD Map and the JD Question Stories tab), every story is framed to fit the
company's real values and culture per README, and every card ships
alongside its Story Sheet companion file (PDF + HTML).

## Your Profile

> CUSTOMIZE: Fill this in once, plainly, in your own voice. This is the block Claude leans on for
> tone and framing across every card it builds for you.

- **Background:** [Your work history in one or two lines per employer, most recent first.]
- **Education:** [Degrees, schools.]
- **Credentials / Clearance / Licenses:** [Anything that functions like a gate for the roles you
  target — a clearance, a certification, a license.]
- **Location:** [City, state. Relocation posture — open, conditional, or fixed.] Unless a specific
  target city has been explicitly confirmed for a given round, keep this generic: open to
  relocation depending on the role's location, or remote if offered. Do not name a specific
  destination city as if it were a settled plan. This same rule applies inside every card's
  Location field, essentials strip, and Intel notes.
- **Title/scope mismatch, if any:** [If a prior title (military, internal leveling, a staffing-firm
  title) undersold or overclaimed the actual scope of the work, say so plainly here: what the title
  was, what the day-to-day work actually was, and what title you now use and why it's the accurate
  functional title rather than an inflation of it. Note whether this caused real screen-out before
  you could explain the actual work, and what the honest answer is if an interviewer who knows the
  original title system presses on it directly.]
- **Why leaving [CURRENT/MOST RECENT EMPLOYER], if relevant to the round:** [The real, honest reason
  — a contract or program transitioning to a new owner, a layoff, a reorg, wanting more scope, etc.
  If there's one specific program or project that's an easy but misleading shorthand for the whole
  employer, name that risk here and say which other real accomplishments from the data bank should
  be pulled instead so the departure story doesn't get anchored to a single narrow example.]
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
2. Build the card per `README.md`: Resume Map and JD Map both built, every submitted bullet given
   a primary story, every section traces to the JD or the data bank, nothing fabricated, all
   quality checks (resume-bullet coverage audit, same-story audit, one-block-open check, JS syntax,
   div balance) pass before the file is presented. Build the Story Sheet companion file alongside
   it.
3. After each round, fold in what was actually reported (what was asked, what landed, new intel)
   and update the same card rather than starting over, and re-audit per README's Debrief and
   Re-Encode Loop — including rebuilding the Story Sheet if Resume Stories, JD Question Stories, or Extra Stories changed.
4. For a multi-session onsite day, also build the Round-Specific group inside Technical Knowledge
   and the standalone one-page memorization sheet, per README's Multi-Session and Onsite Days
   section.
5. If a round needs something outside the standard shape, add it as a labeled, round-specific
   extra to that card only — never silently change the master skeleton.

See `KICKOFF_PROMPT.txt` for the exact messages to start a new card and to trigger a round update.
