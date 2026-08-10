# Setup Guide

Total setup time: 30-60 minutes if you're filling everything in from scratch, less if you're
starting from an existing resume (see Step 2 below).

## Step 1: Create the Claude Project

1. In Claude, create a new Project (this keeps your Manifesto and Data Bank as persistent
   "project knowledge" so you don't re-paste them every conversation).
2. Open `PROJECT_SYSTEM_PROMPT.md` from this repo, copy everything below the line under the
   heading, and paste it into the Project's custom instructions field.

## Step 2: Build your Data Bank

You have two starting points. Pick one.

**Option A: You have an existing resume.**
Start a chat inside your new Project (before you've uploaded the templates, or even in a
scratch chat) and upload your current resume, then say something like:

> "Here's my current resume. Use DATA_BANK_TEMPLATE.md's structure to pull every accomplishment
> out of it into a first-draft Data Bank. Keep every metric and detail exactly as I wrote it,
> don't round anything up or add context I didn't include. Write one version of each
> accomplishment under a single track for now, I'll duplicate it into other tracks later. Flag
> anything that's vague or missing a metric so I can fill it in."

Review what comes back carefully. An existing resume often already has some exaggeration or
vague language in it (nobody's is perfect), so this step is a starting draft, not a finished
product. Tighten anything that isn't precisely true before it becomes your source of truth,
since every future resume will inherit it.

**Option B: You're starting from scratch.**
Open `DATA_BANK_TEMPLATE.md` and fill it in directly, employer by employer. For each
accomplishment, write down three things: what needed solving, what you specifically did about
it, and what the measurable result was. If you don't have a number, get as close as you can
(a percentage, a headcount, a dollar range, a time saved), a bullet with no metric is a weak
bullet no matter how it's phrased later.

Either way, finish this step before Step 3, your Manifesto's tracks and translation rules are
easier to define once you can see the shape of your actual experience.

## Step 3: Build your Manifesto

Open `MANIFESTO_TEMPLATE.md` and fill in every bracket. The parts worth the most thought:

- **Career tracks (Section 1):** these determine how the system reframes the same underlying
  accomplishment for different types of roles. If you're only targeting one type of role, use
  one track and skip the rest, don't force four tracks you don't need.
- **Auto-skip list (Section 4):** keep this short and only put things here you'd reject
  regardless of pay or company. Everything else should be a judgment call the AI presents to you
  as options, not a silent filter.
- **Industry translation table (Section 6):** only needed if you're moving between fields that
  use different vocabulary for similar work. If you're staying in the same industry, delete this
  section.

## Step 4: Upload both files as Project knowledge

Upload your filled-in `MANIFESTO_TEMPLATE.md` (renamed to something like
`[YourName]_Manifesto.md`) and `DATA_BANK_TEMPLATE.md` (renamed similarly) to the Project's
knowledge files, not just to a single chat, so every new conversation in the Project has them
automatically.

## Step 5: Test it

Start a new chat inside the Project and paste in a real job description you're considering.
You should get back a PASS/SKIP verdict, a compensation and sector read, and (if it's a PASS) a
tailored resume and cover letter as downloadable files.

Check the first one closely against your Data Bank line by line. Confirm every bullet traces
back to something you actually wrote down. If anything looks invented, softened past
recognition, or over-claimed, that's a bug to fix in your Manifesto (usually a formatting or
tailoring rule that's under-specified), not something to let slide.

## Step 6: Iterate

- If a build keeps making the same mistake, add a rule to your Manifesto that prevents it, rather
  than correcting it by hand every time.
- Use Mode 4 (Rejection Analysis) to keep a running log of why applications aren't converting,
  and feed real patterns back into your Manifesto once you've seen them repeat.
- Use Mode 3 (Manifesto & Data Bank Maintenance) any time you have a new accomplishment,
  a new job, or a new skill to add. Always confirm changes before they're written, this is your
  system of record.

## A note on honesty

This system is only as good as what you put in the Data Bank. It is built to refuse to
fabricate, but it can't verify your accomplishments independently, that part is on you. Every
number and claim in your Data Bank should be something you'd be comfortable defending in detail
to an interviewer, because that's exactly what will happen if a resume built from it gets you in
the room.
