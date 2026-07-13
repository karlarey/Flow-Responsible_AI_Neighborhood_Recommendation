# MCP Server Setup

This project requires an **MCP server** that exposes your recommender and dataset tools to an AI agent.

## Required tools

| Tool | Inputs | Output |
|------|--------|--------|
| `schema` | — | Dataset column names and notes |
| `area_stats` | `zip_code` (optional) | Public-style area statistics |
| `crowd_themes` | `zip_code` | NLP theme snippets for that ZIP |
| `recommend` | `budget_max`, `tags` (comma-separated), `k` | Top-k area recommendations |
| `ethics` | — | Responsible-use charter and limitations |

## Reference prototype

The Challenge Advisor maintains a working reference at:
https://github.com/karlarey/miami-newcomer-explorer

Key files:
- `src/mcp_server.py` — MCP tool definitions
- `src/tools.py` — shared logic used by MCP and UI
- `src/recommender.py` — cosine-similarity ranking
- `src/nlp_themes.py` — crowd text themes

## Run the reference MCP server (local)

```bash
git clone https://github.com/karlarey/miami-newcomer-explorer.git
cd miami-newcomer-explorer
python -m venv .venv
.venv\Scripts\activate          # Windows
pip install -r requirements.txt
python src/mcp_server.py
```

Optional Gemini agent (separate from MCP):

```bash
copy .env.example .env
# set GEMINI_API_KEY in .env
```

## Connect in Cursor (example)

Add to your Cursor MCP settings:

```json
{
  "mcpServers": {
    "miami-neighborhood-rec": {
      "command": "python",
      "args": ["src/mcp_server.py"],
      "cwd": "C:/path/to/your/project"
    }
  }
}
```

Adjust `cwd` to your project root after you implement your own `src/mcp_server.py`.

## Team deliverable (October)

1. Implement the five tools above using this repo's `data/` files.
2. Verify the agent only answers from tool outputs (measure **tool grounding rate**).
3. Verify prohibited requests are refused (measure **refusal rate**).
4. Document how to run your MCP server in your team README.

## Testing checklist

- [ ] `schema` returns column names for all starter CSV files
- [ ] `recommend` returns 3–5 ZIPs for a sample budget + tags
- [ ] `crowd_themes` returns snippets for a known ZIP
- [ ] `ethics` returns fair-housing / limitations text
- [ ] Agent does not invent rents, listings, or neighborhoods when tools are available
