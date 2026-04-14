---
name: not-just-a-skill
description: >-
  Audit and rewrite prose that carries AI-writing tells — inflated significance,
  negative parallelisms like "not just X, but Y", vague attribution, and assistant
  leakage. Use when the user asks to "check for AI slop", "rewrite this so it
  sounds less like ChatGPT", "audit this draft", "why does this sound AI-generated",
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

## Core workflow

1. Read the text once for overall effect.
2. Mark the highest-signal clusters before touching line edits.
3. Classify what you see using the taxonomy in `references/signs-of-ai-writing.md`.
4. Explain the problem in plain editorial terms, not detector jargon.
5. Rewrite toward specificity, directness, and verifiable claims.
6. If markup or citations look machine-generated, check those separately instead of only fixing the prose surface.

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
  "The project combines a tool with a broader coordination layer."

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
