---
name: headphone-review
description: Use this skill when the user wants a buyer-facing review of a headphone, IEM, earbud, or TWS model by name. Ask for language and description mode first, then turn multilingual reviews and official specs into a pure-Markdown conclusion about sound, fit, and tradeoffs.
---

# Headphone Review

Use this skill when the user names a headphone, IEM, earbud, or TWS model and wants a buyer-facing review: what it sounds like, who it fits, who should skip it, and why.

When web lookup is needed, also use `$web-access` or the environment's browsing tools.

## Trigger Hints

- Model-name requests such as `WH-1000XM5`, `IE 900`, `Blessing 3`, `Susvara`
- Questions like `这耳机适合谁`, `什么声音`, `值不值得买`, `fit`, `sound signature`, `should I buy`
- Requests to aggregate multilingual reviews into one conclusion

Do not use this skill for pure repair, firmware, pairing, or EQ-only tasks unless the user also wants a buying summary.

## Workflow

1. Ask the missing preference questions first.
Read [`rules/intake.md`](./rules/intake.md).

2. Gather multilingual evidence and reduce it into facts, consensus, and uncertainty.
Read [`rules/research.md`](./rules/research.md).

3. Write the review in pure Markdown with the chosen language and description mode.
Read [`rules/output.md`](./rules/output.md).

4. If you are validating sample outputs, score them against the eval rules.
Read [`rules/eval.md`](./rules/eval.md).

## Done When

The review clearly answers:

1. what it sounds like
2. strengths and weaknesses
3. who should buy it
4. who should avoid it
5. confidence level and evidence boundary
