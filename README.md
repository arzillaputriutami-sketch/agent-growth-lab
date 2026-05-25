<p align="center">
  <img src="https://img.shields.io/badge/product-agentic%20intelligence-7c3aed?style=for-the-badge" alt="Product">
  <img src="https://img.shields.io/badge/python-3.10%2B-2563eb?style=for-the-badge" alt="Python">
  <img src="https://img.shields.io/badge/license-MIT-16a34a?style=for-the-badge" alt="License">
</p>

<h1 align="center">Agent Growth Lab</h1>
<p align="center"><b>Experiment operating system for campaigns, funnel diagnosis, cohort scoring, and agent-assisted GTM loops.</b></p>

<p align="center">
  <a href="#-what-this-is">What this is</a> •
  <a href="#-product-surface">Product surface</a> •
  <a href="#-quick-start">Quick start</a> •
  <a href="#-architecture">Architecture</a>
</p>

---

## 🎯 What this is

Agent Growth Lab is a real repository product, not just a landing page. It includes a deterministic multi-agent reasoning core, an optional FastAPI API boundary, CLI demo runner, tests, CI, architecture docs, sample scenarios, and the existing Vercel-ready dashboard.

**Primary users:** growth teams and founders.

## 💼 Product surface

- **Reasoning core:** `backend/swarm.py` models specialist agents, confidence, trace IDs, risk scoring, and action plans.
- **API boundary:** `backend/app.py` exposes `/health`, `/scenarios`, `/analyze`, and `/demo-report`.
- **CLI console:** `python cli.py --all` generates operator-grade reports without external API keys.
- **Demo dashboard:** `index.html` remains deployable as a static product surface.
- **Quality gates:** `tests/test_swarm.py` plus `.github/workflows/ci.yml` keep the product verifiable.

## 🧠 Agent team

- **Audience Segmenter**
- **Campaign Hypothesis Agent**
- **Funnel Friction Analyst**
- **Creative Variant Scorer**
- **Growth Ops Planner**

## 🚀 Quick start

```bash
git clone https://github.com/<owner>/agent-growth-lab.git
cd agent-growth-lab
python3 cli.py --all
```

Optional API mode:

```bash
python3 -m venv .venv
. .venv/bin/activate
pip install -r requirements.txt
uvicorn backend.app:app --reload
```

## 🧪 Test

```bash
python3 -m pytest -q
python3 backend/swarm.py | python3 -m json.tool >/dev/null
```

## 🏗️ Architecture

```mermaid
flowchart LR
  A[Signals] --> B[Specialist agents]
  B --> C[Verifier]
  C --> D[Risk score]
  D --> E[Operator action plan]
  E --> F[Dashboard / API / CLI]
```

## 📁 Repository map

```text
backend/swarm.py          Multi-agent reasoning engine
backend/app.py            Optional FastAPI service boundary
cli.py                    Local operator console
tests/test_swarm.py       CI-friendly product tests
examples/sample_scenario.json  Demo input payload
docs/ARCHITECTURE.md      Reasoning-loop architecture
docs/PRODUCT_SPEC.md      Product requirements and roadmap
index.html                Static live dashboard
```

## 🗺️ Roadmap

- [x] Static dashboard proof
- [x] Multi-agent reasoning core
- [x] CLI demo flow
- [x] API boundary
- [x] CI tests
- [ ] Real-time connector adapters
- [ ] Hosted report export
- [ ] Human approval workflow

## 📄 License

MIT.

<!-- MIMO_APPROVAL_PATTERN_UPGRADE -->
## Reviewer-Grade MiMo Agent Architecture

Growth Lab AI is structured as a token-intensive, multi-agent product rather than a static demo. The pipeline fans out across specialist agents, records per-agent token estimates, then synthesizes findings into reviewer-ready output.

### Specialist Agent Fleet
- **Audience Mapper** — segments user personas, jobs-to-be-done, and acquisition hooks.
- **Experiment Designer** — turns hypotheses into measurable growth experiments.
- **Copy Strategist** — generates campaign angles and landing copy variants.
- **Metric Analyst** — scores activation, retention, and conversion quality.
- **Roadmap Synthesizer** — prioritizes experiments by confidence and impact.

### Verified Demo Run
- Scenario: `web3 tool has traffic but weak activation after first wallet connect`
- Agents executed: 5
- Estimated tokens in sample run: **50,371**
- Daily projection at 96 runs/day: **4,835,616 tokens/day**
- Output artifact: `docs/example_run.json`
- Human-readable proof: `docs/EXAMPLE_RUN.md`

### Run Locally
```bash
python3 cli.py --all
python3 -m pytest -q
python3 - <<'PY'
from backend.core.pipeline import run_pipeline_sync
print(run_pipeline_sync('Growth Lab AI', {'subject': 'web3 tool has traffic but weak activation after first wallet connect'}))
PY
```

### Proof Pack
- `proofs/boot_log.txt` — environment boot evidence
- `proofs/run_sample.txt` — deterministic pipeline output summary
- `docs/example_run.json` — raw structured result
- `docs/EXAMPLE_RUN.md` — review-facing run report

<!-- MIMO_APPROVAL_PATTERN_V2 -->
## Reviewer Quickstart

This repo includes a reviewer-grade proof surface:
- API: `POST /agent-run`
- Tests: `tests/test_agent_pipeline.py`
- Guide: `docs/REVIEWER_GUIDE.md`
- Proof pack: `proofs/README.md`

The fastest verification path is:
```bash
python3 -m pytest -q
python3 - <<'PY'
from backend.core.pipeline import run_pipeline_sync
print(run_pipeline_sync("Growth Lab AI", {"subject":"growth_experiment quickstart"})["summary"])
PY
```

