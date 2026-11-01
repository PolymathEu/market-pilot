# MarketPilot

**AI Marketing Intelligence & Strategy System**  
**Deep Intelligence. High Clarity. Maximum Impact.**

MarketPilot helps business owners understand their business and market, diagnose root causes, identify opportunities, choose strategic priorities, and turn decisions into execution plans. It is designed to work through the user's AI workspace, not as an analytics dashboard or code-execution application.

## Get Started
## Install in Claude.ai

1. Use a Claude account with custom Skills and code execution available. Current upload guidance and limits are in Anthropic's [custom Skills help article](https://support.claude.com/en/articles/12512198-creating-custom-skills).
2. Upload `market-pilot.zip` from Claude Settings > Features. The Skill folder must be the ZIP's root folder and contain `SKILL.md`.
3. Complete `templates/business-context-template.md` and make the document accessible in the chat or Project where MarketPilot will be used.
4. Ask for the business-specific analysis or decision you need. MarketPilot routes to relevant capabilities automatically. General educational questions do not require Business Context.

## Install in Claude Code

Extract the `market-pilot` Skill folder from the ZIP into `.claude/skills/market-pilot/` in a project or `~/.claude/skills/market-pilot/` for personal use. Claude.ai, Claude Code, and the Claude API manage custom Skills separately; installing on one surface does not sync them to another.

No Python installation, MarketPilot scripts, terminal configuration, or analytics infrastructure is required. If Business Context is missing, inaccessible, or empty, business-specific work stops at the exact gate response. Supporting reports remain optional and task-dependent.

Supporting reports are optional and task-dependent. If a recommendation requires unavailable data, MarketPilot names the specific gap and explains its effect rather than inventing results.

## Strategic Capabilities

1. Business Diagnosis
2. Market Intelligence
3. Customer Psychology
4. Positioning Strategy
5. Offer & Pricing Strategy
6. Growth & Go-to-Market Strategy
7. Campaign & Creative Strategy
8. Conversion Rate Optimization (CRO)
9. Retention Strategy
10. Execution & Budget Strategy

Supporting capabilities include Opportunity Radar, Strategic Marketing Diagnosis, 80/20 Prioritization, Strategic Self-Critique, and the Visual Strategy Canvas.

The system routes requests to relevant capabilities automatically. Comprehensive strategy requests connect business diagnosis, market and customer insight, strategy, prioritization, and execution; narrow requests receive focused answers.

## Analytical Integrity

MarketPilot distinguishes FACT, CALCULATION, ASSUMPTION, HYPOTHESIS, and DATA UNAVAILABLE. Financial reasoning, unit economics, CAC, CPA, ROAS, contribution margin, break-even analysis, attribution, cohorts, retention, and budget allocation remain part of its strategic guidance.

Calculations use supplied inputs and transparent formulas. MarketPilot does not claim to execute scripts, validate large datasets, access advertising platforms, or retrieve current market research unless the relevant tool is available and actually used. External claims require current sources when research tools are available; otherwise, the limitation is stated.

## Repository Map

- `SKILL.md`: central operating instructions and request routing
- `references/`: ten strategic modules and supporting frameworks
- `rules/`: data, financial, attribution, decision, and output safeguards
- `templates/`: Business Context and project instruction templates
- `examples/`: illustrative business contexts and outputs