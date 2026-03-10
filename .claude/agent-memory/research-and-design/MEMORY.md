# Research & Design Agent Memory

## Data Source Reliability Notes

### Confirmed Accessible via WebFetch
- `worldpopulationreview.com` — works reliably, good for country rankings with numeric values
- `numbeo.com` rankings pages — works reliably, returns full tables (e.g. Healthcare Index 2024)
- `epi.yale.edu` — works reliably, EPI scores with country values
- `nationalgeographic.com` — works reliably for article content
- `staygenerator.com` — works reliably
- `beveragedaily.com` — works reliably
- `theculturetrip.com` — works reliably

### Blocked / Unreliable via WebFetch (returns 403 or JS-only)
- `en.wikipedia.org` — returns 403; use search summaries or alternative sources instead
- `visualcapitalist.com` — returns 403
- `theglobaleconomy.com` — returns JS only, no table data
- `ourworldindata.org/grapher/*` — metadata page only, no actual data values
- `who.int/data/gho` — interactive widgets, data not in HTML; consider CSV download fallback
- `deel.com` — returns CSS/JS only

### WHO GHO Pharmacist Data Workaround
WHO pharmacist density data is in interactive widgets. Use OECD Health at a Glance report or Wikipedia's pharmacist data as fallback. Known reference points: Belgium=1.27/1000, Netherlands=0.21/1000 people.

## Design Patterns

### Inversion Test (Surprise Mandate)
- Keep the most "obvious" variable (e.g., alcohol consumption) OUT of the scoring formula
- Use it instead as the X-axis of the scatter chart
- This surfaces countries that are high consumers but poorly equipped to recover — and vice versa

### Cultural Cure Score Pattern
- When quantifying cultural/qualitative phenomena, use a named rubric with 2-4 sub-dimensions
- Document the rubric clearly in plan.md so the data agent can assign scores without ambiguity
- South Korea is consistently a surprise top-performer for any "recovery infrastructure" type index due to its commercial hangover product market and 24h convenience store density

### Quadrant Naming Convention
- Upper-right (high X, high Y): aspirational/positive label ("The Professionals")
- Upper-left (low X, high Y): ironic/paradox label ("The Prepared Abstainers")
- Lower-right (high X, low Y): danger/warning label ("The Walking Wounded")
- Lower-left (low X, low Y): innocent/sympathetic label ("The Innocent Sufferers")

## Pop Culture Index Patterns

### Qualitative Rubric Design (e.g., Disney Villain CEO Index)
- For pop culture rankings with no external data, write a detailed 4-anchor rubric per metric (0-2, 3-5, 6-8, 9-10) with named examples
- Include the rubric directly in plan.md so the data-collector agent can score without ambiguity
- Ruthlessness-style "optimal midpoint" metrics use transformation: `score = 10 - |raw - optimal|`
- The inversion test still applies: identify the "expected" top 3 and engineer the formula to surface a surprise
- Tier list chart (S/A/B/C/D) is the highest-engagement format for pop culture rankings — always include it
- Recommend all 4 chart types for pop culture: tier, bar, radar (head-to-head comparison), heatmap

### Narrative Category Naming for Pop Culture
- "The C-Suite Predators" / "The Charming Frauds" / "The Micromanagers from Hell" / "The PowerPoint Villains" — useful archetypes for villain/character rankings
- Quadrant labels should be ironic and specific to the domain (not generic)

## Confirmed Data Points (reusable)

- South Korea convenience stores: 55,200 stores / 52M people = 1 per 950 people (world's highest density, 2023)
- Japan: 1 vending machine per 23 people (5.5M machines total)
- Romania alcohol: 17.1L pure alcohol per capita (world #1, 2022)
- Georgia alcohol: 15.5L (world #2)
- Numbeo Healthcare Index top 5 (2024): Taiwan 86.0, South Korea 82.7, Japan 79.3, Netherlands 78.9, France 78.1
- EPI water top scorers (2024): Finland, Germany, Switzerland, UK all score 100.0
