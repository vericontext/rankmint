# Global Hangover Recovery Index

## Overview
- **Slug**: hangover-recovery-index
- **Description**: A country-level ranking of how well each nation equips its citizens to survive — and recover from — a big night out, measuring everything from pharmacy access to cultural cure traditions to how late you're allowed to sleep in.
- **Items**: 30 countries

## Narrative Angle
- **Thesis**: The countries best at recovering from a hangover are NOT the ones that drink the most. True hangover resilience comes from infrastructure (pharmacies, water quality), cultural permission (flexible work hours, generous sick leave), and dedicated recovery rituals — a combination that rewards countries who have institutionalized the morning-after as a social practice. Heavy-drinking nations like Romania and Latvia score surprisingly low because they pair high intake with poor healthcare infrastructure and little scheduling slack. Meanwhile South Korea — which has built an entire consumer economy around hangover relief — and Nordic countries — with late-start work cultures and top-tier tap water — emerge as the true hangover superpowers.
- **Expected surprise**: South Korea ranks in the top 3 despite not being a stereotypical "drinking culture" country in Western imagination. Romania and Latvia, which lead the world in alcohol consumption per capita, rank near the bottom because they lack the recovery infrastructure to match. Ireland — the country most associated with drinking culture in popular imagination — lands squarely in the middle tier.
- **Hook**: "The world's best hangover country isn't Ireland, Germany, or Australia — it's the place that turned recovery into a billion-dollar science."

## Scoring Formula

### Formula Description
Each country is scored 0–100 on five equally-weighted sub-indices, then combined into a single **Hangover Recovery Score (HRS)**:

```
HRS = (0.25 × Healthcare Access Score)
    + (0.20 × Recovery Infrastructure Score)
    + (0.20 × Scheduling Slack Score)
    + (0.20 × Water Quality Score)
    + (0.15 × Cultural Cure Score)
```

The **alcohol consumption per capita** metric is intentionally NOT in the formula as a positive driver — instead it is a contextual "exposure" variable used for the scatter chart axes only. This forces the index to measure readiness, not habit.

### Variables

| Variable | Weight | Direction | Source | Notes |
|----------|--------|-----------|--------|-------|
| **Healthcare Access Score** | 25% | Higher = better | Numbeo Healthcare Index 2024 | Measures pharmacy availability, healthcare system quality, doctor availability — scaled 0–100 (already normalized) |
| **Recovery Infrastructure Score** | 20% | Higher = better | Composite: Pharmacists per 10k pop (WHO GHO) + OTC medicine availability (PMC research) | Higher pharmacy density + freely available OTC painkillers = better score |
| **Scheduling Slack Score** | 20% | Higher = better | Composite: Statutory paid annual leave days (Wikipedia) + average annual hours worked inverted (OECD) | More leave + fewer hours worked = more time to recover; US gets penalized for zero statutory leave |
| **Water Quality Score** | 20% | Higher = better | EPI 2024 Sanitation & Drinking Water component | Clean tap water for morning-after hydration; tap water safety is a direct hangover recovery factor |
| **Cultural Cure Score** | 15% | Higher = better | Qualitative rubric (0–10 scale) based on documented tradition strength, commercial hangover product availability, and 24-hour food access | South Korea scores 10 (dedicated hangover soup restaurants, commercial recovery drinks at every convenience store); UK/Ireland score 8 (full fry-up culture, chip shops); Georgia scores 2 |

### Scoring Notes
- All sub-scores are normalized to a 0–100 scale before weighting.
- The **Scheduling Slack Score** inverts annual hours worked: Germany (1,340 hrs/yr) gets a high score; Mexico (2,128 hrs/yr) gets a low score.
- Statutory leave uses total days (vacation + public holidays) from Wikipedia's minimum annual leave list.
- Countries with no statutory sick leave (USA) receive a 0 on the sick-leave sub-component.

## Chart Strategy

### Primary Chart: Lollipop / Bar Chart
- **Type**: Horizontal lollipop bar chart (bar template)
- **What it shows**: Overall Hangover Recovery Score for all 30 countries, sorted descending
- **Color coding**: Color bands by quadrant category (see below)
- **Tooltip**: On hover, shows breakdown of all 5 sub-scores
- **File**: `chart.html`

### Secondary Chart: Scatter / Quadrant Chart (MANDATORY)
- **Type**: Scatter plot (scatter template)
- **X-axis**: Alcohol Consumption Per Capita (litres of pure alcohol, WHO data) — "How hard they drink"
- **Y-axis**: Hangover Recovery Score (HRS) — "How well they recover"
- **Bubble size**: Healthcare Access Score (larger bubble = better healthcare)
- **What it reveals**: Countries in the upper-right quadrant are "high drinking + high recovery" — the true hangover elite. Countries in the lower-right are the danger zone: they drink a lot but can't recover well.
- **File**: Referenced within `chart.html` or as a second interactive section

### Quadrant Labels (Scatter Chart)

| Quadrant | X (Drinking) | Y (Recovery) | Name | Description |
|----------|-------------|--------------|------|-------------|
| Upper-right | High | High | **The Professionals** | They drink hard AND recover expertly. Infrastructure, culture, and leave policies all align. (South Korea, Germany, Netherlands) |
| Upper-left | Low | High | **The Prepared Abstainers** | Drink little but have world-class recovery systems in place. Ready for any emergency binge. (Japan, Singapore, Finland) |
| Lower-right | High | Low | **The Walking Wounded** | The most dangerous quadrant. High exposure, low readiness. (Romania, Latvia, Georgia) |
| Lower-left | Low | Low | **The Innocent Sufferers** | Low drinking and equally underprepared. A single bad night could be catastrophic. (Pakistan, Nigeria, Indonesia) |

## Data Sources

| Metric | Source URL | Collection Method |
|--------|-----------|-------------------|
| Alcohol consumption per capita (litres/year, 15+) | https://worldpopulationreview.com/country-rankings/alcohol-consumption-by-country | WebFetch — confirmed accessible, top 30 countries with values |
| Numbeo Healthcare Index 2024 | https://www.numbeo.com/health-care/rankings_by_country.jsp?title=2024 | WebFetch — confirmed accessible, 95 countries with scores |
| EPI 2024 Sanitation & Drinking Water Score | https://epi.yale.edu/measure/2024/H2O | WebFetch — confirmed accessible, top countries with scores (100 = best) |
| Pharmacists per 10,000 population | https://www.who.int/data/gho/data/indicators/indicator-details/GHO/pharmacists-(per-10-000-population) | WebFetch (WHO GHO) — page accessible; data may require CSV download fallback |
| Statutory minimum paid leave (vacation days + public holidays) | https://en.wikipedia.org/wiki/List_of_minimum_annual_leave_by_country | WebFetch Wikipedia table |
| Average annual hours worked | https://en.wikipedia.org/wiki/List_of_countries_by_average_annual_labor_hours | WebFetch Wikipedia table |
| OTC medicine availability by country | https://pmc.ncbi.nlm.nih.gov/articles/PMC7911380/ | WebFetch PMC article — confirmed accessible |
| Hangover cure cultural traditions | https://www.atlasobscura.com/articles/15-hangover-cures-from-around-the-world + https://www.nationalgeographic.com/travel/article/nine-hangover-cures-from-around-the-world | WebFetch — qualitative coding into 0–10 Cultural Cure Score rubric |
| South Korea convenience store density / hangover product market | https://www.beveragedaily.com/Article/2020/01/24/Korea-s-booming-hangover-treatments-trade/ | WebFetch — context for Cultural Cure Score |

## Cultural Cure Score Rubric (0–10)

This metric is qualitatively assigned based on:
1. **Documented tradition strength** (0–3): Is there a named, widely-practiced hangover food/drink ritual?
2. **Commercial hangover product availability** (0–4): Are dedicated hangover recovery products (drinks, pills, sachets) sold at pharmacies or convenience stores?
3. **24-hour food/recovery access** (0–3): Can you get your cure at 3am or 7am equally easily?

| Country | Score | Rationale |
|---------|-------|-----------|
| South Korea | 10 | Haejangguk restaurants open 24/7; billion-dollar hangover drink industry; CU/GS25 convenience stores stock full cure lines |
| Japan | 8 | Ukon no Chikara drinks in every vending machine; 24-hour konbini; umeboshi tradition; extreme convenience store culture |
| United Kingdom | 8 | Full fry-up / greasy spoon universally available; chip shops; a documented social institution |
| Germany | 7 | Katerfrühstück (hangover breakfast) is a recognized meal; rollmops/pickled herring tradition; strong beer culture infrastructure |
| Mexico | 7 | Menudo served Sunday mornings specifically for hangovers; pozole; birria; widely practiced |
| Ireland | 7 | Full Irish breakfast; chicken fillet roll; culturally embedded; widespread chip shop access |
| France | 6 | Bouillon/onion soup tradition; strong café culture for morning coffee; less specialized |
| Russia | 6 | Pickle brine (rassol) tradition; kefir; well-documented folk remedies |
| Canada | 5 | Poutine tradition; Bloody Caesar cocktail as official remedy; less institutionalized |
| Australia | 5 | Smashed avo/eggs culture; Vegemite on toast; less specialized cure infrastructure |
| USA | 5 | Diner breakfast culture; Gatorade widely available; no single unified cure tradition |
| Netherlands | 5 | Broodje haring street food tradition; moderate |
| Spain | 6 | Churros con chocolate; vermut culture; Sunday recovery meals institutionalized |
| Sweden | 5 | Beef Rydberg; filmjölk (fermented milk); moderate tradition |
| Czech Republic | 6 | Utopenci (pickled sausages); strong pub culture; Pivní lázeň (beer spas nearby) |
| Poland | 5 | Żurek (sour rye soup); bigos; tradition exists but less commercial |
| Romania | 3 | Ciorbă de burtă (tripe soup) tradition but poor commercial infrastructure |
| Georgia | 2 | Khinkali hangover myth; very low commercial product availability |
| Latvia | 3 | Kefir/sauerkraut brine tradition; limited infrastructure |
| Finland | 5 | Sauna culture as recovery tool; sports drinks available; mämmi tradition |
| Norway | 5 | Kvite lørdagslapper (Saturday pancakes); moderate infrastructure |
| Denmark | 5 | Reparationsbajer ("repair beer"); moderate |
| Austria | 5 | Viennese Würstelstand (sausage stand, often 24h); moderate |
| Singapore | 6 | Hawker centres open late/early; strong Southeast Asian remedy culture; commercial products available |
| Taiwan | 7 | Congee tradition; 7-Eleven density extreme (highest in world per capita); 24h food access unmatched |
| China | 5 | Congee tradition; century eggs; limited Western-style commercial recovery products |
| Vietnam | 4 | Pho as hangover cure; moderate tradition |
| India | 3 | Lassi/nimbu pani; limited commercial infrastructure; wide regional variation |
| Brazil | 4 | Caldo de mocotó (marrow broth); acai; moderate |
| Colombia | 5 | Changua (milk-poached egg soup); tradition well-practiced but infrastructure variable |

## Items List (30 Countries)

Selected to maximize geographic diversity, data availability, and spread across all four quadrants:

1. South Korea
2. Japan
3. Germany
4. Netherlands
5. Finland
6. Denmark
7. Sweden
8. Norway
9. Austria
10. France
11. United Kingdom
12. Spain
13. Czech Republic
14. Australia
15. Canada
16. Taiwan
17. Singapore
18. Ireland
19. United States
20. Poland
21. Romania
22. Latvia
23. Georgia
24. Russia
25. Mexico
26. China
27. Vietnam
28. Brazil
29. Colombia
30. India

## Collection Notes for Data Agent

- **Numbeo Healthcare Index**: Confirmed accessible via WebFetch. Collect all 30 countries from the 2024 table.
- **EPI Water Score**: Confirmed accessible. Top performers score 100 (Finland, Germany, Switzerland, UK). Collect exact scores for all 30 countries.
- **Alcohol Consumption**: Confirmed accessible from WorldPopulationReview. Values in litres of pure alcohol per capita, 15+.
- **Pharmacist density**: WHO GHO page accessible but data is in an interactive widget. Use the OECD Healthcare at a Glance 2023 report (https://www.oecd.org/en/publications/2023/11/health-at-a-glance-2023_e04f8239/full-report/pharmacists-and-pharmacies_521be7d5.html) as alternative; or Wikipedia's list. Belgium=1.27/1000, Netherlands=0.21/1000 as reference points.
- **Annual leave**: Wikipedia table (https://en.wikipedia.org/wiki/List_of_minimum_annual_leave_by_country) — confirmed accessible in prior research. Use total statutory days (leave + public holidays).
- **Hours worked**: Wikipedia table (https://en.wikipedia.org/wiki/List_of_countries_by_average_annual_labor_hours) — use latest OECD data. Invert for scoring (fewer hours = more slack).
- **Cultural Cure Score**: Use the rubric table above — assign scores directly from the qualitative research conducted. No additional fetching required.
- **OTC availability**: Binary or 3-point scale (0=prescription required, 1=pharmacy only OTC, 2=supermarket/convenience OTC). Use PMC paper findings.
