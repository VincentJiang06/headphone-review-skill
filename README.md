# headphone-review-skill

[中文说明](./README.zh-CN.md)

`headphone-review` is a Codex skill for buyer-facing reviews of headphones, IEMs, earbuds, and TWS models.

It is designed to answer the questions that matter in an actual buying decision:

- What does this model sound like?
- Who is it good for?
- Who should avoid it?
- What are the real tradeoffs?

## Current Version

- `1.0.4`

## What's New In 1.0.4

- adds `rules/humanize.md` to suppress common AI-sounding phrasing
- keeps the body long-form, but tighter than the earlier longform experiments
- keeps the disagreement section short, plain, and decision-relevant
- upgrades the opening verdict from one sentence to a compact two-sentence verdict

## What The Skill Does

Before writing a review, the skill asks two preference questions with `AskUserQuestion`:

1. Do you want Chinese or English output?
2. Do you want a more objective description, or a more emotional / abstract description?

After that, it:

- locks the exact model, revision, and form factor
- gathers official facts plus multilingual review consensus
- separates confirmed facts from repeated reviewer agreement
- turns sound traits into buyer guidance
- outputs a pure-Markdown long review article

## Output Shape

- starts with language, description mode, a two-sentence verdict, style tags, and confidence
- keeps the full article within roughly 3000-word scale unless the material clearly needs more
- puts special weight on a dedicated but concise disagreement section
- adds a separate humanization constraint file to suppress common AI-sounding phrasing
- prioritizes strong Chinese output quality
- marks assumptions and lower confidence when naming or evidence is ambiguous

## Output Contract

- asks language first: `中文` or `English`
- asks description mode next: objective or emotional / abstract
- opens with short labels before the article body
- keeps the two-sentence verdict within 200 Chinese characters for Chinese output
- keeps the disagreement section short enough to scan, but specific enough to guide a purchase
- avoids source dumps at the end of the article

## Repository Structure

```text
headphone-review/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── rules/
    ├── eval.md
    ├── humanize.md
    ├── intake.md
    ├── output.md
    └── research.md
```

## Use Cases

- quickly judge whether a headphone fits your taste
- turn scattered multilingual reviews into one buyer-facing conclusion
- test article-style Chinese audio-review output
- compare multiple models without falling back to spec-sheet summaries

## Writing Constraints

- do not let the article drift into generic assistant prose
- avoid overused contrast templates and over-explained transitions
- tie every major audio claim back to an audible consequence
- make the disagreement section read like an editor's note, not a second essay

## Usage

Call the skill in Codex with:

```text
$headphone-review
```

Then provide the model name. The skill will ask for language and description mode first, then generate the review.
