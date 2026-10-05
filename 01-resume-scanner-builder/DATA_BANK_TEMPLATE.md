# [YOUR NAME] - MASTER SKILLS & ACCOMPLISHMENTS DATA BANK

> HOW TO USE THIS FILE: This is the ONLY place resume content is allowed to come from. If it's
> not written here, it does not go on a resume, no matter how well it would match a job
> description. Be thorough. Delete instructional notes (lines starting with `>`) once you've
> filled the section in. See SETUP_GUIDE.md for how to bootstrap this from an existing resume.
> Sections marked OPTIONAL can be deleted outright if they don't apply to you.

## PART 0: SECTOR/INDUSTRY TRANSLATION TABLE (OPTIONAL, mirror of Manifesto Section 6)

> If your Manifesto defines a translation table (Section 6), it's useful to keep a copy here too
> so every build-time lookup happens in one pass against whichever file is open. If you update the
> table, update it in both places, this duplication is a known tradeoff for not having to cross-
> reference two files on every single build. Delete this section if you deleted Manifesto Section 6.

NOTE: This table gives fixed term-level swaps only. Per the Manifesto's Modern/Current Vocabulary
Standard, every translated bullet and summary sentence, not just these listed terms, should read
in the target sector's current register, not stiff word-for-word translation.

| Original term | Translated term |
|---|---|
| [Term] | [Equivalent] |

## PART 1: SKILLS INVENTORY

> A flat list of real skills, tools, and knowledge areas. This is a menu the AI pulls
> "Areas of Expertise" keywords from, it should not itself contain resume-ready sentences.

### Soft skills
- [Skill]
- [Skill]

### Hard skills / technical
- [Skill or tool]
- [Skill or tool]

### Domain knowledge
- [Domain area]
- [Domain area]

### Skills you're still building (NOT for professional experience claims)
> Personal projects, side learning, bootcamp work, self-study. These are honest and useful in a
> cover letter as "I've been learning X on my own," but must never be presented as professional
> fluency or used to paper over a required-skill gap. Flag them clearly like this so the AI
> never confuses them with the rest of the bank.
- [Thing you're learning, and how, e.g. "SQL, via a self-paced course and a personal project"]

## PART 2: ACCOMPLISHMENTS BY EMPLOYER

> One block per employer, most recent first. Within each employer, write one version of each
> accomplishment per career track you defined in your Manifesto (Section 1). If you only have one
> track, only write one version per accomplishment, delete the extra track headers below.
>
> Each accomplishment needs an ID so future builds can cite it (e.g. cite "ACME-SE-3" so you can
> verify where a bullet came from). Use a short employer code plus track code plus number.
>
> Every entry should already be closeish to Task/Action/Outcome so tailoring later is easy:
> what needed solving, what you specifically did, what the measurable result was. Where a real
> metric exists, include it; where it genuinely doesn't, describe the scope of the problem solved
> concretely instead of leaving the entry vague, per the Manifesto's Technical Rigor Standard.

================================================================================
### [EMPLOYER NAME] ([Start Date] - [End Date]) -- Employment type: [Full-Time / Contract / etc.]
================================================================================

> OPTIONAL, recommended once you're applying the Technical Rigor Standard: a one or two line
> Program/Market Context note at the top of each employer block, reference-only, giving the scale
> or context a bullet alone can't carry (e.g. the size of the org, the program's budget tier).
> Never presented as your own accomplishment on a resume; it's here so the AI doesn't understate
> the environment you operated in when framing a bullet.

---[TRACK 1 NAME] TRACK---

* [CODE-T1-1]: [Task/problem]. [Action you took]. [Measurable outcome].
* [CODE-T1-2]: [...]

---[TRACK 2 NAME] TRACK---

* [CODE-T2-1]: [Same underlying accomplishment as above, reframed for this track's audience]
* [CODE-T2-2]: [...]

> Repeat the employer block above for every employer you want represented. Aim for at least
> 3 to 6 accomplishments per employer if you can, more is fine, the AI selects the most
> relevant ones per build rather than using all of them.

## PART 3: AWARDS AND RECOGNITION (reference only, not placed directly on resumes)

> Useful for interview prep and for the AI to cross-reference when picking the strongest bullet,
> but these don't appear as their own resume line items in this system, delete this note if you
> want to change that rule in your Manifesto instead.

**[Award Name] -- [Date]**
Issued by: [Name/Title]
[1-3 sentences of real context: what happened, what you did, what the result was.]

## PART 4: EDUCATION

> List every real degree or program. If something should never be cited on a resume (withdrawn,
> incomplete, not relevant to your target tracks), flag it explicitly so it never gets pulled in
> by mistake, the way the withdrawn-credential example below does.

- **[Degree name], [Major]** — [Institution, City, State] — [Status: completed date, or "In
  Progress"]
- [Repeat per real degree/program.]
- *[Any credential you do NOT want used on resumes]* — **DO NOT USE ON RESUMES. DO NOT CITE IN
  THE EDUCATION SECTION OR ANYWHERE ELSE a build produces.** Reference only, shows [why it's
  excluded, e.g. "withdrawn, incomplete, not relevant to target tracks"].

## PART 5: SOLO VENTURES / PERSONAL PROJECTS (flagged, not professional experience)

> Side projects, independent tools, a portfolio site, freelance work done entirely on your own
> time and outside any employer relationship. These are real and can add color, especially in a
> cover letter or when a question specifically calls for personal/technical-curiosity material,
> but they never substitute for a real employer-sourced proof point, and never get dressed up as
> if they were a job deliverable. If a JD requirement has no honest employer-sourced answer, that's
> a gap to flag honestly, not an opening to reach for a personal project instead.

* [SV-1]: [What you built/did independently, what it does, any real usage/outcome if applicable.]
* [SV-2]: [...]

## PART 6: INTERVIEW DETAIL ADDENDUM (OPTIONAL, recommended for FAANG-level rigor)

> This is where the Technical Rigor Standard's "lead with the real mechanism" requirement gets its
> raw material. A resume bullet compresses an accomplishment down to one line; this section is
> where the full mechanism lives, so the AI (and you, live in an interview) can go one level
> deeper than the bullet without inventing anything. Write one entry per accomplishment ID that's
> worth expanding, not every single one.

* **[CODE-T1-1] expanded:** [The real step-by-step mechanism behind the outcome: what tool, what
  specific method, what sequence of actions. This is reference-only, it sharpens a bullet or an
  interview answer, it never becomes a resume bullet on its own.]

## PART 7: WHY EACH MOVE (OPTIONAL, recommended if your work history has more than 2-3 employers)

> A real, honest reason for each job change (contract ending, acquisition, commute, scope change,
> layoff, whatever actually happened). This feeds both the cover letter's "why leaving" framing and
> any interview-prep tooling built from this Data Bank, so career tenure never gets explained with
> a vague "looking for new challenges" gloss.

* **[Employer A] → [Employer B]:** [Real reason.]
* **[Employer B] → [Employer C]:** [Real reason.]

## PART 8: HOW TO USE THIS TRACKER

1. Track selection: match a job description's core function to one of your Manifesto's tracks
   (and Altitude Tier, if you defined one).
2. Translation: apply your Manifesto's industry translation table automatically if the build is
   flagged as needing it, in the target sector's current register per the Modern/Current
   Vocabulary Standard, not word-for-word swaps.
3. Metrics: pull metrics directly from the entries above, don't estimate or round up. Where no
   metric exists, use the concrete scope of the problem instead of a vague descriptor.
4. Rigor: before finalizing a bullet, check it against the Interview Detail Addendum (if used) for
   a sharper, mechanism-level phrasing, per the Manifesto's Technical Rigor Standard.
5. Interview prep: every bullet must be defensible in a live follow-up conversation. If you can't
   speak to it in detail, it shouldn't be in this file.
6. Audit rule: if a bullet cannot be verified against this file, it does not go on a resume.
