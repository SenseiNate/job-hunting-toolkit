# [YOUR NAME]

## MASTER APPLICATION MANIFESTO

> HOW TO USE THIS FILE: Replace everything in [BRACKETS]. Delete this callout block and any
> instructional notes (lines starting with `>`) before uploading to your Claude Project. Keep
> the section headers and structure, they are what the system prompt refers back to.

**DATA BANK IS THE ONLY SOURCE OF TRUTH.** The [YOUR NAME]_DATA_BANK file is the exclusive
source for all resume content. This has zero exceptions. See PROJECT_SYSTEM_PROMPT.md for the
full fabrication rules; this document does not repeat them, it only supplies the specifics below.

## SECTION 1: CAREER TRACKS

> List the 1 to 4 types of role you're targeting. One track is fine if you only want one kind of
> job. Each track needs its own name and a one-line definition so the AI can classify a JD into
> the right one.

- **[Track 1 Name]:** [What this track covers, e.g. "hands-on technical delivery, architecture, engineering ownership"]
- **[Track 2 Name]:** [Definition]
- **[Track 3 Name]:** [Definition]
- **[Track 4 Name]:** [Definition]

## SECTION 2: TARGET SECTORS / INDUSTRIES

> Which industries are you aiming for? This drives which JDs get a "welcome home" reading versus
> which ones need your background translated into different vocabulary.

- [Target industry 1]
- [Target industry 2]
- [Target industry 3]
- [Target industry 4]

## SECTION 3: COMPENSATION & LOCATION

- Target base salary: $[XXX,XXX] (flag-and-report, not a hard gate, see screening protocol)
- Location strategy: [e.g. "remote-first", "willing to relocate to X", "local to Y metro only"]
- Locations to exclude from relocation framing: [list, or "none"]

## SECTION 4: AUTO-SKIP LIST (Step 2, hard and non-negotiable)

> This is the only list that produces an automatic SKIP verdict. Keep it short and be precise,
> vague entries here just become Step 4 judgment calls instead. List categories of work you will
> not do regardless of title or company, e.g. "cold outbound sales as a core function" or
> "roles requiring a license I don't hold and can't get."

- [Auto-skip category 1]
- [Auto-skip category 2]
- [Auto-skip category 3]

## SECTION 5: CLEARANCES, LICENSES, OR CREDENTIALS

> Delete this section if not applicable to your field.

- [Credential name]: [status, e.g. "Active", "In progress, expected date"]

## SECTION 6: INDUSTRY / SECTOR TRANSLATION TABLE

> If you're moving between industries that use different vocabulary for similar work (e.g.
> military to civilian, agency to in-house, academia to industry), build a translation table here.
> Delete this whole section if it doesn't apply to you, in which case your Data Bank language can
> be used as-is on every build.

| Original term | Translated term |
|---|---|
| [Term from your current/past industry] | [Equivalent phrase for target industries] |
| [Term] | [Equivalent] |

Rules for applying this table:
- Apply automatically on any build flagged as needing translation. No manual trigger.
- The reader should not be able to tell which industry the work originally happened in from the
  bullet language alone.
- Do not translate credential names or clearance/license status lines, only bullet and summary
  language.

## SECTION 7: DOCUMENT FORMAT SPECIFICATION

**Typography**
- Font: [e.g. "Arial 11pt"] throughout.
- Page size: [e.g. "US Letter"].
- Margins: [e.g. "0.6 inch resume, 0.7 inch cover letter"].
- Section headers: [e.g. "All caps, bold, with a bottom border rule"].
- No em dashes anywhere. [Any other style rules, e.g. "no pipe characters in body text"].

**Bold usage**
Reserved exclusively for: [list, e.g. "employer names, section headers, degree names"].
Never bolded: [list, e.g. "job titles, bullet text, metrics"].

**Header format**
- Line 1: [YOUR NAME] (bold, [size]).
- Line 2: [phone] | [email] | [LinkedIn URL] [ | any credential line, only when the JD calls for it].
- Must remain a single line at your chosen margins.

**Professional Summary rules**
- First person. Never third person.
- Opens with: [Targeted Track Title, bold] with [X]+ years [hook tied to the JD's core problem].
- Include at least [N] scale or financial metrics in the body.
- Never end on a hedge (an in-progress credential, a "pursuing" statement). End on a completed
  claim.

**Areas of Expertise**
- [N] categories, [N] to [N] keywords total.
- Format: Category Name (bold): keyword, keyword, keyword.

**Professional Experience formatting**
- Employer name: bold, all caps, own line.
- Title line: [Title], [Employment Type] --- Date Range (right aligned).
- Present tense for your current role, past tense for prior roles.

**Bullet methodology**
- Every bullet: Task/Problem, Action, Outcome. All three parts required.
- One accomplishment per bullet. Split anything that combines two actions or two outcomes.
- 1 line strongly preferred, [2] lines absolute maximum.
- At least one metric per bullet (number, dollar figure, percentage, scale).
- Bullets per employer: [state a number or range per employer, e.g. "4 to 5"].

**Certifications/Education sections**
- [Format spec, mirror however you want these to render]

**Cover letter structure**
- [N] paragraphs maximum, one page maximum.
- P1: [opening hook rule]
- P2: [metric/proof rule]
- P3: [depth/breadth rule]
- P4: [close rule]

## SECTION 8: FILE OUTPUT RULES

- Resume naming: [YourName]_[JD Title]_[Company].docx
- Cover letter naming: [YourName]_[JD Title]_[Company]_CoverLetter.docx
- Always validate the file before presenting it. Always present the files after every build.
