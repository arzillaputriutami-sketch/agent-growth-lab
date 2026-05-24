# Agent Growth Lab Architecture

## Purpose

Experiment operating system for campaigns, funnel diagnosis, cohort scoring, and agent-assisted GTM loops.

## Runtime loop

1. **Observe** — collect domain signals: activation_rate, wallet_connect_dropoff, referral_k_factor, campaign_cac, retention_d7.
2. **Orient** — map the active scenario to specialist agent responsibilities.
3. **Decide** — score severity, confidence, and operator urgency.
4. **Act** — emit next actions that a human operator can verify.
5. **Reflect** — attach trace IDs and deterministic evidence for review.

## Components

- `backend/swarm.py` — pure Python reasoning core, safe for CI and static demos.
- `backend/app.py` — FastAPI wrapper for product integration.
- `cli.py` — terminal demo path for reviewers.
- `index.html` — front-facing dashboard surface.

## Agent responsibilities

- `Audience Segmenter`: owns one part of the analysis loop.
- `Campaign Hypothesis Agent`: owns one part of the analysis loop.
- `Funnel Friction Analyst`: owns one part of the analysis loop.
- `Creative Variant Scorer`: owns one part of the analysis loop.
- `Growth Ops Planner`: owns one part of the analysis loop.

## Production extension points

- Replace deterministic signals with live connectors.
- Persist reports in Postgres or SQLite.
- Add auth and organization workspaces.
- Add export hooks for Slack, Discord, Telegram, or email.
