# Interview Prep Card Builder — Build Spec & Toolkit

This is the authoritative reference for how every interview prep card gets built. Claude reads
this file, `INTERVIEW_PREP_CARD_SKELETON_GOLD.html`, and the master data bank before building or
updating any card. `PROJECT_INSTRUCTIONS.md` (the Project's custom instructions field) only holds
what's personal — your profile, your data bank pointer, your comp anchor — and a directive to
follow this file for everything else. If the two ever seem to disagree on methodology, this file
wins.

## What's in this repo

| File | What it is |
|---|---|
| `PROJECT_INSTRUCTIONS.md` | Short. Goes in the Project's custom instructions field. Your profile + a pointer to this file. |
| `README.md` (this file) | The full ruleset: card structure, rules, technique library, content depth, quality checks. |
| `MASTER_DATA_BANK_TEMPLATE.txt` | Blank template for your accomplishment record. Filled in once, reused for every job. |
| `INTERVIEW_PREP_CARD_SKELETON_GOLD.html` | The structural, styling, and JS reference. Every card built in this project matches this file's shape unless a chat-specific extra is called for — see below. |
| `KICKOFF_PROMPT.txt` | Exact messages to start a new round-1 card and to update after a round. |

## Setup (one time)

1. **Fill in your data bank** — every metric, story, and award you can actually back up in a live
   conversation. Nothing in a card gets fabricated; if it isn't in this file, it doesn't go in the
   card.
2. **Fill in `PROJECT_INSTRUCTIONS.md`** — your profile and comp anchor. Everything else in that
   file is a pointer back here.
3. **Create a Claude Project**, paste `PROJECT_INSTRUCTIONS.md` into custom instructions, upload
   your data bank and `INTERVIEW_PREP_CARD_SKELETON_GOLD.html` as project knowledge files.

## Using it for a new role

One chat per role, not per round — rounds for the same role build on each other in the same
thread. Start a new chat, upload the JD, the resume submitted for that role, and any
recruiter/hiring-manager emails, then send the kickoff message in `KICKOFF_PROMPT.txt`. After each
round, report what actually happened and send the update message.

---

## What This Project Does

Builds a standalone, single-file HTML interview prep card for every round of every interview,
driven entirely by the job description and the master data bank. No fabrication, no generic
template filler — every story, stat, and answer traces back to something real.

The card's core inputs are the JD and the data bank / submitted resume. As a round progresses,
real information from actual conversations (recruiter emails, interviewer names, what was asked,
what landed) becomes a third input and takes priority over assumption.

## The Non-Negotiable Rules

1. **Zero fabrication.** Every metric, claim, and story traces to the data bank, the submitted
   resume, or something directly reported from a real conversation.
2. **No em dashes anywhere in card content.** Commas, periods, or natural sentence breaks only.
3. **Natural spoken language throughout.** The card gets read live or memorized beforehand. It
   sounds like a person talking, not a document being read. First person throughout.
4. **All sections and q-blocks closed by default.** Study Mode and the sticky essentials strip
   (see below) exist precisely so nothing needs to be opened just to scan it.
5. **Both quality checks pass before presenting any file** — every time, not just on first build.
   See Quality Checks below.
6. **STAR structure with unambiguous content** in every answer where it applies, with visible
   styled headers inside the prose. Factual or definitional questions use a direct-answer format
   without STAR.
7. **Domain terminology gets acronym expansions** on first use in each answer, derived from the JD
   and data bank.
8. **Every substantive q-block gets one inline fallback** — see Inline Fallback Model below.
   Exceptions are fine for pure technique tips, questions to ask the interviewer, and honest
   pure-gap answers with nothing real to bridge to.
9. **Salary range is determined by fit analysis**, not by stated targets, unless a specific number
   has already been communicated in a real conversation, in which case the card reflects what was
   actually said. Never claim a number was discussed unless it actually was.
10. **Coverage is determined by the JD, not by role type.** Every requirement, responsibility, and
    preferred qualification gets a matched answer, then whatever isn't in the JD but always gets
    asked for that kind of work gets one too.
11. **Compliance gets checked continuously**, not once at initial build. Any time content gets
    added mid-session, re-audit the affected sections before considering the work done: STAR
    headers present, fallback present per q-block, subtab structure still matches spec, search
    index entry added for anything new.

## Card Structure

Single standalone HTML file. All navigation, search, and content in one file, no external
dependencies beyond Google Fonts. Structure matches `INTERVIEW_PREP_CARD_SKELETON_GOLD.html`
exactly.

**Four tabs, always in this order:** Overview, Role-Based Questions, Behavioral, Intel. For a
multi-session onsite round, a Study tab is added first — see Multi-Session and Onsite Days below.

- **Overview** — five subtabs: Summary (stage, role, location, pay range and recommended ask,
  total comp if offered), Pitch (why-them, why-leaving, the opening elevator pitch), Ask Them
  (questions to ask, split into recruiter / hiring-manager / peer tiers), Interview Tips (the
  technique library, condensed — mirroring, labeling, strategic silence), Closing (the last-60-
  seconds script).
- **Role-Based Questions** — one flat, searchable list. This tab absorbs everything JD-driven and
  everything a senior person in the domain would ask regardless of the JD: responsibility-based
  questions, ownership and independent-work questions, fully narratable deep-dive examples, and
  technical/domain-depth questions including field-standard fundamentals (see Domain Fundamentals
  below). Order roughly by likelihood: core JD-mapped questions first, then domain depth, then
  deep dives. No further tab-switching needed to reach any of it.
- **Behavioral** — one flat list, fixed order: strength (two angles), weakness (real, with a real
  fix), competing priorities, a problem or risk no one else caught, an ambiguous environment
  handled without a clear mandate, influence without formal authority, pushback on budget, scope,
  or cost. Every one gets a full STAR answer built from a real story, never a pointer to
  improvise from.
- **Intel** — company, org, and program context, researched live at build time. Always includes a
  "Recent News & Talking Points" card and a "Team & Who You'd Integrate With" card, both sourced
  from a live search done as part of the build, never evergreen template content.

There are no separate Keywords or Stories tabs. Keyword-to-answer routing is handled by the search
bar (see Search Engine below), and stories live directly inside the q-block they answer rather
than in a shared tab reached by cross-links.

### Sticky Essentials Strip (Overview tab, required)

A thin bar pinned under the header while scrolling the Overview tab, holding the 3-5 absolute
must-says for this call: clearance line, target comp, anchor differentiator, location/relocation
stance. Visible without opening anything.

### Study Mode (global, required)

A toggle in the header. When on, every q-block header across Role-Based and Behavioral shows a
one-line cue and 3-5 keyword tags without needing to be opened, so the whole tab can be scanned in
seconds the night before or morning of. This is the primary study tool for a standard round — a
separate standalone memorization sheet is only built for multi-session onsite days (see below).

## Inline Fallback Model

Every substantive q-block in Role-Based and Behavioral gets exactly one fallback, living inside
that same q-block behind a "🔄 Different Angle" toggle — no separate tab, no cross-links to chase.
Use it when the interviewer might go deeper, or when the same question could plausibly get asked
by a second person on the same day and repeating the identical answer would read as rehearsed. The
fallback is either a genuinely different story or a different angle on the same story, with its
own full STAR and its own `story-source` line.

This replaces the old Core/Fallback story-pool-with-cross-links model. It is deliberately simpler:
each question is self-contained, so nothing needs to be looked up mid-answer. When drafting, it's
fine to pull from a mental pool of your strongest 10-15 reusable stories across employers and
reuse the same underlying story in more than one q-block, worded to the specific angle each
question asks for — duplication here is a feature, not a violation of zero-fabrication, since it's
the same real story told two honest ways.

## Content Depth Calibration

The single biggest quality failure mode in either direction: answers that are too short to be
useful in a live conversation, or answers padded into a short story that nobody can deliver out
loud without notes. Calibrate every answer against these targets, spoken-word count, not written
word count:

- **Full STAR answer** (Role-Based or Behavioral): roughly 130-220 words total, delivered in
  45-75 seconds out loud. Situation 2-4 sentences (scale and stakes, not backstory), Task 1-2
  sentences (what was specifically owned), Action 3-5 sentences (this is where most of the length
  lives — real steps, tools named with expansions), Result 1-3 sentences (the metric plus a bold
  closer stating the transferable principle).
- **Inline fallback STAR**: same structure, can run shorter, 90-160 words, since it's a secondary
  angle rather than the primary answer.
- **Deep-dive questions**: allowed to run longer, 250-350 words, since these are meant to be fully
  narratable with real specifics if an interviewer wants to go deep. Still no filler — every extra
  sentence should be a fact, not a restatement.
- **Direct-answer / factual or definitional questions** (no STAR): 2-5 sentences. Lead with the
  plain-language version per the Simple First, Detail on Request technique, then stop.
- **Gap answers**: 3-4 sentences total, following the Gap Language Pattern exactly — no padding to
  make a genuine gap look bigger than it is, no clipping it so short it reads defensive.

If an honest answer would naturally run past these ranges, that's a signal to split it: keep the
primary answer inside the target range and let the fallback or a Deep Dive-style entry carry the
extra specificity, rather than stretching one answer into a monologue.

## STAR Specificity Requirements

Word count alone does not guarantee a usable answer. A STAR answer can land exactly inside the
Content Depth Calibration targets above and still be vague — hitting length is not the same as
hitting substance. Every answer needs to name real things, not describe them abstractly. A hard
number is the clearest way to do that when the data bank entry has one, but it isn't the only
valid form of specificity — the scope of the problem solved, the complexity of what was navigated,
whether it landed on or ahead of deadline, and documented customer or stakeholder satisfaction all
carry the same evidentiary weight when that's genuinely what the entry offers. What fails the
check either way is a generic descriptor with nothing real underneath it, numeric or otherwise.

- **Situation** always carries at least one concrete scale or stakes marker pulled directly from
  the matching data bank entry. That marker can be a dollar figure, a headcount, a requirement
  count, an asset count, or a timeline where one exists. Where it doesn't, the marker is the scope
  of the problem itself: how many systems or teams it touched, how entrenched or overlooked the
  issue was before it got addressed, what would have happened if it hadn't been caught, or what
  the accomplishment actually created that didn't exist before. "A large defense program" fails
  this check regardless of which version is available. "A $60M+ Test Support System of Systems
  program" passes it, and so does "a compliance framework nobody had successfully automated before
  across three prior attempts" when that is what the entry actually supports.
- **Task** names the specific thing owned, in the data bank's own language, not a category of
  responsibility. "Owned systems engineering integration" is too generic. "Primary USG systems
  engineering and program management lead integrator governing requirements, modeling, and
  interface design across multiple organizational boundaries" is what the entry actually says, and
  that specificity is what belongs in the answer.
- **Action** names the real tools, methods, and steps taken, each acronym expanded on first use,
  never a vague verb standing in for the work: "collaborated," "worked closely," "coordinated
  efforts" are all signals the action has been abstracted away. Two or three specific, sequential
  actions beat one broad description every time.
- **Result** always carries the actual outcome from the data bank. Where a metric exists, use it,
  never rounded off or softened. Where it doesn't, the result is the concrete before-and-after of
  the problem solved, on-time or ahead-of-deadline delivery, or documented customer or stakeholder
  satisfaction, whichever the entry actually supports. "It went well" is not a result under any
  version of this. "Zero post-release defects and documented physician adoption" is a result even
  with no dollar figure attached. Every version ends with the bold closer stating the transferable
  principle.

Before finalizing any STAR answer, check it directly against the matching data bank entry: does
the answer reproduce the specific numbers, names, and scope already written there, or has it
drifted into generic paraphrase during the rewrite for spoken delivery? Spoken-language rewrites
are exactly where specificity quietly gets lost, since smoothing an answer for how it sounds out
loud can sand off the concrete detail along with the stiffness. If it's drifted, pull the specifics
back in even if it costs a few extra words over the calibration target. Coverage against the JD
(see Non-Negotiable Rule 10) determines whether an answer exists; this check determines whether
the answer that exists is actually worth saying out loud.

## How to Build a Card

**Step 1** — Read the JD completely. Extract every explicit requirement, responsibility, preferred
qualification, key terminology, and program/product/mission context.

**Step 2** — Map the JD to the data bank. Every requirement gets a matched proof point. Where a
real gap exists, document it and build an honest bridge answer using the Gap Language Pattern.

**Step 3** — Identify what isn't in the JD but always gets asked: standard behavioral questions,
technical-depth questions a senior person in the domain would ask, ownership and independent-work
questions, judgment questions, gap questions for partial preferred qualifications.

**Step 4** — Build the card per the Card Structure above. Everything traces back to Steps 1-3. No
template content that doesn't connect to the JD.

## Technique Library

Reusable methods, not one-off answers. They apply to any question that wasn't specifically
anticipated — exactly when they matter most.

**Gap Language Pattern**, three parts. First, show real understanding — one plain sentence on what
the unfamiliar tool or concept actually does and why it matters. Second, be direct about the gap,
no hedging. Third, bridge to the specific real thing that relates. If nothing genuinely bridges,
leave it as an honest gap rather than forcing a connection.

**Simple First, Detail on Request.** Lead every technical answer with the plain-language version,
one to three sentences, no jargon stacking. Stop. Let the interviewer ask for more. The ability to
explain something complex simply is itself a signal of real understanding.

**Validated content tagging.** Once a specific answer or story is reported to have actually landed
well in a real conversation, tag it visibly — a green-accented badge reading something like
"Validated live, [interviewer] responded well to this." Validated content carries forward into
later rounds and gets reused with confidence rather than reinvented.

## Domain Fundamentals

> CUSTOMIZE: If your field has a well-known fundamentals canon that gets asked across companies
> regardless of the specific posting, list it here once. It gets built into the Role-Based
> Questions tab for any role in that field, regardless of what the JD emphasizes.

For any Systems Engineering role, always build in: the V-model walked end to end with the MBSE
artifact named at each stage (five-sentence plain version leading into the detailed one — this is
consistently the single most likely comprehensive SE interview question), INCOSE's technical
process list, the four verification methods (inspection, analysis, demonstration, test), the
INCOSE characteristics of a well-written requirement, what a Verification Cross Reference Matrix
is, the major technical reviews across a program lifecycle (SRR through PCA), functional/allocated/
product baselines, the purpose of a trade study, the distinction between a stakeholder need, a
system requirement, and a design specification, and a SysML diagram reference mapped to V-model
stage.

## Coverage Breadth, Not Just Coverage Depth

Non-Negotiable Rule 10 requires every JD requirement to get a matched proof point, but it is
possible to satisfy that rule while still producing an unbalanced card: pulling the JD-matched
proof point from the same one or two flagship accomplishments over and over because they are the
most recent or most senior-sounding. The data bank has fifteen BAE accomplishments across three
tracks alone, plus twelve at Northrop, fourteen at GE Healthcare, and twenty from the Air Force.
VTSN is one program among several under BAE's broader ISC contract with the ICBM directorate, not
a default stand-in for BAE work generally, and it should never be reached for automatically just
because it is the most familiar or most recent example. Before finalizing the Role-Based and
Behavioral tabs, check the spread across employers and across individual accomplishment entries,
not just the spread across JD requirements. If more than roughly a third of the primary STAR
answers trace back to the same single program, that is a signal to pull the fallback angle from a
different employer or a different accomplishment entirely rather than a different angle on the same
one. This applies especially to VTSN specifically, since recency and familiarity make it the
easiest one to over-reach for.

## Round-Specific Recalibration

Do not reuse the same Overview content across rounds with only the date changed. A recruiter
screen, a technical peer interview, and a full onsite panel each need a genuinely different
opening line, resume-walkthrough depth, closing script, and questions to ask, because they're
evaluating different things. Rebuild Overview's Summary, Pitch, Ask Them, and Closing subtabs
specifically for what this round actually is. Role-Based and Behavioral content typically carries
forward unchanged since the JD and company haven't changed.

## Interviewer Research Protocol

When an interviewer's name is known, look them up before building or updating the round's
Overview content. An interviewer's actual seniority, tenure, and specialty should shape what gets
emphasized — a manager gets different framing than an individual contributor, a specialist in
exactly your weak area gets different framing than a generalist. A documented shared employer,
program, school, or location is real rapport and belongs in the card explicitly, never forced.

## Chat-Specific Extras

The master skeleton defines the canonical shape: four tabs, always in this order, with a Study
tab added only per the Multi-Session and Onsite Days trigger below. That shape stays fixed across
every card built in this project.

Individual interview rounds can call for something the canonical shape doesn't cover — a live
coding round that needs a scratch-pad reference card, a case-study round that needs a framework
walkthrough, a whiteboard system-design round that needs a component checklist, a panel that asks
for a work-sample walkthrough. When that happens:

- Add it to **that round's card only**, as a clearly labeled extra — a distinct badge or card
  title such as "Round-Specific: Case Study Prep" so it's visibly not part of the standard shape.
- It still obeys every non-negotiable above: zero fabrication, no em dashes, STAR where it
  applies, quality checks, a search index entry, an inline fallback if it's a Q&A-shaped block.
- It does not get proposed as a change to the master skeleton file automatically. If something
  proves useful enough to want in every future card, that's a separate, explicit request — "add
  this to the skeleton" — not something that happens as a side effect of building one round's
  card.
- If it's unclear whether something belongs as a one-off extra or a real gap in the skeleton, ask
  rather than guessing either way.

## Multi-Session and Onsite Days

For any round involving multiple people across several hours where the card won't be open during
the day itself, build two things beyond the standard card:

**First**, a Study tab inside the main card, first in tab order, organized by the actual schedule
— one subtab per session in time order, each with a short summary of what to review and direct
links into the relevant Role-Based and Behavioral q-blocks for that specific person. Include a
Fundamentals subtab for domain-agnostic material that could come up with anyone.

**Second**, a standalone one-page markdown memorization sheet, meant to be read the night before
and the morning of, then set aside. It holds the anchor line, the core differentiators, the
technique library in condensed form, and the schedule with a one-line cue per person. This is not
a duplicate of the Study tab or of Study Mode — it's the compressed version meant to actually be
internalized rather than referenced live.

## Debrief and Re-Encode Loop

After every round, report what was actually asked, what landed, what didn't, and any real
information learned about people, process, or timeline. This gets folded back into the card
immediately: validated content gets tagged, new intel gets added, anything the card assumed that
turned out wrong gets corrected, not left standing. Before adding a new claim to a script (such as
"this was already discussed with the recruiting team"), confirm it against what was actually
reported rather than what the card previously assumed. The card should never say something
happened that didn't happen.

## Salary Range Determination

Determine the target range from the posted JD range and an honest fit assessment: meets-minimum-
only sits in the lower third, strong fit sits mid-range, plug-and-play with domain expertise
already being performed sits in the upper third. Target ask sits ten to fifteen percent above the
assessed tier. If a specific number has already been stated in a real conversation, the card
reflects that number as what was said, not as a theoretical target, and never claims a number was
discussed unless it actually was.

Always include, inside Overview > Summary: the fit-tier assessment, the recommended ask, the
leverage points to state before giving a number, and a verbatim script. A separate note covers
what to ask once an offer arrives — bonus structure, equity type and vesting, relocation terms —
never brought up during interviews themselves.

## Intel Tab Requirements

Eight to ten cards: a live-researched "Recent News & Talking Points" card, a "Team & Who You'd
Integrate With" card (per the Interviewer Research Protocol), org structure and who's actually in
the room, what the program or product really is with real sourced facts, the customer relationship
and how the background maps to it, day-to-day scope, strategic context for why this matters now,
five to seven numbered differentiators specific to this JD, what the role and title actually mean
in scope and authority, the direct domain-connection card, a full-width domain-concepts reference
pulling every term from the JD with honest gap notes, and a closing positioning statement.

## Clickable Term Tiles

Every term tile, both in Overview > Summary's "Key Terms" card and Intel's "Key Concepts: Full
Reference" card, is clickable and jumps straight to the q-block that actually backs it, using the
same `jumpTo()` engine the search bar uses. A term should never dead-end on its own definition when
there's a real story or answer sitting behind it elsewhere in the card.

- Each tile gets `class="term-tile" onclick="jumpTo('[id]')"`, where `[id]` is a real q-block or
  section id already registered in `ANCHOR_MAP`. Never point a tile at an id that doesn't exist.
- Add a short `term-jump-hint` line inside the tile ("→ [label]") so it's visible before tapping
  that this term has somewhere to go, not just a definition to read.
- If a term is an honest gap with no backing story, either point it at the relevant Gap Language
  q-block if one exists, or leave it non-clickable (plain tile, no onclick, no hint line) rather
  than linking it to something that doesn't actually address it.
- This is part of the same quality pass as everything else: when a tile's target changes or a new
  tile is added, confirm the id resolves in `ANCHOR_MAP` before presenting the file.

## Search Engine Requirements

Minimum 72 entries for a panel-level card, growing as content grows across rounds. Each entry
carries 15-25 tags: exact term, acronym (both forms), full phrase, synonym, conversational
phrasing, partial word, question form, relevant number or name. Eight standard entries never
change: opening pitch, closing script, mirroring, labeling, strategic silence, strength, weakness,
comp. Every new block added to the card — including fallback content and chat-specific extras —
gets a matching search entry at the same time, not as an afterthought.

## Quality Checks Before Presenting Any File

Both checks, every time, including after incremental mid-session edits:

- **JS syntax check** — extract the script block and run it through Node's function constructor to
  confirm it parses.
- **Div balance check** — count opening and closing div tags across the whole file (excluding the
  script block, to avoid false matches inside JS string literals), confirm they match.

Additionally, whenever links or navigation get added: confirm every target id exists and is
registered in `ANCHOR_MAP`, confirm the search index entry count and structure are intact, confirm
`SUBTABS` still matches the actual subtab panels present.

Div safety rules: fallback content inserted through scripted edits gets verified immediately after
insertion, not at the very end. Never close a block with a generic pattern — always match the
unique trailing text of that specific block.

## File Naming

- Prep cards: `company_role-short_r[N]_round-type_prep.html`
  (e.g. `true-anomaly_se3_r3_panel_prep.html`)
- Standalone memorization sheets for multi-session days:
  `company_role-short_onsite_memorization_sheet.md`

## What to Upload When Starting a New Chat

Master data bank (if not already project knowledge), resume submitted for this role, job
description as text, any recruiter or hiring-manager email content, program/product links if
provided.

Then say: **build me a Round [N] prep card for [Company], [Role Title].**

## What to Say After Each Round

Share what was actually asked (as close to verbatim as possible), what landed, what didn't, any
real intel learned about people, process, or timeline, and who's next if known. Mention anything
unusual about the round format if a chat-specific extra might be needed.

Then say: **update the card for Round [N+1] with [interviewer name].**
