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

### Corpus by Company

| Company              |    EN |    DE | Total |  Words |  W/PR |
| -------------------- | ----: | ----: | ----: | -----: | ----: |
| adidas               |   213 |   183 |   396 |   307K |   775 |
| allianz              |   450 |   491 |   941 | 1,276K | 1,355 |
| basf                 | 2,112 | 2,041 | 4,153 | 2,940K |   707 |
| bayer                |   466 |   462 |   928 | 1,589K | 1,711 |
| beiersdorf           |   207 |    88 |   295 |   123K |   417 |
| bmw                  | 1,996 | 1,942 | 3,938 | 3,854K |   978 |
| brenntag             |   315 |   314 |   629 |   274K |   435 |
| commerzbank          |   355 |   481 |   836 |   898K | 1,073 |
| continental          | 2,008 | 2,256 | 4,264 | 2,377K |   557 |
| covestro             |   430 |   567 |   997 |   752K |   754 |
| daimler_truck        | 1,410 | 1,622 | 3,032 | 2,231K |   735 |
| deliveryhero         |   144 |   144 |   288 |   368K | 1,279 |
| deutsche_bank        | 1,912 | 1,533 | 3,445 | 2,074K |   602 |
| deutsche_borse       | 3,273 | 1,716 | 4,989 | 1,330K |   266 |
| deutsche_post        |   801 | 1,116 | 1,917 | 1,173K |   611 |
| deutsche_wohnen      |   240 |   172 |   412 |   351K |   851 |
| fresenius_pref       |   824 |   921 | 1,745 | 2,351K | 1,347 |
| freseniusmedicalcare |   101 |    93 |   194 |   172K |   889 |
| gea                  |   418 |   447 |   865 |   644K |   744 |
| hannover             |   142 |   143 |   285 |   308K | 1,082 |
| heidelbergmaterials  |   320 |   320 |   640 |   490K |   766 |
| hello_fresh          |   110 |   117 |   227 |   232K | 1,022 |
| henkel               |   608 |   760 | 1,368 |   763K |   557 |
| infineon             |   299 |   247 |   546 |   299K |   547 |
| kplus                |   201 |   219 |   420 |   207K |   491 |
| lanxess              |   463 |   526 |   989 |   572K |   578 |
| lufthansa            |   705 |   776 | 1,481 |   719K |   485 |
| mercedes             | 1,320 | 1,514 | 2,834 | 2,509K |   885 |
| mtu                  |   564 |   774 | 1,338 |   766K |   573 |
| munichre             |   136 |   115 |   251 |   264K | 1,050 |
| porsche              | 3,887 | 2,275 | 6,162 | 5,749K |   933 |
| prosiebensat1        |   104 |   103 |   207 |   126K |   608 |
| puma                 |   119 |   107 |   226 |   148K |   652 |
| rheinmetall          |   893 |   862 | 1,755 |   905K |   515 |
| rwe                  |   841 |     0 |   841 |   416K |   494 |
| sap                  |   629 |   642 | 1,271 |   913K |   718 |
| sartorius            |   364 |   241 |   605 |   331K |   546 |
| scout24              |   108 |   108 |   216 |   244K | 1,130 |
| siemens              | 2,070 | 2,072 | 4,142 | 3,272K |   789 |
| siemens_energy       |   331 |   219 |   550 |   246K |   447 |
| siemens_health       |   371 |   356 |   727 |   386K |   531 |
| symrise              |   497 |   497 |   994 |   550K |   553 |
| telekom              | 1,308 | 1,961 | 3,269 | 2,153K |   659 |
| thyssen              |   229 |   229 |   458 |   355K |   776 |
| volkswagen           |   659 |   512 | 1,171 |   861K |   735 |
| zalando              |   872 |   661 | 1,533 | 1,088K |   710 |

Note: RWE is EN-only (German site blocked during scraping). Infineon W/PR reflects post-cleaning values (navigation boilerplate removed).

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
| lanxess             | 0.913 | 0.884 |    75.4 |    65.8 |
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

Companies with largest asymmetry: Bayer (EN→DE 0.682 vs DE→EN 0.922), Telekom (0.916 vs 0.813), Deutsche Börse (0.799 vs 0.895), Deutsche Post (0.932 vs 0.859).

## Topic Modeling

BERTopic identified **84 topics** in untranslated German PRs (5,028 docs) and **32 topics** in untranslated English PRs (5,326 docs). Both directions have a large "catch-all" cluster (Topic 0) where BERTopic placed documents that don't fit neatly into any theme.

### German PRs Not Matched in English (excluding catch-all: 3,427 docs, 83 topics)

| Category                          | Docs  |     % |
| --------------------------------- | ----: | ----: |
| Local Operations & Community      | 1,014 | 29.6% |
| Sports & Motorsport               |   566 | 16.5% |
| Industry & Technology             |   555 | 16.2% |
| Corporate & Financial             |   451 | 13.2% |
| Consumer Products & Retail        |   198 |  5.8% |
| Media & Entertainment             |   176 |  5.1% |
| ESG (all sub-categories)          |    94 |  2.7% |
| Legal / Boilerplate               |    89 |  2.6% |
| Other                             |   284 |  8.3% |

**Largest topics (German-only):**

| Topic | Docs | Content |
| ----- | ---: | ------- |
| Local Operations / Training | 261 | Apprenticeships, vocational training at company sites (MTU Munich, Henkel Düsseldorf, Fresenius Bad Homburg, LANXESS, GEA, Sartorius Göttingen) |
| Sports Sponsoring / Media | 233 | MagentaSport, football EM campaigns, Commerzbank DFB |
| Industry / Operations | 217 | Henkel adhesives, BASF chemicals, Continental materials, Lufthansa fleet |
| Media / Entertainment | 176 | Telekom MagentaTV series, streaming, MagentaMusik festivals |
| Consumer Products | 171 | Schwarzkopf hair care, Persil laundry, WC Frisch, Henkel household |
| Technology / Digital | 153 | SAP Cloud/S4HANA in German, enterprise software for German market |
| Motorsport / Brand Heritage | 129 | Porsche 911 stories, classic cars, museum events |
| Local Community / Culture | 124 | Deutsche Post stamps, Deutsche Bank art, MTU museum, orchestras |
| Financial Products / Retail | 112 | ETFs, ComStage, retail investor products (Deutsche Börse, Commerzbank) |
| Motorsport / Racing | 106 | Porsche GT3/Formula E racing, Continental tyres in motorsport |

### English PRs Not Matched in German (excluding catch-all: 1,744 docs, 31 topics)

| Category                          | Docs  |     % |
| --------------------------------- | ----: | ----: |
| Regulatory / Governance           |   862 | 49.4% |
| Pharma / Clinical Trials          |   237 | 13.6% |
| Technology                        |   189 | 10.8% |
| Industry / Operations             |   121 |  6.9% |
| Financial                         |   103 |  5.9% |
| ESG                               |    64 |  3.7% |
| Legal / Boilerplate               |    67 |  3.8% |
| Other                             |   101 |  5.8% |

**Largest topics (English-only):**

| Topic | Docs | Content |
| ----- | ---: | ------- |
| Regulatory / Governance | 862 | Deutsche Börse governance pages, board announcements, compliance disclosures |
| Pharma / Clinical Trials | 237 | Bayer oncology (darolutamide, larotrectinib), cardiology (rivaroxaban, vericiguat), ophthalmology (aflibercept) |
| Technology / Cloud | 171 | SAP cloud solutions, enterprise software for international markets |
| Industry / Operations | 73 | BASF cosmetics/chemicals, international product launches |
| Financial / Investor Events | 53 | Deutsche Bank conferences, SAP analyst calls |

## Key Findings

### 1. Germany does NOT show a systematic ESG communication gap

Unlike Spain (where 23.6% of Spanish-only content was ESG), German companies show only **2.7% ESG** in their untranslated German content. The dominant untranslated German content is:

- **Local operations** (apprenticeships, site news, workforce): 30%
- **Sports and motorsport** (Porsche racing, Telekom sports streaming, sponsoring): 17%
- **Industry and technology** (German-language product/operations content): 16%

German companies do not systematically fail to translate their sustainability communications. ESG content appears to be translated at roughly the same rate as other content.

### 2. The language split maps to audience and content type

| | German-only content | English-only content |
|---|---|---|
| **Dominant theme** | Local ops (30%) + Sports (17%) | Regulatory (49%) + Pharma (14%) |
| **ESG share** | 2.7% | 3.7% |
| **Target audience** | Domestic employees, consumers, local communities | International investors, regulators, clinical community |

### 3. Three distinct communication patterns

**Pattern A: Near-perfect translation** (ThyssenKrupp, Mercedes, Lufthansa, HeidelbergMaterials)
- Industrial companies with regulatory obligations to publish bilingually
- Similarity >0.93 in both directions
- Very little untranslated content in either language

**Pattern B: German-domestic surplus** (Telekom, Deutsche Post, Henkel, Commerzbank)
- Companies with large domestic consumer/retail operations
- German-only content: local services, consumer products, sports sponsoring, entertainment
- EN→DE similarity high (>0.9), DE→EN lower (0.7-0.86)

**Pattern C: English-international surplus** (Bayer, SAP, Deutsche Börse, Beiersdorf)
- Companies with global operations publishing primarily in English
- English-only content: pharma trials, cloud technology, regulatory filings
- DE→EN similarity high (>0.87), EN→DE lower (0.68-0.80)

### 4. Comparison with Spain and Italy

| | Spain (IBEX-35) | Italy (FTSE MIB) | **Germany (DAX)** |
|---|---|---|---|
| ESG in local-only content | **23.6%** | 9.1% | **2.7%** |
| ESG in English-only content | 14.6% | 9.5% | 3.7% |
| Main driver of gap | ESG communication gap | Audience segmentation | **Local operations + domestic media** |
| Dominant local-only | Local events (30%) + ESG (24%) | Industry/Ops (36%) | Local ops (30%) + Sports (17%) |
| Dominant English-only | Corporate (48%) | International Markets (39%) | Regulatory (49%) + Pharma (14%) |
| Average similarity | EN→ES 0.889 / ES→EN 0.852 | EN→IT 0.864 / IT→EN 0.847 | EN→DE 0.880 / DE→EN 0.882 |

### 5. The key question reframed

The three markets reveal three different communication strategies:

- **Spain**: Companies fail to translate ESG content → missed opportunity for international ESG reputation
- **Italy**: Companies segment by business model (retail vs institutional, domestic vs export)
- **Germany**: Companies segment by **content type** — operational/local content stays in German; regulatory/scientific content goes to English. ESG is translated at the same rate as everything else.

This suggests that the ESG communication gap is **not universal** but rather a feature of specific markets. German companies, operating under stricter EU disclosure requirements (CSRD, EU Taxonomy) and with a tradition of integrated reporting, appear to translate their sustainability communications more systematically than their Spanish counterparts.

## Output Files

| File | Description |
| ---- | ----------- |
| `results/DAX/corpus.json` | Unified corpus: 68,527 documents with text, metadata, company, language (322 MB) |
| `results/DAX/embeddings_mpnet.npz` | Document embeddings (68,527 × 768) |
| `results/DAX/similarity_mpnet.json` | Per-company cross-lingual similarity scores |
| `results/DAX/topics/topics_untranslated_de.json` | BERTopic results: 84 topics from German PRs not matched in English |
| `results/DAX/topics/topics_untranslated_en.json` | BERTopic results: 32 topics from English PRs not matched in German |
| `results/DAX/topics/topics_labeled_de.json` | Labeled DE topics with categories |
| `results/DAX/topics/topics_labeled_en.json` | Labeled EN topics with categories |
| `results/DAX/topics/topics_all_companies_de_labeled.xlsx` | Excel: DE topics by company with categories |
| `results/DAX/topics/topics_all_companies_en_labeled.xlsx` | Excel: EN topics by company with categories |
