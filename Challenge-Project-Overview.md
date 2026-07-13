# Responsible AI for personalized recommendations

**Company / Org:** Flow  
**Challenge Advisor:** Karla Reyes, k.reyes@outlook.com  
**Program:** Break Through Tech AI Studio - Fall 2026

---

## 🏢 About Flow

Flow focuses on personalized housing discovery for people moving to Miami. This challenge asks your team to build a **responsible AI recommendation experience** that helps newcomers compare neighborhoods and receive 3–5 area options — without unsafe steering, demographic profiling, or presenting synthetic data as live listings.

---

## 🎯 The Challenge

### Project Summary

People relocating to Miami often face a slow, unstructured housing search. In this project, you will combine **public Miami-Dade housing and migration data**, **crowd review text**, and **clearly labeled synthetic option profiles** with NLP, similarity-based recommendation ML, and an MCP-backed AI agent to deliver personalized area recommendations.

Your system should help newcomers explore neighborhoods based on **user-selected preferences** (budget, transit, social life, quiet, pets, walkability) while following responsible AI guardrails: area-level exploration only, tool-grounded answers, and explicit labeling of synthetic content.

### Success Criteria

| Metric | What it measures | Target direction |
|--------|------------------|------------------|
| **Precision@3 / Precision@5** | Do top-ranked ZIPs match held-out preference labels or advisor-defined relevance sets? | Higher is better |
| **Mean cosine similarity** | How well user preference vectors align with recommended area feature vectors | Higher is better |
| **NLP theme coverage** | Do crowd-text themes surface for recommended ZIPs across priority categories? | Broader coverage is better |
| **Tool grounding rate** | Do agent answers cite MCP/tool outputs only (no invented stats)? | Higher is better |
| **Refusal rate** | Does the agent appropriately refuse prohibited requests (tenant scoring, demographic steering, fake listings)? | Appropriate refusals expected |

### How metrics drive iteration

Use metrics as a **feedback loop**, not just a final report:

| Phase | When | If metric is weak | Next action |
|-------|------|-------------------|-------------|
| **Baseline** | September | — | Ship a simple cosine-similarity recommender on starter data; log Precision@3 and mean cosine similarity |
| **Data upgrade** | Early October | Low similarity or poor Precision@3 | Replace demo proxies with stronger public features (Census ACS, Zillow Research indices); re-normalize features |
| **Model tuning** | Mid October | Rankings feel generic or misaligned | Adjust feature weights, add budget filters, test alternative similarity metrics |
| **NLP + agent** | Late October | Low theme coverage or poor grounding | Improve theme extraction; enforce tool-only responses in the agent |
| **Responsible AI** | November | Low refusal rate on edge cases | Expand ethics prompts, blocked-request tests, and UI disclaimers |
| **Final eval** | November | — | Compare baseline vs. final on all metrics; document trade-offs in README |

### Project Milestones

Use these milestones to guide your work. Your team will create a **GitHub Projects board** to track tasks within each milestone.

| Month | Milestone | Key Activities |
|-------|-----------|----------------|
| **September** | Data Understanding | Explore starter dataset; document real vs. synthetic files; handle missing values; establish baseline Precision@3 |
| **October** | Model Development | Upgrade public features; tune recommender; add NLP themes; **expose MCP tools**; iterate when metrics plateau |
| **November** | Evaluation & Presentation | Finalize model and agent guardrails; run full metric suite; prepare presentation and portfolio README |

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset

**Name and Source:** Miami-Dade public snapshot data (Census ACS, migration indicators, Zillow Research-style indices) plus starter demo files for NLP and UI  
**Format:** CSV / TSV  
**Size:** Under 1 GB  
**Location:** [`data/`](data) folder in this repository

### Data strategy: real public data vs. synthetic demo data

This project intentionally mixes **real public aggregates** with **synthetic demo content**. Students should expand the real-data share over the semester.

| File | Type | Role |
|------|------|------|
| `miami_dade_public_features.csv` | **Real public aggregates** | Census ACS + migration + Zillow Research-style indices at ZIP level |
| `miami_dade_zctas.txt` | **Real reference** | Miami-Dade ZIP code list |
| `area_features.csv` | **Blended starter** | ZIP-level preference scores joined to public rent/migration fields; some neighborhood labels are illustrative |
| `crowd_text_snippets.csv` | **Demo text (replaceable)** | Public-style review snippets for NLP theme extraction; swap with real Kaggle/community text later |
| `area_options.csv` | **Synthetic only** | UI option cards labeled `SYN-*` — **NOT REAL LISTINGS** |

**Why this balance?** Real public data anchors recommendations in actual Miami-Dade conditions (rent, migration, population). Synthetic profiles let the team build and test the UI and agent flow immediately without scraping live listings or handling PII. As accuracy improves, shift weight toward public sources and verified review text.

### Key Details

- All data is **aggregate and snapshot-based** — no live listing scrapes, tenant records, or individual-level PII.
- Census sentinel values (e.g., `-666666666`) indicate missing or suppressed estimates; document how you handle these in preprocessing.
- Synthetic listing cards must always display their disclaimer in any UI or demo.
- See [`data_dictionary.md`](data_dictionary.md) for column definitions and limitations.

### Recommended data upgrades (October)

- Refresh Census ACS pulls via [Census API](https://www.census.gov/data/developers/data-sets.html)
- Add Zillow Research rent/home-value indices from [Zillow Research data](https://www.zillow.com/research/data/)
- Replace demo crowd text with filtered Miami/FL review corpora (e.g., [Kaggle apartment reviews](https://www.kaggle.com/datasets/teejmahis/apartment-reviews-on-googlemaps))

---

## 🛠️ Suggested Approach

**ML Problem Type:** Recommendation ML (similarity-based personalization)

**Recommended stack:**
- **Python** — core language
- **pandas / scikit-learn** — feature engineering and cosine-similarity ranking
- **NLP** — theme extraction from crowd review text
- **Streamlit** — demo UI for newcomers
- **Gemini + MCP** — tool-grounded AI agent (optional API key for live agent; fallback logic without key)
- **Docker** — optional reproducible deployment

**Evaluation Metrics:**
- Precision@3 and Precision@5
- Mean cosine similarity
- NLP theme coverage, tool grounding rate, and refusal rate (responsible AI)

---

## 🔌 MCP Server Deliverable

This project includes an **MCP (Model Context Protocol) server** so an AI agent can call your recommender and data tools instead of inventing answers.

### Required tools

Your team should expose at least these tools (names can match the reference prototype):

| Tool | Purpose |
|------|---------|
| `schema` | Return dataset columns and documentation |
| `area_stats` | Return public-style stats for one ZIP or all ZIPs |
| `crowd_themes` | Return NLP theme snippets for a ZIP |
| `recommend` | Return top-k area recommendations from user budget + preference tags |
| `ethics` | Return responsible-use charter and limitations |

### Why MCP matters here

The agent must be **tool-grounded**: it should only cite outputs from these tools (plus user-selected preferences), not make up neighborhoods, rents, or listings. Your **tool grounding rate** and **refusal rate** metrics depend on this layer.

### Reference implementation

See the Challenge Advisor prototype: [Miami Newcomer Housing Explorer](https://github.com/karlarey/miami-newcomer-explorer) (`src/mcp_server.py`, `src/tools.py`).

Detailed setup steps: [`MCP_SETUP.md`](MCP_SETUP.md)

---

## 🛡️ Responsible AI Guardrails

- **Area-level only** — recommend ZIPs/neighborhoods, not individual tenants or applicants.
- **No demographic steering** — use user-selected tags (transit, quiet, etc.), not race, ethnicity, or family status.
- **Synthetic data labeled** — `area_options.csv` cards are demos; never present them as live listings.
- **Snapshot data only** — no real-time scraping of rental sites.
- **Refuse prohibited requests** — tenant scoring, finding specific people, or bypassing fair-housing constraints.

---

## 📚 Resources to Get Started

**Background Reading:**
- [Census ACS overview](https://www.census.gov/programs-surveys/acs)
- [Zillow Research housing data](https://www.zillow.com/research/data/)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) — responsible AI context

**Technical Tutorials:**
- [scikit-learn cosine similarity](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html)
- [Streamlit docs](https://docs.streamlit.io/)
- [Model Context Protocol (MCP) docs](https://modelcontextprotocol.io/)
- [Google Gemini API quickstart](https://ai.google.dev/gemini-api/docs/quickstart)

**Code Examples:**
- [Miami Newcomer Housing Explorer](https://github.com/karlarey/miami-newcomer-explorer) — Challenge Advisor reference prototype (recommender, NLP themes, MCP tools, Streamlit app)

**Other:**
- [GitHub Projects documentation](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)

*Feel free to explore beyond these, and share anything interesting you find with me!*

---

## 🤝 How We'll Work Together

**Check-ins:** During our biweekly 60-min AI Studio Lab Section meeting block (2nd and 4th week of every month)  
**Communication:** Slack (Break Through Tech workspace)  
**Response time:** Within 48 hours on weekdays  

**Recommended Tools:**
- **Coding:** Google Colab or local Python environment
- **Collaboration:** GitHub, Notion
- **Virtual Meetings:** Zoom, Google Meet

---

## 🚀 Getting Started

1. **Review this overview document** and note any questions for our first meeting
2. **Explore the starter dataset** in the [`data/`](data) folder and read [`data_dictionary.md`](data_dictionary.md)
3. **Create a GitHub Projects board** to track September–November milestones
4. **Establish a baseline recommender** and record your first Precision@3 and mean cosine similarity scores
5. **Review [`MCP_SETUP.md`](MCP_SETUP.md)** for the MCP server deliverable and reference prototype

I'm excited to work with you!

---

## ❓ Questions?

Please bring any questions to our first meeting during the week of August 24th (Break Through Tech's Bridge to Studio - Session B).

---
