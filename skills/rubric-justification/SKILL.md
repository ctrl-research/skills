---
name: rubric-justification
description: >
  Given a rubric, contextual evidence, and a specified target level,
  produce evidence-grounded justifications for why the subject meets that
  level. Use when the user asks to "justify a rating", "write the
  justification for level N", "support this score", or provides a rubric
  plus supporting material — e.g. performance reviews, grading, maturity
  models, vendor assessments, or compliance evaluations.
---

# Rubric Justification

Produce per-criterion justifications for a specified rubric level, grounded
entirely in the evidence provided. The output must survive scrutiny from a
reviewer who has the same rubric and evidence in hand.

## Required Inputs

1. **Rubric** — the levels and the criteria that define each level. Any
   format is acceptable (table, list, prose, pasted doc).
2. **Context** — the evidence to draw from: work samples, metrics, peer
   feedback, project summaries, audit notes, etc.
3. **Target level** — the specific level to justify.

If any of the three is missing, ask for it before proceeding. If the
rubric's criteria for the target level are ambiguous or overlap heavily
with adjacent levels, say so and state the interpretation you are using.

## Instructions

1. **Decompose the target level** into its individual criteria. Where the
   rubric defines adjacent levels, note what distinguishes the target
   level from the level below it — the justification must clear that bar,
   not just describe generally good work.
2. **Inventory the evidence.** Map each piece of context to the criteria
   it supports. One piece of evidence may support multiple criteria; use
   the strongest available for each.
3. **Write one justification per criterion**, each containing:
   - a direct claim that the criterion is met at the target level
   - the specific supporting evidence, cited or quoted from the context —
     names, numbers, artifacts, dates where available
   - when useful, a contrast line: why this exceeds the level below
     (e.g. "beyond level 2's 'contributes to team processes', they
     designed and rolled out the process itself").
4. **Apply the integrity rules** (below) to every claim.
5. **Assemble the output** using the format that follows.

## Integrity Rules

These are non-negotiable; they are what makes the output defensible.

- Use only the provided context. Never invent, embellish, or extrapolate
  evidence — no assumed impact, no "likely" behaviors, no generic filler
  ("consistently demonstrates excellence") that isn't tied to something
  concrete.
- If a criterion has weak or no supporting evidence, do not paper over
  it. List it in the **Gaps** section with what evidence would be needed
  to close it.
- If the evidence collectively supports a different level better than the
  specified one — in either direction — complete the requested
  justification for the supportable criteria, but state this assessment
  plainly at the top. Do not silently produce an unsupported case.
- Distinguish evidence strength: direct artifacts and metrics outrank
  second-hand descriptions; note when a justification rests on the
  weaker kind.

## Voice

When the output will be presented as written by the subject or requester
(self-evaluations, promo packets), write it in their voice. A reviewer
who knows the author's writing will notice a register change, and
polished assessor prose reads as ghost-written or AI-generated - which
undermines the document's credibility regardless of its content.

- Reuse the author's own phrasing from the source material wherever it
  is already accurate. Do not rewrite working sentences for polish.
- Match person. Self-evaluations use implicit first person ("Onboarded
  X", not "Jonathan onboarded X" or "the candidate onboarded X").
- Match structure. If the source uses terse fragments and uneven
  bullets, do the same. Do not normalize every bullet into an identical
  bolded-lead + claim + qualifier shape - uniform parallelism is itself
  a tell.
- Match punctuation habits and vocabulary register. If the author
  writes plain hyphens, short words, and occasional lowercase, avoid
  em dashes, "corroborated", "deliberately shaped", "testament to".
- No evaluative meta-commentary about the evidence ("a reasoned
  judgment about where controls belong", "mentorship translating into
  shipped work"). State the evidence; let the reader judge. If a gloss
  is worth making, say it in your reply to the user, not in the
  document.
- Level contrasts ("beyond E1's ...") are assessor asides nobody writes
  about themselves. Keep them out of self-authored documents, or
  compress to plain fact ("self-scoped; wasn't handed requirements").

When no source material exists to match, default to plain, concrete
statements over polished-consultant prose - the tells above are tells
in any voice.

## Output Format

Default to the report format below. When the user asks for a version to
paste into a document (Google Docs, Confluence, Word) or to match an
evaluation-form layout, use the rubric table format instead.

### Report Format (default)

```markdown
# <Subject> — Justification for <Level>

**Assessment:** <one sentence: does the evidence support this level?
Fully / with gaps (list count) / better matches level N>

## Justifications

### <Criterion 1>
<Claim + cited evidence + contrast with level below where useful.>

### <Criterion 2>
...

## Gaps
<Criteria with insufficient evidence, and what would close each.
Write "None" if all criteria are supported.>
```

### Rubric Table Format (on request)

One table per competency area, mirroring the rubric's own grouping, with
columns:

| Competency | <Level> Expectation (quoted from the rubric) | Evidence & Justification | Sign-off |

- Quote the target-level expectation verbatim from the rubric so
  reviewers verify against the actual bar, not a paraphrase.
- Evidence cells are bullet lists: claim, cited evidence with links
  preserved from the source material, and a contrast-with-level-below
  line where it strengthens the case.
- Keep the integrity content: the Assessment line goes above the tables;
  weak evidence is annotated inline in its cell; the Gaps section goes
  at the end, clearly marked as to-be-resolved-then-deleted so it is
  not accidentally submitted.
- Leave the Sign-off column empty for reviewers.
- Delivery: if the environment can render an HTML page (e.g. an
  artifact), build real HTML tables — they copy-paste into Google Docs
  with structure, links, and bold intact. Style for paste fidelity, not
  looks: the target editor's default font (Arial for Google Docs),
  standard link blue, plain table borders, light background only, and a
  copy instruction placed outside the document area. Otherwise, emit
  markdown tables.

## Example

Rubric (excerpt): *Level 3 — Engineering: "Leads design of multi-team
features" and "Mentors junior engineers".* Target: Level 3. Context: design
doc for checkout-service split authored solo and implemented across two
teams in Q2; onboarding buddy for one new hire in May.

### Leads design of multi-team features
Met. Authored the checkout-service split design (Q2) and drove its
implementation across the payments and storefront teams — leading design
beyond a single team's scope, which distinguishes this from Level 2's
"designs features within own team".

### Mentors junior engineers
Partially supported. Served as onboarding buddy for one new hire (May).
This is mentorship activity, but a single onboarding assignment is thin
evidence for a sustained mentorship criterion — flagged in Gaps.

## Gaps
- **Mentors junior engineers** — evidence covers one onboarding
  assignment. Recurring mentorship (code review guidance, growth-plan
  involvement, a second mentee) would make this defensible.

## Companion Skill

To evaluate a finished justification (this skill's output or anyone
else's), use the `rubric-justification-review` skill — ideally in a fresh
session or subagent so the review doesn't inherit this session's context.
