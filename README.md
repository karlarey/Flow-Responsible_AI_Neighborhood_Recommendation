# Responsible AI for Personalized Neighborhood Recommendations

**Break Through Tech AI Studio — Fall 2026**  
**Host company:** Flow  
**Challenge Advisor:** Karla Reyes ([k.reyes@outlook.com](mailto:k.reyes@outlook.com))

---

## The idea, in plain terms

You're moving to Miami — maybe from NYC — and you need to figure out **where** to live and **what kind of setup** fits you.

**Example:** You and your partner want **your own apartment** in a great neighborhood. Not co-living. Not roommates. Just a private lease in a place like **Wynwood**, **Downtown**, or **Brickell**.

This recommender matches newcomers to **3–5 Miami neighborhoods** based on:

- **Budget**
- **Who's moving** — alone or with a partner
- **Housing preference** — **own apartment** (private unit) or **co-living** (shared housing if you're alone and want roommates)
- **Lifestyle** — transit, social life, quiet, pets, walkability

> **Student team:** Sections marked *(your team fills this in)* are for your portfolio. Start with [Challenge-Project-Overview.md](Challenge-Project-Overview.md).

---

## Example user stories

| Who | What they want | Where we demo |
|-----|----------------|---------------|
| **You + partner, from NYC** | Own apartment (1–2BR), no co-living | Wynwood, Downtown, Brickell |
| **You alone** | Own studio/1BR, no roommates | Wynwood, Downtown, Brickell |
| **You alone, new to city** | Co-living / roommates to meet people | Downtown, Brickell (optional path) |

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
