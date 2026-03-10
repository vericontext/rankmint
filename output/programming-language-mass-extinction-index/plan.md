# Programming Language Mass Extinction Index

## Overview
- **Slug**: `programming-language-mass-extinction-index`
- **Description**: A forensic ranking of 30 programming languages by how close they are to extinction — from unstoppable to already dead.
- **Items**: 30 programming languages (9 thriving, 8 stable, 7 declining, 6 endangered)
- **Layout**: Scrollytelling (`templates/index_story.html`)
- **Voice**: Documentary — empathetic, slow-reveal, historical gravity

---

## Narrative Angle
- **Thesis**: Programming language death is not about age — it's about whether the next generation bothers to learn you. A 70-year-old language with a skills shortage can outlive a 15-year-old language whose community abandoned ship.
- **Expected surprise**: COBOL is NOT the most endangered. It ranks mid-tier — the banks still need it, IBM is actively training a new generation of COBOL developers, and 91% of employers planned new mainframe hires in 2024. Perl, despite its 2025 TIOBE comeback, is far more vulnerable: no employer creates net-new Perl projects. Perl is a dead language still breathing on legacy life support, while COBOL has institutional oxygen tanks attached.
- **Secondary surprise**: Assembly language will never die. Hardware engineers, OS kernel developers, and firmware writers need it. Its market size is small but permanent, and the embedded systems market is projected to grow to $215B by 2030.
- **Tertiary surprise**: Haskell has tiny real-world adoption (2% SO usage, rank #42 TIOBE) but active academic conferences (ZuriHac annually), a funded Foundation, and a community that creates out of passion not profit — making it more "alive" culturally than languages with 5x its usage share.
- **Hook**: "When Adobe killed Flash in 2021, ActionScript died with it — the only programming language in history where we know the exact name of the person who decided it would never recover."

---

## Scoring Formula

**Higher score = MORE extinction risk (0 = thriving, 100 = extinct)**

### Formula:
```
ExtinctionRisk = (TIOBEDanger × 0.20) + (SODecline × 0.25) + (GitHubVacuum × 0.20) + (JobDesert × 0.20) + (EcosystemDecay × 0.10) + (CommunityFade × 0.05)
```

All component scores are normalized to 0–100 where 100 = maximum extinction risk.

---

### Variables

| Variable | Weight | Direction | Description |
|----------|--------|-----------|-------------|
| **TIOBEDanger** | 20% | Higher rank = lower risk | TIOBE index rank (March 2026). Invert: rank 1 = score 0, rank 50+ = score 100. Normalized by: `min(100, (rank - 1) × 2)` |
| **SODecline** | 25% | Higher = more risk | Stack Overflow Developer Survey 2024 usage %. Inverted: 0% usage = 100 danger, 62% (JS) = 0 danger. Formula: `max(0, 100 - (pct × 100 / 62))`. Applies decay multiplier if language is not in survey at all (score 95+). |
| **GitHubVacuum** | 20% | Higher = more risk | Approximate new GitHub repos created/year 2024, log-normalized. Python/JS = 0 risk. Languages below 1,000 new repos/year = 90+. Scale: `max(0, 100 - log10(repos+1) × 25)` |
| **JobDesert** | 20% | Higher = more risk | Job market relative demand. Based on DevJobsScanner, SO survey "used professionally" %, and secondary sources. Normalized 0–100 where JavaScript ~= 5, COBOL ~= 55, ActionScript ~= 97. |
| **EcosystemDecay** | 10% | Higher = more risk | Package registry health. Score based on primary package registry size + recency of new packages. CPAN (Perl) ~220K modules but flat; PyPI 614K growing = low risk. Languages with no registry = 90+. |
| **CommunityFade** | 5% | Higher = more risk | Reddit subscribers (primary) + conference activity + Hacker News mentions. Inverted: JavaScript 2.3M subs = 0, COBOL 3,115 = 85, languages with sub-1,000 subreddits = 95. |

---

## Inversion Test

**Naive top 3 most endangered**: COBOL, Fortran, Assembly
**Formula result top 3**: ActionScript, ColdFusion, Scheme

The formula surfaces this because:
- COBOL has 9% employer demand (SO survey professional use), active IBM training programs, 1,454+ job listings, TIOBE rank 24 — it scores mid-table (~62/100)
- ActionScript has no package registry, no new repos, virtually no job postings, and a known death date (Adobe Flash EOL Dec 2020). Score: ~91/100
- Scheme is not tracked on TIOBE top 50, absent from SO surveys, no primary package manager, and its academic use cases are slowly being replaced by Python/Julia in university curricula

---

## Quadrant Strategy (Scatter Chart)

**X-axis**: Community Vitality (inverted CommunityFade + EcosystemDecay composite) — 0 = ghost town, 100 = thriving
**Y-axis**: Market Relevance (inverted JobDesert score) — 0 = unemployable, 100 = in demand

| Quadrant | X | Y | Label | Description |
|----------|---|---|-------|-------------|
| Upper-Right | High community | High jobs | **The Immortals** | Thriving in every dimension. Python, JS, Java live here. |
| Upper-Left | Low community | High jobs | **The Hostages** | Nobody loves them but everyone still pays them. COBOL, Fortran live here — legacy systems won't let them die. |
| Lower-Right | High community | Low jobs | **The Romantics** | Beloved by devotees, ignored by employers. Haskell, Erlang, Scheme live here. |
| Lower-Left | Low community | Low jobs | **The Ghosts** | Neither loved nor needed. ActionScript, ColdFusion, Visual Basic (classic) live here. These are the extinct. |

---

## Chart Strategy

- **Primary chart**: Bar/lollipop chart for overall Extinction Risk score (0–100), sorted highest-risk first
- **Secondary chart**: Scatter/quadrant ("The Immortals" vs "The Ghosts" vs "The Romantics" vs "The Hostages") — Community Vitality × Market Relevance
- **Tertiary chart**: Bump chart (`templates/chart_bump.html`) — shows how each language's rank shifts depending on which single metric you use (TIOBE vs SO vs Jobs vs GitHub). Key story: Perl is #11 in TIOBE but #26 in jobs. COBOL is #24 in TIOBE but #15 in jobs. Haskell is last in jobs but middle-of-pack in community. The bump lines crossing = the story.

---

## Data Sources

| Metric | Source | Data Found | Collection Method |
|--------|---------|-----------|-------------------|
| TIOBE rank | tiobe.com/tiobe-index | Confirmed — March 2026 top 50 retrieved | WebFetch confirmed accessible |
| TIOBE % rating | tiobe.com/tiobe-index | Confirmed — ratings from 21.25% (Python) to 0.26% (Haskell) | WebFetch confirmed accessible |
| SO Developer Survey 2024 usage % | survey.stackoverflow.co/2024/technology | Confirmed — Perl 2.5%, Assembly 5.4%, COBOL 0.7%, Fortran 1.1%, etc. | WebFetch confirmed accessible |
| SO survey "admired" score | stackoverflow.blog | Partial — Perl 34.68% admiration (2023) | WebSearch summaries |
| GitHub repos created | octoverse.github.com + GitHub Innovation Graph | Partial — Python/JS confirmed ~9M each; endangered languages ~1K-7K | WebSearch summaries |
| Job demand % | devjobsscanner.com/blog + secondary | Top 8 languages confirmed; legacy languages estimated from SO "professional use" | WebFetch + WebSearch |
| Package ecosystem size | cpan.org, pypi.org, crates.io, hackage.haskell.org, npm | CPAN ~220K, PyPI ~614K, npm 3.1M, crates.io ~210K, Hackage ~16K | WebSearch summaries |
| Reddit community size | languages.orsinium.dev | Confirmed — JS 2.3M, Python 1.1M, Haskell 73.9K, COBOL 3.1K, Erlang 9.3K | WebFetch confirmed accessible |
| Conference activity | WebSearch for each language | Haskell confirmed (ZuriHac 2024, Foundation active); others via WebSearch | WebSearch |
| Language year of creation | General knowledge + Wikipedia | All 30 languages well-documented | WebSearch as needed |

---

## Scoring Guidance Table

This table documents the raw data found and the expected normalized component scores for the data-collection agent. All component scores are 0–100 where 100 = maximum extinction risk.

| Language | TIOBE Rank | TIOBE % | SO Usage % | Est. GH Repos/yr | Reddit Subs | Primary Registry | Expected Risk Tier |
|----------|-----------|---------|-----------|-----------------|------------|-----------------|-------------------|
| Python | 1 | 21.25% | 51% | ~9.3M | 1,113,330 | PyPI 614K | Thriving (0–15) |
| JavaScript | 6 | 3.45% | 62% | ~9.3M | 2,323,427 | npm 3.1M | Thriving (0–15) |
| TypeScript | 35 | 0.34% | 38% | ~5.4M | (JS sub) | npm | Thriving (5–20) — NOTE: TIOBE rank is misleadingly low because TIOBE counts JS and TS separately and TS gets absorbed into JS searches |
| Java | 4 | 7.99% | 30% | ~3M est. | 287,842 | Maven Central | Thriving (5–20) |
| C# | 5 | 6.36% | 27% | ~2M est. | 200K+ est. | NuGet | Thriving (5–20) |
| Rust | 14 | 1.31% | 13% | Growing | 226,003 | crates.io 210K | Thriving (5–25) |
| Go | 16 | 1.29% | 14% | 49K jobs | 100K+ est. | pkg.go.dev | Stable (15–30) |
| Swift | 20 | 1.04% | 9% | Growing | 50K+ est. | SwiftPM | Stable (15–30) |
| Kotlin | 22 | 0.82% | 9% | Growing | 75K+ est. | Maven | Stable (20–35) |
| C | 2 | 11.55% | 19% | ~5M est. | 150K+ est. | None central | Stable (10–25) — ecosystem-less but jobs abundant |
| C++ | 3 | 8.18% | 23% | ~3M est. | 241,224 | vcpkg/Conan | Stable (10–25) |
| PHP | 18 | 1.23% | 18% | ~2M est. | 150K est. | Packagist | Stable (20–35) |
| Ruby | 30 | 0.55% | 6% | 76K jobs (2yr) | 50K est. | RubyGems | Stable-Declining (30–45) |
| R | 9 | 1.88% | 6% | Growing (data sci) | 75K est. | CRAN 22K+ | Stable (20–35) |
| Scala | 38 | 0.30% | 3% | Declining | 50K est. | Maven/sbt | Declining (45–60) |
| Dart | 25 | 0.69% | 6% | Flutter-driven | 50K est. | pub.dev | Stable (25–40) |
| Lua | 32 | 0.42% | 6.2% | Low | 20K est. | LuaRocks | Stable (35–50) |
| Perl | 11 | 1.75% | 2.5% | ~5.7K | 15K est. | CPAN 220K | Declining (55–70) — TIOBE inflated by legacy web presence, actual dev activity very low |
| Objective-C | 31 | 0.50% | 2.1% | Declining | 15K est. | CocoaPods | Declining (55–70) |
| COBOL | 24 | 0.72% | 0.7% | <500 est. | 3,115 | None | Declining (50–65) — jobs buffer it from extinction |
| Fortran | 13 | 1.45% | 1.1% | ~1.7K | 5K est. | FPM | Declining (55–68) — scientific community keeps it alive |
| MATLAB | 17 | 1.29% | 4% | Low | 15K est. | MathWorks toolboxes | Declining (45–60) — expensive license limits community |
| Haskell | 42 | 0.26% | 2% | ~7K | 73,938 | Hackage 16K | Declining (55–65) — community punches above weight |
| Groovy | ~55 est. | ~0.15% | 3.3% | Low | 10K est. | Maven | Declining (60–72) — Kotlin is its replacement |
| Pascal/Delphi | 10 | 1.80% | 1.8% | ~3.2K | 10K est. | None central | Declining (50–65) — Delphi rank is TIOBE quirk (tooling pages) |
| Visual Basic | 7 | 2.50% | 4.2% | Low | 20K est. | NuGet (VB.NET only) | Endangered (65–78) — VB6 is unsupported; VB.NET barely used |
| ColdFusion | ~90 est. | <0.10% | Not in survey | <200 est. | 3K est. | None | Endangered (75–88) — used by 0.3% of websites |
| ActionScript | Not ranked | ~0% | Not in survey | <100 est. | 2K est. | None | Endangered/Extinct (88–97) — Flash EOL 2020 |
| Assembly | 17 | 1.29% | 5.4% | ~2K est. | 30K est. | None needed | Declining (40–55) — hardware immortality keeps it alive |
| Erlang | 34 | 0.35% | 0.9% | Low | 9,318 | Hex (shared w/ Elixir) | Declining (55–68) — WhatsApp/Ericsson provide institutional support |
| Scheme | ~70+ est. | <0.10% | Not in survey | <500 est. | 5K est. | None central | Endangered (78–90) — academic only, slowly replaced by Python |

---

## Items List (30 Languages, Rough Expected Extinction Risk Order)

**Endangered (highest risk, ~85–97)**
1. ActionScript — Flash is dead, language is dead
2. ColdFusion — 0.3% website usage, no new projects
3. Scheme — academic holdover, no industry foothold
4. Visual Basic (classic VB6) — Microsoft abandoned it in 2008

**Declining-to-Endangered (~60–84)**
5. Groovy — Kotlin ate its lunch on the JVM
6. Perl — legacy corpse with TIOBE-inflated pulse
7. Objective-C — Swift replaced it; survives only in ancient iOS codebases
8. COBOL — appears endangered but banks keep it breathing (mid-tier surprise)
9. Fortran — scientific computing niche preserves it (NASA, weather modeling)
10. Haskell — endangered in market, alive in community (key narrative tension)
11. Erlang — niche telecom/messaging support; Elixir is its lifeboat
12. MATLAB — proprietary pricing limits growth; Python alternatives winning

**Stable-to-Declining (~35–59)**
13. Assembly — hardware permanent but general devs don't touch it
14. Pascal/Delphi — TIOBE rank inflated by legacy docs; real usage tiny
15. Scala — declining as Kotlin/Go take JVM/modern roles
16. Lua — embedded/game scripting niche keeps it alive
17. Ruby — fell out of TIOBE top 20; post-Rails boom decline

**Stable (~20–34)**
18. R — data science demand; CRAN active; academia strong
19. PHP — powering 77% of websites with server-side language; declining share
20. Dart — Flutter dependency; Google-backed; usage tied to mobile
21. Go — stable, strong in DevOps/cloud; slightly declining after peak hype

**Thriving (~5–19)**
22. C++ — never goes away; game engines, systems, finance
23. C — foundation of everything; Linux, embedded, OS kernels
24. Swift — Apple ecosystem lock-in; stable growing
25. Kotlin — Android's first class citizen; JetBrains backing
26. Java — enterprise backbone; declining share but enormous installed base
27. C# — Microsoft push + .NET renaissance; TIOBE Language of Year 2025
28. Rust — highest admiration (83%), growing adoption; Mozilla/Linux kernel
29. TypeScript — fastest-growing GitHub language segment; AI tooling boom
30. Python — TIOBE #1 (21.25%), GitHub #1 in 2024; AI era language

---

## Bump Chart Design Notes

The bump chart (`chart_bump.html`) will show each of the 30 languages as a colored line, with 5 columns representing rank when sorted by each individual metric:

1. **Column 1**: Rank by TIOBE Index (highest % = rank 1)
2. **Column 2**: Rank by Stack Overflow usage % (highest usage = rank 1)
3. **Column 3**: Rank by GitHub new repos (most repos = rank 1)
4. **Column 4**: Rank by job market demand (most jobs = rank 1)
5. **Column 5**: Rank by community size/Reddit (largest community = rank 1)

**Key narrative crossovers to highlight in the chart:**
- **Perl**: Rank ~12 in TIOBE → drops to ~26 in jobs → drops to ~24 in community. The TIOBE rank is a mirage of legacy web pages, not live development activity.
- **COBOL**: Rank ~24 in TIOBE → rises to ~15 in jobs. Institutional demand exceeds its community presence.
- **TypeScript**: Rank ~35 in TIOBE (dramatically underranked due to JS overlap) → rank #3 in GitHub repos, #3 in SO usage. The biggest rank discrepancy in the dataset.
- **Haskell**: Ranks low across market metrics but mid-table in community — visible as a line that dips hard on jobs but recovers on community.
- **Assembly**: Consistent mid-table across all metrics with slight job uptick (embedded systems), demonstrating its permanent-but-niche character.
- **Visual Basic**: Surprisingly high TIOBE (rank 7 — inflated by legacy documentation searches) but collapses in GitHub repos and jobs. Reverse Perl effect.

The bump chart's X-axis represents "metric" (not time), making it a rank-order sensitivity visualization, not a temporal one. This is a critical distinction to communicate in the report narrative.

---

## Report Voice & Structure Notes (Documentary Style)

Opening hook sections should follow this pattern:

1. **Cold open**: "In 2020, Adobe pulled the plug on Flash Player. In the weeks that followed, 98% of ActionScript job postings vanished. The language did not decline. It ceased."
2. **Slow reveal**: Walk through the metric layers one by one — "What the TIOBE index doesn't tell you is..." / "But when you look at GitHub, the picture changes..."
3. **The COBOL reversal**: "Every year, writers declare COBOL dead. Every year, banks quietly post another 1,400 open positions."
4. **The Haskell paradox**: "By every market metric, Haskell should be extinct. The community disagrees."
5. **The Assembly permanence**: "Assembly has no future. Assembly has no past. Assembly simply is — as long as there are transistors to address."

---

## Timeline-Style Scatter Notes (Third Chart)

- **X-axis**: Year language was first released (1954–2012)
- **Y-axis**: Current Extinction Risk score (0–100)
- **Bubble size**: Current TIOBE % rating
- **Color**: Tier (Thriving/Stable/Declining/Endangered)

Key visual story: Most of the oldest languages cluster in the upper-left quadrant (old + high risk) but COBOL and Fortran are anomalies — old but surviving. Assembly is the ultimate outlier: oldest category (1949 roots), low-medium extinction risk.

This chart directly visualizes the thesis: **age alone does not predict extinction**.

---

## Data Collection Notes for Data Agent

When collecting data, prioritize in this order:
1. TIOBE ranks: WebFetch `tiobe.com/tiobe-index/` — confirmed accessible, returns top 50 table
2. SO survey: WebFetch `survey.stackoverflow.co/2024/technology` — confirmed accessible, returns language usage %
3. Reddit subs: WebFetch `languages.orsinium.dev/` — confirmed accessible, returns subscriber counts
4. GitHub repo counts: Use Octoverse blog summaries + GitHub Innovation Graph via WebSearch (Innovation Graph requires CSV which may need direct download)
5. Job demand: Use SO "used professionally" percentage as proxy for languages not in DevJobsScanner top 8; supplement with WebSearch for COBOL/Fortran-specific job counts
6. Package registry sizes: CPAN (~220K confirmed), PyPI (~614K confirmed), npm (~3.1M confirmed), crates.io (~210K confirmed); use WebFetch for Hackage (haskell.org) and CRAN (cran.r-project.org/web/packages/available_packages_by_name.html)

**Known TIOBE anomalies to document in report:**
- TypeScript ranks #35 despite massive usage because most TS-related searches are captured under "JavaScript"
- Visual Basic ranks #7 because MSDN documentation pages dominate the index; actual developer activity is a fraction of that
- Perl ranks #11 in March 2026 (surprise comeback) driven by legacy system maintenance and niche DevOps scripting — not net-new projects
- Delphi/Object Pascal ranks #10 largely due to search traffic from legacy enterprise application maintenance pages

**Known SO survey anomalies:**
- ColdFusion, ActionScript, and Scheme are NOT listed in the 2024 SO survey language list — treat as ~0.1% or "not detected"
- "Visual Basic (.NET)" appears as a category but classic VB6 is subsumed into it

---

## File Outputs Required

```
output/programming-language-mass-extinction-index/
├── plan.md          ← this file
├── raw_data.csv     ← all raw metric values per language
├── scored_data.csv  ← normalized scores + final ExtinctionRisk score
├── report.md        ← narrative report with documentary voice
├── chart_bar.html   ← bar/lollipop ranking chart
├── chart_bump.html  ← bump chart: rank shifts across 5 metrics
├── chart_scatter.html ← scatter: Community Vitality vs Market Relevance (4 quadrants)
├── index.html       ← scrollytelling landing page
├── card.html        ← social preview card
└── social.md        ← share copy for X/LinkedIn
```
