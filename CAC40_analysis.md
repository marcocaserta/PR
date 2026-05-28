# Cross-Lingual Analysis of CAC40 Press Releases

## Dataset

**44 CAC40 companies** (excluding Bouygues, BNP Paribas, Saint-Gobain, SE — blocked by WAF during scraping).

| Metric          | Value                                 |
| --------------- | ------------------------------------- |
| Total PRs       | 49,477                                |
| English PRs     | 27,969                                |
| French PRs      | 21,508                                |
| Total words     | 43.3M                                 |
| Period          | ~2002–2026                            |
| Embedding model | paraphrase-multilingual-mpnet-base-v2 |

## Cross-Lingual Similarity

Average similarity: **EN→FR 0.841, FR→EN 0.848**.

| Company              | EN→FR | FR→EN | EN>0.9% | FR>0.9% |
| -------------------- | ----: | ----: | ------: | ------: |
| urw                  | 0.955 | 0.942 |    81.2 |    75.3 |
| orange               | 0.933 | 0.886 |    75.8 |    60.9 |
| totalenergies        | 0.931 | 0.914 |    82.6 |    72.9 |
| publicis             | 0.926 | 0.936 |    72.8 |    76.1 |
| lvmh                 | 0.920 | 0.921 |    74.3 |    75.1 |
| renault              | 0.917 | 0.915 |    75.4 |    75.3 |
| edf                  | 0.909 | 0.861 |    65.8 |    48.8 |
| axa                  | 0.905 | 0.898 |    65.3 |    60.0 |
| stellantis           | 0.903 | 0.905 |    57.4 |    60.0 |
| bureauveritas        | 0.898 | 0.871 |    68.6 |    62.3 |
| eiffage              | 0.896 | 0.868 |    61.6 |    55.7 |
| safran               | 0.896 | 0.907 |    66.5 |    69.8 |
| euroapi              | 0.891 | 0.900 |    51.0 |    55.5 |
| sanofi               | 0.888 | 0.910 |    54.7 |    64.3 |
| sodexo               | 0.888 | 0.886 |    50.5 |    50.2 |
| vinci                | 0.884 | 0.888 |    47.3 |    50.1 |
| societegenerale      | 0.883 | 0.776 |    45.8 |    28.5 |
| edenred              | 0.881 | 0.879 |    43.4 |    43.4 |
| klepierre            | 0.881 | 0.857 |    34.4 |    26.7 |
| airliquide           | 0.881 | 0.893 |    51.8 |    55.4 |
| investors_worldline  | 0.870 | 0.876 |    46.1 |    45.4 |
| kering               | 0.864 | 0.866 |    36.0 |    36.5 |
| danone               | 0.864 | 0.860 |    30.0 |    31.8 |
| vivendi              | 0.863 | 0.811 |    48.8 |    35.8 |
| michelin             | 0.855 | 0.860 |    40.3 |    42.6 |
| tp                   | 0.854 | 0.858 |    29.1 |    31.8 |
| accor                | 0.853 | 0.848 |    47.9 |    46.7 |
| essilorluxottica     | 0.852 | 0.863 |    40.0 |    48.6 |
| hermes               | 0.852 | 0.852 |    22.9 |    24.9 |
| pernod               | 0.847 | 0.863 |    40.0 |    43.3 |
| atos                 | 0.841 | 0.764 |    36.3 |    23.6 |
| legrand              | 0.841 | 0.837 |    25.3 |    25.0 |
| valeo                | 0.836 | 0.837 |    22.3 |    26.4 |
| loreal               | 0.834 | 0.824 |    32.5 |    31.0 |
| thales               | 0.832 | 0.751 |    44.1 |    16.9 |
| 3ds                  | 0.795 | 0.879 |    31.4 |    59.2 |
| veolia               | 0.781 | 0.826 |     8.0 |    15.6 |
| creditagricole       | 0.735 | 0.717 |    16.3 |    12.4 |
| alstom               | 0.733 | 0.815 |     5.9 |    15.2 |
| euronext             | 0.660 | 0.897 |     3.3 |    63.2 |
| holcim               | 0.554 | 0.630 |     0.2 |     1.0 |
| capgemini            | 0.218 | 0.467 |     0.0 |     0.0 |

Companies with highest symmetry (both >0.9): URW, TotalEnergies, Publicis, LVMH, Renault, Stellantis, Safran.

Companies with largest asymmetry: Société Générale (EN→FR 0.883 vs FR→EN 0.776), Vivendi (0.863 vs 0.811), Atos (0.841 vs 0.764).

**Note on outliers**: Capgemini (EN→FR 0.218), Euronext (0.660), and Holcim (0.554) show artificially low EN→FR scores due to severely imbalanced corpora (9, 117, and 96 FR docs respectively). These companies are excluded from the bilingual comparison in the topic analysis but retained in the similarity table for completeness.

## Topic Modeling

BERTopic run **per company** on untranslated PRs (bottom 20th percentile of similarity), matching the methodology of the Italian and German studies. Produced **92 topics** across 33 companies for the FR direction, and **117 topics** across 40 companies for the EN direction.

### French PRs Not Matched in English (92 topics, 3,726 docs)

| Category                     | Docs  |     % |
| ---------------------------- | ----: | ----: |
| Financial / Capital Markets  |   934 | 25.1% |
| Local Operations / Community |   531 | 14.3% |
| Industry / Operations        |   479 | 12.9% |
| Regulatory / Governance      |   362 |  9.7% |
| ESG / Sustainability         |   336 |  9.0% |
| Consumer Products / Brands   |   263 |  7.1% |
| Digital / Innovation         |   235 |  6.3% |
| International Markets        |   221 |  5.9% |
| Pharma / Healthcare          |   151 |  4.1% |
| Media / Entertainment        |   122 |  3.3% |
| Legal / Boilerplate          |    92 |  2.5% |

### English PRs Not Matched in French (117 topics, 4,931 docs)

| Category                     | Docs  |     % |
| ---------------------------- | ----: | ----: |
| Financial / Capital Markets  | 1,484 | 30.1% |
| International Markets        |   968 | 19.6% |
| Digital / Innovation         |   637 | 12.9% |
| ESG / Sustainability         |   432 |  8.8% |
| Industry / Operations        |   346 |  7.0% |
| Regulatory / Governance      |   316 |  6.4% |
| Pharma / Healthcare          |   235 |  4.8% |
| Local Operations / Community |   183 |  3.7% |
| Consumer Products / Brands   |   136 |  2.8% |
| Legal / Boilerplate          |   194 |  3.9% |

## Key Findings

### 1. ESG communication is balanced between languages

**9.0% of French-only content is ESG**, compared to **8.8% of English-only content**. There is essentially no ESG translation gap in France. This contrasts sharply with Spain (where ESG is over-represented in Spanish) and Germany (where ESG is over-represented in English). French companies translate their ESG content at similar rates in both directions.

### 2. The audience segmentation is driven by geography, not ESG

| | French-only content | English-only content |
|---|---|---|
| **Dominant themes** | Financial (25%) + Local Ops (14%) + Industry (13%) | Financial (30%) + International (20%) + Digital (13%) |
| **ESG share** | **9.0%** | **8.8%** |
| **Unique content** | Media/Entertainment (3%), Consumer brands (7%) | Pharma/Healthcare (5%), International markets (20%) |
| **Target audience** | Domestic stakeholders, employees, local communities, regulators | International investors, global customers, tech community |

The main driver of the translation gap in France is **international expansion content** — 19.6% of English-only content relates to international markets (hotel signings, foreign acquisitions, government contracts abroad), while French-only content emphasizes **local operations and community** (14.3% — factory events, apprenticeships, sports sponsoring, cultural partnerships).

### 3. Three distinct communication patterns

**Pattern A: Near-perfect translation** (URW, TotalEnergies, Publicis, LVMH, Renault, Stellantis)
- Companies with strong international brands and regulatory obligations
- Similarity >0.90 in both directions
- Systematic bilingual publishing

**Pattern B: French-domestic surplus** (Société Générale, Vivendi, Atos, EDF, Eiffage)
- Companies with large domestic consumer/retail operations or French media content
- French-only content: local services, TV broadcasting, cultural events, regulatory filings
- EN→FR high (>0.85), FR→EN lower (0.76–0.87)

**Pattern C: English-international surplus** (Euronext, Capgemini, 3DS/Dassault Systèmes, Holcim, Alstom)
- Companies operating primarily in English internationally
- English-only content: stock exchange listings, tech research, global infrastructure contracts
- FR→EN high (>0.82), EN→FR lower (0.22–0.80)

### 4. Comparison with Spain, Italy, and Germany

| | Spain (IBEX-35) | Italy (FTSE MIB) | Germany (DAX) | **France (CAC40)** |
|---|---|---|---|---|
| ESG in local-only content | **23.6%** | 9.1% | 11.5% | **9.0%** |
| ESG in English-only content | 14.6% | 9.5% | 17.2% | **8.8%** |
| ESG gap direction | Local > English | Balanced | English > Local | **Balanced** |
| Main driver of gap | ESG communication gap | Audience segmentation | ESG directed to English | **Geographic audience** |
| Dominant local-only | Local events (30%) + ESG (24%) | Industry/Ops (36%) | Industry/Ops (21%) + Financial (15%) | Financial (25%) + Local Ops (14%) |
| Dominant English-only | Corporate (48%) | International Markets (39%) | Financial (21%) + ESG (17%) + Tech (17%) | Financial (30%) + International (20%) |
| Average similarity | EN→Local 0.889 / Local→EN 0.852 | EN→Local 0.864 / Local→EN 0.847 | EN→Local 0.880 / Local→EN 0.882 | EN→Local 0.841 / Local→EN 0.848 |

### 5. The key insight

France represents a **fourth model** of bilingual corporate communication:

- **Spain**: ESG is communicated **locally** but not translated → missed opportunity for ESG ratings.
- **Italy**: Content is segmented by **audience type** (retail vs institutional) with no systematic ESG gap.
- **Germany**: ESG is communicated **internationally** (in English) as an investor-relations tool.
- **France**: Content is segmented by **geography** — English for international operations and investors, French for domestic stakeholders — with ESG translated **equally** in both directions.

The French model suggests that CAC40 companies, operating under the same EU disclosure requirements (CSRD, EU Taxonomy) as their German counterparts, have adopted a different approach: rather than directing ESG primarily toward international investors (the German model), they communicate ESG content to both domestic and international audiences at similar rates. The translation gap in France is driven not by topic selection but by the inherent geographic scope of operations — international deals are published in English, local community engagement in French.

This balanced ESG approach may reflect France's strong regulatory framework for non-financial reporting (Loi Grenelle II, Loi PACTE, Devoir de Vigilance), which creates domestic demand for ESG disclosure that matches the international investor demand. French companies face ESG pressure from both directions simultaneously, resulting in equilibrium rather than asymmetry.

France also shows the **lowest overall similarity** of the four markets (0.841/0.848 vs 0.864–0.889 for others), suggesting that French companies produce more original content in each language rather than translating. This is consistent with the geographic segmentation finding — companies actively tailor content to different audiences rather than simply translating everything.

## Excluded and Partial Companies

**Fully excluded** (not in corpus):

| Company | Reason |
| ------- | ------ |
| Bouygues | WAF blocks all automated access (Akamai). 3,033 PDFs pending. |
| BNP Paribas | CDN-level 403 on all tested IPs. 1,251 URLs pending. |
| Saint-Gobain | Cloudflare challenge on all tested IPs. 1,006 URLs pending. |
| SE (Schneider Electric) | Source URLs were category pages, not individual PRs. |

**Partially included** (in corpus but with caveats):

| Company | Issue | Impact on analysis |
| ------- | ----- | ------------------ |
| Thales | Only 1,407 of 4,520 PRs scraped (Incapsula WAF) | Bilingual analysis valid but incomplete |
| Capgemini | Only 9 FR docs (EN site blocked during initial scrape, FR fine) | Excluded from bilingual comparison |
| Carrefour | 1,201 EN, 0 FR in corpus (FR blocked by Cloudflare) | EN-only, excluded from bilingual comparison |
| Engie | 407 EN, 0 FR (only 1 FR URL in source data) | EN-only, excluded from bilingual comparison |
| Holcim | 443 EN, 96 FR (headquartered in Switzerland, limited FR content) | Low FR count affects similarity scores |

## Output Files

| File | Description |
| ---- | ----------- |
| `results/CAC40/corpus.json` | Unified corpus: 49,477 documents (308 MB) |
| `results/CAC40/embeddings_mpnet.npz` | Document embeddings (49,477 × 768) |
| `results/CAC40/similarity_mpnet.json` | Per-company cross-lingual similarity scores |
| `results/CAC40/similarity_scores_per_pr.json` | Per-PR best-match similarity scores |
| `results/CAC40/corpus_summary.xlsx` | Corpus statistics by company |
| `results/CAC40/analysis_summary.xlsx` | Three sheets: Similarity, FR topics, EN topics |
| `results/CAC40/topics/topics_untranslated_fr.json` | Per-company BERTopic: 92 topics (FR not in EN) |
| `results/CAC40/topics/topics_untranslated_en.json` | Per-company BERTopic: 117 topics (EN not in FR) |
| `results/CAC40/topics/topics_labeled_fr.json` | Labeled FR topics with categories |
| `results/CAC40/topics/topics_labeled_en.json` | Labeled EN topics with categories |
| `results/CAC40/topics/topics_all_companies_fr_labeled.xlsx` | 3-tab Excel: Summary, Topics, Representative PRs (FR direction) |
| `results/CAC40/topics/topics_all_companies_en_labeled.xlsx` | 3-tab Excel: Summary, Topics, Representative PRs (EN direction) |
