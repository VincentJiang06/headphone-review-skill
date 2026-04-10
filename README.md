# headphone-review-skill

[中文说明](./README.zh-CN.md)

`headphone-review` is a Codex skill for buyer-facing reviews of headphones, IEMs, earbuds, and TWS models.

It is designed to answer the questions that matter in an actual buying decision:

- What does this model sound like?
- Who is it good for?
- Who should avoid it?
- What are the real tradeoffs?

## Current Version

- `1.0.1`

## What The Skill Does

Before writing a review, the skill asks two preference questions:

1. Do you want Chinese or English output?
2. Do you want a more objective description, or a more emotional / abstract description?

After that, it:

- locks the exact model, revision, and form factor
- gathers official facts plus multilingual review consensus
- separates confirmed facts from repeated reviewer agreement
- turns sound traits into buyer guidance
- outputs a pure-Markdown short review article

## Output Shape

- starts with language, description mode, one-line verdict, style tags, and confidence
- keeps the body in article form instead of bullet spam
- prioritizes strong Chinese output quality
- marks assumptions and lower confidence when naming or evidence is ambiguous

## Repository Structure

```text
headphone-review/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── rules/
    ├── eval.md
    ├── intake.md
    ├── output.md
    └── research.md
```

## Use Cases

- quickly judge whether a headphone fits your taste
- turn scattered multilingual reviews into one buyer-facing conclusion
- test article-style Chinese audio-review output
- compare multiple models without falling back to spec-sheet summaries

## Usage

Call the skill in Codex with:

```text
$headphone-review
```

Then provide the model name. The skill will ask for language and description mode first, then generate the review.
