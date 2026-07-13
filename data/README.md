# Starter Dataset

Files in this folder get you started on day one. See [`data_dictionary.md`](../data_dictionary.md) for column-by-column details.

## Anchor neighborhoods

Use these three areas to test **solo vs. co-living** recommendations:

| Neighborhood | ZIP | Try co-living when… | Try solo when… |
|--------------|-----|---------------------|----------------|
| **Wynwood** | 33127 | New to Miami, want community and roommates | Want your own creative, walkable spot |
| **Downtown Miami** | 33128 | Want shared housing near transit and work | Want your own unit in the urban core |
| **Brickell** | 33130 | Young professional, roommate-friendly tower | Solo high-rise, Metrorail access |

## What's in each file

| File | What it is |
|------|------------|
| `miami_dade_public_features.csv` | **Real public data** — rent, population, migration by ZIP |
| `miami_dade_zctas.txt` | **ZIP code list** for Miami-Dade |
| `area_features.csv` | **Model starter** — includes `co_living_friendly` score per ZIP |
| `crowd_text_snippets.csv` | **Sample reviews** — includes `co_living` themes |
| `area_options.csv` | **Fake demo cards** — `living_type` = `solo` or `co_living` — **NOT REAL LISTINGS** |

## Important reminders

- No personal info — area-level aggregates only
- Co-living cards are **synthetic demos**, not real roommate listings
- Don't use outputs for actual leasing decisions
