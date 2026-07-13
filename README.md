# Responsible AI for Personalized Neighborhood Recommendations

**Break Through Tech AI Studio — Fall 2026**  
**Host company:** Flow  
**Challenge Advisor:** Karla Reyes ([k.reyes@outlook.com](mailto:k.reyes@outlook.com))

---

## The idea, in plain terms

**For newcomers:** You're moving to Miami — maybe from NYC — and need the **right neighborhood** and **living setup** (e.g. you and your partner, your own apartment in Wynwood, Downtown, or Brickell — no co-living).

**For Flow:** A **recommendation engine + LLM** that improves **occupancy** (faster, better lease matches) and **renewals** (residents who fit their area stay longer). Stronger operations look better to **PE investors and lenders**.

This project builds that engine: match users to **3–5 neighborhoods** from budget, household, housing preference, and lifestyle — with an MCP-backed LLM that explains results without inventing listings.

> **Student team:** Sections marked *(your team fills this in)* are for your portfolio. Start with [Challenge-Project-Overview.md](Challenge-Project-Overview.md).

---

## Example user stories

| Who | What they want | Business impact for Flow |
|-----|----------------|--------------------------|
| **Couple from NYC** | Own apartment in Wynwood / Downtown / Brickell | Faster lease decision → **occupancy** |
| **Solo mover** | Own studio/1BR, no roommates | Better initial fit → **renewal** likelihood |
| **Solo, wants community** | Co-living (optional path) | Fill appropriate inventory → **occupancy** |

---

## What you'll build

| Step | What happens |
|------|----------------|
| 1 | User enters budget, alone vs. with partner, own apartment vs. co-living, and lifestyle priorities |
| 2 | Recommender ranks ZIP codes — prioritizing **own apartment** matches for couples and solo movers |
| 3 | NLP surfaces review themes (transit, social, co_living, etc.) |
| 4 | MCP server + agent answer only from tool outputs |

### Anchor neighborhoods (own apartment)

| Area | ZIP | Why newcomers like it |
|------|-----|------------------------|
| **Wynwood** | 33127 | Creative, walkable, social — good for couples who want energy |
| **Downtown Miami** | 33128 | Central, Metromover, easy commute |
| **Brickell** | 33130 | Towers, Metrorail, restaurants, young professional vibe |

Full details: [Challenge-Project-Overview.md](Challenge-Project-Overview.md)

---

## What's in this repo

| File or folder | What's inside |
|----------------|---------------|
| [Challenge-Project-Overview.md](Challenge-Project-Overview.md) | Full project brief |
| [data/](data/) | Starter dataset |
| [data_dictionary.md](data_dictionary.md) | Column definitions |
| [MCP_SETUP.md](MCP_SETUP.md) | MCP server guide |

**Reference prototype:** [Miami Newcomer Housing Explorer](https://github.com/karlarey/miami-newcomer-explorer)

---

## Get started locally

```bash
git clone https://github.com/Break-Through-Tech/Flow-Responsible_AI_Neighborhood_Recommendation.git
cd Flow-Responsible_AI_Neighborhood_Recommendation
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

Starter data is in [`data/`](data/). Key fields:

| File | Key columns |
|------|-------------|
| `area_features.csv` | ZIP scores + `co_living_friendly` |
| `area_options.csv` | `housing_preference` (`own_apartment` / `co_living`), `household` (`alone` / `with_partner`) |
| `crowd_text_snippets.csv` | Review themes by ZIP |

---

## 👥 Team members *(your team fills this in)*

| Name | GitHub | What they worked on |
|------|--------|---------------------|
| | | |

---

## 🎯 Project highlights *(your team fills this in)*

---

## 📊 Data exploration *(your team fills this in)*

---

## 🧠 Model development *(your team fills this in)*

---

## 📈 Results *(your team fills this in)*

---

## 🚀 Next steps *(your team fills this in)*

---

## 📝 License

MIT License — confirm with Challenge Advisor before final submission.

---

## 🙏 Acknowledgements

- **Challenge Advisor:** Karla Reyes, Flow
- **Program:** Break Through Tech AI Studio, Fall 2026
