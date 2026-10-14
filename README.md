# Job Hunting Toolkit

Two Claude Projects that run your job search end to end, both built on the same hard rule: **the
AI can only ever use accomplishments you actually wrote down.** No fabricated skills, no invented
metrics, nothing that gets caught the moment an interviewer asks a follow-up question.

Free. Self-hosted. Runs entirely inside Claude Projects (claude.ai) — nothing to install, no
subscription beyond whatever Claude plan you already have.

## The pipeline

```
1. Find a job posting
        │
        ▼
2. RESUME SCANNER & BUILDER  ──▶  screening verdict + tailored resume + cover letter
   (/01-resume-scanner-builder)
        │
        │  (the resume you actually submitted)
        ▼
3. Get an interview
        │
        ▼
4. INTERVIEW PREP CARD BUILDER  ──▶  a live-reference prep card, one per round
   (/02-interview-prep-card-builder)
        │
        ▼
5. Debrief after each round → card updates for the next one
```

Both projects read from **the same Data Bank file** — the one you build once in Step 2. You never
maintain two separate records of your own accomplishments; you build it once, upload it to both
Projects, and update it in one place (Mode 3 of the resume system) whenever something new happens.

## Setup order

1. Set up `/01-resume-scanner-builder` first — follow its own `SETUP_GUIDE.md`. This is where you
   build your Data Bank and Manifesto from scratch.
2. Once you have a real job you're interviewing for, set up `/02-interview-prep-card-builder` —
   follow its own `README.md`. Reuse the Data Bank you already built; don't rebuild it.

Each subfolder is a self-contained Claude Project with its own instructions, template files, and
setup guide. You'll end up with two separate Claude Projects (two different custom-instructions
sets, since screening/resume logic and live-interview logic are different jobs), sharing one
source-of-truth document.

## Why two separate Projects instead of one

A resume build and a live interview-prep card ask the AI to do genuinely different things — one
screens and writes, the other researches interviewers and builds a searchable reference tool. Each
project's Custom Instructions field is already long and specific; combining them would mean either
document fighting the other for context. Keeping them separate, sharing only the Data Bank, keeps
each one focused and keeps the shared source of truth from drifting.

## Ground rules both systems enforce

- No fabricated skills, tools, metrics, or experience, ever. Anything a job needs that isn't in
  your Data Bank gets flagged as a gap, not invented.
- Every claim is traceable back to a specific Data Bank entry (by accomplishment ID in the resume
  system, by story reference in the prep card system).
- Compensation is reported as information, never used as a silent pass/fail filter.
- You decide on every judgment call the system surfaces. It presents options; it doesn't make
  decisions for you.

## License

Use it, fork it, change it, share it. No warranty. It's prompts and template documents, not legal
or career advice — you're responsible for reviewing anything before it goes to an employer or gets
said out loud in an interview.
