---
name: deslop
description: >-
  Audit and rewrite prose that carries AI-writing tells — inflated significance,
  negative parallelisms like "not just X, but Y", vague attribution, and assistant
  leakage. Use when the user asks to "check for AI slop", "rewrite this so it
  sounds less like ChatGPT", "audit this draft for AI slop", "why does this sound AI-generated",
  "clean up LLM prose", or wants to identify and fix synthetic writing patterns.
license: MIT
metadata:
  author: danielhowells
  version: "1.0.0"
  argument-hint: <text-or-file>
---

# Not Just a Skill

Use this skill to review, diagnose, and rewrite prose that carries common AI-writing tells.
The name is deliberately anchored to one of the loudest recurring patterns: negative parallelisms such as "not just X, but Y" and "not X, but Y".

This skill is for practical editing, not authorship forensics.
Treat the patterns as clues, not proof.
Do not claim a text is AI-generated from a single tell.
Do not rely on detector tools alone.
Prefer clusters of indicators over isolated phrases.

## When to use it

Use this skill when the user asks to:

- audit writing for AI slop
- explain why a passage sounds LLM-ish
- rewrite copy so it feels more grounded and less synthetic
- spot recurring phrasal templates, inflated significance, or assistant leakage
- review citations, markup, or formatting for chatbot artifacts

## Input handling

The user may provide text in several ways. Handle each:

- **Inline text** in the conversation: use it directly.
- **File path**: read the file, then apply the workflow to its contents.
- **URL**: fetch the page content, then apply the workflow to the prose.
- **Code block or selection**: treat the selected text as the input.
- **No input provided**: ask the user to paste or point to the text they want reviewed.

If the input is not prose (e.g. source code, structured data), say so and ask whether the user wants to review comments, docstrings, or surrounding documentation instead.

## Core workflow

1. Read the text once for overall effect.
2. Mark the highest-signal clusters before touching line edits.
3. Classify what you see using the taxonomy in `references/signs-of-ai-writing.md`.
4. Explain the problem in plain editorial terms, not detector jargon.
5. Rewrite toward specificity, directness, and verifiable claims.
6. If markup or citations look machine-generated, check those separately using the citation checklist below instead of only fixing the prose surface.

### Citation and markup checklist

When step 6 applies, run through these checks:

- Verify that links resolve and point to the claimed content.
- Compare DOI/ISBN identifiers against the cited claim — do they match the actual publication?
- Flag references that lack page numbers, access dates, or usable locating detail.
- Check for leaked model artifacts (`oaicite`, `contentReference`, `turn0search0`, etc.).
- Preserve the host system's native markup; do not introduce Markdown into non-Markdown contexts.
- Mark anything you cannot verify as needing human review in the `Residual risk` section.

## What to look for first

Start with the strongest clusters:

- inflated claims of significance paired with generic language
- source-listing or media-name dropping used as a substitute for substance
- vague attributions such as "experts say" or "observers note"
- negative parallelisms, especially "not just X, but Y"
- assistant-style formatting: Markdown, em dashes, bold sprawl, title case drift
- broken citations, suspicious links, or placeholder-like markup

If two or more of these appear together, treat the passage as high-priority for rewrite.

## The headline tell

Negative parallelisms are common enough to deserve special treatment:

- "not just X, but Y"
- "not only X, but Y"
- "not X, but Y"
- "this is not A, but B"

These constructions often signal synthetic emphasis rather than genuine reasoning.
Default move: rewrite them as direct statements.

Examples:

- "The project is not just a tool, but a platform for change."
  becomes
  "The project automates permit routing and lets three departments share status updates."

- "It is not a list of incidents, but a record of systemic failure."
  becomes
  "The incidents point to a recurring operational failure."

If the contrast is fake, cut it entirely.

## Rewrite rules

- Replace generic importance language with concrete facts.
- Replace "broader trends" talk with the actual mechanism or evidence.
- Turn source roll-calls into sourced claims.
- Cut vague praise, policy-sounding abstractions, and promotional framing.
- Prefer simple copulatives and declarative sentences over ornamental variation.
- Remove conclusion-style recaps unless the genre truly needs them.
- Normalize punctuation and formatting to the house style.
- Preserve meaning, but do not preserve synthetic cadence.

## Output shape

When reviewing text, structure the response as:

1. `Observed tells:` the main patterns and the exact phrases that trigger them
2. `Why they matter:` what the patterns are doing to the prose
3. `Rewrite:` either a surgical line edit or a clean replacement passage
4. `Residual risk:` markup, citation, or sourcing issues that still need human review

If the user only wants a rewrite, keep the explanation brief and focus on the revised text.

### Example response

Given input: *"The initiative is not just a policy update, but a testament to the organization's enduring commitment to fostering inclusive dialogue. Experts argue it represents a pivotal shift in the evolving landscape of stakeholder engagement."*

**Observed tells:** negative parallelism ("not just X, but Y"), inflated significance ("testament", "enduring commitment", "pivotal shift", "evolving landscape"), vague attribution ("experts argue"), AI vocabulary cluster ("fostering", "pivotal", "landscape").

**Why they matter:** the passage uses five words to gesture at importance without naming a single concrete outcome, policy, or stakeholder. The vague attribution makes the claim uncheckable.

**Rewrite:** "The updated policy requires quarterly feedback sessions with tenant associations and publishes responses within 30 days."

**Residual risk:** "experts argue" has no source — verify whether a named expert or report supports this claim, or cut it.

## Guardrails

- Do not overclaim authorship.
- Do not treat every em dash or every triad as decisive.
- Do not flatten strong human prose just because it is polished.
- Do not stop at style if the passage also shows citation or factual-risk patterns.
- If the text predates public ChatGPT use, weigh that heavily against an AI-origin claim.
- If a human author can clearly explain the editorial choices, weigh that against an AI-origin claim too.

## Reference

Open `references/signs-of-ai-writing.md` when you need the full taxonomy:

- content tells
- language and grammar tells
- formatting and style tells
- assistant-to-user leakage
- markup and citation artifacts
- weak and historical indicators
