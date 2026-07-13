# Starter Dataset

See [`data_dictionary.md`](../data_dictionary.md) for full column details.

## Three housing types

| Type | What it means |
|------|---------------|
| **co_living** | Shared housing / roommates — for newcomers who don't want to live alone |
| **solo_apartment** | Your own unit in a building (studio, 1BR, etc.) |
| **single_family** | Detached house — more space, yard, suburban feel |

Users **choose** their housing type. The model should never guess family status from demographics.

## Urban anchors (co-living + solo apartment)

| Neighborhood | ZIP |
|--------------|-----|
| Wynwood | 33127 |
| Downtown Miami | 33128 |
| Brickell | 33130 |

## Single-family anchors

| Neighborhood | ZIP |
|--------------|-----|
| Kendall | 33186 |
| Coral Gables | 33134 |
| Pinecrest | 33156 |

## Files

| File | What's inside |
|------|-----------------|
| `miami_dade_public_features.csv` | Real public data by ZIP |
| `area_features.csv` | Model features + `co_living_friendly` + `single_family_friendly` |
| `crowd_text_snippets.csv` | Sample reviews (co_living, single_family, etc.) |
| `area_options.csv` | Demo cards by housing type — **NOT REAL LISTINGS** |
