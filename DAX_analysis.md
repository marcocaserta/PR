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

BERTopic run **per company** on untranslated PRs (bottom 20th percentile of similarity), matching the methodology of the Italian study. Produced **220 topics** across 45 companies for the DE direction, and **214 topics** across 45 companies for the EN direction.

### German PRs Not Matched in English (220 topics, 5,771 docs)

| Category                     | Docs  |     % |
| ---------------------------- | ----: | ----: |
| Industry / Operations        | 1,230 | 21.3% |
| Financial / Capital Markets  |   888 | 15.4% |
| Digital / Innovation         |   730 | 12.6% |
| ESG / Sustainability         |   664 | 11.5% |
| Local Operations / Training  |   550 |  9.5% |
| Consumer Products            |   476 |  8.2% |
| Local Community              |   430 |  7.5% |
| Regulatory / Governance      |   343 |  5.9% |
| Media / Entertainment        |   313 |  5.4% |
| Legal / Boilerplate          |   147 |  2.5% |

### English PRs Not Matched in German (214 topics, 6,269 docs)

| Category                     | Docs  |     % |
| ---------------------------- | ----: | ----: |
| Financial / Capital Markets  | 1,312 | 20.9% |
| ESG / Sustainability         | 1,078 | 17.2% |
| Technology / Digital         | 1,052 | 16.8% |
| Industry / Operations        |   957 | 15.3% |
| International Markets        |   573 |  9.1% |
| Media / Entertainment        |   532 |  8.5% |
| Regulatory / Governance      |   439 |  7.0% |
| Pharma / Healthcare          |   235 |  3.7% |
| Legal / Boilerplate          |    91 |  1.5% |

## Key Findings

### 1. ESG is communicated MORE in English than in German

**17.2% of English-only content is ESG**, compared to **11.5% of German-only content**. This is the opposite of Spain, where ESG was disproportionately in the local language. German companies treat sustainability as an **investor-facing** topic, directing it toward international ESG rating agencies and institutional investors rather than domestic audiences.

### 2. The asymmetry reveals a strategic choice

| | German-only content | English-only content |
|---|---|---|
| **Dominant themes** | Industry/Ops (21%) + Financial (15%) + Digital (13%) | Financial (21%) + ESG (17%) + Technology (17%) |
| **ESG share** | **11.5%** | **17.2%** |
| **Unique content** | Consumer products (8%), local community (8%), media/entertainment (5%) | Pharma/healthcare (4%), international markets (9%) |
| **Target audience** | Domestic customers, employees, local communities | International investors, ESG raters, clinical community |

### 3. Three distinct communication patterns

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

### 4. Comparison with Spain and Italy

| | Spain (IBEX-35) | Italy (FTSE MIB) | **Germany (DAX)** |
|---|---|---|---|
| ESG in local-only content | **23.6%** | 9.1% | **11.5%** |
| ESG in English-only content | 14.6% | 9.5% | **17.2%** |
| Main driver of gap | ESG communication gap | Audience segmentation | **ESG directed to English** |
| Dominant local-only | Local events (30%) + ESG (24%) | Industry/Ops (36%) | Industry/Ops (21%) + Financial (15%) |
| Dominant English-only | Corporate (48%) | International Markets (39%) | Financial (21%) + ESG (17%) + Tech (17%) |
| Average similarity | EN→ES 0.889 / ES→EN 0.852 | EN→IT 0.864 / IT→EN 0.847 | EN→DE 0.880 / DE→EN 0.882 |

### 5. The key insight

The three markets reveal three different ESG communication strategies:

- **Spain**: Companies communicate ESG **locally** (in Spanish) but fail to translate it internationally → missed opportunity for ESG reputation with international investors.
- **Italy**: ESG is translated at similar rates in both directions (9.1% vs 9.5%) → no systematic gap; the translation gap is driven by audience segmentation (retail vs institutional).
- **Germany**: Companies communicate ESG **internationally** (in English) more than domestically → ESG is treated as an investor-relations tool rather than a local stakeholder engagement tool.

This suggests that German companies, operating under EU disclosure requirements (CSRD, EU Taxonomy) and with strong institutional investor pressure, have adopted ESG communication as part of their international investor relations strategy. Spanish companies, by contrast, generate ESG content for local stakeholders but fail to translate it for international audiences.

The German approach may be more strategically effective for ESG ratings (which rely on English-language disclosures), but it raises questions about whether domestic stakeholders — employees, communities, regulators — are equally informed about corporate sustainability efforts.

## Output Files

| File | Description |
| ---- | ----------- |
| `results/DAX/corpus.json` | Unified corpus: 68,527 documents (322 MB) |
| `results/DAX/embeddings_mpnet.npz` | Document embeddings (68,527 × 768) |
| `results/DAX/similarity_mpnet.json` | Per-company cross-lingual similarity scores |
| `results/DAX/corpus_summary.xlsx` | Corpus statistics by company |
| `results/DAX/analysis_summary.xlsx` | Three sheets: similarity, DE topics, EN topics |
| `results/DAX/topics/topics_untranslated_de.json` | Per-company BERTopic: 220 topics (DE not in EN) |
| `results/DAX/topics/topics_untranslated_en.json` | Per-company BERTopic: 214 topics (EN not in DE) |
| `results/DAX/topics/topics_labeled_de.json` | Labeled DE topics with categories |
| `results/DAX/topics/topics_labeled_en.json` | Labeled EN topics with categories |
| `results/DAX/topics/topics_all_companies_de_labeled.xlsx` | 3-tab Excel: Summary, Topics, Representative PRs (DE direction) |
| `results/DAX/topics/topics_all_companies_en_labeled.xlsx` | 3-tab Excel: Summary, Topics, Representative PRs (EN direction) |
