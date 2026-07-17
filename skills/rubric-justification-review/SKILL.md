---
name: rubric-justification-review
description: >
  Evaluate an existing rubric justification and provide actionable
  feedback on whether it defensibly supports its claimed level. Use when
  the user asks to "review this justification", "is this rating
  defensible", "critique this assessment", or provides a written
  justification alongside a rubric — e.g. performance reviews, promo
  packets, grading appeals, maturity or compliance assessments.
  Companion to the rubric-justification skill, which writes
  justifications; this skill reviews them.
---

# Rubric Justification Review

Evaluate a justification the way a skeptical calibration reviewer would:
verify that every claim is grounded, every criterion is covered, and the
evidence actually clears the claimed level — then deliver feedback the
author can act on.

## Required Inputs

1. **The justification** to review.
2. **The rubric** — including, where available, the levels adjacent to
   the claimed level.
3. **The underlying evidence** (optional but material): the context the
   justification was written from.

The evidence determines the review depth. With it, verify claims against
their sources. Without it, review internal quality only — and state
prominently that claim accuracy could not be checked.

If the justification was produced earlier in this same session, recommend
running this review in a fresh session or subagent instead: a reviewer
sharing the author's context inherits the author's blind spots.

## Evaluation Dimensions

Assess each, in order:

1. **Criterion coverage** — Is every criterion of the claimed level
   addressed? Unaddressed criteria are findings, even if everything
   present is strong. Are weak areas declared as gaps, or papered over?
2. **Evidence grounding** — Does each claim cite something concrete
   (artifact, metric, name, date)? Flag generic filler ("consistently
   demonstrates excellence"), unsupported assertions, and — when the
   underlying evidence was provided — any claim that embellishes or
   cannot be traced to it. Fabrication is an automatic fail for the
   affected criterion.
3. **Level calibration** — Does the justification clear the bar of the
   claimed level specifically, or does it describe work the level below
   also satisfies? Check the contrast against adjacent levels; note if
   the evidence better matches a different level in either direction.
4. **Evidence strength** — Do claims rest on direct artifacts and
   metrics, or on second-hand descriptions? Note where the case depends
   on the weaker kind.
5. **Defensibility** — Would this survive a reviewer holding the same
   rubric and evidence? Identify the single weakest point a skeptic
   would attack first.
6. **Voice authenticity** (self-authored documents only) — Does it read
   like the author wrote it? Flag ghost-writing/AI tells: third-person
   references to the author, evaluative meta-commentary about the
   evidence, uniformly parallel bullet structure, assessor asides
   ("beyond level N's..."), and a vocabulary register that doesn't
   match the author's other writing when samples are available.

## Feedback Rules

- Every finding quotes or pinpoints the specific passage it concerns —
  no feedback the author has to hunt for.
- Every finding says why it weakens the case and what would fix it
  (rewrite suggestion, missing evidence to gather, gap to declare).
- Rank findings by severity: what threatens the level claim outright
  versus what merely weakens polish.
- Review the case, not the person. The question is whether the argument
  is defensible, never whether the subject deserves the level.
- If the justification is sound, say so plainly — do not invent findings
  to appear thorough.

## Output Format

```markdown
# Review — <Subject>, <Claimed Level>

**Verdict:** <Defensible / Defensible with revisions / Not defensible as
written> — <one-sentence reason>
**Review depth:** <claims verified against evidence / internal review
only — evidence not provided>

## Findings
<Ordered by severity. Each: the quoted/pinpointed passage, the problem,
the fix. Number them.>

## Weakest Point
<The one attack a skeptical reviewer would open with.>

## What Would Strengthen the Case
<Concrete evidence to gather or revisions to make, if any.>
```
