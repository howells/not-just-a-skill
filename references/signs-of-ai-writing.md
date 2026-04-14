# Signs of AI Writing

An operational checklist for identifying and editing AI-generated prose.
Originally adapted from the Wikipedia editorial community's observations, generalized for any context.

Source: https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing

Use it as a taxonomy of clues, not as proof of authorship.
These are observations, not rules, and many signs are surface indicators of deeper quality or sourcing problems.

## 1. Caveats

- Detector tools are weak evidence on their own.
- Human judgment is fallible, especially on isolated examples.
- Fixing only the visible tell can hide the deeper problem without solving it.

## 2. Content tells

### Inflated significance

Watch for prose that keeps insisting a subject is important, pivotal, enduring, emblematic, or part of a broader shift without adding concrete information.

Common pattern:

- a blurry, high-status summary replaces a precise fact
- the text gestures at "legacy", "impact", or "the evolving landscape"
- the subject is framed as symbolic even when the source material is mundane

### Notability by assertion

Watch for copy that tries to prove importance by naming outlets, coverage, or "independent sources" rather than summarizing what those sources actually say.

Common pattern:

- source roll-calls
- "featured in" laundry lists
- "maintains an active social media presence"
- separate "media coverage" sections that are just inventories

### Superficial analysis

Watch for shallow interpretive gloss pasted onto ordinary facts.

Common pattern:

- trailing `-ing` phrases that force a moral or thematic reading
- abstract verbs like "underscoring", "highlighting", "fostering", "reflecting"
- claims of significance with no attributable reasoning

### Promotional tone

Watch for copy that sounds like marketing, branding, institutional self-description, or a puff piece.

Common pattern:

- grandiosity
- praise without friction
- frictionless transitions from fact to endorsement

### Vague attribution

Watch for authority with no owner.

Common pattern:

- "experts argue"
- "observers note"
- "researchers say"
- plural attributions that rest on one or two sources

### Outline-style endings

Watch for conclusion paragraphs that summarize "challenges", "future prospects", or "broader implications" in generic terms.

### Improper noun inflation

Watch for leads that treat broad article titles or list names as if they were formal proper nouns.

## 3. Language and grammar tells

### AI vocabulary density

Watch for clusters of overrepresented words and phrases:

- additionally
- align with
- bolstered
- boasts
- crucial
- delve
- emphasizing
- enduring
- enhance
- foster
- garner
- highlight
- interplay
- intricate / intricacies
- key
- landscape
- meticulous / meticulously
- multifaceted
- nuanced
- pivotal
- showcase
- tapestry
- testament
- underscore
- valuable
- vibrant

Vocabulary shifts across model generations. Earlier models leaned on `delve`, `tapestry`, `testament`, and `intricate`. More recent models prefer `align with`, `enhance`, `fostering`, and `highlighting`. The specific words change; the underlying pattern — inflated register and synonym-swapping to avoid plain language — stays constant.

Any single word can be innocent. The issue is density and cadence.

### Avoidance of plain copulatives

Watch for a tendency to dodge simple `is` and `are` sentences in favor of inflated structures.

### Negative parallelisms

This is the loudest tell and the basis of the skill name.

Patterns:

- not just X, but Y
- not only X, but Y
- not X, but Y
- this is not A; it is B

These are often rhetorical scaffolds rather than actual reasoning.

### Rule of three

Watch for repeated triplets:

- adjective, adjective, adjective
- phrase, phrase, and phrase

Triplets often make weak analysis sound finished.

### Elegant variation

Watch for needless synonym swapping that avoids repeating a simple noun, even when repetition would be clearer.

## 4. Style and formatting tells

### Title case drift

Headings, labels, or inline phrases slip into title case where sentence case would be normal.

### Boldface sprawl

Too much bold for emphasis, labels, or list items.

### Inline-header vertical lists

Bullet structures that read like generated outlines rather than prose shaped for the medium.

### Emoji

Emoji in contexts where the house style would almost never use them.

### Em dash overuse

Frequent em dashes used as an all-purpose dramatic hinge.

### Strange tables

Tables appear where prose or lists would be more natural.

### Curly quotes and apostrophes

Typography can reflect copy-paste from chatbot UIs or stylized generation defaults.

### Heading-level skips and thematic breaks

Generated structure often inserts decorative breaks or jumps heading levels without a clean document outline.

## 5. Communication intended for the user

These are strong signs that assistant output leaked directly into the document.

### Collaborative assistant voice

Watch for:

- "let's explore"
- "here's a breakdown"
- "we can also"
- "I hope this helps"

### Knowledge-cutoff disclaimers

Watch for:

- speculation about missing sources
- reminders that information may be outdated
- "as of my last update" style caveats

### Placeholder phrasing

Watch for generic templates and fill-in-the-blank scaffolds that were never fully replaced.

## 6. Markup tells

These are especially useful in Wikipedia-style environments, but the principle generalizes: machine output often carries formatting from the interface it came from.

### Markdown leakage

Watch for:

- Markdown headings
- `**bold**`
- backticks used out of place
- numbered or bulleted structures that do not match the host system

### Broken native markup

Generated text often mixes formats incorrectly or invents malformed syntax.

### Search-result residue

Internal traces from model tooling or UI references leaking into output, such as `turn0search0`, `turn1search3`, or similar indexed retrieval markers.

### Reference-markup bugs

Watch for internal citation tags from various model pipelines:

- `contentReference`
- `oaicite`
- `oai_citation`
- `+1`
- `attached_file`
- `grok_card`

### Attribution and index artifacts

Watch for non-standard attributes leaking from generation tooling:

- `attribution`
- `attributableIndex`

These are internal metadata fields from some model pipelines that end up pasted into output.

### Other fabricated or misplaced structures

Watch for:

- non-existent categories
- non-existent templates
- broken attribution metadata

## 7. Citation tells

### Broken links

External links fail, redirect strangely, or point somewhere unrelated.

### Invalid or mismatched identifiers

DOIs and ISBNs are malformed or contain formatting errors incompatible with standard databases.

### Identifiers that resolve to unrelated works

A DOI or ISBN is syntactically valid but points to a completely different publication than the one cited. This is distinct from a broken link — the reference looks functional but the source says something else entirely.

### Thin book citations

Books are cited without page numbers, URLs, or usable locating detail.

### Reference-style misuse

Footnotes are present but used in unconventional or mechanically repeated ways.

### Tracking parameters

Links carry `utm_source=` and similar residues.

### Dead named refs

Named references are declared but never used in the body.

## 8. Miscellaneous behavioral tells

### Sudden style shift

A passage changes voice abruptly inside the same document. A sophisticated paragraph followed by an elementary one, or a neutral passage followed by promotional copy, suggests spliced generation sessions.

### Overlong meta-writing

Commit messages, PR descriptions, cover letters, submission notes, or other meta-text becomes verbose, overexplained, and defensively thorough in a way that reads like a model hedging rather than a human summarizing.

### Anticipatory formatting

Content arrives pre-equipped with disclaimers, warnings, or structural scaffolding that anticipates review or moderation rather than serving the reader. The general pattern is strategic formatting that manages objections rather than improving content.

## 9. AI-written comments and discussion posts

When reviewing comments, reviews, forum posts, or any conversational text, watch for:

- canned appeals to good faith, community values, or procedural compliance
- offers to receive constructive criticism in formulaic language ("I welcome any feedback")
- weirdly polished or generic subject lines
- invented rules, acronyms, or procedural references that sound authoritative but do not exist
- legalistic parsing of rules or guidelines with rigid syllogistic reasoning

## 10. Signs against AI authorship

These counter-signals should temper any AI-origin assumption.

### Age of text

If the text clearly predates mainstream ChatGPT use, that matters.

### Explainable editorial choices

If the author can explain why the text is structured the way it is, that weighs against a machine-origin assumption.

## 11. Ineffective indicators

Do not over-index on one-off tells.
Many popular intuitions about AI writing are noisy and unreliable in isolation.

## 12. Historical indicators

Some signs were stronger in older model generations and are weaker now.

### Older tells

- didactic "important to note" disclaimers
- section summaries and "in conclusion" endings
- explicit "as an AI language model" refusals
- abrupt mid-sentence truncation
- outdated dates in citations that predate the document

These were strong signals in 2022–2024 but are now largely trained out. Treat as historical residue, not current proof.

## 13. Practical editing moves

When you find a cluster of tells, the strongest fixes are usually:

- replace inflated abstractions with specific facts
- turn media-name dropping into actual sourced claims
- remove fake contrast structures
- collapse triplets into one clear statement
- convert vague authority into named attribution or delete it
- normalize formatting to the target house style
- inspect references, not just prose
