# Not Just a Skill, But a Testament to the Enduring Legacy of Prose That Doesn't Sound Like It Was Written by a Chatbot

An [Agent Skill](https://skills.sh) that audits and rewrites AI-slop prose. It finds the tells, explains why they matter, and rewrites toward specificity — so your copy stops reading like it was fostered by a vibrant tapestry of language models.

## Install

```bash
npx skills add howells/not-just-a-skill
```

Works with Claude Code, Cursor, Copilot, Windsurf, and any agent that supports the [Agent Skills spec](https://agentskills.io/specification).

## What it does

Give it prose. It looks for clusters of AI-writing indicators — inflated significance, negative parallelisms, vague attribution, assistant leakage, broken citations, and the rest — then explains what's wrong and rewrites the weak lines.

It will not claim a text is AI-generated from a single em dash. It treats the patterns as clues, not proof.

## Usage

Paste text, point to a file, or drop a URL:

- "check this for AI slop"
- "why does this sound like ChatGPT"
- "rewrite this so it sounds less synthetic"
- "audit this draft for AI-writing tells"

## What's inside

```
not-just-a-skill/
├── SKILL.md                          # Instructions + workflow
└── references/
    └── signs-of-ai-writing.md        # Full taxonomy of AI-writing indicators
```

The taxonomy covers content tells, language patterns, formatting artifacts, assistant-to-user leakage, markup and citation bugs, and historical indicators. Originally adapted from the Wikipedia editorial community's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), generalised for any context.

## License

MIT
