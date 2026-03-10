# The Startup Graveyard Index: Avoidable Death Score

## Overview
- **Slug**: startup-graveyard-index
- **Description**: Ranking 30 famous startup failures by how stupid, preventable, and inexcusable their deaths were — not just how much money they lost.
- **Items**: 30 startups (spanning dot-com bubble era through 2020s unicorn collapses)

## Narrative Angle
- **Thesis**: The most spectacular startup failures are not those that lost the most money, but those that had every conceivable advantage — elite investors, proven teams, massive markets — and still managed to die in ways that look obvious in hindsight. Money lost measures ambition. Avoidability measures stupidity.
- **Expected surprise**: Juicero — a $120M startup that made a $699 Wi-Fi-connected juice press for packets you could squeeze by hand — ranks higher than Theranos on the stupidity scale, despite Theranos being the larger, more notorious fraud. Theranos required a 15-year sustained deception campaign; Juicero required journalists to simply squeeze a bag.
- **Hook**: Quibi burned $1.75 billion in six months. Theranos defrauded investors for fifteen years. But neither is the stupidest startup death of all time — that distinction belongs to a company that raised $120 million to solve a problem that did not exist, built a $699 machine to do it, and got exposed by a reporter who squeezed a bag.

## Scoring Formula

### Formula Name: Avoidable Death Score (ADS)
**ADS = (DelusionScore × 0.30) + (PMF_Gap × 0.25) + (BurnRecklessness × 0.20) + (IgnoredWarnings × 0.15) + (HypeMultiplier × 0.10)**

The formula deliberately weights founder delusion and product-market fit gap over total losses (burn recklessness), so companies with massive ambition-driven losses (Solyndra, Better Place) don't auto-win the stupidity trophy. Total losses are used only as a modifier, not the primary driver.

### Variables

| Metric | Weight | Direction | Description |
|--------|--------|-----------|-------------|
| **DelusionScore** | 30% | Higher = more stupid | Qualitative 1–10 rubric measuring how disconnected founder claims were from reality. Scored across 4 dimensions: (1) Founder self-mythology, (2) Misrepresentation to investors/press, (3) Response to red flags, (4) Exit behavior. See rubric below. |
| **PMF_Gap** | 25% | Higher = more stupid | Qualitative 1–10 rubric: Did anyone actually want this product at this price? Scored on: (1) Organic demand evidence before launch, (2) Price vs. consumer willingness-to-pay, (3) Market size validation, (4) Competitor existence. See rubric below. |
| **BurnRecklessness** | 20% | Higher = more stupid | Derived from total funding raised ÷ (revenue generated or units actually sold or months of operation). Normalized to 1–10. Penalizes burning enormous capital with near-zero output, not just large absolute losses. |
| **IgnoredWarnings** | 15% | Higher = more stupid | Number of months between the first documented public red flag (press article, analyst warning, internal leak, regulatory notice) and the company's shutdown date. Longer = stupider. Normalized to 1–10 scale. |
| **HypeMultiplier** | 10% | Higher = more stupid | Peak valuation ÷ peak annual revenue (or peak valuation alone if revenue was near-zero), normalized to 1–10. Captures how inflated the bubble was relative to actual business output. |

### Scoring Rubrics

#### DelusionScore Rubric (0–10)
- **9–10** (Full Messiah): Founder claimed to have invented something that physics or reality forbid. Actively suppressed internal dissent with legal threats. Continued making false public claims after red flags were documented. Examples: Theranos (blood test tech), Elizabeth Holmes courtroom persona.
- **7–8** (Willful Blindness): Founder knew the business was broken but ran a PR reality distortion field. Self-dealing (buying back own shares, trademark deals, loans against equity) while publicly projecting confidence. Example: Adam Neumann/WeWork, Shai Agassi/Better Place.
- **5–6** (Galaxy-Brained): Founder genuinely believed in a vision that neutral observers called delusional. Built expensive infrastructure before proving unit economics. Interpreted every failure as a "scaling problem." Example: Webvan, Better Place battery swapping.
- **3–4** (Arrogant Pivot Addict): Founder showed signs of self-awareness but refused to adjust product to market signals. Made multiple pivots that each cost more than the last. Example: MoviePass, Segway.
- **1–2** (Honest Dreamer): Founder had a real vision, honest communication, but market timing or tech was simply wrong. No fraud, no self-dealing, no reality distortion. Example: Rdio (legitimate streaming service beaten by better-funded Spotify), Vine (shut by corporate parent).

#### PMF_Gap Rubric (0–10)
- **9–10** (Nobody Wanted This): Product solved a problem that was invented by the startup. Organic demand was zero or negative. Consumer testing would have revealed this in a weekend. Price was orders of magnitude above consumer WTP. Example: Juicero ($699 machine for pre-squeezable bags), Google+ (forcing social on search users), Amazon Fire Phone (nobody asked for this phone).
- **7–8** (Wanted By Very Few): Product addressed a real problem but only for a tiny market at a price the mass market would never pay. The "market" was primarily journalists, conference attendees, and early-adopter blogs. Example: Segway, Color Labs photo app.
- **5–6** (Wrong Time, Wrong Price): Product concept was validated but execution missed on pricing, timing, or distribution. A competitor later succeeded with the same concept. Example: Webvan (Instacart succeeded 20 years later), Pets.com (Chewy succeeded), Better Place (Tesla Model S succeeded without battery swapping).
- **3–4** (Real Market, Real Competitor Problem): Clear demand existed, but the startup was outcompeted or legally blocked from a genuine market. Failure was competitive or regulatory, not conceptual. Example: Rdio (Spotify/Apple Music), Aereo (broadcast copyright law), Myspace (Facebook), Friendster (Myspace, Facebook).
- **1–2** (Legitimate Market, Genuine Attempt): Strong PMF evidence existed — real users, real revenue, real traction — but the business model or unit economics were ultimately wrong. Example: MoviePass (3M paying subscribers proves demand; economics were the problem), Vine (80M users at peak), Jawbone (real fitness wearables market).

#### BurnRecklessness Score Calculation
Raw metric: Total Funding Raised (USD millions) ÷ Approximate Revenue or Output Proxy (months active × average revenue/month, or units sold)
- For pure pre-revenue startups: use Funding ÷ Months Active as a proxy
- Normalize final values to 1–10 where 10 = most reckless burn (Color Labs: $41M for 20 months with near-zero users; Quibi: $1.75B for 6 months)
- Scale: 10 = more than $20M/month with near-zero revenue output; 1 = had real revenue that funded a non-trivial portion of operations

#### IgnoredWarnings Score Calculation
Raw metric: Months from First Documented Red Flag to Shutdown
- First red flag = first published critical report, analyst downgrade, regulatory filing, or internal whistleblower becoming public
- 0–6 months: score 1–3 (fast implosion, not much time to course-correct)
- 7–18 months: score 4–6 (could have pivoted)
- 19–36 months: score 7–8 (should have pivoted)
- 37+ months: score 9–10 (criminal negligence level — this is Theranos territory: 15 years of fraud after internal doubts surfaced in year 2)

#### HypeMultiplier Score Calculation
Raw metric: Peak Valuation ÷ Annual Revenue (or Peak Valuation alone if revenue < $1M/year)
- Captures valuation-to-reality ratio
- Score 10: ratio > 1000x (WeWork $47B valuation / $1.8B revenue = 26x is moderate; Theranos $9B / $0 verifiable revenue = infinite)
- Normalize: infinite or >500x = 10; 100–500x = 8–9; 50–100x = 6–7; 20–50x = 4–5; <20x = 1–3

## Inversion Test
**Most money lost (raw):** WeWork (~$12.8B raised, billions in losses), Solyndra (~$850M government/private), Webvan (~$800M raised), Better Place (~$850M raised), Quibi ($1.75B burned)

**Expected #1 by money lost:** WeWork or Webvan

**Why they should NOT be #1 on the Avoidable Death Score:**
- WeWork failed spectacularly but its co-working model was real, its revenue was real ($1.8B/year), and the failure was primarily corporate governance + overvaluation by SoftBank, not product delusion.
- Webvan's failure was genuinely visionary but premature — Instacart proved the concept 20 years later. The market existed. The timing was wrong. High BurnRecklessness, but low PMF_Gap (3/10) and moderate Delusion (5/10) keeps it out of #1.
- The formula surfaces **Juicero** at or near #1 (DelusionScore 8, PMF_Gap 10, BurnRecklessness 9 — $120M for a problem you could solve by hand) and **Color Labs** (DelusionScore 7, PMF_Gap 9, BurnRecklessness 10 — $41M for a photo-sharing app with no users, acquired for $7M in 18 months).

**Verified surprise:** Theranos ranks high (DelusionScore 10, IgnoredWarnings 10) but PMF_Gap is only 6 (blood testing IS a real market, the tech just didn't work). WeWork ranks mid-table: real revenue, real market, corporate governance failure. Segway ranks very high despite losing "only" $80M — its PMF_Gap is 9 (nobody needed a $5,000 self-balancing scooter) and DelusionScore is 8 (inventor claimed it would replace cars).

## Chart Strategy
- **Primary chart**: Horizontal bar chart (lollipop style) — all 30 startups ranked by ADS score, color-coded by tier
- **Secondary chart**: Scatter plot — X-axis: Total Funding Raised (log scale), Y-axis: Avoidable Death Score. Bubble size = peak valuation. This reveals the "Wasted Capital Quadrant" vs "Cheap Stupidity Quadrant"
- **Tertiary chart**: Tier list (S/A/B/C/D) — the highest-engagement format for this type of pop culture ranking

### Quadrant Labels (Scatter Chart)
- **Upper-right** (High Funding, High Stupidity — "The Expensive Idiots"): Quibi, Juicero, Color Labs. Burned the most money on the dumbest ideas. The true Hall of Shame.
- **Upper-left** (Low Funding, High Stupidity — "The Cheap Disasters"): Secret, Yik Yak, Homejoy. Didn't need billions to achieve world-class stupidity.
- **Lower-right** (High Funding, Low Stupidity — "The Ambitious Losers"): WeWork, Webvan, Solyndra, Better Place. Burned enormous capital chasing genuinely ambitious (if flawed) visions. More tragedy than farce.
- **Lower-left** (Low Funding, Low Stupidity — "The Unlucky Underdogs"): Rdio, Vine, Aereo, Friendster. Ran into bad timing, corporate apathy, or legal brick walls. Would have been fine in a different universe.

### Tier List Categories
- **S-Tier (ADS 8.5–10): "The Hall of Shame"** — Juicero, Color Labs, Theranos, Amazon Fire Phone
- **A-Tier (ADS 7–8.4): "Spectacular Own Goals"** — Quibi, MoviePass, Segway, WeWork, Yik Yak, Google+
- **B-Tier (ADS 5–6.9): "Forgivably Stupid"** — Webvan, Pets.com, Better Place, Homejoy, Secret, Beepi, Zune
- **C-Tier (ADS 3–4.9): "Mostly Unlucky"** — Solyndra, MySpace, Jawbone, Friendster, Essential, Aereo
- **D-Tier (ADS 1–2.9): "Wrong Place Wrong Time"** — Rdio, Vine, Aereo (overlap possible), MySpace (later period)

## Data Sources

| Metric | Source URL | Collection Method |
|--------|-----------|-------------------|
| Total funding raised | Crunchbase / Tracxn / TechCrunch articles | WebFetch per startup |
| Peak valuation | CB Insights, press reports (IPO filings, funding round announcements) | WebSearch + WebFetch |
| Year founded / shutdown | Crunchbase, Wikipedia, press | WebSearch |
| Months active (for burn calc) | Derived from founded/shutdown years | Calculated |
| DelusionScore | Qualitative rubric (4-anchor scoring per startup) | Scored in-context by data agent |
| PMF_Gap | Qualitative rubric (4-anchor scoring per startup) | Scored in-context by data agent |
| IgnoredWarnings months | First critical press report vs shutdown date, sourced from TechCrunch/WSJ/Bloomberg archival articles | WebSearch per startup |
| Revenue proxy | Annual reports, press estimates, IPO filings | WebSearch per startup |

## Items List

1. **Theranos** — Blood test fraud, $9B valuation, $945M raised, shut 2018 after 15 years of fraud
2. **WeWork** — Co-working unicorn, $47B peak valuation, $12.8B raised, IPO failed 2019, bankruptcy 2023
3. **Quibi** — Mobile video, $1.75B raised, shutdown 6 months after launch in 2020
4. **Juicero** — Wi-Fi juice press, $120M raised, $699 product, shut 2017 after "bag squeeze" scandal
5. **Pets.com** — Online pet supplies, ~$82M raised, IPO to shutdown in 268 days (2000)
6. **Webvan** — Online grocery delivery, ~$800M raised, $8B peak valuation, bankrupt 2001
7. **MoviePass** — $10/month unlimited movies, $68.7M raised, 3M subscribers then collapse, shut 2019
8. **Solyndra** — Solar panels, ~$850M (mostly US government loans), bankrupt 2011
9. **Better Place** — Battery-swap EV network, ~$850M raised, sold assets for $450K in 2013
10. **Jawbone** — Fitness wearables, $930M raised, bankrupt 2017, assets sold for pennies
11. **Vine** — 6-second video (Twitter-owned), shut down 2017 despite 200M users
12. **Google+** — Social network by Google, billions in internal investment, shut 2019 after 8 years
13. **Zune** — Microsoft music player/service, hundreds of millions in dev cost, 2% market share, discontinued 2011
14. **Amazon Fire Phone** — Smartphone, $170M write-down, estimated <35K units sold, discontinued 2015
15. **Segway** — Self-balancing scooter, $80M+ invested pre-launch, 140K units sold in 19 years vs 100K/year projection
16. **Yik Yak** — Anonymous campus social app, $73.5M raised, $400M valuation, shut 2017
17. **Color Labs** — Photo-sharing app, $41M raised before launch, sold to Apple for $7M, shut 2012
18. **Homejoy** — On-demand home cleaning, $38M raised, shut 2015 due to contractor misclassification lawsuits
19. **Rdio** — Music streaming, $126M raised, sold to Pandora for $75M, shut 2015
20. **Secret** — Anonymous social app, $35M raised, founders pocketed $3M each, shut 2015 after 18 months
21. **Beepi** — Online used car marketplace, ~$150M raised, shut 2017
22. **Aereo** — Antenna-based TV streaming, $97M raised, killed by Supreme Court ruling 2014
23. **Friendster** — Social network pioneer, $48.5M raised, acquired for $26.4M by MOL Global 2009, pivot to gaming failed
24. **MySpace** — Social network, acquired by News Corp for $580M in 2005, sold for $35M in 2011
25. **Essential** — Premium Android phone, $330M raised, Andy Rubin founder, shut 2020, only ~150K phones sold
26. **Zume Pizza** — Robot pizza delivery, ~$375M raised (SoftBank-backed), $2B valuation, pivoted, folded 2023
27. **Clinkle** — Mobile payments app, $30M raised from top VCs, never launched publicly, dissolved ~2016
28. **Doppler Labs** — Smart earbuds (Here One), $50M raised, filed Chapter 7 bankruptcy 2017
29. **Brandless** — "Unbranded" D2C consumer goods, $240M raised (SoftBank), shut 2020 after 3 years
30. **Lily Robotics** — Follow-me camera drone, $34M raised from 60K+ pre-orders ($15M in deposits), never shipped, shut 2017

## Scoring Notes for Data Agent

### DelusionScore — detailed per-startup guidance
| Startup | Expected DelusionScore | Rationale |
|---------|----------------------|-----------|
| Theranos | 10 | Physics fraud + 15 years of suppression + courtroom denial |
| WeWork | 8 | Trademark self-dealing, reality distortion field, "We" as a tech company |
| Quibi | 7 | Hollywood exec hubris, refused to put content on TV despite user requests |
| Juicero | 9 | $700 machine for a $5 problem; CEO said "it's like the Keurig of juice" with a straight face |
| Pets.com | 5 | Genuinely believed internet + Super Bowl ad = pet supply dominance |
| Webvan | 6 | $1B Bechtel contract before proving Bay Area market |
| MoviePass | 7 | CEO publicly called $9.95/month plan "not a charity" while losing $21.7M/month |
| Solyndra | 5 | Genuine clean energy mission; executives knew China competition was coming |
| Better Place | 8 | Forecast 100K cars in Israel by 2010; sold fewer than 1,000 |
| Jawbone | 7 | 17 funding rounds while clearly losing market to Fitbit and Apple Watch |
| Vine | 2 | Twitter killed a working product with 200M users due to internal strategy failure |
| Google+ | 6 | Google forced G+ login on YouTube users; organic demand was near-zero |
| Zune | 4 | Microsoft's honest but doomed attempt; internal resources were the real waste |
| Fire Phone | 8 | Jeff Bezos personally championed gimmick features; no customer research suggesting demand |
| Segway | 9 | Dean Kamen told Steve Jobs it would be "bigger than the internet" |
| Yik Yak | 5 | Real product/traction, moderation failure; founders pivoted to enterprise and failed |
| Color Labs | 8 | $41M pre-launch for a "social photo" app with zero differentiation; called it "the photo platform for the next century" |
| Homejoy | 4 | Legitimate business model, killed by legal/regulatory environment, not delusion |
| Rdio | 2 | Good product, honest team, simply outcompeted by Spotify's superior licensing deals |
| Secret | 6 | Founders pocketed $6M while "returning" remaining funds; no Plan B for moderation |
| Beepi | 6 | Real market, poor unit economics, executives paid lavishly as company burned |
| Aereo | 3 | Legitimate legal bet; Barry Diller was honest that "if we lose, we're finished" |
| Friendster | 5 | Technology scale failures led to exodus; Google $30M buyout offer rejected in 2003 |
| MySpace | 6 | News Corp acquisition created bureaucratic paralysis; missed mobile entirely |
| Essential | 7 | Andy Rubin raised $330M for a "differentiated" phone with a $699 notch; sexual misconduct scandal buried it |
| Zume Pizza | 7 | SoftBank poured $375M into robots making mediocre pizza; pivoted to "packaging innovation" |
| Clinkle | 8 | Raised $30M in a room, took 2 years to produce nothing; spent on office luxuries |
| Doppler Labs | 5 | Real product, real users, poor timing — AirPods launched 6 months before |
| Brandless | 5 | Interesting DTC experiment, killed by SoftBank pressure to scale unprofitably |
| Lily Robotics | 9 | Took $15M in pre-order deposits, shipped nothing, filed for bankruptcy; CEO called it a "miscalculation" |

### PMF_Gap — detailed per-startup guidance
| Startup | Expected PMF_Gap | Rationale |
|---------|-----------------|-----------|
| Theranos | 5 | Blood diagnostics IS a real, massive market. Technology didn't work, not the market |
| WeWork | 4 | Co-working space is a genuine, growing market — WeWork simply wasn't a tech company |
| Quibi | 9 | "10-minute premium content, mobile-only, pay $8/month" — nobody asked for this specific format |
| Juicero | 10 | $699 Wi-Fi juice press for packets you could squeeze by hand. Problem was invented by the company |
| Pets.com | 6 | Online pet supply IS valid (Chewy proves it) — timing and unit economics were wrong |
| Webvan | 5 | Online grocery IS valid (Instacart proves it) — timing and infrastructure cost were wrong |
| MoviePass | 3 | 3M paying subscribers prove massive demand for cheap movie access; model broke the math |
| Solyndra | 4 | Clean energy market real; Chinese competition on cost was the killer |
| Better Place | 6 | EV adoption is real, battery-swapping model required manufacturer cooperation that never came |
| Jawbone | 3 | Fitness wearables market proven by Fitbit, Apple Watch; Jawbone simply lost |
| Vine | 2 | TikTok proved 6-second (now 60-second) video format was exactly right — Vine was ahead |
| Google+ | 9 | Users had Facebook and did not want another mandatory social network from their search engine |
| Zune | 6 | Digital music player market existed; iPod owned it; Zune was a real product in a real market |
| Fire Phone | 10 | No consumer research suggested people wanted a "Dynamic Perspective" 3D-effect smartphone |
| Segway | 9 | Personal electric transport is real (e-scooters prove it) but $5,000 and 65 lbs is wrong on every dimension |
| Yik Yak | 4 | Anonymous social had real use case; moderation failure, not market failure |
| Color Labs | 9 | Social photo sharing (Instagram was already dominant); Color had zero differentiation and no users |
| Homejoy | 4 | On-demand cleaning services market is real and survived (TaskRabbit, Handy) |
| Rdio | 3 | Music streaming proven by Spotify; Rdio simply couldn't match Spotify's licensing power |
| Secret | 7 | Anonymous social had niche but real use case; product destroyed itself with harassment |
| Beepi | 4 | Used car online marketplace real; Carvana proved it. Beepi's unit economics were wrong |
| Aereo | 3 | TV cord-cutting proved valid; Aereo's specific antenna-rental model was legally killed |
| Friendster | 4 | Social networking is massively real; Friendster had scale problems and Facebook outran it |
| MySpace | 4 | Social networking is real; MySpace failed to evolve product after Facebook launched |
| Essential | 7 | Premium Android phone market exists; Essential had no differentiator beyond founder fame |
| Zume Pizza | 7 | Robot food delivery had no consumer demand signal; pizza quality was the same or worse |
| Clinkle | 8 | Mobile payments real (Venmo, CashApp won); Clinkle had no product to even test |
| Doppler Labs | 6 | Smart earbuds real (AirPods crushed it); Doppler was first but outgunned |
| Brandless | 5 | DTC brand model real; Brandless's "no brand" value proposition was paradoxically weak |
| Lily Robotics | 9 | Consumer camera drone real (DJI); Lily's specific "throw it in the air" concept was undeliverable |
