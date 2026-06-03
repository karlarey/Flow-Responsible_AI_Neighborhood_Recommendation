---

> ## Challenge Advisor: Update & Finalize Your Project Overview
>
> > 💡 **These grey text instructions are just for you, the team's Challenge Advisor; please delete them once you have completed the steps below.**
>
> We've pre-populated this Challenge Project Overview page — which is what will be shared with your Break Through Tech student team in August — using the details from your submission form. You should have received an email inviting you to join this repo as a Collaborator, enabling you to add files and make edits.
> 
> In order for your project to be finalized and assigned to a team, please:
> 1. **Review all sections below** and update or expand any content as needed, making sure to address the SME Feedback in the section immediately below. Look for square brackets to find the places below that require additional inputs from you (e.g., "About [Company / Org Name]").
> 2. **Add your dataset** to the [data folder](data) in this repo.
> 3. **Close the Issue assigned to you in this repo** to let us know that you have made your edits and the overview page is ready for final review. You can do this by going to the _Issues_ tab in the top left section of the menu above, add a comment that says "CA review complete", and click the button to Close the Issue. 
>
> If you're unfamiliar with how to edit a page like this in GitHub, check out [this tutorial](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/handson/edit-readme.html) for a quick overview (start with step 2 and only edit this page), and [this guide](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/markdown.html) on how to use Markdown to compose text.
>
>
> ❌ Remember that this is a public repo. Do NOT include: Proprietary data, PII, API keys, credentials, or anything confidential.

---

## 📋 BTT Internal Evaluation Notes
*(This section is for BTT staff only — remove before sharing with students)*

| Check | Status | Notes |
|-------|--------|-------|
| Python Compatibility | 🟢| The tech stack is centered around Python, ensuring compatibility with the fellows' skill set in ML foundations. |
| Data Readiness | 🟢| The data size is under 1GB, indicating it is manageable and presumably clean enough for use within a semester without extensive preprocessing. |
| Resource Check | 🟢| Only requires the Google Colab free tier, which is accessible to all students and poses no additional hurdles. |

**Student Fit Score:** 8/10  
**Technical Depth Score:** 7/10  
**Overall Recommendation:** REVISE

**Advisor Feedback Draft:**
The project effectively leverages NLP and recommendation systems to provide individual experiences for newcomers in Miami, addressing a real pain point. However, to ensure the project meets its goals, focus on balancing the use of synthetic profiles with real-world data for better accuracy. Additionally, clarify how the measures of success will guide iterative improvements in the model. Consider these adjustments to maximize impact.

---

# Responsible AI for personalized recommendations

**Company / Org:** Flow  
**Challenge Advisor:** Karla Reyes, k.reyes@outlook.com  
**Program:** Break Through Tech AI Studio - Fall 2026

---

## 🏢 About Flow

Flow specializes in delivering innovative solutions for personalized housing recommendations, focused on enhancing the experience for newcomers in the Miami area through advanced AI technologies.

---

## 🎯 The Challenge

### Project Summary
In this project, you will use public Miami housing/migration data, crowd review text, and synthetic option profiles and NLP plus recommendation ML (similarity-based personalization) and an MCP-backed AI agent to deliver 3–5 personalized area recommendations for newcomers. This will help address slow, unstructured housing search for people moving to Miami without unsafe steering or real-time listing scraping.

### Success Criteria
Ranking quality (Precision@3 and Precision@5), Match quality (Mean cosine similarity), NLP theme coverage, tool grounding (answers must cite tool outputs only), and refusal rate for prohibited requests.

### Project Milestones

Use these milestones to guide your work. Your team will create a **GitHub Projects board** to track tasks within each milestone.

| Month | Milestone | Key Activities |
|-------|-----------|----------------|
| **September** | Data Understanding | Explore dataset, handle missing values, document findings |
| **October** | Model Development | Train baseline model, experiment with approaches, iterate |
| **November** | Evaluation & Presentation | Finalize model, prepare presentation, document results |

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset

**Name and Source:** Public snapshot datasets for Miami-Dade (census/ACS, rent benchmarks, migration indicators)  
**Format:** CSV/TSV  
**Size:** under 1gb  
**Location:** [Link to dataset or instructions for accessing it]

### Key Details
- Public snapshot datasets for Miami-Dade (census/ACS, rent benchmarks, migration indicators), synthetic area profiles, and public apartment/community text. Data is stored in CSV/TSV format and includes numerical, categorical, text, and time series data.
- [Any known limitations or preprocessing needed]
- [Link to data dictionary or documentation, if available]

---

## 🛠️ Suggested Approach

**ML Problem Type:** Recommendation ML (similarity-based personalization)

**Recommended Libraries:**
- NLP
- Recommendation ML (similarity-based personalization)
- MCP-backed AI agent
- Python
- Gemini agent
- Streamlit
- Docker

**Evaluation Metrics:**
- Precision@3
- Precision@5
- Mean cosine similarity

---

## 📚 Resources to Get Started

The following resources will help your team understand the problem space and potential technical approaches for this project:

**Background Reading:**
- [e.g., Link to an article or blog post about the problem domain]
- [e.g., Link to an industry report or case study]

**Technical Tutorials:**
- [e.g., Link to a free tutorial on the ML technique(s) involved]
- [e.g., Link to documentation for a key library or tool]

**Code Examples:**
- [e.g., Link to a relevant GitHub repo]
- [e.g., Link to a sample implementation or starter code]

**Other:**
- [Links to any additional resources — e.g., papers, videos, podcasts, etc.]

*Feel free to explore beyond these, and share anything interesting you find with me!*

---

## 🤝 How We'll Work Together

**Check-ins:** During our biweekly 60-min AI Studio Lab Section meeting block (2nd and 4th week of every month)  
**Communication:** Slack (Break Through Tech workspace)  
**Response time:** Within 48 hours on weekdays  

**Recommended Tools:**
- **Coding:** Google Colab
- **Collaboration:** GitHub, Notion
- **Virtual Meetings:** Zoom, Google Meet

---

## 🚀 Getting Started

1. **Review this overview document** and note any questions for our first meeting
2. **Begin reviewing the dataset** using the link above
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)

I'm excited to work with you!

---

## ❓ Questions?

Please bring any questions to our first meeting during the week of August 24th (Break Through Tech's Bridge to Studio - Session B).


---
