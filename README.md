# Responsible AI for Personalized Neighborhood Recommendations

**Break Through Tech AI Studio — Fall 2026**  
**Host company:** Flow  
**Challenge Advisor:** Karla Reyes ([k.reyes@outlook.com](mailto:k.reyes@outlook.com))

---

## The idea, in plain terms

Moving to Miami is exciting — but finding the **right neighborhood** and **right living setup** is hard. Do you want your own place, or co-living with roommates so you're not alone in a new city?

This project builds a recommender that helps newcomers:

1. **Localize** to the best Miami neighborhoods for them
2. Choose a **living style** — **solo apartment** or **co-living / shared housing**
3. Get **3–5 tailored suggestions** — starting with **Wynwood**, **Downtown Miami**, and **Brickell**

We use public data, machine learning, and a responsible AI assistant that answers from real tool outputs — not made-up listings.

> **Student team:** This README becomes your portfolio at the end of the semester. Sections marked *(your team fills this in)* are for you. Start with [Challenge-Project-Overview.md](Challenge-Project-Overview.md).

---

## What you'll build

| Step | What happens |
|------|----------------|
| 1 | User picks **budget**, **living style** (solo or co-living), and **priorities** (transit, social, quiet, pets, walkable). |
| 2 | A **recommender model** ranks ZIP codes — with strong starter examples in **Wynwood**, **Downtown**, and **Brickell**. |
| 3 | **NLP** pulls themes from reviews (including co-living and social life). |
| 4 | An **MCP server** gives the AI agent access to your data and recommender. |
| 5 | The **agent** answers only from those tools — no fake apartments or invented rent. |

### Anchor neighborhoods to demo

| Area | ZIP | Good for solo if… | Good for co-living if… |
|------|-----|-------------------|------------------------|
| **Wynwood** | 33127 | You want creative, walkable, social | You want roommates and community when new |
| **Downtown Miami** | 33128 | You want central transit and your own unit | You want shared housing near work |
| **Brickell** | 33130 | You want a high-rise and Metrorail | You want roommate-friendly towers |

Full details: [Challenge-Project-Overview.md](Challenge-Project-Overview.md)

---

## What's in this repo

| File or folder | What's inside |
|----------------|---------------|
| [Challenge-Project-Overview.md](Challenge-Project-Overview.md) | The full project brief — milestones, metrics, guardrails |
| [data/](data/) | Starter dataset to explore on day one |
| [data_dictionary.md](data_dictionary.md) | What each column means |
| [MCP_SETUP.md](MCP_SETUP.md) | How to build and run the MCP server |
| [notebooks/](notebooks/) | Your team's notebooks *(your team fills this in)* |
| [requirements.txt](requirements.txt) | Python packages you'll need |

**Working example to learn from:** [Miami Newcomer Housing Explorer](https://github.com/karlarey/miami-newcomer-explorer) — has a recommender, NLP, MCP tools, and a Streamlit demo app.

---

## Get started locally

### 1. Clone and install

```bash
git clone https://github.com/Break-Through-Tech/Flow-Responsible_AI_Neighborhood_Recommendation.git
cd Flow-Responsible_AI_Neighborhood_Recommendation
python -m venv .venv
.venv\Scripts\activate          # Windows
# source .venv/bin/activate     # macOS/Linux
pip install -r requirements.txt
```

### 2. Optional API keys

```bash
copy .env.example .env
```

- `GEMINI_API_KEY` — only if you want the live Gemini agent (optional)
- `CENSUS_API_KEY` — if you refresh public Census data later in the semester

### 3. Look at the data

Open the [`data/`](data/) folder. Here's what each file is:

| File | What it is |
|------|------------|
| `miami_dade_public_features.csv` | **Real public data** — rent, population, migration by ZIP |
| `area_features.csv` | **Starter file for the model** — includes `co_living_friendly`; see **Wynwood, Downtown, Brickell** |
| `crowd_text_snippets.csv` | **Sample review text** — includes co-living themes |
| `area_options.csv` | **Fake demo cards** — `living_type`: `solo` or `co_living` — **NOT REAL LISTINGS** |

More detail: [`data/README.md`](data/README.md) and [`data_dictionary.md`](data_dictionary.md).

### 4. Try the reference MCP server

Clone the working prototype and run it:

```bash
git clone https://github.com/karlarey/miami-newcomer-explorer.git
cd miami-newcomer-explorer
pip install -r requirements.txt
python src/mcp_server.py
```

The server exposes five tools: `schema`, `area_stats`, `crowd_themes`, `recommend`, and `ethics`. See [MCP_SETUP.md](MCP_SETUP.md).

---

## 👥 Team members *(your team fills this in)*

| Name | GitHub | What they worked on |
|------|--------|---------------------|
| | | |

---

## 🎯 Project highlights *(your team fills this in)*

What did you build? What results did you get? Add 3–5 bullet points here at the end of the semester.

---

## 📊 Data exploration *(your team fills this in)*

What did you learn from the data? What cleaning or fixes did you make?

---

## 🧠 Model development *(your team fills this in)*

How does your recommender work? What was your baseline vs. final performance?

---

## 📈 Results *(your team fills this in)*

Share your metrics, charts, and responsible AI findings (did the agent stay grounded? did it refuse bad requests?).

---

## 🚀 Next steps *(your team fills this in)*

What would you improve with more time?

---

## 📝 License

MIT License — check with your Challenge Advisor before final submission.

---

## 🙏 Acknowledgements

- **Challenge Advisor:** Karla Reyes, Flow
- **Program:** Break Through Tech AI Studio, Fall 2026
