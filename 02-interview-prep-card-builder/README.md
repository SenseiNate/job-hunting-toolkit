# Interview Prep Card Builder — Build Spec & Toolkit

This is the authoritative reference for how every interview prep card gets built. Claude reads
this file, `INTERVIEW_PREP_CARD_SKELETON_GOLD.html`, and the master data bank before building or
updating any card. This file is the full ruleset, including why each piece exists and how to
build toward it. `PROJECT_INSTRUCTIONS.md` (the
Project's custom instructions field) only holds what's personal — your profile, your data bank
pointer, your comp anchor — and a directive to follow this file for everything else. If any of
these ever seem to disagree on methodology, this file wins.

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
   your data bank and `INTERVIEW_PREP_CARD_SKELETON_GOLD.html` as
   project knowledge files.

## Using it for a new role

One chat per role, not per round — rounds for the same role build on each other in the same
thread. Start a new chat, upload the JD, the resume submitted for that role, and any
recruiter/hiring-manager emails (including any sample answers or scoring criteria they send — see
Focus Card below), then send the kickoff message in `KICKOFF_PROMPT.txt`. After each round, report
what actually happened and send the update message.

---

## What This Project Does

Builds a standalone, single-file HTML interview prep card for every round of every interview,
driven entirely by the job description, the submitted resume, and the master data bank. No
fabrication, no generic template filler — every story, stat, and answer traces back to something
real, and every bullet actually on the submitted resume gets a story that defends it, and every JD
requirement and preferred qualification gets a story or an honest gap answer.

The card's core inputs are the JD, the submitted resume, and the data bank. As a round progresses,
real information from actual conversations (recruiter emails, interviewer names, what was asked,
what landed, any scoring criteria or sample answers the recruiter sent) becomes an additional
input and takes priority over assumption.

## The Non-Negotiable Rules

1. **Zero fabrication.** Every metric, claim, and story traces to the data bank, the submitted
   resume, or something directly reported from a real conversation. A drafted deeper-dive line or
   follow-up that isn't yet backed by a data bank entry gets a red dot (see Flagging Drafted
   Content below) until it's confirmed, not presented as settled fact.
2. **No em dashes anywhere in card content.** Commas, periods, or natural sentence breaks only.
3. **Natural spoken language throughout**, per the Read-Aloud Language Rules below. The card gets
   read live or memorized beforehand. It sounds like a person talking, not a document being read.
   First person throughout, in every Action sentence, not just the opening pitch.
4. **All sections and blocks closed by default, and only one block open at a time.** Every block
   header shows a one-line cue underneath the question, visible without opening anything. Opening
   a new block closes whichever one was open, so the card never scrolls into a wall of expanded
   text — see Navigation below.
5. **Both quality checks pass before presenting any file** — every time, not just on first build.
   See Quality Checks below.
6. **STAR structure with unambiguous content** in every story block, with visible styled headers
   inside the prose. Factual, definitional, or judgment-call questions use a direct-answer format
   without STAR (a knowledge block, see Block Anatomy below). An honest gap uses the Gap Language
   Pattern instead of either.
7. **Domain terminology gets acronym expansions** on first use in each block *and* in each of its
   follow-ups, derived from the JD and data bank, in whichever register (defense-authentic or
   commercial-translated) the Sector-Coded Language Rule below calls for. A brand or product name
   that isn't itself an acronym (OEC, say) gets a short plain-language description instead of an
   expansion. Internal program jargon that means nothing outside the company it came from gets
   dropped from spoken text entirely rather than explained mid-answer.
8. **Every story block gets exactly one alternate story toggle** — see Block Anatomy below.
   Exceptions are fine for pure technique tips, questions to ask the interviewer, knowledge blocks,
   same-story pointer blocks in JD Question Stories (the alternate lives on the block they point
   to), and honest pure-gap answers with nothing real to bridge to.
9. **Salary range is determined by fit analysis**, not by stated targets, unless a specific number
   has already been communicated in a real conversation, in which case the card reflects what was
   actually said. Never claim a number was discussed unless it actually was.
10. **Every resume bullet and every JD line gets a story.** Every bullet on the submitted resume
    gets a primary defending story in the Resume Stories tab, checked bullet by bullet. A bullet
    covered only by an alternate story gets that story promoted to its own primary block. Every JD
    requirement, responsibility, and preferred qualification separately gets a block in the JD
    Question Stories tab (a full story, a pointer to a resume story that already answers it, or an
    honest Gap answer), and all of them are tracked on the JD Map card in Overview > Summary, so a
    real coverage gap against the posting is visible even when every resume bullet is already
    defended.
11. **No story told twice without a flag.** If the same real event backs two different blocks
    (because it answers two different questions honestly), the second occurrence gets a same-story
    flag pointing back to the first — see Same-Story Flag below. The card never presents the same
    event as if it were two different pieces of evidence.
12. **Compliance gets checked continuously**, not once at initial build. Any time content gets
    added mid-session, re-audit the affected sections before considering the work done: STAR
    headers present, alternate story present per story block, resume bullet coverage, JD Question Stories coverage, JD Map and
    `ANCHOR_MAP` entries added for anything new, search index entry added, jump-to dropdown option
    added.
13. **Technical rigor is held to a FAANG standard on every card, no matter the sector or the
    company.** This is independent of register: see FAANG-Level Rigor Standard below for what it
    requires and how it's different from the Sector-Coded Language Rule's vocabulary choices.
14. **Open-ended questions get their gap closed before they get an answer.** Any question without a
    clear scope (design, hypothetical, theoretical, or broad behavioral) is answered with ask,
    frame, outline, stop, never with a full unprompted answer. Every card carries an
    Open-ended questions block at the top of Technical Knowledge, see Open-Ended Questions below.

## Sector-Coded Language Rule

Every card gets one sector determination, made once at the start of the build and applied
consistently across the whole card, not decided answer by answer. The sector is fixed for the
target company and JD, so it never flips mid-card.

**Step 0, before any content gets drafted:** classify the target company as either Defense/
Government or Commercial/Enterprise/Startup, from the JD and what's known about the company. This
becomes part of Step 1 of How to Build a Card below, not a separate pass done after the fact.

**Defense/Government builds** use authentic defense terminology throughout: real program names,
real military acronyms, real agency and platform references, exactly as Non-Negotiable Rule 7
already requires, expanded on first use. No translation applied. This is the only register where
real program names and named mission partners appear as-is.

**Commercial/Enterprise/Startup builds** get the full Sector Translation Table from the master
data bank applied automatically, and not just to isolated terms. The data bank's own build rule
puts it plainly: every sentence in a commercial build should read like current big tech or
high-growth startup language, not stiff defense-coded prose translated word for word. That
standard governs prep cards the same way it governs resume bullets:

- No defense program names, military acronyms, classified-environment references, or mission-coded
  language anywhere in the card: not in STAR answers, not in Intel, not in the pitch, not in
  terminology tiles.
- Named mission partners are never named individually. Use the data bank's own generic substitute,
  or the specific translated term the Sector Translation Table gives for that entry.
- Every translated term runs through the Sector Translation Table first. Where a specific term
  isn't listed there, translate it in the same spirit the table demonstrates rather than leaving
  the original defense term in place.
- Register isn't just word-swapping. Rewrite full sentences to sound like a big tech or startup
  candidate actually talks: active outcome verbs, platform/roadmap/ownership vocabulary, numbers
  leading the sentence rather than buried at the end. Calibrate to the specific JD's flavor inside
  that range: a startup-flavored JD pulls toward ownership, 0-to-1, and scrappy framing; a
  big-tech-flavored JD pulls toward scale, cross-org, and metrics-driven framing. Neither reads like
  generic corporate boilerplate.
- This applies to every part of the card that carries language, not just STAR answers: Intel's
  program-context framing, the Key Terms and Key Concepts tiles, the opening pitch, and the resume
  walkthrough all get the same translation and register pass.
- **Keep one plain program description.** Even after translation, Intel's "What [Program/Product]
  Actually Is" card and the Interview Stage & Role Overview card each keep one unclassified, plain
  sentence describing what the system or product actually does. The point of translation is
  register, not opacity: if asked "what was the system?" the honest plain answer should already be
  sitting in the card, not something that has to be improvised live because everything on the page
  was written at one remove.

**The honest boundary line for restricted details.** Separately from translation, any follow-up
or deeper-dive line that would require naming a specific classification level, program name, or
other detail that genuinely can't be disclosed says so plainly: the word "restricted," then
whatever honest, unclassified context can still be given about scope, role, or outcome. This is
not a dodge and not a dramatic refusal, it's the same calm, direct tone as the rest of the card.
Never invent a plausible-sounding specific to avoid saying "restricted," and never let "restricted"
stand in for a detail that was simply never looked up.

Zero-fabrication still governs both registers absolutely. Translating a defense program name into
an enterprise-platform description is a register change on a real fact, not a new claim, since the
scale and nature of the work are unchanged. Translating in a way that implies different work, a
different employer type, or a different scope than what actually happened is fabrication
regardless of which register it's dressed in.

## FAANG-Level Rigor Standard

Every card, regardless of sector, is held to the level of detail and rigor you would want if you
were interviewing at a FAANG company. This never relaxes: a defense/government build is exactly as
rigorous as a commercial/enterprise build, a recruiter screen exactly as rigorous as an onsite
panel. It applies no matter which company the card is actually for.

This is a different axis from the Sector-Coded Language Rule above, not a restatement of it. That
rule decides which words a story gets told in, real defense terms or translated commercial
language. This rule decides how sharp and well-evidenced the story is underneath those words,
and it holds constant across both registers.

- **Lead with the real mechanism, not just the outcome.** Whenever the data bank documents the
  actual mechanism behind a result, the Action section uses it instead of stopping at the number.
  "Cut weekly merge time by 5 hours by eliminating unused project dependencies and establishing a
  single source of truth" beats "improved process efficiency." If the data bank or a future
  addendum to it holds mechanism-level detail that a past resume bullet compressed away, pull that
  detail into the block's Action sentences, deeper dive, and follow-ups, it's exactly the kind of
  specificity STAR Specificity Requirements already asks for, this just names where to look for it.
- **Never trade a real technical specific for leadership or scope language.** For senior,
  staff-plus, or leadership-level targets especially, find the sentence that carries both the
  technical substance and the scope, rather than dropping the technical detail to make room for
  "led," "owned," or "drove."
- **Never state a number with more precision than the data bank actually supports.** Where a
  figure in the data bank is approximate or unresolved, use the single most defensible version of
  it rather than presenting two conflicting numbers in the same card, and never invent false
  precision to sound more rigorous than the underlying fact is.
- **This bar applies everywhere in the card that carries content**, story blocks, knowledge blocks,
  the opening pitch, the resume walkthrough, Intel, not only the Resume Stories tab.

Zero-fabrication still governs this absolutely: sharpening an answer with real mechanism-level
detail from the data bank is not the same as inventing detail to sound sharper. If the data bank
doesn't have the mechanism, the answer stays at the level of detail the data bank actually
supports, phrased as directly and specifically as that level allows, rather than reaching for
invented specificity to hit this bar.

## Company Values Alignment and the Values Tab

At the same Step 1 research pass where sector gets classified, also check whether the target
company has publicly documented values, leadership principles, engineering practices, or a stated
operating philosophy: a well-known named example (Amazon's Leadership Principles, Google's
engineering practices, Meta's execution culture, or similar), or a smaller company's own About,
Careers, or Values page language. If nothing public and credible turns up, skip this step entirely
and don't build the Values tab described below (per Card Structure, it's an optional slot, omitted
whenever this check turns up nothing real). Never invent a company's values to build toward, and
never treat a generic guess ("they probably value teamwork") as a documented value.

When real, documented values exist, identify the two or three most relevant to this specific JD's
function, not a generic sweep of the whole published list. Use those two or three as a **selection
and framing lens** over content that is already real and already sourced from the JD, the resume,
and the data bank, never as license to add anything new. This lens governs:

- Which accomplishment becomes the anchor line in Overview's hero box.
- Which accomplishment leads the "Present" section of the opening elevator pitch.
- Which of two or more honestly-qualifying stories gets pulled forward as the primary block
  versus pushed to the alternate story, when a real tie exists between them.
- The closing sentence of Intel's Positioning Statement card.

The alignment has to live in the substance of what actually happened, never as a caption bolted
onto it afterward. A story that demonstrates ownership demonstrates it through what was decided and
done, not through the word "ownership" appearing anywhere in the answer. If a value's name would
only fit into an answer as a label ("this reflects a shared commitment to X"), that is the signal to
cut the label and trust the story on its own, not to add the label in. The value's name is never
said out loud inside an actual answer; the story is what shows it.

**Values tab (optional, see Card Structure).** One card per targeted value (2-5 cards, the
same two or three identified above, never a sweep of the whole published list): what it means to
you, why it matters at this company, one short real example, and links that jump straight to the
real story or stories that prove it (including the alternate-angle version). Skip this tab entirely
for a company whose values aren't publicly documented or genuinely interviewed against — the lens
above still applies to anchor-line and story selection even without the tab.

**Culture fit on every story.** Every story block, in Resume Stories, JD Question Stories, and
Extra Stories alike, is built to land with this specific company, not just to be true and well
structured. Step 1's research gathers more than named values: it also looks for how the company
describes the people it hires and keeps (its stated ethics, the traits interviewers say they screen
for, how it talks about ownership, safety, speed, customers, and mistakes, and what its recent news
and employee-facing material show about how it actually operates). Each story block carries a
one-line **Culture fit note** (coaching only, never said out loud) naming which of those real
signals the story shows through what actually happened, and the bold closer is phrased to fit them.
Same rules as the lens above: the signal must be documented and real (and cited in Intel), the
alignment lives in the substance of the story and never as a pasted-on label, and a story that
doesn't honestly fit a signal gets no note rather than a forced one. Where no values or culture
signals can be found, the note is omitted and the story is framed to the JD's own priorities.

## Repeatable Capability Anchor

Overview's hero box anchor line, the opening elevator pitch's "Future" close, and Intel's
Positioning Statement should read as one consistent case for hire, not three separately written
blurbs that happen to sit in the same card. Anchor all three to a single, repeatable capability
statement: one sentence describing the core thing done well across employers (finding the real
constraint in an unfamiliar system and getting the disconnected pieces moving together, say),
restated in each of the three spots and evidenced by whichever real accomplishment fits that
specific spot best.

The sentence is never copy-pasted verbatim between spots, or between different cards. Each time
it's used, it gets phrased in the target JD's own functional vocabulary, so it reads as fluent in
what this specific role actually does, not like a fixed slogan wearing different clothes. A systems
engineering JD pulls the capability statement toward requirements, architecture, and integration
language; a program or technical program management JD pulls it toward schedule, risk, and
cross-functional delivery language. Same underlying pattern every time, different fluent phrasing
every time, checked against that specific JD's own verbs, never against a fixed template sentence
carried over from the last card.

This is a consistency and positioning tool, not a new content source. The capability itself has to
be real and already evidenced somewhere in the data bank before it becomes the anchor, and it never
substitutes for the specific STAR proof points the rest of the card carries.

## Card Structure

Single standalone HTML file. All navigation, search, and content in one file, no external
dependencies beyond Google Fonts. Structure matches `INTERVIEW_PREP_CARD_SKELETON_GOLD.html` exactly.

**Tabs, always in this order:** Overview, Resume Stories, JD Question Stories, Extra Stories,
Technical Knowledge, Values (optional, see above), Intel.

- **Overview** — five subtabs: Summary, Pitch, Ask Them, Interview Tips, Closing.
  - **Summary** holds: the anchor line (3-4 sentences, best proof points plus why this industry,
    said in the first answer); the sticky essentials strip (clearance, target comp, anchor
    strength, known gap, location/onsite); the Focus Card (see below); the Resume Map (every
    submitted bullet, clickable, mapped to the story that defends it); Stage and Role (round, date,
    time, format, interviewer, role summary); the Interviewer Card (background, how to play it,
    real common ground, JD priorities in order — see Interviewer Research below); the JD Map
    (every JD line mapped to the story or answer that covers it); Recovery Lines ("if you lose your
    place"); and Logistics and Comp (join instructions, comp script, what to say if asked about
    comp early).
  - **Pitch** holds: why them (excited, specific, accurate, include "I learn new systems fast" when
    the domain is genuinely new), why leaving (factual, never negative), the opening elevator pitch
    (Past, Present, Future, plus an "outside work" line), and the resume walkthrough (2 minutes).
  - **Ask Them** is tiered: Recruiter level (process, level, logistics, clearance or licensing),
    Hiring Manager level, This Interviewer (specific to whoever's on this round), Ask Like a
    Teammate (phrased as if already on the team: scaling pain, handoffs, the first problem to pick
    up, how new hires ramp), and Peer or Panel level.
  - **Interview Tips / Closing** hold the technique library condensed (mirroring, labeling,
    strategic silence), the call structure, and the closing statement.
- **Resume Stories** — the resume actually submitted for this role, in order, grouped by company.
  Each bullet is quoted word for word in a gold box with its defending story directly under it.
  Bullets that share one real story are grouped above that single block. Every bullet must have a
  primary story; a bullet covered only by an alternate gets that alternate promoted to its own
  primary block (Non-Negotiable Rule 10). If no resume was submitted for the role, this tab is
  omitted and the core stories that would have lived here go to the top of Extra Stories instead.
- **JD Question Stories** — every requirement, responsibility, and preferred qualification from
  the JD, in the JD's own order, grouped as Required, Preferred, and Responsibilities. Each JD line
  is quoted word for word in a box with a Required or Preferred tag, and its story block directly
  under it. Where a resume story already answers the line, the block is a short pointer (a
  same-story flag, one or two sentences on the angle for this JD line, and its own follow-ups)
  instead of a second full retelling. Where the data bank holds a real story the resume doesn't
  carry, the block is a full Story block. Where nothing honest exists, the block is a Gap answer per
  the Gap Language Pattern, never padded.
- **Extra Stories** — stories that don't live in the resume or the JD lines, kept for extra context
  and in case they're needed, in this order: core stories (only when no resume was submitted),
  focus areas the recruiter or hiring team named (see Focus Card, if any), anything said in the
  pitch that isn't already covered elsewhere (every pitch claim needs a story), technical work not
  covered elsewhere, then behavioral questions grouped by type (strength, weakness, priorities,
  ambiguity, influence, customer, results, hiring, learning, failure, outside of work).
- **Technical Knowledge** — opens with the Open-ended questions block (see Open-Ended Questions
  below), then knowledge blocks built from the JD: standards and approach for this
  specific role, test and verification depth, scenario questions (troubleshoot it, design it), fit
  and logistics (why us, your moves, domain background, regulators, tools, AI use, relocation), and
  a collapsed Fundamentals group, opened only if the round goes textbook (see Domain Fundamentals
  below).
- **Values** — optional, see Company Values Alignment and the Values Tab above. Omitted entirely
  when the company has no real documented values.
- **Intel** — company, product, team, interviewer background, recent news, and competitors,
  researched live at build time. Never evergreen template content.

There is no separate Keywords or Fallbacks tab. Keyword-to-answer routing is handled by the search
bar and the jump-to dropdown (see Navigation below), and every alternate story lives inside the
block it belongs to.

### Focus Card (Overview > Summary, when applicable)

When a recruiter or hiring team has said in advance what they'll score, named values or
competencies, described the format, length, or number of interviewers, or sent sample answers,
that goes here verbatim: each named theme linked to the story blocks that answer it. If a sample
answer they sent contains a specific detail that isn't in the data bank, flag it the same way a
drafted follow-up gets flagged (see Flagging Drafted Content below) rather than quietly adopting
it as fact.

### Resume Map (Overview > Summary, required)

Every bullet on the submitted resume, clickable, linked to the Resume Stories block that defends
it. This is the single place that shows the resume itself is fully covered, the way the JD Map
shows the posting is fully covered. The two maps answer different questions (is every resume claim
defended, versus is every JD requirement answered) and both stay current.

### JD Map (Overview > Summary, required)

A card listing every JD requirement, responsibility, and preferred qualification phrase, quoted
verbatim, each linking to the JD Question Stories block that answers it, plus any other block that also backs it. This is how a coverage gap against the
posting gets caught before the call rather than during it, even when every resume bullet is
already defended by the Resume Map above. A JD line with no honest story shows up here as a link to
its Gap answer rather than a blank, so a real gap is visible and never hidden.

### Recovery Lines (Overview > Summary, required)

A card of 3-4 short things to say when buying a second to think, or redirecting a question that's
run long, so a real pause reads as thoughtful rather than as blanking. These are generic enough to
reuse across every card; customize only the one line that names the two angles a specific role
tends to split into (technical vs. process, supplier side vs. internal reporting, whatever fits).

## Block Anatomy

Two block types cover everything in Resume Stories, JD Question Stories, Extra Stories,
Technical Knowledge, and Values. Every block in the card is one of these two.

**Story block** (used in Resume Stories, JD Question Stories, Extra Stories, and story-shaped
parts of Values):

1. Number, question, one-line cue.
2. Badges: a gold note (focus or tip) and/or a red note (confirm before using), only when they
   genuinely apply.
3. Use-when line (which JD phrase, resume bullet, or focus theme this answers), with a one-line
   Culture fit note beside it (coaching only, never spoken; see Culture fit on every story above).
4. Story head: company plus the value or competency tags it's being used to demonstrate.
5. Same-story flag if this exact event appears elsewhere in the card (see Same-Story Flag below).
6. STAR: Situation, Task, Action, Result, a bold closing line stating the transferable principle,
   and a source line (company plus data bank entry ID).
7. Deeper dive: the hardest part, a hiccup and how it was recovered from, what could have gone
   wrong, what would be done differently. Only shown when expanded further, not part of the base
   60-90 second answer.
8. If they keep probing: follow-ups, always including a version of "what were the numbers" or
   "give me one example" for anything stated in general terms, and the honest boundary line for any
   restricted detail (see Sector-Coded Language Rule above).
9. Alternate story (toggle) — a genuinely different story or a different angle on the same one,
   with its own full STAR and its own source line.

**Knowledge block** (used in Technical Knowledge, and definitional/judgment questions anywhere
else in the card):

1. Direct answer, plain-language first, per Simple First, Detail on Request (see Technique
   Library below).
2. Deeper dive: where this has actually been used, how it tends to go wrong, what would get
   checked first in this company's specific domain.
3. Follow-ups, same honest-boundary and specificity rules as a story block's follow-ups.

Label every block on one line at the top using the skeleton's `story-head` element: "Main story ·
[Company]" for a STAR block, "Alternate story · [Company]" for its toggle, "Direct answer" for a
knowledge block, "Gap answer" for an honest-gap answer. This single line replaces any stacked
badge rows.

## Same-Story Flag

The same real event can honestly answer more than one question (a story about catching a
contractor gap might answer both "tell me about holding a vendor accountable" and "tell me about a
problem no one else caught"). That's fine, it's one real thing with two honest angles, but the card
never presents it twice as if it were two separate pieces of evidence.

The first time an event appears, it's a full block per Block Anatomy above. Every later block that
would otherwise retell the same event instead carries a same-story flag: a short note naming which
block already tells it in full, with a link there, plus (if there's a genuinely different detail
worth surfacing for this specific question) one or two sentences of the different angle rather than
the full STAR again. "Tell it once" is the rule; a same-story flag is how a second question that
honestly points at the same event gets handled without breaking that rule.

## Follow-Up Questions and Flagging Drafted Content

Every story block and knowledge block gets a "follow-ups" section holding 2-4 realistic follow-up
questions, each with a 1-3 sentence answer written to be read aloud, not a bullet of notes. Always
include a version of "what were the numbers" or "give me one example" for anything stated in
general terms, a version of "what would you do differently" somewhere across the card, and wherever
an answer has no hard metric, "how did you measure it" or an equivalent, answered with an honest
proxy rather than skipped. Where a follow-up would require naming a restricted detail, it uses the
honest boundary line from the Sector-Coded Language Rule above instead.

Tag every follow-up and deeper-dive line one of two ways, using the skeleton's `probe-tag` classes,
shown as a red dot until confirmed:

- **`confirm`** ("Only say it if true") — the line states a specific fact (a name, a number, a
  detail) that was drafted to fill out the follow-up or deeper dive but has not yet been confirmed
  against the data bank or a real conversation. This is the flag from Non-Negotiable Rule 1: it
  stays on until you confirm the specific is accurate, at which point the tag comes off and the
  line is treated as settled.
- **`draft`** ("Your judgment") — the line is your own honest approach or opinion, not a
  factual claim that needs a data bank source. It never needs the `confirm` flag, but it should
  still be rewritten in your voice rather than left generic.

A follow-up or deeper-dive line with no tag at all means it's already a confirmed fact with a real
source line elsewhere in the block. Never leave a drafted specific unflagged; that's exactly the
gap between "sounds right" and "is true" that Non-Negotiable Rule 1 exists to close.

## Read-Aloud Language Rules

Every sentence in every answer, including follow-ups and deeper dives, is written to be spoken,
not read silently.

- **Sentence length.** Cap sentences around 30 words. A sentence that needs a comma-separated list
  of more than two items usually wants to be two sentences instead.
- **No contrast framing.** Never write "it's not X, it's Y." Say what it is, directly.
- **Closers are personal, not slogans.** The bold closer at the end of a STAR Result is a first-
  person takeaway ("Now I always...", "I learned that...", "That's the habit I'd bring here"), never
  a tagline-style phrase that could sit on a poster.
- **No company jargon in spoken text.** A JD's or employer's internal shorthand doesn't carry over
  into the card's spoken language unless it's a real, expandable domain acronym per Non-Negotiable
  Rule 7. Dropped jargon doesn't need a replacement phrase; just say the thing plainly.
- **"I" in every action, not "we."** Every Action sentence is first person. See Directness and
  Ownership Check below for the full rule on this, since it governs more than just pronoun choice.
- **Honest "why."** When a block needs to explain why you did something, the honest register is
  "it had to get done" or "I was trusted to do it," not an inflated sense of mission.

## Content Depth Calibration

The single biggest quality failure mode in either direction: answers that are too short to be
useful in a live conversation, or answers padded into a short story that nobody can deliver out
loud without notes. Calibrate every answer against these targets, spoken-word count, not written
word count:

- **Full STAR block** (Resume Stories, JD Question Stories, or Extra Stories): roughly 150-230 words for the base answer,
  delivered in 60-90 seconds out loud. Situation 2-4 sentences (scale and stakes, not backstory),
  Task 1-2 sentences (what was specifically owned), Action 3-5 sentences (this is where most of the
  length lives — real steps, tools named with expansions), Result 1-3 sentences (the metric plus a
  bold closer stating the transferable principle). The deeper dive is additional and only surfaces
  when expanded or asked for, it is never folded into the base 60-90 second answer.
- **Open-ended answers** (see Open-Ended Questions): clarifying questions first, then a design
  outline of about 90 seconds or a theoretical answer of 30 to 45 seconds, then stop.
- **Alternate story**: same structure, can run shorter, 100-170 words, since it's a secondary angle
  rather than the primary block.
- **Knowledge block direct answer**: 2-5 sentences. Lead with the plain-language version per Simple
  First, Detail on Request, then stop.
- **Gap answers**: 3-4 sentences total, following the Gap Language Pattern exactly — no padding to
  make a genuine gap look bigger than it is, no clipping it so short it reads defensive.
- **Deeper dive**: 2-4 sentences per prompt (hardest part, hiccup and recovery, what could have
  gone wrong, what you'd do differently), shown only on request.
- **Follow-up answers**: 1-3 sentences, per Follow-Up Questions and Flagging Drafted Content above.

If an honest answer would naturally run past these ranges, that's a signal to split it: keep the
base STAR answer inside the target range and let the deeper dive, the alternate story, or a
follow-up carry the extra specificity, rather than stretching one answer into a monologue.

## STAR Specificity Requirements

Word count alone does not guarantee a usable answer. A STAR block can land exactly inside the
Content Depth Calibration targets above and still be vague — hitting length is not the same as
hitting substance. Every answer needs to name real things, not describe them abstractly. A hard
number is the clearest way to do that when the data bank entry has one, but it isn't the only valid
form of specificity — the scope of the problem solved, the complexity of what was navigated, whether
it landed on or ahead of deadline, and documented customer or stakeholder satisfaction all carry the
same evidentiary weight when that's genuinely what the entry offers. What fails the check either way
is a generic descriptor with nothing real underneath it, numeric or otherwise. See also the
FAANG-Level Rigor Standard above: that standard is what tells you to go looking for the real
mechanism behind a result, this section is what tells you how to verify the mechanism you found is
actually specific enough.

- **Situation** always carries at least one concrete scale or stakes marker pulled directly from the
  matching data bank entry. That marker can be a dollar figure, a headcount, a requirement count, an
  asset count, or a timeline where one exists. Where it doesn't, the marker is the scope of the
  problem itself: how many systems or teams it touched, how entrenched or overlooked the issue was
  before it got addressed, what would have happened if it hadn't been caught, or what the
  accomplishment actually created that didn't exist before. A vague descriptor fails this check
  regardless of which version is available; a concrete figure or a concretely scoped problem passes
  it.
- **Task** names the specific thing owned, in the data bank's own language, not a category of
  responsibility.
- **Action** names the real tools, methods, and steps taken, each acronym expanded on first use,
  never a vague verb standing in for the work: "collaborated," "worked closely," "coordinated
  efforts" are all signals the action has been abstracted away. Two or three specific, sequential
  actions beat one broad description every time.
- **Result** always carries the actual outcome from the data bank. Where a metric exists, use it,
  never rounded off or softened. Where it doesn't, the result is the concrete before-and-after of the
  problem solved, on-time or ahead-of-deadline delivery, or documented customer or stakeholder
  satisfaction, whichever the entry actually supports. Every version ends with the bold closer
  stating the transferable principle.

Before finalizing any STAR block, check it directly against the matching data bank entry: does the
answer reproduce the specific numbers, names, and scope already written there, or has it drifted
into generic paraphrase during the rewrite for spoken delivery? Spoken-language rewrites are exactly
where specificity quietly gets lost, since smoothing an answer for how it sounds out loud can sand
off the concrete detail along with the stiffness. If it's drifted, pull the specifics back in even
if it costs a few extra words over the calibration target. Coverage against the resume and the JD
(see Non-Negotiable Rule 10, the Resume Map, and the JD Map) determines whether a block exists; this
check determines whether the block that exists is actually worth saying out loud.

## Directness and Ownership Check

Specificity and directness are different failure modes, and an answer can pass one while still
failing the other. An answer can carry a real number, a real program name, and a real timeline and
still dodge the actual question, or describe the work in a way that hides what the person delivering
it specifically did. Both of the following get checked on every STAR block, separately from the
specificity check above.

**Does the answer actually answer the question asked.** Read the question as written, then read
only the first sentence of the Situation and the first sentence of the Result. If those two
sentences alone don't make clear what question is being answered, the answer has drifted into a
favorite story instead of a direct response. A question about handling pushback should produce an
answer about handling pushback, not an adjacent story about a hard deadline that technically involved
a disagreement somewhere in it. If the honest best story is a genuine stretch, the answer says so
briefly in one clause before telling it, rather than pretending it is a perfect match.

**Does the Action section show what was specifically done, not what happened around the person.**
Every Action sentence gets read with an eye for passive or team-diffused framing: "the team
implemented," "a decision was made to," "it was decided that," "the group worked through" are all
signals the actual individual contribution has been hidden behind the surrounding activity. Rewrite
these in first person with the specific verb for what was done. When a real result required a team,
name the individual's specific piece of it, not just that a team existed around the outcome. Two or
three first-person, specific-verb action sentences that clearly belong to the candidate beat five
sentences describing a collaborative process in the abstract.

Both checks run at the same time as the specificity check, on the same pass, not as a separate later
step: a drafted answer gets checked against the data bank for factual accuracy, against the question
for direct relevance, and against its own Action section for ownership language, before it's
considered finished.

## Open-Ended Questions: Close the Gap Before Answering

Applies to any question without a clear scope: design, hypothetical, theoretical, or broad
behavioral ("tell me about yourself," "how do you handle risk"). Thin information in a question is
often the test. A systems engineer gathers requirements before designing, and an interview is no
different. Never answer an open-ended question until the gap is closed.

1. **Ask first.** Before answering, ask 2 to 4 clarifying questions: users, primary goal,
   constraints, what success looks like. For a broad behavioral question, ask one scope question
   instead: "Do you want a specific example or my general approach?"
2. **Frame in one sentence.** Restate the problem and the worst outcome before solving it.
3. **Give the outline only.** Three or four points, one line each, 60 to 90 seconds.
4. **Stop and hand it back.** "Where do you want me to go deeper?"
5. **Keep detail in reserve.** Do not volunteer everything. Their follow-ups show what they care
   about, and covering every detail up front reads as unfocused, not thorough.

**Where it lives.** Every card gets an Open-ended questions block at the top of Technical
Knowledge (a knowledge block per Block Anatomy). It holds the steps above, 3 to 5 sample
clarifying questions written for this company's actual domain (not generic ones), and the stop
line. It is a required block on every card, including recruiter screens, since broad behavioral
questions show up there too.

**Answer length guide:**

- Behavioral STAR: 60 to 90 seconds.
- Design outline: 90 seconds, after clarifying.
- Theoretical: 30 to 45 seconds (the answer, one reason, one example, stop).

This sits alongside Simple First, Detail on Request in the Technique Library: that rule governs how
an answer is built once the question is clear, this one governs what happens before the question is
clear.

## How to Build a Card

**Step 1** — Read the JD and the submitted resume completely. Extract every explicit JD
requirement, responsibility, preferred qualification, key terminology, and program/product/mission
context, and every bullet actually on the submitted resume. Classify the target company as
Defense/Government or Commercial/Enterprise/Startup per the Sector-Coded Language Rule above, and
check for publicly documented company values per Company Values Alignment above, any recruiter-
stated scoring criteria for the Focus Card, and the broader culture signals (stated ethics, traits
interviewers say they screen for, how the company talks about ownership, safety, speed, customers,
and mistakes) that feed each story's Culture fit note. The FAANG-Level Rigor Standard above applies regardless
of what Step 1 finds; it isn't a third classification to make here, it's the constant bar every
later step is held to.

**Step 2** — Build the Resume Map first: match every submitted resume bullet to a real data bank
entry and draft its primary story block (Resume Stories tab). A bullet with no honest matching
entry is a problem to flag to you, not to paper over.

**Step 3** — Build the JD Question Stories tab and the JD Map: take every JD requirement,
responsibility, and preferred qualification in the JD's own order and give each one a block,
pointing at a Step 2 resume story where one already answers it (same-story flag), building a full
story block from a real data bank entry where the resume doesn't carry one, and building a Gap
answer with the Gap Language Pattern where nothing honest exists. Then build the JD Map in Overview
> Summary linking every JD line to its block.

**Step 4** — Identify what isn't covered by either map but always gets asked: standard behavioral
questions, technical-depth questions a senior person in the domain would ask, ownership and
independent-work questions, judgment questions, gap questions for partial preferred qualifications,
and a standard tenure answer (see Standard Tenure Answer below). These become Extra Stories and
Technical Knowledge blocks.

**Step 5** — Build the full card per Card Structure above, including the Open-ended questions
block at the top of Technical Knowledge with clarifying questions written for this company's
domain. Everything traces back to Steps 1-4. No
template content that doesn't connect to the resume, the JD, or the data bank.

## Technique Library

Reusable methods, not one-off answers. They apply to any question that wasn't specifically
anticipated — exactly when they matter most.

**Gap Language Pattern**, three parts. First, show real understanding — one plain sentence on what
the unfamiliar tool or concept actually does and why it matters. Second, be direct about the gap, no
hedging. Third, bridge to the specific real thing that relates. If nothing genuinely bridges, leave
it as an honest gap rather than forcing a connection.

**Simple First, Detail on Request.** Lead every technical answer with the plain-language version,
one to three sentences, no jargon stacking. Stop. Let the interviewer ask for more. The ability to
explain something complex simply is itself a signal of real understanding.

**Validated content tagging.** Once a specific answer or story is reported to have actually landed
well in a real conversation, tag it visibly — a short note reading something like "Validated live,
[interviewer] responded well to this." Validated content carries forward into later rounds and gets
reused with confidence rather than reinvented.

## Domain Fundamentals

> CUSTOMIZE: If your field has a well-known fundamentals canon that gets asked across companies
> regardless of the specific posting, list it here once. It gets built into the Technical Knowledge
> tab, as a collapsed Fundamentals group, opened only if the round goes textbook.

For any Systems Engineering role, always build in: the V-model walked end to end with the MBSE
artifact named at each stage (plain version leading into the detailed one — this is consistently the
single most likely comprehensive SE interview question), the four verification methods (inspection,
analysis, demonstration, test) and what a Verification Cross Reference Matrix is, the major
technical reviews across a program lifecycle, functional/allocated/product baselines, the purpose of
a trade study, the distinction between a stakeholder need, a system requirement, and a design
specification, a SysML diagram reference mapped to V-model stage, Technology/Manufacturing
Readiness Levels, and the basics of earned value (CPI/SPI) if the role touches program management at
all.

## Interviewer Research and the Interviewer Card

When an interviewer's name is known, look them up before building or updating the round's Overview
content. An interviewer's actual seniority, tenure, and specialty should shape what gets
emphasized — a manager gets different framing than an individual contributor, a specialist in
exactly your weak area gets different framing than a generalist. A documented shared employer,
program, school, or location is real rapport and belongs in the card explicitly, never forced.

This research becomes the **Interviewer Card** in Overview > Summary: background, how to play it
(what to lead with, what to go deeper on if asked), real common ground, and the JD priorities in
the order this specific interviewer is likely to weight them. Once a named interviewer's specialty
is known, also add a short group of knowledge blocks in Technical Knowledge matched to that
specialty, framed as backing up a specific JD line rather than floating free, tied back to a real
JD phrase or a clearly-labeled "deep dive" rationale. Build this only once a real interviewer and
specialty are known; don't speculate a depth group for a hypothetical panelist.

## Coverage Breadth, Not Just Coverage Depth

Non-Negotiable Rules 10 and 11 require every resume bullet and every JD requirement to get a
matched block, but it is possible to satisfy both while still producing an unbalanced card: pulling
proof points from the same one or two flagship accomplishments over and over because they are the
most recent or most senior-sounding. Before finalizing Resume Stories, JD Question Stories, Extra Stories, and Technical
Knowledge, check the spread across employers and across individual accomplishment entries, not just
the spread across resume bullets and JD requirements. If more than roughly a third of the primary
blocks trace back to the same single program, that is a signal to pull the alternate story from a
different employer or a different accomplishment entirely rather than a different angle on the same
one.

## Standard Tenure Answer

Every card gets a knowledge block covering "why so many moves" or an equivalent framing of career
tenure, inside Technical Knowledge's Fit and Logistics group, even when the interviewer doesn't ask
it outright — recruiters and hiring managers often weigh it silently. Build it from the data bank's
real, documented reasons for each move (contract endings, commute, acquisition, scope change,
whatever actually happened), never a vague gloss like "looking for new challenges." If the move
being discussed in this round is itself a reason tenure might look choppy (an internal transfer
ahead of a contract transition, say), state that plainly and frame it as evidence of staying power,
not as something to minimize.

## Solo Venture / Personal Project Boundary

The data bank's personal-project entries (side projects, independent tools, a portfolio site, and
similar) are marked there as personal, independent work, not professional experience. They never
serve as a primary block in Resume Stories, JD Question Stories, or Extra Stories, and never get presented as if they were
a job deliverable or employer accomplishment, however strong the story reads on its own.

If a question genuinely calls for this kind of material, such as being asked directly about side
projects, technical curiosity outside the day job, or how a tool gets used personally, a personal-
project entry can come up, framed exactly as the data bank frames it: something built independently
to learn, on personal time, separate from professional work. It does not get STAR-ified as a
polished employer accomplishment, and it does not substitute for a real employer proof point when a
resume bullet or JD requirement needs one. If no honest employer-sourced answer exists, that's a
gap to handle with the Gap Language Pattern, not an opening to reach for a personal-project entry
dressed up as professional experience.

## Round-Specific Recalibration

Do not reuse the same Overview content across rounds with only the date changed. A recruiter screen,
a technical peer interview, and a full onsite panel each need a genuinely different opening line,
resume-walkthrough depth, closing script, and questions to ask, because they're evaluating different
things. Rebuild Overview's Summary, Pitch, Ask Them, and Closing subtabs specifically for what this
round actually is, including a fresh Interviewer Card for whoever's on this round. Resume Stories,
JD Question Stories, Extra Stories, and Technical Knowledge content typically carries forward unchanged since the resume,
JD, and company haven't changed, though a depth group matched to a new interviewer's specialty may
be added.

## Chat-Specific Extras

The master skeleton defines the canonical shape described in Card Structure above. That shape stays
fixed across every card built in this project.

Individual interview rounds can call for something the canonical shape doesn't cover — a live coding
round that needs a scratch-pad reference card, a case-study round that needs a framework walkthrough,
a whiteboard system-design round that needs a component checklist, a panel that asks for a
work-sample walkthrough. When that happens:

- Add it to **that round's card only**, as a clearly labeled extra — a distinct group inside
  Technical Knowledge, or an Intel card, titled something like "Round-Specific: Case Study Prep" so
  it's visibly not part of the standard shape.
- It still obeys every non-negotiable above: zero fabrication, no em dashes, STAR where it applies,
  quality checks, a search index entry, a jump-to dropdown entry, an alternate story if it's a
  Q&A-shaped block.
- It does not get proposed as a change to the master skeleton file automatically. If something
  proves useful enough to want in every future card, that's a separate, explicit request — "add this
  to the skeleton" — not something that happens as a side effect of building one round's card.
- If it's unclear whether something belongs as a one-off extra or a real gap in the skeleton, ask
  rather than guessing either way.

## Multi-Session and Onsite Days

For any round involving multiple people across several hours where the card won't be open during the
day itself, build two things beyond the standard card:

**First**, a short "Round-Specific" group inside Technical Knowledge (per Chat-Specific Extras
above), organized by the actual schedule, with a short summary per session of what to review and
direct links into the relevant Resume Stories, JD Question Stories, Extra Stories, and Technical Knowledge blocks for that
specific person.

**Second**, a standalone one-page markdown memorization sheet, meant to be read the night before and
the morning of, then set aside. It holds the anchor line, the core differentiators, the technique
library in condensed form, and the schedule with a one-line cue per person. This is separate from the
Story Sheet companion file below, it's the compressed version meant to actually be internalized
rather than referenced live, built only for multi-session days.

## Companion File: Story Sheet

Every card gets a Story Sheet built alongside it, in both PDF and HTML: every story block in Resume
Stories order, then every JD Question Stories block, then every Extra Stories block, laid out as columns (question, company and tags, what
was actually done, result and closing line, alternate). The last page is a technical quick-reference
for this role's domain, pulling the same facts as Technical Knowledge's knowledge blocks into a
flat, printable sheet. This is the thing to glance at on a phone or print out, when the full
interactive card isn't practical to have open, a condensed, linear version of the same real content,
never a different or softer version of it. Rebuild it any time Resume Stories, JD Question Stories, or Extra Stories
content changes meaningfully, the same trigger that re-audits the card per Non-Negotiable Rule 12.

## Debrief and Re-Encode Loop

After every round, report what was actually asked, what landed, what didn't, and any real
information learned about people, process, or timeline. This gets folded back into the card
immediately: validated content gets tagged, new intel gets added, any follow-up or deeper-dive line
that was flagged `confirm` gets its tag removed once checked against what actually happened,
anything the card assumed that turned out wrong gets corrected, not left standing. Before adding a
new claim to a script (such as "this was already discussed with the recruiting team"), confirm it
against what was actually reported rather than what the card previously assumed. The card should
never say something happened that didn't happen.

When the data bank itself changes (an entry gets removed, corrected, or added), re-audit the card
the same way: a removed entry's blocks come out or get rebuilt from a different real entry, and
every resume bullet stays defended per Non-Negotiable Rule 10 even after the underlying data bank
changes.

## Salary Range Determination

Determine the target range from the posted JD range and an honest fit assessment: meets-minimum-only
sits in the lower third, strong fit sits mid-range, plug-and-play with domain expertise already being
performed sits in the upper third. Target ask sits ten to fifteen percent above the assessed tier. If
a specific number has already been stated in a real conversation, the card reflects that number as
what was said, not as a theoretical target, and never claims a number was discussed unless it
actually was.

Always include, inside Overview > Summary's Logistics and Comp card: the fit-tier assessment, the
recommended ask, the leverage points to state before giving a number, and a verbatim script for what
to say if comp comes up early. A separate note covers what to ask once an offer arrives — bonus
structure, equity type and vesting, relocation terms — never brought up during interviews themselves.

## Intel Tab Requirements

Eight to ten cards: a live-researched "Recent News & Talking Points" card, a "Team & Who You'd
Integrate With" card (built from the same research as the Interviewer Card), org structure and
who's actually in the room, what the program or product really is with real sourced facts (plus the
one plain, unclassified sentence per the Sector-Coded Language Rule), the customer relationship and
how the background maps to it, day-to-day scope, strategic context for why this matters now, five
to seven numbered differentiators specific to this JD, what the role and title actually mean in
scope and authority, competitors, the direct domain-connection card, a full-width domain-concepts
reference pulling every term from the JD with honest gap notes, and a closing positioning statement
that also names, in one short line, which two or three company values or principles the card's
strongest content was framed toward, per Company Values Alignment above (omit that line entirely
when no real documented values turned up for this company).

## Clickable Tiles and Maps

Every clickable surface in the card, the Resume Map, the JD Map, Key Terms tiles in Overview, and
Key Concepts tiles in Intel, jumps straight to the block that actually backs it, using the same
`jumpTo()` engine the search bar and jump-to dropdown use. Nothing should ever dead-end on its own
label when there's a real story or answer sitting behind it elsewhere in the card.

- Each tile or map row gets `onclick="jumpTo('[id]')"`, where `[id]` is a real block or section id
  already registered in `ANCHOR_MAP`. Never point one at an id that doesn't exist.
- Resume Map rows and JD Map rows show which block answers them directly in the row text; Key Terms
  and Key Concepts tiles add a short `term-jump-hint` line ("→ [label]") so it's visible before
  tapping that this term has somewhere to go, not just a definition to read.
- If a term or JD line is an honest gap with no backing story, either point it at the relevant Gap
  Language block if one exists, or leave it non-clickable (plain tile, no onclick, no hint line)
  rather than linking it to something that doesn't actually address it.
- This is part of the same quality pass as everything else: when a tile's or map row's target
  changes or a new one is added, confirm the id resolves in `ANCHOR_MAP` before presenting the file.

## Navigation

Every card gets the same navigation layer, wired to the same `ANCHOR_MAP`/`jumpTo()` engine as the
clickable tiles and maps above:

- **One block open at a time.** Opening a new story or knowledge block closes whichever block was
  previously open, anywhere in the card. This is Non-Negotiable Rule 4: the card never turns into a
  wall of expanded text, and there's always exactly one thing open to read.
- **Jump-to dropdown**, in the search bar, grouped by `<optgroup>` per tab (Overview, Resume
  Stories, JD Question Stories, Extra Stories, Technical Knowledge, Values, Intel). One `<option>` per block, card, or
  section id. Rebuild this list whenever a block is added, removed, or renamed; a stale dropdown is
  worse than none.
- **Full-text search**, triggered by typing in the search input. Press `/` anywhere on the page
  (outside the input) to focus it, `Esc` to close search and the results bar. The engine:
  - Strips filler/stop words ("what," "how," "do," "the," and similar) before scoring, so a
    conversational question matches as well as a terse keyword.
  - Applies light stemming and a per-card `SYN` synonym table (manager → leadership, deadline →
    schedule, and similar JD- or domain-specific pairs) so a plain-language rephrase still finds the
    right block.
  - Indexes each `SEARCH_INDEX` entry's own rendered text at load time (`indexText()`), not just its
    hand-written tags, so a search can match on anything actually said inside the block.
  - Shows a real snippet pulled from that matched text in the results list, not just a static
    sublabel, so the result shows why it matched.
- **Multi-step back.** A back button (and the Backspace key) steps back through the actual
  navigation history, not just one level, returning each time to the exact block that was open and
  the exact scroll position, so a chain of jumps can be unwound the same way it was made.
- **Sticky header and tab bar**, working at phone width, so the must-says and the five-to-seven tab
  buttons are always reachable without scrolling back to the top.
- Minimum 72 `SEARCH_INDEX` entries for a panel-level card, growing as content grows across rounds.
  Each entry carries 15-25 tags: exact term, acronym (both forms), full phrase, synonym,
  conversational phrasing, partial word, question form, relevant number or name. Eight standard
  entries never change: opening pitch, closing script, mirroring, labeling, strategic silence, JD
  Map, Resume Map, recovery lines, comp. Every new block added to the card, including alternate
  stories, follow-ups, and chat-specific extras, gets a matching search entry and a matching
  `ANCHOR_MAP` entry and jump-to dropdown option at the same time, not as an afterthought.

## Quality Checks Before Presenting Any File

All of the following, every time, including after incremental mid-session edits:

- **JS syntax check** — extract the script block and run it through Node's function constructor (or
  `node --check`) to confirm it parses.
- **Div balance check** — count opening and closing div tags across the whole file (excluding the
  script block, to avoid false matches inside JS string literals), confirm they match.
- **Link and navigation resolution** — every `jumpTo()`/`jumpAlt()` call, every jump-to dropdown
  option, every Resume Map and JD Map row, and every term tile resolves to a real id that exists and
  is registered in `ANCHOR_MAP`. Confirm `SUBTABS` still matches the actual subtab panels present.
- **Resume bullet coverage audit** — every bullet actually on the submitted resume has a primary
  story block in Resume Stories, per Non-Negotiable Rule 10. A bullet backed only by an alternate
  gets that alternate promoted.
- **JD coverage audit** — every JD requirement, responsibility, and preferred qualification has a
  block in JD Question Stories (a full story, a pointer to a resume story, or an honest Gap
  answer), quoted verbatim and linked from the JD Map.
- **Culture fit check** — every Culture fit note traces to a real documented value or culture
  signal cited in Intel, lives in what happened rather than a pasted label, and was not forced onto
  a story that doesn't honestly fit.
- **Same-story audit** — scan for any event told in full more than once; the second occurrence gets
  a same-story flag per Non-Negotiable Rule 11, not a second full retelling.
- **One-block-open check** — confirm opening any block closes whichever one was previously open,
  and that the multi-step back button and Backspace both return to the right block and scroll
  position.
- **Open-ended block check** — the Open-ended questions block exists at the top of Technical
  Knowledge, its sample clarifying questions are specific to this company's domain, and it is
  registered in `ANCHOR_MAP`, the search index, and the jump-to dropdown.
- **Acronym audit** — every acronym used in a block or a follow-up is expanded on its first use in
  that specific block. An acronym expanded once in the main answer still needs expanding again the
  first time it appears inside that block's own follow-ups, since a follow-up can get read out of
  order.
- **Language scan** — scan all card content for long sentences (over roughly 30 words), "it's not X,
  it's Y" contrast framing, third-person team-diffused action verbs ("the team," "it was decided"),
  and em dashes or en dashes used as sentence punctuation.
- **Rigor scan** — spot-check Action and Result sentences against the FAANG-Level Rigor Standard:
  does the sentence name the real mechanism when the data bank has one documented, or does it stop
  at the outcome. Flag any answer that settles for a vague outcome-only phrasing when a sharper,
  data-bank-backed version was available, and rewrite it before presenting.
- **Word count per answer** — spot-check STAR and direct answers against the Content Depth
  Calibration targets; flag anything well outside its range for a rewrite rather than letting a
  single answer run long unnoticed.
- **Browser check** — confirm the page renders correctly at both desktop and phone width (the
  skeleton's `@media (max-width:600px)` block covers most of this, but a visual check after major
  structural changes catches what the CSS rules alone don't).

Div safety rules: alternate stories, follow-up blocks, or new groups inserted through scripted edits
get verified immediately after insertion, not at the very end. Never close a block with a generic
pattern — always match the unique trailing text of that specific block.

## File Naming

- Prep cards: `company_role-short_r[N]_round-type_prep.html`
  (e.g. `acme_se3_r3_panel_prep.html`)
- Story Sheets: `company_role-short_story-sheet.html` and `company_role-short_story-sheet.pdf`,
  rebuilt alongside the card whenever Resume Stories, JD Question Stories, or Extra Stories content changes meaningfully.
- Standalone memorization sheets for multi-session days:
  `company_role-short_onsite_memorization_sheet.md`

## Build Process Note

The strongest recent builds in this project were assembled by hand, following this spec block by
block, and then checked against it. A parameterized generator script (resume + JD + data bank in, a
fully wired HTML card and Story Sheet out) would make the mechanical parts of this — `ANCHOR_MAP`
entries, search index entries, jump-to dropdown options, div/JS validation — impossible to get
wrong by construction rather than by careful checking. If a working generator script exists from an
earlier build, upload it to this project as a reference file and this section will be rewritten to
describe using it; until then, this spec and the skeleton file are
the source of truth, and every card still gets hand-assembled against all three plus the Quality
Checks above.

## What to Upload When Starting a New Chat

Master data bank (if not already project knowledge), resume submitted for this role, job description
as text, any recruiter or hiring-manager email content (including any stated scoring criteria,
named values, or sample answers, for the Focus Card), program/product links if provided.

Then say: **build me a Round [N] prep card for [Company], [Role Title].**

## What to Say After Each Round

Share what was actually asked (as close to verbatim as possible), what landed, what didn't, any real
intel learned about people, process, or timeline, and who's next if known. Mention anything unusual
about the round format if a chat-specific extra might be needed.

Then say: **update the card for Round [N+1] with [interviewer name].**
