# n8n Revenue Ops CRM Sync

Scheduled stale-deal sync with enrichment, AI slippage-risk analysis, rescue-task branching, and RevOps alerts.

## Files
- `n8n/workflow.json` importable n8n workflow (AI-assisted + deterministic fallback)

## Architecture
- 6-hour trigger -> stale-deal fetch -> enrichment
- Deterministic deal health scoring + AI risk analysis
- Signal merge -> final risk decision
- At-risk branch to rescue tasks + CRM health upsert + RevOps channel notifications

## Runtime Requirements
- n8n (validated with containerized import on n8n latest)
- Set `OPENROUTER_API_KEY` in your n8n environment for AI nodes
- Replace placeholder webhook/API endpoints and credentials before activation

## Import
1. Open n8n UI.
2. Go to `Workflows -> Import from File`.
3. Select `n8n/workflow.json`.
4. Configure credentials and endpoint placeholders.
5. Run a manual execution test before enabling schedule/webhook traffic.

## Live Demo
- https://jeffery-addae-portfolio-web.vercel.app/projects/revenue-ops-crm-sync-enrichment-pipeline
