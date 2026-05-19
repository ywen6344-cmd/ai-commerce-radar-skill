# AI Commerce Radar Skill

Reusable research skill for tracking AI, technology, and cross-border commerce signals.

It helps an agent generate daily briefs, weekly reviews, urgent alerts, source audits, and business hypotheses from first-party sources such as official platform changelogs, seller policy pages, API docs, investor releases, and regulatory updates.

## What It Does

- Tracks AI, agentic commerce, marketplace, seller policy, ads, checkout, catalog, fulfillment, customs, VAT, and compliance signals.
- Prioritizes original sources over commentary.
- Scores each signal by relevance, credibility, freshness, business impact, and verifiability.
- Turns high-value updates into testable business hypotheses.
- Keeps social/community posts as leads unless they are backed by first-party evidence.

## Repository Structure

```text
ai-commerce-radar-skill/
  README.md
  .gitignore
  ai-commerce-radar/
    SKILL.md
    agents/
      openai.yaml
    references/
      source-map.md
      scoring-rules.md
      report-templates.md
      business-hypothesis-template.md
```

## Install For Hermes

Copy the `ai-commerce-radar` folder into Hermes' user skills directory:

```powershell
Copy-Item -Recurse -Force .\ai-commerce-radar "$env:LOCALAPPDATA\hermes\skills\research\ai-commerce-radar"
```

Then verify:

```powershell
hermes skills list
```

You should see:

```text
ai-commerce-radar | research | local | local | enabled
```

Use it with:

```powershell
hermes -s ai-commerce-radar
```

Example prompt:

```text
使用 ai-commerce-radar，生成今天的 AI + 跨境电商日报，优先使用一手来源，并输出 3 个可验证业务机会。
```

## Install For Codex

Copy the `ai-commerce-radar` folder into Codex skills:

```powershell
Copy-Item -Recurse -Force .\ai-commerce-radar "$env:USERPROFILE\.codex\skills\ai-commerce-radar"
```

Then start a new Codex session so the skill list refreshes.

## Example Prompts

```text
使用 ai-commerce-radar，生成今天的 AI + 跨境电商日报。
```

```text
使用 ai-commerce-radar，基于过去一周信息生成周报，并输出 3 个可验证业务机会。
```

```text
使用 ai-commerce-radar，审计我的信息源池，指出 AI、平台规则、关税合规、市场信号各自缺哪些一手源。
```

```text
使用 ai-commerce-radar，把这条 Amazon/Shopify/TikTok Shop 更新转成一个业务假设。
```

## Update Workflow

1. Update source links in `references/source-map.md`.
2. Adjust thresholds in `references/scoring-rules.md` when briefs feel too noisy or too sparse.
3. Refine output style in `references/report-templates.md`.
4. Add or retire hypotheses in `references/business-hypothesis-template.md`.
5. Reinstall the skill into Hermes/Codex after changes.

## Privacy Notes

This repo should not include:

- API keys
- Cookies
- Private seller dashboards
- Paid database credentials
- Personal business notes
- Proprietary opportunity analysis

Keep private sources and credentials in local config files outside the repository.
