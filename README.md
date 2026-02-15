# n8n Revenue Ops CRM Sync

Scheduled stale-deal sync with enrichment, AI slippage-risk analysis, rescue-task branching, and RevOps alerts.

## Files
- `n8n/workflow.json` importable n8n workflow (AI Agent + deterministic fallback + native app nodes)

## Architecture
- 6-hour trigger -> HubSpot deal search -> deterministic risk scoring
- AI Agent + OpenAI Chat Model risk analysis
- Signal merge -> final risk decision
- HubSpot sync + Notion log + Slack branch + Gmail RevOps summary

## Runtime Requirements
- n8n (validated with containerized import on n8n latest)
- Configure credentials for:
  - `OpenAI` (for `AI Agent` model connection)
  - `Slack`
  - `Notion`
  - `Gmail`
  - `HubSpot` (where used)
- Replace placeholder channel/database IDs and recipient addresses before activation

## Import
1. Open n8n UI.
2. Go to `Workflows -> Import from File`.
3. Select `n8n/workflow.json`.
4. Configure credentials and placeholder IDs.
5. Run a manual execution test before enabling schedule/webhook traffic.

## Live Demo
- https://jeffery-addae-portfolio-web.vercel.app/projects/revenue-ops-crm-sync-enrichment-pipeline
