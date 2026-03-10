# City Ramen Value Index

## Overview
- **Slug**: city-ramen-value-index
- **Description**: Ranks 30 major cities by the total value proposition of their ramen scene — blending bowl quality, price-to-wage ratio, shop density, style variety, and cultural authenticity.
- **Items**: 30 cities (Japanese, Asian, Western)

## Narrative Angle
- **Thesis**: "Best ramen value" is not where you think. When you divide quality by what it actually costs a local resident to eat there — and reward cities where ramen is culturally embedded rather than an import trend — Tokyo slides down the list and cities like Bangkok, Fukuoka, and Taipei rise to the top.
- **Expected surprise**: Bangkok ranks in the top 3 globally. Fukuoka beats Tokyo. New York ranks in the bottom third despite its world-class ramen shops. Portland outscores London, Paris, and Sydney on value despite being a small Western city.
- **Hook**: "You don't need a plane ticket to Tokyo to eat exceptional ramen — but you do need to know which cities make you pay through the nose for the privilege."

## Inversion Test
- **Obvious #1**: Tokyo
- **Why it fails the test**: Tokyo has the most ramen shops and highest concentration of elite talent, but prices have climbed near $7-9 USD per bowl with intense competition, and the city's high cost of living means even locals feel the pinch. Tokyo scores high on quality and density but is penalized by price and the "tourist markup" that inflates perceived prestige.
- **Formula response**: Weight the Price-to-Local-Wage Ratio at 25% and add a Depth-not-just-Density bonus so Fukuoka (which pioneered tonkotsu and has a tighter cultural fabric around one defining style) scores higher on cultural depth than Tokyo's broader but more diffuse scene.

## Scoring Formula

**Formula**: `CRVI = (0.25 × A) + (0.20 × B) + (0.20 × C) + (0.20 × D) + (0.15 × E)`

All component scores are normalized to a 0–10 scale before weighting.

### Variables

| Variable | Label | Weight | Direction | Description |
|----------|-------|--------|-----------|-------------|
| A | Price-to-Wage Score | 25% | Higher = Better | Measures how affordable a ramen bowl is relative to local hourly wages. Raw = (Avg local hourly wage USD) / (Avg ramen bowl price USD). Higher ratio = more bowls per hour of work = better value. |
| B | Scene Density Score | 20% | Higher = Better | Number of dedicated ramen-serving restaurants per 100,000 city population. Proxied from Numbeo restaurant price index tiers, known shop counts (Tokyo ~10,000 / 14M pop), and qualitative tier assignment by city. |
| C | Quality Ceiling Score | 20% | Higher = Better | Reflects the top-end quality achievable in the city. Based on: Michelin Bib Gourmand recognitions (ramen-specific), Tabelog top-100 appearances, Timeout/Infatuation editorial picks, and whether world-class chains (Ichiran, Ippudo, Nagi, Afuri) operate locations there. Scored on 0–10 rubric. |
| D | Style Variety Score | 20% | Higher = Better | Counts how many distinct ramen categories are regularly available: tonkotsu, shoyu, shio, miso, tsukemen, mazemen/abura, tori-paitan, regional specialty variants, fusion. Each confirmed style = 1 point, max 9 → normalized to 0–10. |
| E | Cultural Embeddedness Score | 15% | Higher = Better | Qualitative rubric (0–10) measuring how deeply ramen is woven into local food culture rather than treated as a novelty. Factors: native ramen variants, ramen street/districts, local media/competitions, year-round demand vs. trend cycles. |

### Normalization Method
For quantitative variables (A, B): min-max scale each variable across all 30 cities to 0–10 before applying weights.

For qualitative variables (C, D, E): assign raw scores using the rubrics below, then normalize.

---

## Rubric: Quality Ceiling Score (C) — 0 to 10

| Score | Criteria |
|-------|----------|
| 9–10 | Multiple Michelin Bib Gourmand or starred ramen restaurants; listed in global "world's best" guides; multiple acclaimed independent shops with 1+ year waits or viral prestige |
| 7–8 | At least one Bib Gourmand-recognized shop or equivalent (Tabelog 3.8+); several highly rated locations by Time Out or The Infatuation; major chains (Ippudo, Ichiran, Nagi) with city-specific locations |
| 5–6 | Strong regional reputation; consistently well-reviewed shops (Google 4.3+, Yelp 4+); at least one internationally known chain present |
| 3–4 | Emerging scene; mostly chain imports (Ippudo or similar) with few standout independents; quality ceiling exists but not internationally recognized |
| 0–2 | Nascent scene; ramen present but mostly casual, inconsistent, or instant-noodle-adjacent; no noteworthy shop has received press coverage |

### Example Anchors for Quality Ceiling
- **10**: Fukuoka (tonkotsu birthplace, dozens of generational family shops, extreme local competition raising quality floors)
- **9**: Tokyo (most Bib Gourmands globally for ramen), Taipei (Morimendou trained by world's first Michelin-starred ramen chef)
- **7**: New York (Ippudo flagship, Ivan Ramen, Tonchin, Noodle Pudding), Bangkok (Ramen Bankara, Mensho Tokyo outposts)
- **5**: Berlin, London (solid chains, few standout independents)
- **3**: São Paulo, Dubai (growing but nascent)

---

## Rubric: Style Variety Score (D) — count of confirmed styles / 9 × 10

Confirmed styles to check per city:
1. Tonkotsu (pork bone)
2. Shoyu (soy sauce broth)
3. Shio (salt-based)
4. Miso
5. Tsukemen (dipping)
6. Mazemen / Abura soba (broth-less)
7. Tori-paitan (chicken bone broth)
8. Regional specialty (e.g., Hakata thin noodle, Sapporo corn-butter, Kitakata flat)
9. Fusion / local adaptation (e.g., Bangkok spice-infused, Seoul gochujang ramen, Portland yuzu-local)

Cities with native regional styles automatically score a point for item 8.

---

## Rubric: Cultural Embeddedness Score (E) — 0 to 10

| Score | Criteria |
|-------|----------|
| 9–10 | Ramen is a civic identity marker (Fukuoka = hakata ramen is city branding; Sapporo = miso ramen maps); annual ramen festivals; ramen streets/districts; national media coverage of local shops |
| 7–8 | Ramen is a daily staple, not a novelty; multiple neighborhoods compete for ramen supremacy; strong local food blog/media ecosystem covering ramen; ramen visible on convenience store menus |
| 5–6 | Ramen is mainstream and well-integrated into the food scene; no native style but consistent demand; press regularly covers new openings |
| 3–4 | Ramen is a recognized dining category but treated as imported novelty or ethnic cuisine; interest is growing but not embedded |
| 0–2 | Ramen is fringe or unfamiliar; primarily found in tourist districts or Japanese expat enclaves; no local ramen culture |

### Example Anchors for Cultural Embeddedness
- **10**: Fukuoka (ramen is city identity, yatai stall culture), Sapporo (miso ramen = tourism anchor)
- **8**: Tokyo, Seoul (Korean-style ramen culture is distinct and deeply embedded; instant ramyeon = national dish)
- **7**: Osaka, Taipei (ramen streets, chain saturation, local adaptations)
- **6**: Bangkok (Japanese expat community drives quality; Thai-Japanese fusion styles emerging)
- **5**: New York, Los Angeles, Portland (ramen is mainstream, featured in food media regularly)
- **3**: London, Berlin, Sydney (ramen is trendy but not embedded; scene driven by tourism)
- **2**: São Paulo, Mexico City, Dubai (niche expat-driven market)

---

## Price-to-Wage Score (A) — Methodology

**Raw value** = Avg local monthly wage (USD) / (Avg ramen bowl price USD × 30)
→ This gives "ramen affordability fraction": what proportion of monthly spending a bowl represents.

Alternatively expressed as: **Bowls purchasable per day's wages**.

**Data inputs**:
- Average ramen bowl price per city: sourced from Numbeo inexpensive meal benchmark + city-specific ramen price research. Ramen typically costs 0.8–1.2× the Numbeo "inexpensive restaurant meal" benchmark for Japanese cities, and 1.5–2× in Western cities.
- Local average monthly wage: World Bank / national statistics / Numbeo average net salary data.

**Proxy prices** (to be validated during data collection):

| City | Est. Ramen Price (USD) | Source Basis |
|------|------------------------|--------------|
| Tokyo | $9 | ~1,000 JPY (2024 inflation-adjusted) |
| Osaka | $8 | Slightly cheaper than Tokyo |
| Fukuoka | $7 | Tonkotsu stalls, lower COL than Tokyo |
| Sapporo | $8 | Comparable to Osaka |
| Bangkok | $6 | Mid-range Japanese restaurant |
| Seoul | $8 | Korean ramen shops, JPY parity |
| Taipei | $7 | Below Seoul, strong value |
| Manila | $5 | Lower-end market |
| Jakarta | $5 | Similar to Manila |
| Kuala Lumpur | $6 | Mid-tier market |
| Singapore | $12 | Premium pricing in high-COL city |
| Hong Kong | $10 | High COL market |
| Shanghai | $8 | Growing premium market |
| New York | $22 | Premium ramen market |
| Los Angeles | $20 | Premium ramen market |
| San Francisco | $22 | Highest COL US city |
| Portland | $16 | Lower than major US cities |
| Chicago | $18 | Mid-tier US market |
| London | $22 | Premium post-Brexit pricing |
| Paris | $18 | French market premium |
| Berlin | $15 | Lower COL European city |
| Amsterdam | $20 | High COL European city |
| Stockholm | $18 | Scandinavian premium |
| Sydney | $18 | AUD-adjusted |
| Melbourne | $16 | Slightly cheaper than Sydney |
| Toronto | $16 | CAD-adjusted |
| Vancouver | $17 | Similar to Toronto |
| São Paulo | $9 | PPP-adjusted local market |
| Mexico City | $8 | PPP-adjusted, growing scene |
| Dubai | $14 | Expat market with competition |

---

## Scene Density Score (B) — Methodology

**Raw value** = Estimated ramen restaurants per 100,000 population.

Data collection approach:
- Google Maps category search for "ramen" in each city (count results on first 3 pages, multiply by coverage factor)
- Cross-reference Yelp listing counts where available (US/Canada/Australia cities)
- TripAdvisor "ramen" category total listing count
- Known anchors: Tokyo ~10,000 shops / 14M pop = ~71 per 100k; Fukuoka anecdotally higher ratio; NYC ~200 shops / 8.3M pop = ~2.4 per 100k

**Known anchors for normalization**:

| City | Est. Ramen Shops | Population (M) | Per 100k |
|------|-----------------|----------------|----------|
| Fukuoka | ~1,000 | 1.6 | ~62 |
| Tokyo | ~10,000 | 14 | ~71 |
| Sapporo | ~500 | 2.0 | ~25 |
| Osaka | ~1,500 | 2.7 | ~55 |
| Seoul | ~800 | 9.7 | ~8 |
| Taipei | ~300 | 2.7 | ~11 |
| Bangkok | ~200 | 10.5 | ~2 |
| New York | ~200 | 8.3 | ~2.4 |
| Los Angeles | ~150 | 4.0 | ~3.8 |
| Portland | ~40 | 0.65 | ~6 |
| Singapore | ~150 | 5.9 | ~2.5 |
| London | ~100 | 9.0 | ~1.1 |
| Other Western cities | ~20–60 | varies | ~0.5–2 |

Note: Density scores favor Japanese cities on this metric, so the Price-to-Wage and Cultural Embeddedness metrics are critical for Southeast Asian cities to compete.

---

## Chart Strategy

### Primary Chart: Horizontal Bar — Overall CRVI Score
- All 30 cities ranked by total CRVI score
- Color-coded by region (Japan = red, East Asia = orange, Southeast Asia = green, Western = blue)
- Hover tooltip shows breakdown of all 5 component scores
- Annotations on top 3 and bottom 3 to highlight surprises

### Secondary Chart: Scatter — Quality vs. Affordability Quadrant
- X-axis: Price-to-Wage Score (A) — affordability for locals
- Y-axis: Quality Ceiling Score (C) — top-end ramen quality
- Bubble size: Scene Density Score (B)
- This chart makes the story visual: Tokyo sits upper-left (high quality, low affordability), Bangkok sits upper-right (high quality, high affordability = the sweet spot)

### Quadrant Labels (Scatter Chart)

| Quadrant | Label | Description |
|----------|-------|-------------|
| Upper-right (high affordability, high quality) | "The Slurp Spots" | Where great ramen is a birthright, not a splurge — the true value champions |
| Upper-left (low affordability, high quality) | "The Prestige Bowls" | World-class ramen that will drain your wallet — worth it, but not for locals |
| Lower-right (high affordability, low quality) | "The Cheap Gamble" | Affordable, but the ramen scene hasn't caught up yet |
| Lower-left (low affordability, low quality) | "The Tourist Trap" | Expensive AND mediocre — the worst of both worlds |

### Tertiary Chart: Radar — Head-to-Head Comparison
- Select 6 cities for radar overlay: Fukuoka, Bangkok, Tokyo, New York, London, Taipei
- Show all 5 component scores per city
- Makes it visually obvious why Fukuoka or Bangkok beats London on every axis

### Tier Chart: Tier List (S/A/B/C/D)
- S tier: The ultimate value destinations (top 5 CRVI scorers)
- A tier: Excellent value with minor trade-offs
- B tier: Solid ramen cities worth the visit
- C tier: Has ramen, but not worth a special trip
- D tier: Approach with low expectations

---

## Data Sources

| Metric | Source URL | Collection Method |
|--------|-----------|-------------------|
| Avg inexpensive restaurant meal price (proxy for ramen price) | https://www.numbeo.com/cost-of-living/prices_by_city.jsp?itemId=1 | WebFetch — confirmed accessible |
| Restaurant Price Index by City 2025 | https://www.numbeo.com/cost-of-living/rankings.jsp?title=2025&displayColumn=4 | WebFetch — confirmed accessible |
| Average net salary by city | https://www.numbeo.com/cost-of-living/prices_by_city.jsp?itemId=105 | WebFetch (Numbeo net salary page) |
| Ramen shop counts by city (Tokyo) | https://www.bitemybun.com/how-many-ramen-shops-in-tokyo/ | WebFetch — confirmed accessible |
| Michelin Bib Gourmand ramen listings | https://guide.michelin.com/en/restaurants/ramen | WebFetch — confirmed accessible (59 restaurants listed) |
| Quality scene guides by city (Bangkok, Portland, Melbourne) | TripAdvisor /Restaurants-g[id]-zfd11722/ pages | WebFetch per city |
| Style variety (what styles are available per city) | Timeout, The Infatuation, local guides per city | WebFetch per city guide page |
| Cultural embeddedness (qualitative) | Research + rubric scoring | In-context scoring by data agent |
| Population by city | worldpopulationreview.com | WebFetch — confirmed accessible |

---

## Items List

1. Tokyo, Japan
2. Osaka, Japan
3. Fukuoka, Japan
4. Sapporo, Japan
5. Seoul, South Korea
6. Bangkok, Thailand
7. Taipei, Taiwan
8. Singapore
9. Hong Kong
10. Shanghai, China
11. Manila, Philippines
12. Jakarta, Indonesia
13. Kuala Lumpur, Malaysia
14. New York, USA
15. Los Angeles, USA
16. San Francisco, USA
17. Portland, USA
18. Chicago, USA
19. London, UK
20. Paris, France
21. Berlin, Germany
22. Amsterdam, Netherlands
23. Stockholm, Sweden
24. Sydney, Australia
25. Melbourne, Australia
26. Toronto, Canada
27. Vancouver, Canada
28. São Paulo, Brazil
29. Mexico City, Mexico
30. Dubai, UAE

---

## Anticipated Final Ranking (Pre-Collection Hypothesis)

Based on research and formula design, the surprise result should look approximately like:

**Top 5 (hypothesis)**:
1. Fukuoka — Unmatched cultural depth, high density, authentic quality ceiling, affordable prices
2. Bangkok — Exceptional quality-to-price ratio, surprising variety, massive Japanese expat influence
3. Taipei — Strong quality ceiling (Michelin-trained chefs), variety, affordable pricing
4. Osaka — High density, strong quality, cheaper than Tokyo
5. Seoul — High cultural embeddedness (ramyeon as national identity), density, affordable

**Middle tier**:
- Portland, Sapporo, Kuala Lumpur, Manila, Chicago

**Bottom tier**:
- Amsterdam, Stockholm, São Paulo, Dubai, Mexico City

**Tokyo**: Expected rank 6–8 — quality is undeniable but price-to-wage score and "too much choice, not enough soul" in Cultural Embeddedness prevents #1

**New York**: Expected rank 14–18 — world-class quality ceiling but crushed by price-to-wage ratio and low density

**London/Paris**: Expected rank 22–27 — high prices, low density, low embeddedness

This ranking structure passes the inversion test: a Western ramen tourist would guess Tokyo #1, New York top 5. The actual formula surfaces Fukuoka and Bangkok instead.
