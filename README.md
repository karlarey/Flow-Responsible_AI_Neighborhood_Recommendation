# Responsible AI for Personalized Neighborhood Recommendations

**Break Through Tech AI Studio — Fall 2026**  
**Host company:** Flow  
**Challenge Advisor:** Karla Reyes ([k.reyes@outlook.com](mailto:k.reyes@outlook.com))

Help newcomers to Miami explore neighborhoods and receive **3–5 personalized area recommendations** using public housing/migration data, NLP crowd themes, similarity-based ML, and an **MCP-backed responsible AI agent**.

> **For the student team:** This README is your portfolio artifact. Sections marked *(team to complete)* should be filled in during AI Studio. Start with [Challenge-Project-Overview.md](Challenge-Project-Overview.md) and [Getting-Started-for-Fellows.md](Getting-Started-for-Fellows.md).

---

## What this project builds

1. Newcomer sets **budget** and **priorities** (transit, social, quiet, pets, walkable).
2. **ML recommender** (cosine similarity) ranks Miami-Dade ZIPs from starter data.
3. **NLP** surfaces crowd-review themes by ZIP.
4. **MCP server** exposes data and recommender tools to an AI agent.
5. **Agent** answers only from tool outputs — no invented listings or stats.

See [Challenge-Project-Overview.md](Challenge-Project-Overview.md) for milestones, success metrics, and responsible AI guardrails.

---

## Repository guide

| Path | Description |
|------|-------------|
| [Challenge-Project-Overview.md](Challenge-Project-Overview.md) | Full project brief from your Challenge Advisor |
| [data/](data/) | Starter dataset (public + synthetic demo files) |
| [data_dictionary.md](data_dictionary.md) | Column definitions and limitations |
| [MCP_SETUP.md](MCP_SETUP.md) | MCP server deliverable and setup |
| [notebooks/](notebooks/) | Your team's Jupyter notebooks *(team to complete)* |
| [requirements.txt](requirements.txt) | Python dependencies |

**Reference prototype:** [Miami Newcomer Housing Explorer](https://github.com/karlarey/miami-newcomer-explorer) — working recommender, NLP, MCP tools, and Streamlit UI.

---

## Setup and installation

### Clone and install

```bash
git clone https://github.com/Break-Through-Tech/Flow-Responsible_AI_Neighborhood_Recommendation.git
cd Flow-Responsible_AI_Neighborhood_Recommendation
python -m venv .venv
.venv\Scripts\activate          # Windows
# source .venv/bin/activate     # macOS/Linux
pip install -r requirements.txt
```

### Environment variables (optional)

```bash
copy .env.example .env
# GEMINI_API_KEY — for live Gemini agent (optional)
# CENSUS_API_KEY — for refreshing public data in October
```

### Explore the starter data

Dataset files live in [`data/`](data/). See [`data/README.md`](data/README.md) and [`data_dictionary.md`](data_dictionary.md).

| File | Type |
|------|------|
| `miami_dade_public_features.csv` | Real public aggregates |
| `area_features.csv` | Blended starter features for the recommender |
| `crowd_text_snippets.csv` | Demo text for NLP themes |
| `area_options.csv` | Synthetic UI cards — **NOT REAL LISTINGS** |

### Run the reference MCP server

Use the linked prototype repo for a working MCP example:

```bash
git clone https://github.com/karlarey/miami-newcomer-explorer.git
cd miami-newcomer-explorer
pip install -r requirements.txt
python src/mcp_server.py
```

Tools: `schema`, `area_stats`, `crowd_themes`, `recommend`, `ethics` — see [MCP_SETUP.md](MCP_SETUP.md).

---

## 👥 Team members *(team to complete)*

| Name | GitHub Handle | Contribution |
|------|---------------|--------------|
| | | |

---

## 🎯 Project highlights *(team to complete)*

- 
- 
- 

---

## 📊 Data exploration *(team to complete)*

Document your EDA, preprocessing choices, and insights from the starter and upgraded datasets.

---

## 🧠 Model development *(team to complete)*

Document your recommender, NLP approach, feature engineering, and baseline vs. final metrics (Precision@3, mean cosine similarity, etc.).

---

## 📈 Results and key findings *(team to complete)*

Document performance, responsible AI evaluation (tool grounding rate, refusal rate), and fairness/explainability notes.

---

## 🚀 Next steps *(team to complete)*

Document limitations, future data upgrades, and what you would do with more time.

---

## 📝 License

MIT License — confirm with Challenge Advisor before final submission.

---

## 🙏 Acknowledgements

- **Challenge Advisor:** Karla Reyes, Flow
- **Program:** Break Through Tech AI Studio, Fall 2026
