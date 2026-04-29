# Cross-Lingual Analysis of FTSE MIB Press Releases

## Dataset

**30 FTSE MIB companies** (excluding Campari, Unipol, Hera, Prysmian due to data quality issues).

| Metric          | Value                                 |
| --------------- | ------------------------------------- |
| Total PRs       | 49,673                                |
| English PRs     | 23,650                                |
| Italian PRs     | 26,023                                |
| Total words     | 31.3M                                 |
| Period          | ~2001–2026                            |
| Embedding model | paraphrase-multilingual-mpnet-base-v2 |

### Corpus by Company

| Company           |    EN |    IT | Total |  Words |  W/PR |
| ----------------- | ----: | ----: | ----: | -----: | ----: |
| a2a               |   598 | 1,131 | 1,729 |   676K |   391 |
| amplifon          |   293 |   290 |   583 |   153K |   262 |
| azimut            |   530 |   564 | 1,094 |   921K |   841 |
| bancagenerali     |   405 |   369 |   774 |   699K |   903 |
| bancamps          |   324 |   377 |   701 |   209K |   298 |
| bper              |   828 |   834 | 1,662 |   247K |   148 |
| brunellocucinelli |   195 |   198 |   393 |   845K | 2,150 |
| buzzi             |    79 |   151 |   230 |   126K |   546 |
| diasorin          |    98 |    98 |   196 |    61K |   313 |
| enel              | 2,289 | 3,324 | 5,613 | 2,684K |   478 |
| eni               | 2,111 | 2,153 | 4,264 | 1,699K |   398 |
| ferrari           |   378 |   202 |   580 |   412K |   710 |
| finecobank        |    48 |    86 |   134 |   417K | 3,114 |
| generali          |   820 |   817 | 1,637 |   957K |   584 |
| interpump         |   281 |   281 |   562 | 4,422K | 7,868 |
| intesasanpaolo    |   778 | 1,339 | 2,117 | 1,698K |   802 |
| inwit             |   170 |   205 |   375 |   176K |   469 |
| italgas           |   109 |   460 |   569 |   233K |   409 |
| leonardo          | 2,086 |   921 | 3,007 | 1,617K |   538 |
| mediobanca        |   835 |   366 | 1,201 |   277K |   230 |
| nexi              |   313 |   311 |   624 |   976K | 1,564 |
| pirelli           | 5,434 | 3,330 | 8,764 | 4,816K |   549 |
| posteitaliane     |   355 | 3,113 | 3,468 | 2,381K |   687 |
| recordati         |   393 |   426 |   819 |   718K |   876 |
| saipem            |   626 |   629 | 1,255 |   634K |   505 |
| snam              |   598 |   608 | 1,206 |   369K |   306 |
| stellantis        |   408 |   409 |   817 |   537K |   657 |
| telecomitalia     |   765 |   890 | 1,655 |   976K |   590 |
| terna             |   604 |   283 |   887 |   453K |   510 |
| unicredit         |   921 | 1,878 | 2,799 | 1,211K |   433 |

Note: Interpump EN and IT are identical (bilingual PDFs).

## Cross-Lingual Similarity

Average similarity: **EN→IT 0.864, IT→EN 0.847**.

| Company           | EN→IT | IT→EN | EN>0.9% | IT>0.9% |
| ----------------- | ----: | ----: | ------: | ------: |
| interpump         | 1.000 | 1.000 |   100.0 |   100.0 |
| nexi              | 0.943 | 0.944 |    76.7 |    79.7 |
| italgas           | 0.941 | 0.757 |    86.2 |    20.7 |
| stellantis        | 0.936 | 0.934 |    86.0 |    86.3 |
| saipem            | 0.932 | 0.928 |    80.4 |    79.2 |
| snam              | 0.928 | 0.924 |    77.9 |    76.2 |
| eni               | 0.925 | 0.918 |    76.2 |    73.0 |
| unicredit         | 0.909 | 0.810 |    66.0 |    31.9 |
| recordati         | 0.912 | 0.886 |    62.6 |    61.3 |
| a2a               | 0.894 | 0.806 |    53.7 |    29.3 |
| azimut            | 0.887 | 0.869 |    40.9 |    32.8 |
| diasorin          | 0.885 | 0.878 |    58.2 |    56.1 |
| inwit             | 0.883 | 0.876 |    53.5 |    50.2 |
| brunellocucinelli | 0.882 | 0.883 |    32.3 |    33.3 |
| generali          | 0.881 | 0.882 |    52.1 |    52.0 |
| amplifon          | 0.867 | 0.861 |    31.4 |    32.4 |
| posteitaliane     | 0.871 | 0.769 |    35.5 |     9.1 |
| bancamps          | 0.853 | 0.817 |    41.4 |    36.6 |
| enel              | 0.852 | 0.783 |    29.4 |    20.2 |
| bancagenerali     | 0.847 | 0.898 |    19.5 |    49.9 |
| bper              | 0.843 | 0.851 |    14.0 |    13.9 |
| ferrari           | 0.840 | 0.840 |    25.4 |    38.6 |
| finecobank        | 0.834 | 0.745 |    20.8 |     4.7 |
| telecomitalia     | 0.828 | 0.817 |    26.3 |    24.2 |
| pirelli           | 0.824 | 0.856 |    23.8 |    37.3 |
| terna             | 0.819 | 0.855 |    17.4 |    32.5 |
| mediobanca        | 0.776 | 0.860 |    14.4 |    30.6 |
| leonardo          | 0.729 | 0.786 |     3.4 |     6.2 |
| intesasanpaolo    | 0.710 | 0.735 |     0.1 |     0.1 |
| buzzi             | 0.629 | 0.630 |     1.3 |     0.7 |

Companies with highest symmetry (both >0.9): Stellantis, Saipem, SNAM, ENI, Nexi.

Companies with largest asymmetry: UniCredit (EN→IT 0.909 vs IT→EN 0.810), Enel (0.852 vs 0.783), Poste Italiane (0.871 vs 0.769), A2A (0.894 vs 0.806). In all cases, the Italian corpus is larger and contains more content without an English equivalent.

## Topic Modeling

BERTopic identified **155 topics** in untranslated Italian PRs (4,619 docs) and **162 topics** in untranslated English PRs (4,098 docs).

### Largest Topics: Italian PRs Not Matched in English

| Company         | Docs | Content                                                        |
| --------------- | ---: | -------------------------------------------------------------- |
| Pirelli         |  426 | Italian motorsport: Rally, Superbike, tyre performance reports |
| ENI             |  308 | Upstream operations: drilling, wells, production capacity      |
| Poste Italiane  |  219 | Philately: stamp issues, commemorative editions                |
| Leonardo        |  132 | Defense products in Italian: helicopters, military programs    |
| Intesa Sanpaolo |   76 | International banking expansion: Ukraine, China                |
| Enel            |   75 | Bond issuances, financial transactions                         |
| UniCredit       |   71 | Italian corporate/impact lending for SMEs                      |
| Banca MPS       |   66 | Italian agrifood sector banking                                |
| Stellantis      |   61 | Annual results (bilingual, differently framed)                 |
| ENI             |   60 | Italian regulatory filings                                     |

### Largest Topics: English PRs Not Matched in Italian

| Company    | Docs | Content                                                  |
| ---------- | ---: | -------------------------------------------------------- |
| Leonardo   |  243 | Helicopter/aircraft deliveries to international clients  |
| Mediobanca |  133 | M&A advisory, tender offers, securities transactions     |
| Pirelli    |  110 | Rally/F1 tyre technical previews for international media |
| ENI        |   93 | International environmental partnerships                 |
| ENI        |   88 | Quarterly financial results for international investors  |
| Terna      |   68 | Innovation initiatives, grid management                  |
| A2A        |   65 | Shareholders' meetings, financial calendar               |
| Stellantis |   64 | Annual results, shipments, strategic plan                |
| Enel       |   60 | Latin American operations: Enersis, mergers              |
| Leonardo   |   58 | Board appointments, Finmeccanica governance              |

## Detailed Company Analysis

### ENI (2,111 EN / 2,153 IT)

Balanced corpus. The translation gap is NOT about missing translations — it's about **communication adaptation**. The same events (quarterly results, governance) are covered in both languages but written differently:

| Content type      | N (EN) | Mean sim | % untranslated |
| ----------------- | -----: | -------: | -------------: |
| Share buybacks    |    332 |    0.947 |             9% |
| Sustainability    |    157 |    0.933 |            10% |
| Partnerships      |    478 |    0.927 |            18% |
| Exploration       |    567 |    0.923 |            20% |
| Industrial ops    |     86 |    0.929 |            13% |
| Financial results |    136 |    0.884 |        **52%** |
| Governance        |    133 |    0.902 |        **41%** |

Financial results and governance have the highest "untranslated" rate — not because they're missing, but because the Italian version follows CONSOB regulatory style while the English version follows investor relations conventions. The embedding model correctly identifies these as structurally different documents.

### UniCredit (921 EN / 1,878 IT)

2:1 Italian surplus. UniCredit operates as **two distinct communication machines**:

- **Italian retail bank** (IT-only): financial literacy, SME lending, Made in Italy support, insurance products, local fundraising, football sponsorships. Audience: Italian consumers and small businesses.
- **Pan-European investment bank** (EN-only): securities offerings, cross-border lending, CEE fund launches, senior appointments. Audience: international institutional investors.
- **Both languages**: major corporate announcements (annual results, sustainability, M&A).

### Leonardo (2,086 EN / 921 IT)

Unusual 2:1 English surplus. The gap reflects **organizational history** — Leonardo is a conglomerate of formerly independent companies (Finmeccanica, AgustaWestland, Selex ES, OTO Melara). Each subsidiary published in its local language. English-only content comes from UK/US subsidiaries (helicopter deliveries, radar systems, electronic warfare). Italian-only content is parent company governance and defense program announcements. Sustainability content is **100% well-translated** (0% untranslated on IT side).

### A2A (598 EN / 1,131 IT)

Local utility with 2:1 Italian surplus. Italian-only content is hyperlocal: hackathons in Milan, LED lighting in Brescia, EV charging stations, sports web series, women in innovation awards. English-only content is corporate/financial: EBITDA results, shareholders' meetings, 10-year strategic plan. The language split maps directly to **local community vs investor** audiences.

### SNAM (598 EN / 608 IT)

Balanced corpus. Italian-only content: pipeline construction (specific routes: Bronte-Montalbano, Bolzano-Brunico), gas storage conferences. English-only content: the same pipeline stories translated for investors, plus Legambiente environmental campaigns and hydrogen studies. SNAM translates based on **international relevance**, not topic.

### Pirelli (5,434 EN / 3,330 IT)

Largest corpus. Both languages have massive motorsport content, but for different markets: Italian Rally Championship and Superbike in Italian; F1, WRC, Moto2/Moto3 in English. English-only also includes tyre product specifications (Lamborghini, Ducati), PZero fashion collaborations, and commercial vehicle events. **Language follows the market**, not the topic.

### Intesa Sanpaolo (778 EN / 1,339 IT)

Similar to UniCredit: Italian content includes Moody's rating actions, subsidiary rebranding, domestic JVs. English content includes ALEXBANK Cairo branch, Renzo Piano skyscraper, Amazon open banking, Neva venture fund, Moscow museum sponsorship. Each language serves a different geographic and institutional audience.

## Conclusions

### 1. The language split maps to business model, not to topic

The primary driver of the translation gap is **audience segmentation**:

- **Banks** (UniCredit, Intesa Sanpaolo) split by retail vs institutional: Italian for domestic customers, English for international capital markets.
- **Utilities** (A2A, Enel, SNAM) split by local operations vs corporate: Italian for communities and regulators, English for investors.
- **Manufacturers** (Pirelli, Ferrari) split by domestic vs export markets: Italian motorsport for Italian fans, English for international media.
- **Conglomerates** (Leonardo) split by subsidiary: each entity publishes in its local language.

The topic (ESG, financial, governance) is secondary to the audience.

### 2. Same events, different framing

When the same event is covered in both languages — particularly financial results and governance filings — the framing differs significantly:

- Italian versions follow CONSOB regulatory conventions;
- English versions follow international investor relations style.

The similarity model identifies these as different documents, inflating the apparent "untranslated" pool.

### 3. Regulatory framing inflates the "untranslated" pool

A significant portion of Italian-only content (15.8% of untranslated topics) consists of CONSOB-style regulatory filings: shareholder assembly notices, statutory amendments, board appointments, mandatory disclosures. The same information exists in English but follows international investor relations conventions. The similarity model correctly identifies these as structurally different documents, but they are not genuinely "untranslated" — they are the same events packaged for different regulatory audiences. This is particularly visible in BPER (6 governance topics), Saipem, Enel, and Generali.

### 4. Sustainability content is not systematically undertranslated

Here we find something different compared with the IBEX-35 Spanish companies. Italian FTSE MIB companies do not show a systematic pattern of leaving ESG content untranslated. ESG accounts for only 9.1% of untranslated Italian content, compared with 23.6% in Spain. ENI translates over 90% of its sustainability content. Leonardo translates 100% of its sustainability communications. SNAM translates its environmental campaigns.

### 5. The key question

Here, perhaps, we can reframe the question: Rather than asking "what topics do companies fail to translate?", a question could be: **"How do multinational companies segment their communication across languages, and what does this reveal about their stakeholder strategy?"** The answer varies by industry:

- **Banking**: language = business line (retail vs institutional)
- **Utilities**: language = audience (community vs investor)
- **Manufacturing**: language = market (domestic vs export)
- **Conglomerates**: language = organizational unit (subsidiary vs parent)

## Topic Labeling

Topics were manually labeled with different category schemes for each direction, reflecting the distinct communication strategies:

### Untranslated Italian PRs (IT → not in EN): 155 topics, 4,619 docs

What companies say to domestic audiences but don't translate:

| Category                    | Docs  |     % |
| --------------------------- | ----: | ----: |
| Industry / Operations       | 1,642 | 35.5% |
| Financial / Capital Markets |   829 | 17.9% |
| Regulatory / Governance     |   730 | 15.8% |
| Retail / Domestic           |   506 | 11.0% |
| ESG / Sustainability        |   421 |  9.1% |
| Local Community             |   283 |  6.1% |
| Digital / Innovation        |   208 |  4.5% |

### Untranslated English PRs (EN → not in IT): 162 topics, 4,098 docs

What companies say to international audiences but don't produce in Italian:

| Category                    | Docs  |     % |
| --------------------------- | ----: | ----: |
| International Markets       | 1,604 | 39.1% |
| Financial / Capital Markets | 1,068 | 26.1% |
| Regulatory / Governance     |   832 | 20.3% |
| ESG / Sustainability        |   389 |  9.5% |
| Local Community             |   112 |  2.7% |
| Digital / Innovation        |    49 |  1.2% |
| Research / Publications     |    44 |  1.1% |

### Key observations

The asymmetry confirms the audience segmentation thesis:

- **Italian-only** content is dominated by domestic operations (35.5%) and retail/domestic content (11.0%) — Pirelli Italian rally, UniCredit SME lending, A2A Brescia utility services, Poste Italiane stamps.
- **English-only** content is dominated by international markets (39.1%) — Pirelli F1/WRC for global motorsport media, Leonardo helicopter exports, ENI international exploration, Ferrari product launches.
- **ESG is ~9% in both directions** — confirming it is not systematically undertranslated in either language, unlike Spain where 23.6% of Spanish-only content was ESG.
- **Regulatory/Governance is 16-20% in both directions** — the CONSOB framing effect works both ways: Italian regulatory filings look different from English investor communications, and vice versa.
- **Retail/Domestic exists only in Italian (11%)**, while **International Markets exists only in English (39%)** — these are the mirror categories that make the audience segmentation visible.

### Comparison with Spanish study

| | Spain (IBEX-35) | Italy (FTSE MIB) |
|---|---|---|
| **Dominant category (local lang)** | Local events (30%) + Corporate (30%) | Industry/Operations (36%) + Regulatory (16%) |
| **Dominant category (English)** | Corporate (48%) + Financial (22%) | International Markets (39%) + Financial (26%) |
| **ESG share (local lang only)** | 23.6% | 9.1% |
| **ESG share (English only)** | 14.6% | 9.5% |
| **Key driver** | ESG communication gap | Audience segmentation + regulatory framing |

## Output Files

### Data

| File                                              |   Size | Description                                                                      |
| ------------------------------------------------- | -----: | -------------------------------------------------------------------------------- |
| `results/IT40/corpus.json`                        | 202 MB | Unified corpus: 49,673 documents with text, metadata, company, language          |
| `results/IT40/embeddings_mpnet.npz`               | 134 MB | Document embeddings (49,673 × 768) using `paraphrase-multilingual-mpnet-base-v2` |
| `results/IT40/similarity_mpnet.json`              | 7.2 MB | Per-document best-match similarity scores and company-level summary              |
| `results/IT40/topics/topics_untranslated_it.json` | 349 KB | BERTopic results: 155 topics from Italian PRs not matched in English             |
| `results/IT40/topics/topics_untranslated_en.json` | 362 KB | BERTopic results: 162 topics from English PRs not matched in Italian             |
| `results/IT40/topics/topics_labeled_it.json`      |        | Labeled IT topics with domestic-facing categories and ESG classification          |
| `results/IT40/topics/topics_labeled_en.json`      |        | Labeled EN topics with international-facing categories and ESG classification     |

### Excel Reports

| File                                                        | Description                                                                                      |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| `results/IT40/corpus_summary.xlsx`                          | Corpus statistics by company (EN/IT counts, words, exclusion flags)                              |
| `results/IT40/analysis_summary.xlsx`                        | Three sheets: similarity scores, IT topic keywords, EN topic keywords                            |
| `results/IT40/topics/topics_all_companies_it_labeled.xlsx`  | Italian topics (labeled): 7 domestic-facing categories (155 topics, 4,619 docs)                   |
| `results/IT40/topics/topics_all_companies_en_labeled.xlsx`  | English topics (labeled): 7 international-facing categories (162 topics, 4,098 docs)              |

### Analysis

| File                     | Description   |
| ------------------------ | ------------- |
| `notes/IT40_analysis.md` | This document |
