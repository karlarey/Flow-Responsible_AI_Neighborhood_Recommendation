# Responsible AI for Personalized Neighborhood Recommendations

**Company / Org:** Flow  
**Challenge Advisor:** Karla Reyes, k.reyes@outlook.com  
**Program:** Break Through Tech AI Studio — Fall 2026

---

## 🏢 About Flow

Flow works on helping people discover **where** and **how** to live in Miami — especially newcomers who may want **solo apartments** or **co-living** so they're not alone in a new city. Your team will build a responsible AI recommender focused on neighborhoods like **Wynwood**, **Downtown Miami**, and **Brickell**, using public data and clear guardrails.

**What we won't do:** steer people by race or family status, score individual tenants, or show fake listings as if they're real.

---

## 🎯 The Challenge

### The problem

Housing search in a new city is overwhelming. Listings are scattered, data is messy, and it's easy for an AI to sound confident while making things up. Your job is to build something **useful, grounded, and fair**.

### What you'll build

A **neighborhood + housing-type recommender** for Miami newcomers. Users pick **how they want to live**, not just where:

| Housing type | What it means | Example areas |
|--------------|---------------|---------------|
| **Co-living** | Shared housing, roommates, co-living spaces — good when you're new and don't want to live alone | Wynwood, Downtown, Brickell |
| **Solo apartment** | Your own unit in a building (studio/1BR+) — privacy, your own lease | Wynwood, Downtown, Brickell |
| **Single-family home** | Detached house with more space — yards, quieter streets, suburban feel | Kendall, Coral Gables, Pinecrest |

> **Important:** These are **housing types the user chooses** — not guesses about whether someone has kids or is married. Never infer family status from demographics.

**Urban anchors** (co-living + solo apartment demos):

| Neighborhood | ZIP | Solo apartment | Co-living |
|--------------|-----|----------------|-----------|
| **Wynwood** | 33127 | Creative, walkable studio/1BR | Shared lofts, roommate-friendly |
| **Downtown Miami** | 33128 | Own unit near Metromover | Co-living rooms near work |
| **Brickell** | 33130 | High-rise solo lease | Roommate-friendly towers |

**Single-family anchors** (when user wants a house, not a tower):

| Neighborhood | ZIP | Why it fits |
|--------------|-----|-------------|
| **Kendall** | 33186 | Suburban streets, more detached housing |
| **Coral Gables** | 33134 | Tree-lined blocks, residential houses |
| **Pinecrest** | 33156 | Quiet, family-style housing stock |

Your full system will:

1. Take **budget**, **housing type** (`co_living`, `solo_apartment`, or `single_family`), and **lifestyle preferences**
2. Recommend **3–5 Miami-Dade ZIP codes** using ML similarity matching
3. Surface **review themes** (transit, quiet, social, co_living, single_family, etc.) from crowd text
4. Connect an **AI agent** to your work through an **MCP server** so it only answers from your tools
5. **Label synthetic demo content clearly** and refuse harmful requests

### How we'll know it's working

| Metric | Plain English | Goal |
|--------|---------------|------|
| **Precision@3 / @5** | Of the top 3 (or 5) ZIPs you recommend, how many are actually good matches? | Higher is better |
| **Mean cosine similarity** | How closely do recommended areas match the user's stated preferences? | Higher is better |
| **NLP theme coverage** | Do recommended areas have review themes for the categories users care about? | Broader is better |
| **Tool grounding rate** | Does the agent stick to your tool outputs instead of inventing facts? | Higher is better |
| **Refusal rate** | When someone asks something off-limits (tenant scoring, demographic steering), does the agent say no? | Should refuse appropriately |

### Use metrics to improve — not just to report

Don't wait until November to check these. Use them like a GPS:

| When | What to do | If results are weak… |
|------|------------|----------------------|
| **September** | Build a simple baseline recommender | — |
| **Early October** | Swap in stronger public data (Census, Zillow indices) | Recommendations feel random → upgrade features |
| **Mid October** | Tune weights, filters, similarity approach | Top picks all look the same → adjust model |
| **Late October** | Add NLP themes + MCP tools + agent | Agent makes up stats → enforce tool-only answers |
| **November** | Test edge cases and fair-housing refusals | Agent says yes to bad requests → tighten ethics layer |
| **End of semester** | Compare baseline vs. final; write it up in README | — |

### Monthly milestones

| Month | Focus | Your main tasks |
|-------|-------|-----------------|
| **September** | Understand the data | Explore CSVs, note what's real vs. demo, handle missing values, get a baseline score |
| **October** | Build and improve the model | Better public data, recommender tuning, NLP themes, **MCP server** |
| **November** | Evaluate and present | Final metrics, responsible AI checks, presentation + README |

> **Tip:** Create a GitHub Projects board in this repo. Add columns for September, October, and November. Break big tasks into weekly to-dos.

---

## 📊 Dataset

**Source:** Public Miami-Dade snapshots (Census, migration, rent indices) + starter demo files  
**Format:** CSV  
**Size:** Under 1 GB — easy to work with in Colab or locally  
**Where:** [`data/`](data) folder in this repo

### Real data vs. demo data — why both?

| File | Real or demo? | Why it's here |
|------|---------------|---------------|
| `miami_dade_public_features.csv` | **Real** | Actual public stats by ZIP — rent, population, migration |
| `miami_dade_zctas.txt` | **Real** | List of Miami-Dade ZIP codes |
| `area_features.csv` | **Mixed starter** | Includes `co_living_friendly` and `single_family_friendly`; urban anchors **Wynwood, Downtown, Brickell**; suburban anchors **Kendall, Coral Gables, Pinecrest** |
| `crowd_text_snippets.csv` | **Demo** | Themes for co_living, single_family, transit, social, etc. |
| `area_options.csv` | **Synthetic only** | `living_type`: `co_living`, `solo_apartment`, or `single_family` — **NOT REAL LISTINGS** |

**The plan:** Start with this mix so you can build fast. Over the semester, replace demo pieces with stronger public sources. The recommender should lean more on real data as you go.

### Good to know

- Everything is **snapshots** — not live Zillow feeds or scraped listings
- Some Census values show as `-666666666` when data is missing; decide how to handle that in cleaning
- Any UI showing `area_options.csv` must say clearly that cards are demos
- Column details: [`data_dictionary.md`](data_dictionary.md)

### Data upgrades for October

- [Census API](https://www.census.gov/data/developers/data-sets.html) — fresher ACS pulls
- [Zillow Research data](https://www.zillow.com/research/data/) — rent and home-value indices
- [Kaggle apartment reviews](https://www.kaggle.com/datasets/teejmahis/apartment-reviews-on-googlemaps) — real review text filtered for Miami/FL

---

## 🛠️ Suggested tools

| Tool | What you'll use it for |
|------|------------------------|
| **Python** | Everything |
| **pandas + scikit-learn** | Data prep and similarity-based recommendations |
| **NLP** | Pulling themes from review text |
| **Streamlit** | Simple demo app for users |
| **Gemini + MCP** | AI agent that calls your tools (Gemini key optional) |
| **Docker** | Optional — for reproducible deployment |

---

## 🔌 MCP server — what it is and why you need it

**MCP (Model Context Protocol)** is a standard way for an AI agent to call your code — like giving it a fixed set of reliable functions instead of letting it guess.

Your team will build an MCP server with **five tools**:

| Tool | What it does |
|------|--------------|
| `schema` | "Here are the columns in our dataset." |
| `area_stats` | "Here are the stats for this ZIP (or all ZIPs)." |
| `crowd_themes` | "Here's what people say about transit, quiet, etc. in this ZIP." |
| `recommend` | "Given budget, housing type, and preferences, here are the top areas." |
| `ethics` | "Here's what this tool is allowed and not allowed to do." |

**Why it matters:** If the agent can only speak through these tools, it's much harder for it to invent a $1,200 Brickell apartment that doesn't exist. That's your **tool grounding rate**.

**See it working:** [Miami Newcomer Housing Explorer](https://github.com/karlarey/miami-newcomer-explorer)  
**Setup guide:** [MCP_SETUP.md](MCP_SETUP.md)

---

## 🛡️ Responsible AI — non-negotiables

- **Neighborhoods, not people** — recommend areas, never score tenants or applicants
- **User picks preferences** — no steering by race, ethnicity, or family status
- **Label fake listings** — `area_options.csv` is for demos only
- **No live scraping** — use public snapshots, not real-time rental site crawlers
- **Say no when you should** — refuse tenant scoring, demographic filtering, or anything that breaks fair housing spirit

---

## 📚 Helpful links

**Background:**
- [Census ACS](https://www.census.gov/programs-surveys/acs)
- [Zillow Research data](https://www.zillow.com/research/data/)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)

**Technical:**
- [scikit-learn cosine similarity](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html)
- [Streamlit](https://docs.streamlit.io/)
- [MCP docs](https://modelcontextprotocol.io/)
- [Gemini API](https://ai.google.dev/gemini-api/docs/quickstart)

**Code to study:**
- [Miami Newcomer Housing Explorer](https://github.com/karlarey/miami-newcomer-explorer)

---

## 🤝 Working together

**Check-ins:** Biweekly during AI Studio Lab (2nd and 4th week of each month)  
**Chat:** Slack (Break Through Tech workspace)  
**I'll reply within:** 48 hours on weekdays  

**Tools we recommend:** Google Colab or local Python, GitHub, Notion, Zoom/Meet

---

## 🚀 Your first week

1. Read this doc and write down questions
2. Open the [`data/`](data) folder and skim the CSVs
3. Create your GitHub Projects board
4. Build a simple baseline recommender and record your first scores
5. Read [MCP_SETUP.md](MCP_SETUP.md) and try the reference prototype

Looking forward to working with you!

---

## ❓ Questions?

Bring them to our first meeting — week of **August 24th** (Bridge to Studio, Session B).

---
