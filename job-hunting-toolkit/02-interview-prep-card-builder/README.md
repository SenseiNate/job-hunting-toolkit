# Interview Prep Card Builder — Toolkit

A Claude Projects workflow that builds an interactive, single-file HTML interview prep card for
every round of every interview, driven entirely by the job description and your own accomplishment
record. No fabrication, no generic template filler — every story, stat, and answer traces back to
something you actually did.

This toolkit was built and battle-tested by one person across a real, active job search, then
stripped of anything personal so anyone can run it. It costs nothing beyond a Claude subscription
with Projects access — no third-party interview-prep service.

## What's in this repo

| File | What it is |
|---|---|
| `PROJECT_INSTRUCTIONS.md` | The full ruleset. This goes in your Project's custom instructions. |
| `MASTER_DATA_BANK_TEMPLATE.txt` | Blank template for your accomplishment record. You fill this in once and reuse it for every job you apply to. |
| `INTERVIEW_PREP_CARD_SKELETON.html` | Reference skeleton showing the exact structure, styling, and JS a finished card should have. Claude reads this as a build reference — you generally don't need to touch it. |
| `KICKOFF_PROMPT.txt` | The exact message to send to start a new round-1 card. |

## Requirements

- A Claude.ai account with **Projects** access (Pro, Max, Team, or Enterprise).
- Basic comfort filling in a text file and uploading files to a Claude Project — no coding
  required.

## Setup (one time)

1. **Get your data bank.** If you've already set up the companion `01-resume-scanner-builder`
   project, use that exact `DATA_BANK_TEMPLATE.md` you filled in there — don't rebuild it. If
   this is the only project you're using, fill in `MASTER_DATA_BANK_TEMPLATE.txt` instead,
   replacing every bracketed section with your real skills, tools, and accomplishments. Be
   honest — anything not in this file will never appear in a card.

2. **Fill in your profile in the instructions.** Open `PROJECT_INSTRUCTIONS.md`, fill in the
   **Your Profile** section near the top (background, education, credentials, location, any
   title/scope mismatch you want a standard line for) and the **Salary Range Determination**
   section (your current base and any credential with real hiring-cost value). Everything else in
   that file is the reusable methodology — leave it as written unless you have a specific reason
   to change it.

3. **Create a new Claude Project.** Name it after your job search (e.g. "Interview Prep").

4. **Paste `PROJECT_INSTRUCTIONS.md` into the Project's custom instructions field.**

5. **Upload your data bank (from Step 1) and `INTERVIEW_PREP_CARD_SKELETON.html` as Project
   knowledge files.** These stay attached to every chat inside the project.

## Using it for a new role

1. **Start a new chat inside the project** — one chat per role, not per round. Rounds for the same
   role build on each other in the same thread.
2. **Upload for that chat:** the job description (paste as text or upload), the resume you
   actually submitted for this role, and any recruiter/hiring-manager emails you have so far.
3. **Send the kickoff message** (see `KICKOFF_PROMPT.txt`):

   > Build me a Round 1 prep card for [Company], [Role Title].

4. Claude reads the JD end to end, matches it against your data bank, and builds the full card —
   cheat sheet, keyword map, stories, five-subtab Q&A, and company intel — as a downloadable HTML
   file you open in any browser.

## After each round

Report back in the same chat: what was actually asked (as close to verbatim as you can recall),
what landed, what didn't, and any new intel (interviewer names, process details, timeline). Then
say:

> Update the card for Round 2 with [interviewer name].

Claude re-audits and updates the existing card rather than starting over — validated answers get
tagged, new intel gets folded in, and anything that turns out to have been wrong gets corrected.

## A note on the rules file

`PROJECT_INSTRUCTIONS.md` is opinionated on purpose: zero fabrication, no em dashes, first-person
throughout, full STAR structure, a specific search-index and fallback-link system so the card is
actually usable live on a call rather than just a document to skim beforehand. You're free to
loosen or change any of it — it's your card — but the stricter version is what makes the card
trustworthy enough to actually read from mid-interview.

## Pairs with

The **resume scanner and builder** project in `/01-resume-scanner-builder` (same house rules —
zero fabrication, JD-driven, data-bank-sourced) is meant to run *before* this one: it screens the
JD, produces the tailored resume you actually submit, and its Data Bank is the same file you
upload here. That submitted resume becomes one of the three inputs this project reads for each
round. You can still use this toolkit on its own with any resume you've already submitted — see
Step 1 above.
