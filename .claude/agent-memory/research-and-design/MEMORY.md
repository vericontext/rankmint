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
- `upgradedpoints.com` — pages load CSS/JS only, no data tables accessible via WebFetch
- `cirium.com/thoughtcloud/*` — article pages return empty content (JS-rendered); use WebSearch summaries
- `reports.cirium.com` — Flipsnack embedded viewer, data not in HTML
- `oag.com/punctuality-league-*` — lead-gen gated PDF, no data on page
- `airhelp.com/en-us/ahr-score/airports/` — returns 404
- `en.wikipedia.org` — returns 403; use search summaries or alternative sources instead
- `visualcapitalist.com` — returns 403
- `theglobaleconomy.com` — returns JS only, no table data
- `ourworldindata.org/grapher/*` — metadata page only, no actual data values
- `who.int/data/gho` — interactive widgets, data not in HTML; consider CSV download fallback
- `deel.com` — returns CSS/JS only
- `tradingeconomics.com/country-list/temperature` — returns 403
- `yawnder.com` — returns JS security challenge (Cloudflare), no content
- `trends.napglobalnetwork.org` — URL misleading; site is about climate adaptation plans (NAPs), not napping data
- `listfist.com` — SSL certificate error, inaccessible

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
- Teacher/mentor rankings: "The Complete Syllabus" / "The Unsung Architects" / "The Coattail Legends" / "The Well-Meaning Disasters" — maps prestige vs. competence quadrants

### Power-Competence Decoupling Pattern (Anime/Mentor Indexes)
- The scatter chart for mentor-type indexes should always use "Student Prestige" (how famous/powerful the student is) as X-axis and "Teaching Competence Score" as Y-axis — this visualizes the core irony
- Characters with the most iconic students (Gojo, All Might, Shanks) reliably cluster in lower-right ("Coattail Legends") because their students succeeded despite the mentorship
- The inversion works because the formula must weight Curriculum Coherence + Availability heavily (≥35% combined) — the two dimensions where powerful/absentee mentors systematically fail
- Confirmed surprise performers: Iruka Umino (chunin-level, top 3), Takeda Ittetsu (non-combat, top 10), Coach Anzai (sports, top 10)
- Confirmed low scorers despite fan prestige: Gojo (D-tier), All Might (D-tier), Kamina (last place, died ep 8 with 1 student)
- Per-character scoring guidance table is ESSENTIAL for 30-item pop culture indexes — without it, scoring agents drift on ambiguous cases like Piccolo (reluctant mentor) or Takeda (non-combat coordinator)
- Single-student mentors (Piccolo, Urokodaki): score EquitableAttention on depth of investment, not breadth — prevents unfair penalty for their role type

### Startup Failure Index Pattern (Avoidable Death Score)
- Inversion test for "failure size" indexes: weight founder delusion + PMF gap highest (30% + 25%), not total losses — this surfaces Juicero over WeWork/Theranos
- "BurnRecklessness" = funding ÷ output proxy (months active × revenue), normalized 1–10
- "IgnoredWarnings" = months between first documented public red flag and shutdown date
- Scatter quadrant naming for high-funding/stupidity space: "Expensive Idiots" (high both), "Cheap Disasters" (low funding, high stupidity), "Ambitious Losers" (high funding, low stupidity), "Unlucky Underdogs" (low both)
- Vine, Rdio, Aereo all score low on stupidity despite famous failure — corporate apathy or legal kills, not delusion
- Juicero ($120M) reliably surprises as top stupid despite not being largest loss: PMF_Gap = 10 (problem invented by startup)
- Per-startup scoring guidance table in plan.md is essential for data agent consistency across 30 items
- Key data: Webvan raised ~$800M (IPO raised $375M separately); Better Place raised $850M (sold for $450K in assets); Color Labs raised $41M, sold to Apple for $7M after 18 months; Lily Robotics took $15M in pre-order deposits and shipped nothing

### Temperature Data Workaround
- `tradingeconomics.com` is blocked (403). Use `fittotravel.net/international-data/348-countries-by-average-temperature` instead — confirmed accessible, 196 countries, 1991–2016 World Bank normals in Celsius.
- `globaldatalab.org/geos/table/surfacetempyear/` is accessible but returns only partial data (subnational table truncated). Use as fallback only.

### Optimal-Midpoint Scoring Pattern (Climate)
- When a metric has a "best value" in the middle of a range (e.g., nap-optimal temp 20–30°C, midpoint 25°C), use: `score = max(0, 10 − |value − midpoint| × scaling_factor)`
- Example for temperature: `max(0, 10 − |temp − 25| × 0.4)` → 10 at 25°C, ~6 at 15°C or 35°C, 0 at ≤0°C or ≥50°C

## Food & Restaurant Index Patterns

### Ramen City Data (City Ramen Value Index)
- Numbeo "inexpensive meal" price (itemId=1) is a reliable proxy for local ramen price; ramen typically costs 0.8–1.2× this value in Japanese cities and 1.5–2× in Western cities
- Numbeo Restaurant Price Index (displayColumn=4) confirmed accessible; Osaka/Fukuoka/Sapporo are NOT in the dataset — use Tokyo as Japan proxy and apply COL discount for smaller cities
- Tokyo: ~10,000 ramen shops / 14M pop = ~71 per 100k (most ramen-dense major city by absolute count)
- Fukuoka: ~1,000 ramen shops / 1.6M pop = ~62 per 100k (very high density, tonkotsu birthplace)
- All Michelin-starred ramen in Tokyo lost stars in 2024 guide; replaced with Bib Gourmand (19 ramen Bib Gourmands in Tokyo, 17 in Kansai edition)
- `guide.michelin.com/en/restaurants/ramen` — confirmed accessible, lists 59 restaurants globally
- Japan average ramen bowl: ~700–1,000 JPY = $4.50–$9 USD (2024, inflation-rising)
- Melbourne ramen: AUD $22–$45 per bowl; Sydney comparable
- `bitemybun.com` ramen stats page — confirmed accessible, Tokyo-specific data

### Inversion Test for Food Indexes
- In food value indexes, weighting "quality ceiling" alone produces obvious results (best cuisines win)
- The surprise comes from adding Price-to-Local-Wage as highest weight (25%) — this collapses the rankings of Western cities even if their ramen quality is high
- Cultural Embeddedness as a metric reliably elevates Japanese smaller cities (Fukuoka, Sapporo) over global megacities
- Bangkok is consistently a surprise top-performer on food value indexes due to high Japanese food quality + very low COL

## Airport Anxiety Index Patterns

### Confirmed Data Sources for Airport Indexes
- `worldairportawards.com/worlds-top-100-airports-2024/` — confirmed accessible via WebFetch; returns full rank table. DOH:#1, SIN:#2, ICN:#3, HND:#4, NRT:#5, CDG:#6, DXB:#7, MUC:#8, IST:#10, HKG:#11, FCO:#12, MAD:#15, AMS:#23, SEA:#24, SFO:#47, BKK:#58, LAX:#60, ATL:~#70, JFK:#93; GRU/DEL/MEX/CAN/PEK/ORD/MIA/DFW not in top 100
- `squaremouth.com/travel-advice/airport-travel-delays-in-2024` — confirmed accessible; returns US airport delay table. JFK 35-38%, ORD 37%, MIA 36%, DFW 29-38%, ATL 32%, LAX 24-25%
- `dailypassport.com/most-stressful-airports-new-study/` — confirmed accessible; iSelect study of 50 airports. Newark #1 (18.46/100), Lisbon #2, Manchester #3, JFK #4 (26.83), ORD #5 (31.01)
- `bounce.com/blog/airport-wait-times-2024` — accessible via WebSearch summary; TSA spring 2024 study. JFK 15 min security, LAX 31 min intl, ORD 26 min avg
- `flightqueue.com/airport/BKK` — Bangkok immigration data; 44–57 min for non-citizens
- Cirium OTP 2024: MEX ranked 3rd globally at 84.04%; RUH #1 at 86.65%; LIM #2 at 84.57% (WebSearch confirmed)
- Eurocontrol 2024: European avg OTP 72.4%; LHR frequently restricted; AMS affected by weather/ATC; avg delay 17.5 min/flight

### Airport Congestion Proxy Pattern
- Use `annual passengers ÷ total gates` as congestion metric — avoids need for proprietary terminal sqm data
- Gate counts: ATL 192, ORD 201, DFW 224, JFK 130, NRT 83. International airports harder to find; use aviation databases + airport fact sheets
- Confirmed pax/gate ratios: ATL 562K, JFK 487K, ORD 398K, LHR ~420K, CDG ~586K (CDG highest congestion in dataset)

### Wayfinding Complexity: Confirmed High-Scorers
- CDG: 9/10 — Terminal 2 split into 9 sub-terminals (2A-2G, 2K, 2M); 1 km average walking distance vs 400-600 m industry standard
- JFK: 8/10 — 5 disconnected terminals, no airside connector, separate security per terminal
- LAX: 8/10 — 9 terminals in U-shape, inter-terminal requires bus or roadway crossing
- HND/DOH/SIN: 2/10 — compact/connected/legendary wayfinding; always low-anxiety scorers

### Heatmap as Primary Visual (Airport Anxiety)
- The heatmap (airports × metrics) is the key differentiator for this topic — it answers "WHY is this airport stressful?" not just "HOW stressful is it?"
- Recommend sorting rows by overall AnxietyScore descending so the heatmap doubles as a ranking
- Color scale: red (max anxiety contribution) → white (neutral) → green (min anxiety)

### Key Narrative Surprises (Airport Anxiety)
- ATL is world's busiest (108M pax, 2024) but scores mid-tier: underground Plane Train + 7 concourses = structured chaos, not random chaos
- MEX surprisingly calm: Cirium 3rd best OTP globally (84.04%) despite reputation
- CDG scores worst despite Skytrax #6 global ranking — prestige ≠ calm
- "Tokyo Split": NRT and HND serve same city but live in different anxiety tiers (NRT: A-tier; HND: D-tier)

## Confirmed Data Points (reusable)

- South Korea convenience stores: 55,200 stores / 52M people = 1 per 950 people (world's highest density, 2023)
- Japan: 1 vending machine per 23 people (5.5M machines total)
- Romania alcohol: 17.1L pure alcohol per capita (world #1, 2022)
- Georgia alcohol: 15.5L (world #2)
- Numbeo Healthcare Index top 5 (2024): Taiwan 86.0, South Korea 82.7, Japan 79.3, Netherlands 78.9, France 78.1
- EPI water top scorers (2024): Finland, Germany, Switzerland, UK all score 100.0
- OECD sleep duration by country (worldpopulationreview.com, 2015 data): Japan lowest at 5:52h/day; New Zealand highest at 7:27h/day; South Korea 6:02h; Spain 6:56h; Italy/Greece 6:54h; Netherlands 7:24h
- OECD weekly working hours (worldpopulationreview.com, ILO/OECD): Netherlands 26.6h (lowest productive economy); Norway 26.6h; India 45.7h (highest in 30-country set); China 44.6h; Japan 31.1h; Spain 32.0h
- Japan inemuri: culturally treated as a signal of diligence, not laziness — earns CultureScore 9 despite world's shortest sleep duration
- China xiuxi: state-sanctioned post-lunch nap, some government offices mandate it — CultureScore 9
- Greece kalo mesimeri: legally protected quiet hours 2–5pm in many municipalities — CultureScore 8
- Albania: most coffehouses per capita globally (654 per 100,000 people, 2016)

## K-Drama Index Patterns (K-Drama Binge Trap Index)

### Data Sources for K-Drama Structural Data
- `mydramalist.com` — returns 403; do NOT use via WebFetch
- `asianwiki.com` — returns 403; do NOT use via WebFetch
- IMDb episode lists and series pages: accessible via WebSearch (search IMDb title name to get confirmed episode counts and runtimes from search result snippets)
- Episode counts and runtimes confirmed via WebSearch against multiple sources (IMDb, Wikipedia summaries, fan wikis)

### K-Drama Binge Trap Confirmed Data Points
- Reply 1988: 20 eps × 95 min = 31.7h total; IMDb 9.0 (highest rated K-drama on IMDb)
- My Mister: 16 eps × 70 min = 18.7h; IMDb 9.0
- Squid Game S1: 9 eps × 50 min avg = 7.5h; IMDb 8.0; 2,315,500,000 Netflix hours viewed
- Crash Landing on You: 16 eps × 90 min = 24h; IMDb 8.7; finale hit 21.7% cable rating (2nd highest ever)
- Goblin: 16 eps × 85 min = 22.7h; IMDb 8.5; first kiss ep 6
- Hospital Playlist: 24 eps × 85 min = 34h; IMDb 8.7; anti-binge by design
- D.P.: 6 eps × 50 min = 5h; IMDb 8.2; smallest total hours in dataset
- Penthouse (all 3 seasons): 45 eps × 65 min = 48.75h; highest cliffhanger density
- Extraordinary Attorney Woo: 662M Netflix hours; IMDb 8.5
- All of Us Are Dead: 659M Netflix hours; 12 eps × 60 min = 12h; IMDb 7.6
- Alchemy of Souls: 30 eps × 80 min = 40h; IMDb 8.7
- The Glory: 16 eps × 55 min = 14.7h; 8 eps per part; IMDb 8.2

### Binge Trap Index Design Patterns
- The key inversion: IMDb's top 3 K-dramas (Reply 1988, My Mister, Hospital Playlist) score LOWEST on the Binge Trap Index — all are slow-burn, long-episode dramas with low cliffhanger density
- Romance tension is a stronger compulsion driver than thriller tension in scoring formulas — weight it 25%, higher than plot twists (10%)
- EpisodeFriction (inverted total hours) is the most powerful surprise generator: D.P. at 5h scores 10, making it a sleeper top-performer despite low prestige
- 5-metric formula: CliffhangerDensity (30%) + RomanceTensionEngine (25%) + SpoilerPressure (20%) + EpisodeFriction inverted (15%) + PlotTwistVelocity (10%)
- Tier list (S/A/B/C/D) is the primary shareability format for pop culture indexes
- For K-drama scatter chart: X-axis = IMDb rating (quality), Y-axis = Binge Trap Score. Quadrant names: "The Perfect Traps" / "The Guilty Destroyers" / "The Prestige Slow Burns" / "The Safe Zone"

## Programming Language Extinction Index Patterns
See detailed notes in `programming-language-extinction.md`.
- `tiobe.com/tiobe-index/` — confirmed accessible via WebFetch
- `survey.stackoverflow.co/2024/technology` — confirmed accessible via WebFetch
- `languages.orsinium.dev/` — confirmed accessible via WebFetch; Reddit subscriber counts for all language subreddits
- TIOBE anomalies: TypeScript #35 (absorbed by JS searches), Visual Basic #7 (MSDN docs inflate), Perl #11 March 2026 "comeback" = legacy web pages not new projects
- Inversion: COBOL is NOT most endangered (bank jobs keep it mid-table ~55/100); ActionScript IS most endangered (~91/100, Flash EOL 2020)
- Bump chart pattern for language indexes: 5-column (TIOBE→SO→GitHub→Jobs→Community); X-axis = metric perspective not time

## Dating App Dark Pattern Index Patterns
See detailed notes in `dating-app-dark-patterns.md`.
- `mozillafoundation.org/en/privacynotincluded/*` — confirmed accessible; returns full privacy analysis per app (Hinge, Grindr, Tantan confirmed)
- Inversion: Hinge (#3 overall) outscores Match.com on PaywallManipulation — "designed to be deleted" brand is the most cynical marketing in tech
- Grindr mid-table overall but 10/10 DataHarvesting — different category of evil ($6.12M GDPR fine, HIV status sold, location data to Catholic org)
- Bumble 10/10 FOMOMechanics — the 24hr timer IS the dark pattern; Boost literally sells back time the free app took from you
- Thursday: 8/10 FOMOMechanics but 4th least manipulative overall — transparent scarcity is less deceptive than fake scarcity
- Quadrants (Addiction vs. Monetization): "The Dopamine Cartel" / "The Toll Road" / "The Crack Dealer" / "The Reluctant Profiteers"
- Match Group $14M FTC settlement (2025) and Valentine's Day 2024 addiction class action are cite-ready documented facts
- `uxplanet.org` blocked (403); `adapty.io/blog` returns JS-only

## Gaming Boss / Character Design Index Patterns

### Boss Fight Fairness Index (Difficulty vs. Fairness Decoupling)
- The core inversion: weight ZERO difficulty in the fairness formula — use community difficulty as the scatter chart X-axis only
- Six fairness metrics: TelegraphClarity (28%) + HitboxAccuracy (22%) + RecoveryWindow (18%) + LearningCurveDesign (17%) + RetryFriction inverted (10%) + CameraArena (5%)
- Easiest boss can be the fairest: Baldur (GoW 2018, 2/10 difficulty) ranks #1 fairest because the design is impeccable — this is the thesis of the index
- Bed of Chaos reliably ranks last: hitboxes don't match platforms, sweep clips geometry, long runback, teaches nothing
- Sans (Undertale) ranks surprisingly high: follows every rule the game establishes; KARMA mechanic is consistent; the "cheating" is intentional narrative design
- RetryFriction is an INVERTED metric: score the friction level, then invert for the fairness contribution. Low friction = high fairness (Absolute Radiance Pantheon saves ranks it surprisingly high on this metric alone)
- TelegraphClarity should be the highest-weight metric (28%) in any boss fairness index — it's the most directly measurable design quality
- Quadrant naming: "The Hall of Mastery" (hard+fair) / "The Honest Pushovers" (easy+fair) / "The Bullshit Wall" (hard+unfair) / "The Forgotten Sins" (easy+unfair)
- Four chart types for gaming: lollipop bar (overall rank), scatter (difficulty vs fairness), tier list S/A/B/C/D (shareability), radar (per-metric head-to-head)
- Psycho Mantis is a scoring edge case: intentionally "unfair" fourth-wall mechanic earns mid-tier score because the obscurity is the design, not a bug
- Confirmed community sources for gaming indexes: Fextralife wikis, ResetEra forums, GDC talks, Kotaku/PC Gamer design analysis, Steam community discussions

## Horror Character Survival Index Patterns

### Horror Movie Survival IQ Index (Qualitative Rubric)
- 6-metric equal-weight formula works for horror character scoring: SituationalAwareness + DecisionQuality + WeaponProficiency + GroupLeadership + FinalOutcome + PanicResistance — all scored 1–10, averaged × 10 = 0–100
- Key inversion: Ash Williams scores MID-TIER (55), NOT bottom. Weapon Proficiency (7) and Panic Resistance (8) save him. The "dumb horror character" label only applies to characters who had information and ignored it.
- Confirmed bottom-dwellers: Micah (Paranormal Activity, 15) — told by a professional demonologist exactly what not to do, did all of it. Lower than a literal 6-year-old (Georgie = 17) because Georgie had zero information and zero agency.
- Jack Torrance scoring edge case: score him as evil/corrupted, not dumb. Decision Quality (2), Group Leadership (1), Final Outcome (2) — but the reason is moral failure not cognitive failure. Copy acknowledges this, index does not adjust for it. The comedy is the gap.
- Archetype characters ("Generic Blonde," "Let's Split Up Guy," "Runs Upstairs"): function as the floor of the index. Always score them 10–18. They're composite tropes, not single characters — useful for anchoring the bottom and generating comedy.
- Per-character guidance table with pre-assigned scores is ESSENTIAL. Without it, scoring agents will drift on characters like Ash (funny ≠ dumb), Jack (evil ≠ dumb), Tree (time loop survivor = does she actually learn?).
- Bracket/versus format works well for horror characters: seed by score, annotate each matchup with 1-line roast. Final match = Ripley vs. Erin (forklift vs. blender).
- Tier labels for horror survival: S = "The Professionals" / A = "The Functional Adults" / B = "The Plot Armor Recipients" / C = "The Walking Warning Labels" / D = "Congratulations, You Played Yourself"
- Horror character sources: TVTropes character pages, Fandom wikis per franchise, Horror Homeroom, WatchMojo top 10 articles, Collider character analyses — all accessible via WebSearch summaries
