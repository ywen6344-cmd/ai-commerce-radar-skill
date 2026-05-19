---
name: ai-commerce-radar
description: Track AI, technology, and cross-border commerce signals for industry research and business opportunity discovery. Use when Codex or an agent needs to generate daily briefs, weekly reviews, urgent alerts, source audits, scoring, evidence-chain checks, or business hypotheses from first-party sources such as official platform changelogs, policy pages, API docs, investor releases, and marketplace seller updates.
---

# AI Commerce Radar

## Workflow

Use this skill to turn scattered AI, technology, and cross-border commerce updates into concise research outputs with evidence, scores, and business implications.

1. Identify the user's output type: daily brief, weekly review, urgent alert, source audit, business hypothesis, or source-map update.
2. Prefer first-party sources: official changelogs, policy pages, API docs, investor relations, regulatory pages, and platform seller updates.
3. For each candidate signal, capture source, date, source grade, verification status, impact area, and original link.
4. Score with the 100-point system in `references/scoring-rules.md`.
5. Include only signals that can support industry judgment, business action, or a hypothesis.
6. Keep C-grade social/community information as leads only. Do not turn it into a conclusion without S/A support.
7. Convert high-value signals into business hypotheses when they reveal a change in rules, costs, automation potential, distribution, compliance, or buyer behavior.

## Source Selection

Use `references/source-map.md` when building or updating the source pool. Prioritize:

- AI model, API, agent, and developer ecosystem updates
- Commerce platform rules and APIs: Amazon, Shopify, TikTok Shop, Google Merchant Center, YouTube, Meta
- Customs, VAT, tariffs, product compliance, and marketplace enforcement
- Product discovery, catalog, ads, affiliate, creator commerce, and checkout infrastructure
- Company filings, investor releases, product launches, and official event pages

## Output Rules

Use `references/report-templates.md` for the final shape.

Daily briefs should be short: 5-10 signals, one top conclusion, source links, scores, and 1-3 opportunity candidates.

Weekly reviews should synthesize: 3-5 major changes, trend judgments, evidence chains, strengthened or weakened hypotheses, and next-week watch items.

Urgent alerts should be even shorter: what changed, who is affected, source link, confidence, and recommended action.

Business hypotheses should follow `references/business-hypothesis-template.md` and include target user, pain, evidence, MVP, validation method, risk, and next action.

## Quality Bar

Reject weak summaries. A useful item must answer at least two of:

- What rule changed?
- What cost changed?
- What workflow can now be automated?
- What platform behavior changed?
- What new distribution or traffic surface appeared?
- What compliance or operational risk increased?
- What product or service opportunity follows?

Label uncertainty clearly:

- `已验证`: at least one S/A source plus an independent corroborating signal or direct documentation.
- `交叉验证中`: an S/A source exists, but market impact is not yet observed.
- `待验证`: only B/C sources, event previews, rumors, or indirect reports.

## References

- `references/source-map.md`: source pool and high-value signal types.
- `references/scoring-rules.md`: source grades, 100-point scoring, entry thresholds, and verification rules.
- `references/report-templates.md`: daily brief, weekly review, urgent alert, and source-audit templates.
- `references/business-hypothesis-template.md`: reusable business opportunity template and starter hypotheses.
