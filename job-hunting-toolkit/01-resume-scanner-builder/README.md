# AI Resume & Job Screening System

A free, self-hosted alternative to paid "AI resume tailoring" services. You provide your own
real accomplishments once, in a structured format. From then on, you paste in a job description
and get: a screening verdict (pass/skip), a tailored resume, and a matching cover letter, built
from a fixed system of rules that will not fabricate anything on your behalf.

This runs entirely inside a **Claude Project** (claude.ai). There is nothing to install and no
subscription beyond whatever Claude plan you already use.

## Why this exists

Most "AI resume builder" tools do one of two things badly: they either invent plausible-sounding
experience you don't have (which gets caught in an interview), or they spit out generic,
keyword-stuffed bullets that read like every other applicant's. This system solves both problems
with one hard rule: **the AI is only allowed to use content you already wrote down.** Its only job
is deciding which real accomplishments to use, and how to phrase them for a given job posting.

## What's in this repo

| File | Purpose |
|---|---|
| `PROJECT_SYSTEM_PROMPT.md` | The exact instructions you paste into your Claude Project's custom instructions field. This is the "brain" of the system. |
| `MANIFESTO_TEMPLATE.md` | Your personal rulebook: formatting rules, screening logic, career tracks, sector/industry translation. You fill in the brackets. |
| `DATA_BANK_TEMPLATE.md` | Your personal database of real accomplishments, organized by employer and by the type of role you're targeting. This is the only source of truth for resume content. |
| `SETUP_GUIDE.md` | Step-by-step instructions to go from zero to a working system, including how to bootstrap your Data Bank from an existing resume. |
| `templates/Skeleton_Resume.docx` | A blank example resume showing the target format and structure. |
| `templates/Skeleton_Cover_Letter.docx` | A blank example cover letter showing the target format and structure. |

## How it works, in one paragraph

You create a Claude Project. You paste `PROJECT_SYSTEM_PROMPT.md` into its custom instructions.
You upload your filled-in `MANIFESTO_TEMPLATE.md` and `DATA_BANK_TEMPLATE.md` as project
knowledge files. From then on, every time you paste a job description into that project, Claude
runs a fixed screening protocol against your Manifesto's rules, decides whether the role is worth
pursuing, and if so builds a resume and cover letter using only accomplishments that already exist
in your Data Bank, tailored in language to that specific posting.

## Quick start

1. Read `SETUP_GUIDE.md`.
2. Fill in `MANIFESTO_TEMPLATE.md` with your own tracks, formatting preferences, and rules.
3. Fill in `DATA_BANK_TEMPLATE.md` with your real accomplishments (or bootstrap it from an
   existing resume, see the guide).
4. Create a Claude Project, paste in `PROJECT_SYSTEM_PROMPT.md` as its instructions, and upload
   both of your filled-in documents as project knowledge.
5. Paste in a job description and see what comes back.

## Ground rules this system enforces

- No fabricated skills, tools, metrics, or experience, ever. If a job needs something not in your
  Data Bank, the system is instructed to flag the gap and ask you, not invent it.
- Every resume bullet is Task/Action/Outcome, one accomplishment per bullet, with a real metric.
- Compensation and location are reported as information, never used as silent pass/fail filters.
- You decide what to do with every gap or risk the system flags. It presents options; it doesn't
  make judgment calls for you on things only you can judge (like whether a stretch role is worth
  the risk).

## Once you get an interview

The `/02-interview-prep-card-builder` project (in the parent folder of this repo) picks up from
here. It reuses this same Data Bank file, so nothing you built in this project goes to waste.

## License

Use it, fork it, change it, share it. No warranty. It's a prompt and two text files, not legal or
career advice, and you're responsible for reviewing anything before you send it to an employer.
