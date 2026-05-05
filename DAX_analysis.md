# Cross-Lingual Analysis of DAX Press Releases

## Dataset

**46 DAX companies** (excluding Merck KGaA — site fully blocked; and Vonovia — too few EN PRs for meaningful comparison).

| Metric          | Value                                 |
| --------------- | ------------------------------------- |
| Total PRs       | 68,527                                |
| English PRs     | 35,836                                |
| German PRs      | 32,691                                |
| Total words     | 44.8M                                 |
| Period          | ~2012–2026                            |
| Embedding model | paraphrase-multilingual-mpnet-base-v2 |

## Cross-Lingual Similarity

Average similarity: **EN→DE 0.880, DE→EN 0.882**.

| Company              | EN→DE | DE→EN | EN>0.9% | DE>0.9% |
| -------------------- | ----: | ----: | ------: | ------: |
| thyssen              | 1.000 | 1.000 |   100.0 |   100.0 |
| mercedes             | 0.997 | 0.966 |    99.2 |    85.4 |
| lufthansa            | 0.945 | 0.932 |    90.4 |    82.7 |
| scout24              | 0.939 | 0.941 |    89.8 |    91.7 |
| mtu                  | 0.935 | 0.892 |    84.4 |    63.7 |
| deutsche_post        | 0.932 | 0.859 |    84.4 |    61.0 |
| hello_fresh          | 0.931 | 0.920 |    76.6 |    76.3 |
| heidelbergmaterials  | 0.930 | 0.930 |    86.6 |    87.2 |
| zalando              | 0.927 | 0.933 |    72.0 |    74.9 |
| basf                 | 0.923 | 0.928 |    80.0 |    82.5 |
| daimler_truck        | 0.920 | 0.897 |    75.1 |    65.7 |
| fresenius_pref       | 0.918 | 0.898 |    73.8 |    65.5 |
| prosiebensat1        | 0.917 | 0.909 |    80.8 |    81.6 |
| telekom              | 0.916 | 0.813 |    75.2 |    38.9 |
| lanxess              | 0.913 | 0.884 |    75.4 |    65.8 |
| covestro             | 0.912 | 0.846 |    73.0 |    57.0 |
| commerzbank          | 0.906 | 0.840 |    71.1 |    52.5 |
| symrise              | 0.905 | 0.901 |    65.0 |    64.2 |
| gea                  | 0.901 | 0.887 |    62.2 |    58.7 |
| deliveryhero         | 0.900 | 0.898 |    60.4 |    60.4 |
| volkswagen           | 0.900 | 0.907 |    68.0 |    75.0 |
| munichre             | 0.892 | 0.922 |    68.4 |    75.7 |
| rheinmetall          | 0.889 | 0.894 |    49.3 |    51.3 |
| continental          | 0.889 | 0.874 |    59.6 |    53.1 |
| siemens              | 0.885 | 0.890 |    51.9 |    51.9 |
| brenntag             | 0.885 | 0.886 |    46.3 |    46.5 |
| kplus                | 0.881 | 0.861 |    52.2 |    47.9 |
| siemens_health       | 0.880 | 0.891 |    57.4 |    58.4 |
| freseniusmedicalcare | 0.880 | 0.889 |    55.4 |    61.3 |
| bmw                  | 0.875 | 0.876 |    46.0 |    45.9 |
| infineon             | 0.873 | 0.867 |    42.5 |    42.9 |
| puma                 | 0.872 | 0.894 |    55.5 |    59.8 |
| hannover             | 0.862 | 0.865 |    16.8 |    20.3 |
| adidas               | 0.860 | 0.906 |    52.0 |    63.4 |
| sartorius            | 0.854 | 0.872 |    43.4 |    63.9 |
| allianz              | 0.830 | 0.820 |    28.4 |    27.0 |
| siemens_energy       | 0.824 | 0.861 |    46.5 |    49.8 |
| deutsche_bank        | 0.811 | 0.849 |    38.5 |    47.2 |
| deutsche_wohnen      | 0.802 | 0.809 |    12.5 |    14.8 |
| porsche              | 0.799 | 0.804 |    19.2 |    26.3 |
| deutsche_borse       | 0.799 | 0.895 |    33.5 |    59.3 |
| sap                  | 0.793 | 0.784 |    20.2 |    24.3 |
| henkel               | 0.758 | 0.700 |     9.2 |     8.0 |
| beiersdorf           | 0.744 | 0.875 |    35.7 |    50.0 |
| bayer                | 0.682 | 0.922 |    29.6 |    71.7 |

Companies with highest symmetry (both >0.9): ThyssenKrupp, Mercedes, Lufthansa, Scout24, HeidelbergMaterials.

Companies with largest asymmetry: Bayer (EN→DE 0.682 vs DE→EN 0.922), Telekom (0.916 vs 0.813), Deutsche Börse (0.799 vs 0.895).

## Topic Modeling

BERTopic run **per company** on untranslated PRs (bottom 20th percentile of similarity). Produced **95 topics** across 39 companies for the DE direction, and **90 topics** across 40 companies for the EN direction.

### German PRs Not Matched in English (95 topics, 3,869 docs across 39 companies)

| Category                     | Topics | Docs  |     % |
| ---------------------------- | -----: | ----: | ----: |
| Industry / Operations        |     31 | 1,547 | 40.0% |
| Financial / Capital Markets  |     17 |   530 | 13.7% |
| Local Operations / Training  |     10 |   459 | 11.9% |
| Regulatory / Governance      |     10 |   380 |  9.8% |
| ESG / Sustainability         |      9 |   253 |  6.5% |
| Local Community              |      7 |   199 |  5.1% |
| Digital / Innovation         |      4 |   196 |  5.1% |
| Consumer Products            |      3 |   115 |  3.0% |
| Media / Entertainment        |      2 |    98 |  2.5% |
| Legal / Boilerplate          |      2 |    92 |  2.4% |

**Largest German-only topics:**

| Company | Docs | Content |
| ------- | ---: | ------- |
| Siemens | 358 | Industrial automation products & digital solutions (German-language product PRs) |
| Daimler Truck | 251 | Bus & truck operations, site infrastructure, local events |
| Porsche | 378 | Porsche SE investments, financial results & governance |
| MTU | 137 | Engine programs, leadership appointments & apprentice awards |
| Telekom | 138 | Fiber broadband rollout & regional infrastructure |
| Henkel | 115 | Consumer products: hair care, body care, laundry (Schwarzkopf, Fa, Perwoll) |
| SAP | 45 | German enterprise customer implementations & Industry 4.0 |

### English PRs Not Matched in German (90 topics, 3,737 docs across 40 companies)

| Category                     | Topics | Docs  |     % |
| ---------------------------- | -----: | ----: | ----: |
| Financial / Capital Markets  |     36 | 1,380 | 36.9% |
| Industry / Operations        |     24 | 1,098 | 29.4% |
| ESG / Sustainability         |     10 |   432 | 11.6% |
| International Markets        |      9 |   395 | 10.6% |
| Pharma / Healthcare          |      3 |   188 |  5.0% |
| Technology / Digital         |      3 |   131 |  3.5% |
| Digital / Innovation         |      2 |    52 |  1.4% |
| Legal / Boilerplate          |      1 |    15 |  0.4% |
| Media / Entertainment        |      1 |    16 |  0.4% |
| Regulatory / Governance      |      1 |    30 |  0.8% |

**Largest English-only topics:**

| Company | Docs | Content |
| ------- | ---: | ------- |
| Siemens | 332 | Industrial automation & digitalization solutions (international product PRs) |
| BMW | 278 | Vehicle specifications, motorsport & electric mobility |
| Telekom | 262 | International telecom operations & 5G rollout |
| Daimler Truck | 237 | Electric truck deliveries & fleet electrification |
| Bayer | 188 | Oncology, cardiology & ophthalmology clinical trials |
| Deutsche Bank | 218 | Investment banking conferences & diversity programs |
| Rheinmetall | 150 | International defense contracts & system deliveries |

## Key Findings

### 1. Germany does NOT show a systematic ESG communication gap

Unlike Spain (where 23.6% of Spanish-only content was ESG), German companies show only **6.5% ESG** in their untranslated German content. The dominant untranslated German content is:

- **Industry/Operations** (40%): German-language product press releases, technical specifications, site operations
- **Financial** (14%): Quarterly results published in German for domestic investors
- **Local operations/training** (12%): Apprenticeships, vocational training, site events

ESG content that stays in German is limited to specific cases: Commerzbank's environmental internship in national parks, Bayer's sustainable agriculture, K+S environmental reclamation, and a few diversity initiatives.

### 2. English-only content has MORE ESG than German-only

**11.6% of English-only content is ESG** — nearly double the German-only rate. This includes:
- BMW electric mobility & sustainability
- Covestro circular economy
- HeidelbergMaterials carbon capture & net-zero cement
- ThyssenKrupp green steel & hydrogen
- Zalando supply chain sustainability
- Deutsche Bank gender equality programs

This suggests German companies communicate ESG **primarily in English** for international ESG rating agencies and investors, rather than in German for domestic audiences.

### 3. The language split maps to content type and audience

| | German-only content | English-only content |
|---|---|---|
| **Dominant theme** | Industry/Ops (40%) + Financial (14%) | Financial (37%) + Industry (29%) |
| **ESG share** | 6.5% | 11.6% |
| **Unique content** | Consumer products, local training, media/entertainment | Pharma trials, international markets, ESG |
| **Target audience** | Domestic customers, employees, local communities | International investors, regulators, clinical community |

### 4. Three distinct communication patterns

**Pattern A: Near-perfect translation** (ThyssenKrupp, Mercedes, Lufthansa, HeidelbergMaterials, Scout24)
- Industrial companies with regulatory obligations to publish bilingually
- Similarity >0.93 in both directions

**Pattern B: German-domestic surplus** (Telekom, Deutsche Post, Henkel, Commerzbank, Covestro)
- Companies with large domestic consumer/retail operations
- German-only content: local services, consumer products, sports sponsoring, entertainment
- EN→DE high (>0.9), DE→EN lower (0.7–0.86)

**Pattern C: English-international surplus** (Bayer, SAP, Deutsche Börse, Beiersdorf, Deutsche Bank)
- Companies with global operations publishing primarily in English
- English-only content: pharma trials, cloud technology, regulatory filings, ESG reporting
- DE→EN high (>0.87), EN→DE lower (0.68–0.80)

### 5. Comparison with Spain and Italy

| | Spain (IBEX-35) | Italy (FTSE MIB) | **Germany (DAX)** |
|---|---|---|---|
| ESG in local-only content | **23.6%** | 9.1% | **6.5%** |
| ESG in English-only content | 14.6% | 9.5% | **11.6%** |
| Main driver of gap | ESG communication gap | Audience segmentation | **Content type segmentation** |
| Dominant local-only | Local events (30%) + ESG (24%) | Industry/Ops (36%) | Industry/Ops (40%) + Financial (14%) |
| Dominant English-only | Corporate (48%) | International Markets (39%) | Financial (37%) + Industry (29%) |
| Average similarity | EN→ES 0.889 / ES→EN 0.852 | EN→IT 0.864 / IT→EN 0.847 | EN→DE 0.880 / DE→EN 0.882 |

### 6. The key insight

The three markets reveal three different communication strategies:

- **Spain**: Companies fail to translate ESG content → missed opportunity for international ESG reputation. The gap is driven by local sustainability initiatives (renewable energy, social inclusion) that stay in Spanish.
- **Italy**: Companies segment by business model — retail vs institutional, domestic vs export. The gap reflects organizational structure.
- **Germany**: Companies segment by **content type**. Technical product information and local operations stay in German; financial reporting and ESG communications go to English. German companies appear to treat ESG as an **investor-facing** topic rather than a domestic one — the opposite of Spain.

This suggests that the ESG communication gap is not universal but market-specific. German companies, operating under EU disclosure requirements (CSRD, EU Taxonomy) and with strong institutional investor pressure, direct their sustainability communications toward international audiences. Spanish companies, by contrast, generate ESG content for local stakeholders (municipalities, regulators, communities) but fail to translate it internationally.

## Output Files

| File | Description |
| ---- | ----------- |
| `results/DAX/corpus.json` | Unified corpus: 68,527 documents (322 MB) |
| `results/DAX/embeddings_mpnet.npz` | Document embeddings (68,527 × 768) |
| `results/DAX/similarity_mpnet.json` | Per-company cross-lingual similarity scores |
| `results/DAX/corpus_summary.xlsx` | Corpus statistics by company |
| `results/DAX/analysis_summary.xlsx` | Three sheets: similarity, DE topics, EN topics |
| `results/DAX/topics/topics_untranslated_de.json` | Per-company BERTopic results: 95 topics (DE not in EN) |
| `results/DAX/topics/topics_untranslated_en.json` | Per-company BERTopic results: 90 topics (EN not in DE) |
| `results/DAX/topics/topics_labeled_de.json` | Labeled DE topics with categories |
| `results/DAX/topics/topics_labeled_en.json` | Labeled EN topics with categories |
| `results/DAX/topics/topics_all_companies_de_labeled.xlsx` | 3-tab Excel: Summary, Topics, Representative PRs (DE direction) |
| `results/DAX/topics/topics_all_companies_en_labeled.xlsx` | 3-tab Excel: Summary, Topics, Representative PRs (EN direction) |
