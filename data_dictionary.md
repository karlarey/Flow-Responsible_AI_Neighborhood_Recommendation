# Data Dictionary

## miami_dade_public_features.csv

**Real public aggregate data** for Miami-Dade ZIP codes (ZCTAs). Pulled from Census ACS, migration tables, and Zillow Research-style indices.

| Column | Type | Description |
|--------|------|-------------|
| NAME | string | Census ZCTA label |
| B01003_001E | int | Total population (ACS) |
| B25064_001E | int | Median gross rent (ACS); `-666666666` = missing/suppressed |
| B25077_001E | int | Median home value (ACS) |
| B07003_001E | int | Total population 1 year and over (migration universe) |
| B07003_004E | int | Same house 1 year ago |
| B07003_008E | int | Moved within same county |
| B07003_010E | int | Moved from different county |
| B11016_001E | int | Total households |
| B25003_002E | int | Owner-occupied units |
| B25003_003E | int | Renter-occupied units |
| zip | string | 5-digit ZIP code |
| moved_different_house_pct | float | Share who moved to a different house (derived) |
| median_rent_usd | int | Median rent (ACS or derived) |
| population | int | Population count |
| zillow_home_value_index | float | Zillow Research-style home value index |
| zillow_rent_index | float | Zillow Research-style rent index |

## miami_dade_zctas.txt

Plain-text list of Miami-Dade ZIP codes used to scope the project.

## area_features.csv

**Blended starter file** for the recommender. Joins public rent/migration fields with normalized preference proxies (transit, social, quiet, pet-friendly, walkable). Some `area_name` labels are illustrative neighborhood names.

| Column | Type | Description |
|--------|------|-------------|
| zip | string | Miami ZIP code |
| area_name | string | Neighborhood or ZCTA label |
| rent_band | string | Illustrative rent range bucket |
| transit | float 0-1 | Transit access proxy |
| social | float 0-1 | Social activity proxy |
| quiet | float 0-1 | Quiet environment proxy |
| pet_friendly | float 0-1 | Pet-friendly proxy |
| walkable | float 0-1 | Walkability proxy |
| migration_score | float 0-1 | In-migration activity proxy (derived) |
| median_rent_usd | int | Rent index from public sources |
| co_living_friendly | float 0-1 | How well the area fits co-living / shared housing (higher for Wynwood, Downtown, Brickell) |

**Anchor rows:** Wynwood (`33127`), Downtown (`33128`), Brickell (`33130`).

## area_options.csv

**Synthetic** listing-style cards for demo UI. **NOT REAL LISTINGS.**

| Column | Type | Description |
|--------|------|-------------|
| option_id | string | Synthetic ID (SYN-*) |
| zip | string | Join key to area_features |
| rent_band | string | Illustrative band |
| living_type | string | `solo` or `co_living` |
| tags | string | Comma-separated tags (includes `co_living` when relevant) |
| summary | string | Short area + living-style description |
| disclaimer | string | Must display NOT A REAL LISTING |

## crowd_text_snippets.csv

Demo snippets mimicking public review/forum text for NLP themes. Replace with real filtered corpora during model development.

| Column | Type | Description |
|--------|------|-------------|
| snippet_id | string | Row ID |
| zip | string | Associated ZIP |
| source | string | e.g. kaggle_reviews (document real source when replaced) |
| theme | string | transit, social, quiet, co_living, etc. |
| text | string | Snippet text (aggregate use only) |

## Limitations

- Snapshot data only — not live market feeds.
- Census suppression codes must be handled explicitly in preprocessing.
- Synthetic options are for UI demonstration; never present them as real listings.
- Do not use outputs for leasing decisions or demographic steering.
- English-only text bias may apply when using real review corpora.
