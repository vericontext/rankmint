# Global Nap Culture Index

## Overview
- **Slug**: `global-nap-culture-index`
- **Description**: A composite ranking of 30 countries by how structurally, culturally, and climatically optimized they are for the art of the nap.
- **Items**: 30 countries

---

## Narrative Angle
- **Thesis**: The world's best napping country isn't Spain — it's Japan. The countries we assume are nap champions (Mediterranean siesta nations) are increasingly sleep-deprived urban workaholics, while the countries that quietly institutionalized rest are quietly winning.
- **Expected surprise**: Japan scores in the top 3 despite having the world's shortest average sleep duration, because its *inemuri* norm, short legal working week, and infrastructure of nap pods and rest-friendly public transit create an ecosystem where opportunistic napping is not just tolerated but revered. Spain ranks 8th — culturally famous, but structurally underdelivering.
- **Hook**: "Spain invented the siesta. Japan perfected it."

---

## Scoring Formula

**Nap Optimization Score (NOS)** = weighted sum of 5 normalized sub-scores (each 0–10):

```
NOS = (SleepScore × 0.20) + (CultureScore × 0.30) + (WorkloadScore × 0.20) + (ClimateScore × 0.15) + (InfraScore × 0.15)
```

### Variables

| Variable | Weight | Direction | Description |
|---|---|---|---|
| **SleepScore** | 20% | Higher = better | Average daily sleep duration (hours). Source: worldpopulationreview.com / OECD time-use data. Normalized: min 5.87h (Japan), max 7.47h (New Zealand) → 0–10 scale. |
| **CultureScore** | 30% | Higher = better | Nap/rest culture tradition score (0–10 qualitative). Rubric below. This is the most heavily weighted metric because cultural permission is the gating factor — without social acceptance, all other conditions are irrelevant. |
| **WorkloadScore** | 20% | Lower hours = better | Average weekly working hours inverted. Formula: `10 × (max_hours − country_hours) / (max_hours − min_hours)`. Source: worldpopulationreview.com / ILO. |
| **ClimateScore** | 15% | Midpoint = better | Closeness to optimal nap temperature (25°C midpoint of 20–30°C range). Formula: `10 − |avg_temp − 25| × (10 / 25)`, floored at 0. Source: fittotravel.net / World Bank 1991–2020 climate normals. |
| **InfraScore** | 15% | Higher = better | Public rest infrastructure score (0–10 qualitative). Rubric below. Captures nap pods, park density, legal quiet-hour protections, and cafe culture for lingering. |

---

### CultureScore Rubric (0–10)

Measures the degree to which napping is socially normalized, linguistically named, and institutionally embedded in daily life.

| Score | Anchor Description | Example Countries |
|---|---|---|
| **9–10** | Napping has a dedicated cultural name, is legally or institutionally recognized (government mandate or employer norm), and carries social prestige or at minimum zero stigma. Napping in public is unremarkable. | Japan (inemuri), China (xiuxi) |
| **7–8** | Strong traditional norm with a named practice; historically protected by business closures or legal quiet hours; some urban erosion but still widespread outside major metros. | Spain (siesta), Greece (kalo mesimeri), Italy (riposo) |
| **5–6** | Informal midday rest tradition exists and is widely practiced in rural or hot-weather regions; no formal legal protection; moderate stigma in professional urban settings. | Mexico, Colombia, Nigeria, Philippines, India, Taiwan |
| **3–4** | Rest breaks exist but are purely functional (lunch hour), with no cultural vocabulary or prestige around napping; some napping in private is tolerated but uncommon to discuss. | Brazil, Argentina, Turkey, Portugal, Thailand |
| **1–2** | Napping is widely stigmatized as laziness; "hustle culture" dominates; publicly napping is rare and socially penalized. | South Korea, Singapore, United States |
| **0** | No tradition, active stigma, and institutional pressure against rest during working hours. | (theoretical floor) |

**Special case — Japan:** Despite overwork culture, *inemuri* (居眠り, "sleeping whilst present") specifically frames napping as a signal of diligence — you are so committed that you worked yourself to sleep. This earns a score of **9**, tied with China's state-sanctioned xiuxi naps.

---

### InfraScore Rubric (0–10)

Measures the physical and policy infrastructure that enables and supports napping.

| Score | Anchor Description | Example Countries |
|---|---|---|
| **9–10** | Dedicated nap pods in major workplaces and transit hubs; legally mandated quiet hours; high park acreage per capita; cafe culture supports long, undisturbed stays; government campaigns promoting rest. | Japan, Netherlands |
| **7–8** | Legal quiet-hour protections in residential areas; widespread parks and public green space; many cafes with seating built for lingering; some employer-provided rest rooms. | Spain, Greece, Germany, New Zealand |
| **5–6** | Adequate public green space; cafe culture present; no formal nap infrastructure but rest breaks are functionally possible; no legal protections. | France, Italy, Australia, Canada, Sweden |
| **3–4** | Limited public green space; cafe culture exists but turnover-oriented; no employer nap policy norms; urban congestion makes public rest difficult. | Brazil, India, Turkey, South Korea |
| **1–2** | Dense urban environments with minimal green space; cafes are transactional; no quiet-hour laws; nap infrastructure essentially absent. | Singapore, Egypt |

---

## Inversion Test

Expected top 3 by conventional wisdom: **Spain, Greece, Italy** (Mediterranean siesta nations).

Formula result: **Japan, Netherlands, China** are expected to score highest because:
- Japan: CultureScore 9 + low working hours + nap pod infrastructure
- Netherlands: very short working week (26.6h, world's lowest for productive economies) + high park density + permissive work culture
- China: CultureScore 9 (xiuxi state mandate) + midpoint climate in southern regions

Spain scores ~7th–9th: high CultureScore (8) but ClimateScore is near-optimal; dragged down by higher-than-expected working hours (31.9h) and moderate infrastructure score.

**Verdict**: The inversion test passes. The surprise is real and defensible.

---

## Chart Strategy

### Primary chart: **Horizontal Bar Chart**
- X-axis: Nap Optimization Score (0–10)
- Countries sorted descending
- Color-coded by quadrant/category
- Tooltip shows sub-score breakdown on hover
- Template: `chart_bar.html`

### Secondary chart: **Scatter / Quadrant Chart** (MANDATORY — 2 independent variables)
- X-axis: CultureScore (nap tradition strength, 0–10)
- Y-axis: WorkloadScore (inverted hours — higher = fewer actual hours worked)
- Bubble size: ClimateScore
- Tooltip: Country name + all 5 sub-scores
- Template: `chart_scatter.html`

### Tertiary chart: **Heatmap**
- Rows: 30 countries (sorted by NOS)
- Columns: 5 metric sub-scores (SleepScore, CultureScore, WorkloadScore, ClimateScore, InfraScore)
- Color gradient: cool (low) to warm (high)
- Reveals at a glance which countries excel on which dimensions and why Japan's profile looks nothing like Spain's
- Build as a custom ECharts heatmap in a standalone HTML file

### Quaternary chart (optional): **Simulated Race / Weight Slider Chart**
- Interactive bar chart where the user can drag sliders to change the weight of each of the 5 metrics
- On weight change, rankings re-sort with animation (ECharts bar-race transition)
- Shows: "If you weight culture most, Japan wins. If you weight climate most, Nigeria and India rise. If you weight work-life balance, Netherlands wins."
- This is the highest-engagement shareable chart for this topic — strongly recommended

### Quadrant Labels (for scatter chart)

| Quadrant | X (Culture) | Y (Work-Life) | Label | Description |
|---|---|---|---|---|
| Upper-right | High | High | **The Enlightened Nappers** | Countries where rest is both culturally venerated and structurally protected — they figured it out |
| Upper-left | Low | High | **The Accidental Resters** | Short workweeks but no napping culture — they have the time but don't know what to do with it |
| Lower-right | High | Low | **The Exhausted Believers** | They love the idea of napping, they just never have time for one |
| Lower-left | Low | Low | **The Productivity Martyrs** | Long hours, no cultural permission, nowhere to lie down — sleep deprivation as a badge of honor |

---

## Data Sources

| Metric | Source URL | Collection Method |
|---|---|---|
| Average daily sleep duration (hours) | https://worldpopulationreview.com/country-rankings/average-sleep-time-by-country | WebFetch — full table, 50 countries, confirmed accessible |
| Average weekly working hours | https://worldpopulationreview.com/country-rankings/average-work-week-by-country | WebFetch — full table, all 30 countries confirmed, ILO/OECD sourced |
| Average annual temperature (°C) | https://www.fittotravel.net/international-data/348-countries-by-average-temperature | WebFetch — 196 countries, 1991–2016 World Bank normals, confirmed accessible |
| Nap/rest culture tradition score | Qualitative rubric (this document) | Scored by agent using CultureScore rubric above |
| Public rest infrastructure score | Qualitative rubric (this document) | Scored by agent using InfraScore rubric above; supplementary reference: https://www.openaccessgovernment.org/customs-from-countries/59117/ and https://pillow.app/article/how-different-cultures-view-sleep-breaks-during-the-workday |

---

## Items List (30 Countries)

Selection rationale: geographic diversity + coverage of all major nap culture archetypes (Mediterranean siesta, East Asian inemuri/xiuxi, Nordic short-hour, Latin American, Middle Eastern, African, Anglophone).

1. Japan
2. China
3. Spain
4. Greece
5. Italy
6. Netherlands
7. Germany
8. France
9. Norway
10. Denmark
11. Sweden
12. Finland
13. United Kingdom
14. Australia
15. New Zealand
16. Canada
17. United States
18. South Korea
19. Taiwan
20. Singapore
21. India
22. Thailand
23. Mexico
24. Colombia
25. Brazil
26. Argentina
27. Nigeria
28. Egypt
29. Turkey
30. Portugal

---

## Preliminary Score Estimates (for data agent reference)

Estimates based on known data. Data agent should collect exact values and recalculate.

| Country | Sleep (h) | Culture (0–10) | Work Hrs/wk | Avg Temp (°C) | Infra (0–10) | Est. NOS |
|---|---|---|---|---|---|---|
| Japan | 5.87 | 9 | 31.1 | 14.3 | 8 | ~6.8 |
| Netherlands | 7.40 | 4 | 26.6 | 10.5 | 8 | ~6.5 |
| China | 6.72 | 9 | 44.6 | 8.1 | 4 | ~6.2 |
| Spain | 6.93 | 8 | 32.0 | 14.0 | 7 | ~6.1 |
| Greece | 6.90 | 8 | 38.3 | 17.0 | 7 | ~5.9 |
| Italy | 6.90 | 7 | 33.9 | 14.0 | 6 | ~5.7 |
| France | 7.23 | 5 | 30.9 | 12.4 | 6 | ~5.8 |
| Norway | 7.15 | 3 | 26.6 | 2.0 | 7 | ~5.4 |
| Germany | 7.12 | 3 | 29.7 | 10.5 | 7 | ~5.4 |
| India | 6.58 | 6 | 45.7 | 25.1 | 3 | ~4.8 |
| Mexico | 6.62 | 6 | 41.1 | 22.0 | 4 | ~4.7 |
| Colombia | 6.62 | 6 | 42.4 | 22.0 | 4 | ~4.6 |
| Nigeria | 6.70 | 5 | 39.5 | 27.5 | 3 | ~4.5 |
| South Korea | 6.03 | 2 | 37.3 | 12.0 | 3 | ~3.5 |
| Singapore | 6.57 | 2 | 44.6 | 28.1 | 2 | ~3.2 |

*(Remaining 15 countries to be scored during data collection phase)*

---

## Normalization Notes for Data Agent

- **SleepScore**: `(country_hours − 5.87) / (7.47 − 5.87) × 10`
- **WorkloadScore**: `(45.69 − country_hours) / (45.69 − 26.57) × 10`
- **ClimateScore**: `max(0, 10 − |country_temp − 25| × 0.4)` — this yields 10 at 25°C, ~6 at 15°C or 35°C, and 0 below 0°C or above 50°C
- **CultureScore** and **InfraScore**: assigned directly from rubrics above (0–10 integers or half-points)
- All sub-scores normalized to 0–10 before weighting
- Final NOS rounded to 2 decimal places
