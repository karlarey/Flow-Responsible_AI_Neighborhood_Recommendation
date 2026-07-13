# Stakeholders & Value Proposition

This project is a **recommendation / personalization engine** connected to an **LLM via MCP**. Each stakeholder gets different value — but all depend on the same thing: **accurate matches, grounded answers, and measurable quality**.

---

## Stakeholder map

| Stakeholder | Role | Value proposition |
|-------------|------|-------------------|
| **Prospective residents** | End user | Find the right Miami neighborhood and living setup faster — without fake listings or AI guesswork |
| **Flow (operations)** | Host company / deployer | **Higher occupancy** (faster lease-up) and **higher renewals** (better initial fit → residents stay) |
| **Flow (capital markets)** | Reports to PE & lenders | Data-backed story: responsible AI improves leasing ops and portfolio performance |
| **PE investors** | Equity capital | Stronger occupancy + retention → better NOI narrative → confidence in the asset |
| **Lenders** | Debt capital | Predictable cash flow from stable occupancy and renewals → lower perceived risk |
| **Student team** | Builders | Portfolio artifact: rec engine + MCP + LLM + eval framework |
| **Challenge Advisor** | Flow / Karla Reyes | Production-ready prototype path for Flow's leasing experience |

---

## Value proposition by stakeholder

### 1. Prospective residents (end users)

**Pain:** Moving to Miami is overwhelming — too many neighborhoods, unclear fit, untrustworthy AI answers.

**Value:**
- **3–5 personalized neighborhood recommendations** based on budget, household, and lifestyle
- **Own apartment** path (e.g. couple from NYC — Wynwood, Downtown, Brickell)
- **Conversational LLM** that explains *why* areas match — citing real tool data only
- **Responsible AI:** no demographic steering, no fake apartments

**Success looks like:** "I found areas that fit us in days, not weeks — and I trust the answers."

---

### 2. Flow — operations & leasing

**Pain:** Slow or mismatched searches → lost prospects (vacancy) and unhappy residents who leave at renewal.

**Value:**

| Metric | How this system helps |
|--------|------------------------|
| **Occupancy** | Better personalization → prospects commit to a lease faster |
| **Renewals / retention** | Right neighborhood + living setup upfront → residents satisfied long-term |
| **Leasing efficiency** | LLM handles exploratory questions; rec engine does ranking — scalable onboarding |
| **Brand trust** | Grounded AI (MCP tools) vs. competitors with hallucinating chatbots |

**Success looks like:** Higher conversion from inquiry → lease, and improved renewal rates in matched cohorts.

---

### 3. PE investors

**Pain:** Need proof that Flow operates the portfolio efficiently and grows revenue predictably.

**Value:**
- **Differentiation:** Flow uses measurable AI personalization — not just marketing
- **Operational alpha:** Faster lease-up and retention improve same-store performance
- **Due diligence story:** Eval framework (Precision@k, grounding rate) shows rigor, not hype

**They don't use the app.** They evaluate **occupancy %, renewal rates, NOI trends** — this system is a lever to improve those numbers.

**Success looks like:** "Flow has a data-driven leasing engine that supports portfolio growth."

---

### 4. Lenders

**Pain:** Underwriting depends on stable occupancy and predictable rental income.

**Value:**
- Lower vacancy risk when prospects match communities faster
- Retention supports debt service coverage
- Responsible AI reduces fair-housing / reputational risk vs. reckless automation

**Success looks like:** Consistent occupancy and renewal metrics in Flow's reporting.

---

### 5. Student team

**Value:**
- Real-world architecture: **rec engine → MCP → LLM**
- Responsible AI constraints (grounding, refusals)
- Eval framework to prove the **whole stack** works — not just a demo
- Portfolio piece for AI Studio

---

## Why the value proposition matters for your build

If the architecture is wrong, stakeholders lose trust:

| Failure | Who gets hurt |
|---------|---------------|
| Bad recommendations | Residents + Flow occupancy |
| LLM invents listings | Everyone — legal/reputation risk |
| Wrong tool routing | Broken user experience |
| No refusals on bad requests | Flow + fair housing exposure |

That's why we include **[EVAL_FRAMEWORK.md](EVAL_FRAMEWORK.md)** — students must **measure** accuracy at every layer, not just demo a chatbot.

---

## One-line pitch

> **For residents:** the right Miami neighborhood, explained clearly.  
> **For Flow:** occupancy and renewals through better matches.  
> **For PE/lenders:** stronger portfolio metrics backed by responsible, measurable AI.

See also: [ARCHITECTURE.md](ARCHITECTURE.md) | [EVAL_FRAMEWORK.md](EVAL_FRAMEWORK.md)
