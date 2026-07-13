# Starter Dataset

See [`data_dictionary.md`](../data_dictionary.md) for column details.

## Who this is for

Newcomers to Miami — e.g. a couple moving from NYC who want **their own apartment** in Wynwood, Downtown, or Brickell. **Not co-living. Not roommates.**

Co-living is an **optional** path in the data for people who are **alone** and **want** shared housing.

## User inputs (what the recommender uses)

| Field | Values | Example |
|-------|--------|---------|
| `household` | `alone`, `with_partner` | `with_partner` |
| `housing_preference` | `own_apartment`, `co_living` | `own_apartment` |
| Budget + lifestyle tags | transit, social, quiet, etc. | transit, walkable |

## Anchor neighborhoods (own apartment)

| Neighborhood | ZIP |
|--------------|-----|
| Wynwood | 33127 |
| Downtown Miami | 33128 |
| Brickell | 33130 |

## Files

| File | What's inside |
|------|-----------------|
| `area_features.csv` | ZIP-level scores for the model |
| `area_options.csv` | Demo cards with `housing_preference` + `household` |
| `crowd_text_snippets.csv` | Sample review text by ZIP |

All listing-style rows are **synthetic demos** — not real apartments.
