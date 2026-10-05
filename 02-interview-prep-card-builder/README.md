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
   resume, or something directly reported from a real conversation. A drafted follow-up answer
   that isn't yet backed by a data bank entry gets flagged as drafted (see Flagging Drafted
   Content below) until it's confirmed, not presented as settled fact.
2. **No em dashes anywhere in card content.** Commas, periods, or natural sentence breaks only.
3. **Natural spoken language throughout**, per the Read-Aloud Language Rules below. The card gets
   read live or memorized beforehand. It sounds like a person talking, not a document being read.
   First person throughout, in every Action sentence, not just the opening pitch.
4. **All sections and q-blocks closed by default.** Every q-block header shows a one-line memory
   cue underneath the question, visible without opening anything — this is what makes the whole
   card scannable in seconds, the night before or live, with no separate study mode to toggle.
5. **Both quality checks pass before presenting any file** — every time, not just on first build.
   See Quality Checks below.
6. **STAR structure with unambiguous content** in every answer where it applies, with visible
   styled headers inside the prose. Factual, definitional, or judgment-call questions use a
   direct-answer format without STAR. An honest gap uses the Gap Language Pattern instead of
   either.
7. **Domain terminology gets acronym expansions** on first use in each answer *and* in each of its
   follow-ups, derived from the JD and data bank, in whichever register (defense-authentic or
   commercial-translated) the Sector-Coded Language Rule below calls for. A brand or product name
   that isn't itself an acronym (OEC, say) gets a short plain-language description instead of an
   expansion. Internal program jargon that means nothing outside the company it came from gets
   dropped from spoken text entirely rather than explained mid-answer.
8. **Every substantive q-block gets one inline fallback** — see Inline Fallback Model below.
   Exceptions are fine for pure technique tips, questions to ask the interviewer, and honest
   pure-gap answers with nothing real to bridge to.
9. **Salary range is determined by fit analysis**, not by stated targets, unless a specific number
   has already been communicated in a real conversation, in which case the card reflects what was
   actually said. Never claim a number was discussed unless it actually was.
10. **Coverage is determined by the JD, not by role type.** Every requirement, responsibility, and
    preferred qualification gets a matched answer, visible on the JD → Card Map (see below), then
    whatever isn't in the JD but always gets asked for that kind of work gets one too.
11. **Compliance gets checked continuously**, not once at initial build. Any time content gets
    added mid-session, re-audit the affected sections before considering the work done: STAR
    headers present, fallback present per q-block, JD → Card Map and `ANCHOR_MAP` entries added
    for anything new, search index entry added, jump-to dropdown option added.
12. **Technical rigor is held to a FAANG standard on every card, no matter the sector or the
    company.** This is independent of register: see FAANG-Level Rigor Standard below for what it
    requires and how it's different from the Sector-Coded Language Rule's vocabulary choices.

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

Zero-fabrication still governs both registers absolutely. Translating a defense program name into
an enterprise-platform description is a register change on a real fact, not a new claim, since the
scale and nature of the work are unchanged. Translating in a way that implies different work, a
different employer type, or a different scope than what actually happened is fabrication
regardless of which register it's dressed in.

## FAANG-Level Rigor Standard

Every card, regardless of sector, is held to the level of detail and rigor you'd want if you were
interviewing at a FAANG company. This never relaxes: a defense/government build is exactly as
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
  detail into the card's Action sentences and follow-ups, it's exactly the kind of specificity STAR
  Specificity Requirements already asks for, this just names where to look for it.
- **Never trade a real technical specific for leadership or scope language.** For senior,
  staff-plus, or leadership-level targets especially, find the sentence that carries both the
  technical substance and the scope, rather than dropping the technical detail to make room for
  "led," "owned," or "drove."
- **Never state a number with more precision than the data bank actually supports.** Where a
  figure in the data bank is approximate or unresolved, use the single most defensible version of
  it rather than presenting two conflicting numbers in the same card, and never invent false
  precision to sound more rigorous than the underlying fact is.
- **This bar applies everywhere in the card that carries content**, STAR answers, follow-ups, the
  opening pitch, the resume walkthrough, Intel, not only the flagship Role-Based questions.

Zero-fabrication still governs this absolutely: sharpening an answer with real mechanism-level
detail from the data bank is not the same as inventing detail to sound sharper. If the data bank
doesn't have the mechanism, the answer stays at the level of detail the data bank actually
supports, phrased as directly and specifically as that level allows, rather than reaching for
invented specificity to hit this bar.

## Company Values & Culture Alignment

At the same Step 1 research pass where sector gets classified, also check whether the target
company has publicly documented values, leadership principles, engineering practices, or a stated
operating philosophy: a well-known named example (Amazon's Leadership Principles, Google's
engineering practices, Meta's execution culture, or similar), or a smaller company's own About,
Careers, or Values page language. If nothing public and credible turns up, skip this step entirely
and don't build the Company Values Picker described below. Never invent a company's values to
build toward, and never treat a generic guess ("they probably value teamwork") as a documented
value.

When real, documented values exist, identify the two or three most relevant to this specific JD's
function, not a generic sweep of the whole published list. Use those two or three as a **selection
and framing lens** over content that is already real and already sourced from the JD and the data
bank, never as license to add anything new. This lens governs:

- Which accomplishment becomes the anchor line in Overview's hero box.
- Which accomplishment leads the "Present" section of the opening elevator pitch.
- Which of two or more honestly-qualifying stories gets pulled forward as the primary STAR answer
  versus pushed to the inline fallback, when a real tie exists between them.
- The closing sentence of Intel's Positioning Statement card.

The alignment has to live in the substance of what actually happened, never as a caption bolted
onto it afterward. A story that demonstrates ownership demonstrates it through what was decided and
done, not through the word "ownership" appearing anywhere in the answer. If a value's name would
only fit into an answer as a label ("this reflects a shared commitment to X"), that is the signal to
cut the label and trust the story on its own, not to add the label in. The value's name is never
said out loud inside an actual answer; the story is what shows it.

Name which two or three values or principles were targeted, visibly, in a short note inside Intel's
Positioning Statement card, so the framing is there to check against rather than buried inside the
build process. This never overrides zero-fabrication: it is a lens for choosing and emphasizing
real accomplishments already in the data bank, never justification for reshaping a story into
something it wasn't.

**Company Values Picker (Behavioral tab, optional UI element).** When the company's values are
prominent enough in how it actually interviews — most visibly Amazon's Leadership Principles, where
interviewers frequently ask "what does [principle] mean to you" directly — build the picker from
the skeleton's `lp-grid`/`lp-row` pattern: one row per targeted value (2-5 rows, the same two or
three identified above, never a sweep of the whole published list), each expandable to "what it
means to me," "why it matters here," and a short quick example, plus chips that jump straight to
the real story or stories that prove it (including the alternate-angle version via `jumpAlt()`).
Skip this element entirely for a company whose values aren't interviewed against this directly —
the lens above still applies to anchor-line and story selection even without the picker UI.

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
dependencies beyond Google Fonts. Structure matches `INTERVIEW_PREP_CARD_SKELETON_GOLD.html`
exactly.

**Four tabs, always in this order:** Overview, Role-Based Questions, Behavioral, Intel.

- **Overview** — five subtabs: Summary (stage, role, location, pay range and recommended ask,
  total comp if offered, the JD → Card Map, the Key Terms tiles, and the recovery-lines card),
  Pitch (why-them, why-leaving, the opening elevator pitch), Ask Them (questions to ask, split into
  recruiter / hiring-manager / peer tiers), Interview Tips (the technique library, condensed —
  mirroring, labeling, strategic silence), Closing (the last-60-seconds script).
- **Role-Based Questions** — organized by JD line, not by likelihood. A short table of contents at
  the top jumps to each group. Each group quotes the JD requirement or responsibility it answers
  verbatim, then holds every q-block that answers it: responsibility-based questions, ownership and
  independent-work questions, fully narratable deep-dive examples, and technical/domain-depth
  questions. A Fundamentals group (domain-agnostic SE/field basics, see Domain Fundamentals below)
  and, where the round calls for it, a round-specific depth group matched to a named interviewer's
  specialty (see Depth Matched to the Interviewer below) both fold in here as ordinary groups, never
  as separate tabs.
- **Behavioral** — optionally opens with the Company Values Picker (see Company Values & Culture
  Alignment above) when the target company's values warrant it, then the fixed-order list: strength
  (two angles), weakness (real, with a real fix), competing priorities, a problem or risk no one
  else caught, an ambiguous environment handled without a clear mandate, influence without formal
  authority, pushback on budget, scope, or cost, and a genuine mistake with what changed after it.
  Every one gets a full STAR answer built from a real story, never a pointer to improvise from.
- **Intel** — company, org, and program context, researched live at build time. Always includes a
  "Recent News & Talking Points" card and a "Team & Who You'd Integrate With" card, both sourced
  from a live search done as part of the build, never evergreen template content.

There are no separate Keywords, Stories, or Fallbacks tabs. Keyword-to-answer routing is handled by
the search bar and the jump-to dropdown (see Search Engine below), and stories live directly inside
the q-block they answer rather than in a shared tab reached by cross-links.

### Sticky Essentials Strip (Overview tab, required)

A thin bar pinned under the subtab nav while scrolling the Overview tab, holding the 3-5 absolute
must-says for this call: clearance line (if applicable), target comp, anchor differentiator,
location/relocation stance. Visible without opening anything.

### JD → Card Map (Overview > Summary, required)

A card listing every JD requirement, responsibility, and preferred qualification phrase, quoted
verbatim, each linking to every q-block that answers it. This is the single place that shows what
the card is actually covering against what the interviewer is actually scoring, and it is how a
coverage gap gets caught before the call rather than during it. Anything genuinely not represented
on this map after a build is a lower-priority gap per Non-Negotiable Rule 10, not an oversight to
quietly leave unflagged.

### Recovery Lines (Overview > Summary, required)

A card of 3-4 short things to say when buying a second to think, or redirecting a question that's
run long, so a real pause reads as thoughtful rather than as blanking. These are generic enough to
reuse across every card; customize only the one line that names the two angles a specific role
tends to split into (technical vs. process, supplier side vs. internal reporting, whatever fits).

## Inline Fallback Model

Every substantive q-block in Role-Based and Behavioral gets exactly one fallback, living inside
that same q-block behind an "🔄 Alternate story" toggle — no separate tab, no cross-links to chase.
Use it when the interviewer might go deeper, or when the same question could plausibly get asked by
a second person on the same day and repeating the identical answer would read as rehearsed. The
fallback is either a genuinely different story or a different angle on the same story, with its own
full STAR and its own `story-source` line.

Label every primary answer and its fallback on one line at the top of the answer, using the
skeleton's `story-head` element: "Main story · [Company]" for a STAR answer, "Alternate story ·
[Company]" for the fallback, "Direct answer" for a no-STAR factual/judgment answer, "Gap answer" for
an honest-gap answer. This single line replaces the old stacked tip-badge rows.

This is deliberately simpler than a shared story pool with cross-links: each question is
self-contained, so nothing needs to be looked up mid-answer. When drafting, it's fine to pull from a
mental pool of your strongest 10-15 reusable stories across employers and reuse the same underlying
story in more than one q-block, worded to the specific angle each question asks for — duplication
here is a feature, not a violation of zero-fabrication, since it's the same real story told two
honest ways.

## Follow-Up Questions and Flagging Drafted Content

Every substantive q-block (Role-Based, Behavioral, and the fundamentals/depth groups) gets a
"Likely follow-ups" block holding 2-4 realistic follow-up questions, each with a 1-3 sentence
answer written to be read aloud, not a bullet of notes. Always include a version of "what would you
do differently" somewhere across the card, and wherever an answer has no hard metric, include "how
did you measure it" or an equivalent, answered with an honest proxy rather than skipped.

Tag every follow-up answer one of two ways, using the skeleton's `probe-tag` classes:

- **`confirm`** ("Only say it if true") — the answer states a specific fact (a name, a number, a
  detail) that was drafted to fill out the follow-up but has not yet been confirmed against the
  data bank or a real conversation. This is the flag from Non-Negotiable Rule 1: it stays on until
  you confirm the specific is accurate, at which point the tag comes off and the line is treated
  as settled.
- **`draft`** ("Your judgment") — the answer is your own honest approach or opinion, not a
  factual claim that needs a data bank source. It never needs the `confirm` flag, but it should
  still be rewritten in your voice rather than left generic.

A follow-up answer with no tag at all means it's already a confirmed fact with a real source line
elsewhere in the q-block. Never leave a drafted specific unflagged; that's exactly the gap between
"sounds right" and "is true" that Non-Negotiable Rule 1 exists to close.

## Read-Aloud Language Rules

Every sentence in every answer, including follow-ups, is written to be spoken, not read silently.

- **Sentence length.** Cap sentences around 30 words. A sentence that needs a comma-separated list
  of more than two items usually wants to be two sentences instead.
- **No contrast framing.** Never write "it's not X, it's Y." Say what it is, directly.
- **Closers are personal, not slogans.** The bold closer at the end of a STAR Result is a first-
  person takeaway ("Now I always...", "I learned that...", "That's the habit I'd bring here"), never
  a tagline-style phrase that could sit on a poster.
- **No company jargon in spoken text.** A JD's or employer's internal shorthand doesn't carry over
  into the card's spoken language unless it's a real, expandable domain acronym per Non-Negotiable
  Rule 7. Dropped jargon doesn't need a replacement phrase; just say the thing plainly.
- **"I" in every action.** Every Action sentence is first person. See Directness and Ownership
  Check below for the full rule on this, since it governs more than just pronoun choice.

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
- **Direct-answer / factual, definitional, or judgment questions** (no STAR): 2-5 sentences. Lead
  with the plain-language version per the Simple First, Detail on Request technique, then stop.
- **Gap answers**: 3-4 sentences total, following the Gap Language Pattern exactly — no padding to
  make a genuine gap look bigger than it is, no clipping it so short it reads defensive.
- **Follow-up answers**: 1-3 sentences, per Follow-Up Questions and Flagging Drafted Content above.

If an honest answer would naturally run past these ranges, that's a signal to split it: keep the
primary answer inside the target range and let the fallback, a follow-up, or a Deep Dive-style entry
carry the extra specificity, rather than stretching one answer into a monologue.

## STAR Specificity Requirements

Word count alone does not guarantee a usable answer. A STAR answer can land exactly inside the
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

Before finalizing any STAR answer, check it directly against the matching data bank entry: does the
answer reproduce the specific numbers, names, and scope already written there, or has it drifted
into generic paraphrase during the rewrite for spoken delivery? Spoken-language rewrites are exactly
where specificity quietly gets lost, since smoothing an answer for how it sounds out loud can sand
off the concrete detail along with the stiffness. If it's drifted, pull the specifics back in even
if it costs a few extra words over the calibration target. Coverage against the JD (see Non-
Negotiable Rule 10 and the JD → Card Map) determines whether an answer exists; this check determines
whether the answer that exists is actually worth saying out loud.

## Directness and Ownership Check

Specificity and directness are different failure modes, and an answer can pass one while still
failing the other. An answer can carry a real number, a real program name, and a real timeline and
still dodge the actual question, or describe the work in a way that hides what the person delivering
it specifically did. Both of the following get checked on every STAR answer, separately from the
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

## How to Build a Card

**Step 1** — Read the JD completely. Extract every explicit requirement, responsibility, preferred
qualification, key terminology, and program/product/mission context. As part of this step, classify
the target company as Defense/Government or Commercial/Enterprise/Startup per the Sector-Coded
Language Rule above, and check for publicly documented company values per Company Values & Culture
Alignment above, since both determinations shape how every later step gets written, not just which
facts get pulled. The FAANG-Level Rigor Standard above applies regardless of what Step 1 finds; it
isn't a third classification to make here, it's the constant bar every later step is held to.

**Step 2** — Build the JD → Card Map first, grouping JD requirements, responsibilities, and
preferred qualifications into the groups that will structure the Role-Based tab. Map every JD line
to a matched proof point from the data bank. Where a real gap exists, document it and build an
honest bridge answer using the Gap Language Pattern.

**Step 3** — Identify what isn't in the JD but always gets asked: standard behavioral questions,
technical-depth questions a senior person in the domain would ask, ownership and independent-work
questions, judgment questions, gap questions for partial preferred qualifications, and a standard
tenure answer (see Standard Tenure Answer below).

**Step 4** — Build the card per the Card Structure above. Everything traces back to Steps 1-3. No
template content that doesn't connect to the JD.

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
> regardless of the specific posting, list it here once. It gets built into the Role-Based Questions
> tab, as its own Fundamentals group, for any role in that field, regardless of what the JD
> emphasizes.

For any Systems Engineering role, always build in: the V-model walked end to end with the MBSE
artifact named at each stage (plain version leading into the detailed one — this is consistently the
single most likely comprehensive SE interview question), the four verification methods (inspection,
analysis, demonstration, test) and what a Verification Cross Reference Matrix is, the major
technical reviews across a program lifecycle, functional/allocated/product baselines, the purpose of
a trade study, the distinction between a stakeholder need, a system requirement, and a design
specification, a SysML diagram reference mapped to V-model stage, Technology/Manufacturing
Readiness Levels, and the basics of earned value (CPI/SPI) if the role touches program management at
all.

## Depth Matched to the Interviewer

Per the Interviewer Research Protocol below, once a named interviewer's specialty is known (test,
software, safety, a particular subsystem), add a short group of direct answers in that specialty,
inside the Role-Based tab, framed as backing up a specific JD line rather than floating free. This
is a group like any other in the JD → Card Map structure: it gets a `jd-group` entry, a TOC link,
and its own short set of q-blocks, each still tied back to a real JD phrase or a clearly-labeled
"deep dive" rationale. Build this only once a real interviewer and specialty are known; don't
speculate a depth group for a hypothetical panelist.

## Coverage Breadth, Not Just Coverage Depth

Non-Negotiable Rule 10 requires every JD requirement to get a matched proof point, but it is
possible to satisfy that rule while still producing an unbalanced card: pulling the JD-matched proof
point from the same one or two flagship accomplishments over and over because they are the most
recent or most senior-sounding. Before finalizing the Role-Based and Behavioral tabs, check the
spread across employers and across individual accomplishment entries, not just the spread across JD
requirements, listed on the JD → Card Map. If more than roughly a third of the primary STAR answers
trace back to the same single program, that is a signal to pull the fallback angle from a different
employer or a different accomplishment entirely rather than a different angle on the same one.

## Standard Tenure Answer

Every card gets a direct-answer q-block covering "why so many moves" or an equivalent framing of
career tenure, even when the interviewer doesn't ask it outright — recruiters and hiring managers
often weigh it silently. Build it from the data bank's real, documented reasons for each move
(contract endings, commute, acquisition, scope change, whatever actually happened), never a vague
gloss like "looking for new challenges." If the move being discussed in this round is itself a
reason tenure might look choppy (an internal transfer ahead of a contract transition, say), state
that plainly and frame it as evidence of staying power, not as something to minimize.

## Solo Venture / Personal Project Boundary

The data bank's personal-project entries (side projects, independent tools, a portfolio site, and
similar) are marked there as personal, independent work, not professional experience. They never
serve as a primary STAR proof point in Role-Based or Behavioral answers, and never get presented as
if they were a job deliverable or employer accomplishment, however strong the story reads on its
own.

If a question genuinely calls for this kind of material, such as being asked directly about side
projects, technical curiosity outside the day job, or how a tool gets used personally, a personal-
project entry can come up, framed exactly as the data bank frames it: something built independently
to learn, on personal time, separate from professional work. It does not get STAR-ified as a
polished employer accomplishment, and it does not substitute for a real employer proof point when a
JD requirement needs one. If no honest employer-sourced answer exists for a requirement, that's a
gap to handle with the Gap Language Pattern, not an opening to reach for a personal-project entry
dressed up as professional experience.

## Round-Specific Recalibration

Do not reuse the same Overview content across rounds with only the date changed. A recruiter screen,
a technical peer interview, and a full onsite panel each need a genuinely different opening line,
resume-walkthrough depth, closing script, and questions to ask, because they're evaluating different
things. Rebuild Overview's Summary, Pitch, Ask Them, and Closing subtabs specifically for what this
round actually is. Role-Based and Behavioral content typically carries forward unchanged since the
JD and company haven't changed, though a Depth Matched to the Interviewer group may be added once a
new interviewer's specialty is known.

## Interviewer Research Protocol

When an interviewer's name is known, look them up before building or updating the round's Overview
content. An interviewer's actual seniority, tenure, and specialty should shape what gets emphasized
— a manager gets different framing than an individual contributor, a specialist in exactly your weak
area gets different framing than a generalist, and a specialist's area is exactly what the Depth
Matched to the Interviewer group above is for. A documented shared employer, program, school, or
location is real rapport and belongs in the card explicitly, never forced.

## Chat-Specific Extras

The master skeleton defines the canonical shape: four tabs, always in this order. That shape stays
fixed across every card built in this project.

Individual interview rounds can call for something the canonical shape doesn't cover — a live coding
round that needs a scratch-pad reference card, a case-study round that needs a framework walkthrough,
a whiteboard system-design round that needs a component checklist, a panel that asks for a
work-sample walkthrough. When that happens:

- Add it to **that round's card only**, as a clearly labeled extra — a distinct `jd-group` or intel
  card titled something like "Round-Specific: Case Study Prep" so it's visibly not part of the
  standard shape.
- It still obeys every non-negotiable above: zero fabrication, no em dashes, STAR where it applies,
  quality checks, a search index entry, a jump-to dropdown entry, an inline fallback if it's a
  Q&A-shaped block.
- It does not get proposed as a change to the master skeleton file automatically. If something
  proves useful enough to want in every future card, that's a separate, explicit request — "add this
  to the skeleton" — not something that happens as a side effect of building one round's card.
- If it's unclear whether something belongs as a one-off extra or a real gap in the skeleton, ask
  rather than guessing either way.

## Multi-Session and Onsite Days

For any round involving multiple people across several hours where the card won't be open during the
day itself, build two things beyond the standard card:

**First**, a short "Round-Specific" group inside the Role-Based tab (per Chat-Specific Extras above),
organized by the actual schedule, with a short summary per session of what to review and direct
links into the relevant Role-Based and Behavioral q-blocks for that specific person.

**Second**, a standalone one-page markdown memorization sheet, meant to be read the night before and
the morning of, then set aside. It holds the anchor line, the core differentiators, the technique
library in condensed form, and the schedule with a one-line cue per person. This is not a duplicate
of anything inside the card — it's the compressed version meant to actually be internalized rather
than referenced live.

## Debrief and Re-Encode Loop

After every round, report what was actually asked, what landed, what didn't, and any real
information learned about people, process, or timeline. This gets folded back into the card
immediately: validated content gets tagged, new intel gets added, any follow-up answer that was
flagged `confirm` gets its tag removed once checked against what actually happened, anything the
card assumed that turned out wrong gets corrected, not left standing. Before adding a new claim to a
script (such as "this was already discussed with the recruiting team"), confirm it against what was
actually reported rather than what the card previously assumed. The card should never say something
happened that didn't happen.

## Salary Range Determination

Determine the target range from the posted JD range and an honest fit assessment: meets-minimum-only
sits in the lower third, strong fit sits mid-range, plug-and-play with domain expertise already being
performed sits in the upper third. Target ask sits ten to fifteen percent above the assessed tier. If
a specific number has already been stated in a real conversation, the card reflects that number as
what was said, not as a theoretical target, and never claims a number was discussed unless it
actually was.

Always include, inside Overview > Summary: the fit-tier assessment, the recommended ask, the
leverage points to state before giving a number, and a verbatim script. A separate note covers what
to ask once an offer arrives — bonus structure, equity type and vesting, relocation terms — never
brought up during interviews themselves.

## Intel Tab Requirements

Eight to ten cards: a live-researched "Recent News & Talking Points" card, a "Team & Who You'd
Integrate With" card (per the Interviewer Research Protocol), org structure and who's actually in the
room, what the program or product really is with real sourced facts (plus the one plain,
unclassified sentence per the Sector-Coded Language Rule), the customer relationship and how the
background maps to it, day-to-day scope, strategic context for why this matters now, five to seven
numbered differentiators specific to this JD, what the role and title actually mean in scope and
authority, the direct domain-connection card, a full-width domain-concepts reference pulling every
term from the JD with honest gap notes, and a closing positioning statement that also names, in one
short line, which two or three company values or principles the card's strongest content was framed
toward, per Company Values & Culture Alignment above (omit that line entirely when no real
documented values turned up for this company).

## Clickable Term Tiles

Every term tile, both in Overview > Summary's "Key Terms" card and Intel's "Key Concepts: Full
Reference" card, is clickable and jumps straight to the q-block that actually backs it, using the
same `jumpTo()` engine the search bar and jump-to dropdown use. A term should never dead-end on its
own definition when there's a real story or answer sitting behind it elsewhere in the card.

- Each tile gets `class="term-tile" onclick="jumpTo('[id]')"`, where `[id]` is a real q-block or
  section id already registered in `ANCHOR_MAP`. Never point a tile at an id that doesn't exist.
- Add a short `term-jump-hint` line inside the tile ("→ [label]") so it's visible before tapping that
  this term has somewhere to go, not just a definition to read.
- If a term is an honest gap with no backing story, either point it at the relevant Gap Language
  q-block if one exists, or leave it non-clickable (plain tile, no onclick, no hint line) rather than
  linking it to something that doesn't actually address it.
- This is part of the same quality pass as everything else: when a tile's target changes or a new
  tile is added, confirm the id resolves in `ANCHOR_MAP` before presenting the file.

## Navigation: Jump-To Dropdown and Full-Text Search

Two complementary ways to get anywhere in the card without scrolling, both wired to the same
`ANCHOR_MAP`/`jumpTo()` engine as the term tiles:

- **Jump-to dropdown**, in the search bar, grouped by `<optgroup>` per tab (Overview, Role-Based,
  Fundamentals, Behavioral, Intel). One `<option>` per q-block, card, or section id. Rebuild this
  list whenever a block is added, removed, or renamed; a stale dropdown is worse than none.
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
- Minimum 72 `SEARCH_INDEX` entries for a panel-level card, growing as content grows across rounds.
  Each entry carries 15-25 tags: exact term, acronym (both forms), full phrase, synonym,
  conversational phrasing, partial word, question form, relevant number or name. Eight standard
  entries never change: opening pitch, closing script, mirroring, labeling, strategic silence, JD →
  Card Map, recovery lines, comp. Every new block added to the card — including fallback content,
  follow-ups, and chat-specific extras — gets a matching search entry and a matching `ANCHOR_MAP`
  entry and jump-to dropdown option at the same time, not as an afterthought.

## Quality Checks Before Presenting Any File

All of the following, every time, including after incremental mid-session edits:

- **JS syntax check** — extract the script block and run it through Node's function constructor (or
  `node --check`) to confirm it parses.
- **Div balance check** — count opening and closing div tags across the whole file (excluding the
  script block, to avoid false matches inside JS string literals), confirm they match.
- **Link and navigation resolution** — every `jumpTo()`/`jumpAlt()` call, every jump-to dropdown
  option, and every term tile resolves to a real id that exists and is registered in `ANCHOR_MAP`.
  Confirm `SUBTABS` still matches the actual subtab panels present.
- **Acronym audit** — every acronym used in a STAR answer or a follow-up is expanded on its first
  use in that specific answer. An acronym expanded once in the main answer still needs expanding
  again the first time it appears inside that block's own follow-ups, since a follow-up can get read
  out of order.
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

Div safety rules: fallback content, follow-up blocks, or JD groups inserted through scripted edits
get verified immediately after insertion, not at the very end. Never close a block with a generic
pattern — always match the unique trailing text of that specific block.

## File Naming

- Prep cards: `company_role-short_r[N]_round-type_prep.html`
  (e.g. `acme_se3_r3_panel_prep.html`)
- Standalone memorization sheets for multi-session days:
  `company_role-short_onsite_memorization_sheet.md`

## Build Process Note

The strongest recent builds in this project were assembled by hand, following this spec block by
block, and then checked against it. A parameterized generator script (JD + data bank in, a fully
wired HTML card out) would make the mechanical parts of this — `ANCHOR_MAP` entries, search index
entries, jump-to dropdown options, div/JS validation — impossible to get wrong by construction rather
than by careful checking. If a working generator script exists from an earlier build, upload it to
this project as a reference file and this section will be rewritten to describe using it; until then,
this spec and the skeleton file are the source of truth, and every card still gets hand-assembled
against both plus the Quality Checks above.

## What to Upload When Starting a New Chat

Master data bank (if not already project knowledge), resume submitted for this role, job description
as text, any recruiter or hiring-manager email content, program/product links if provided.

Then say: **build me a Round [N] prep card for [Company], [Role Title].**

## What to Say After Each Round

Share what was actually asked (as close to verbatim as possible), what landed, what didn't, any real
intel learned about people, process, or timeline, and who's next if known. Mention anything unusual
about the round format if a chat-specific extra might be needed.

Then say: **update the card for Round [N+1] with [interviewer name].**
