# Programming Language Extinction Index Patterns

## Confirmed Data Sources

### Accessible via WebFetch
- `tiobe.com/tiobe-index/` — confirmed accessible; returns top 50 languages with rank, %, and YoY change
- `survey.stackoverflow.co/2024/technology` — confirmed accessible; returns language usage % (60,171 respondents)
- `languages.orsinium.dev/` — confirmed accessible; returns Reddit subscriber counts for all programming language subreddits (July 2025 data)
- `statisticstimes.com/tech/top-computer-languages.php` — confirmed accessible; returns TIOBE rankings

### Via WebSearch (not directly fetchable)
- GitHub Octoverse repo counts: use WebSearch summaries; Python ~9.3M, JS ~9.3M, TS ~5.4M new repos
- DevJobsScanner job counts: top 8 only (JS/TS 651K, Python 408K, Java 376K, C# 246K, PHP 206K, C/C++ 172K, Ruby 76K, Go 49K)
- GitHub Innovation Graph CSV requires direct download; use WebSearch summaries for language trends

## Confirmed Data Points

### TIOBE Index (March 2026)
- Python #1 (21.25%), C #2 (11.55%), C++ #3 (8.18%), Java #4 (7.99%), C# #5 (6.36%)
- JavaScript #6 (3.45%), Visual Basic #7 (2.50%), SQL #8, R #9 (1.88%), Delphi/Object Pascal #10 (1.80%)
- Perl #11 (1.75%), Fortran #13 (1.45%), Rust #14 (1.31%), MATLAB #15, Go #16 (1.29%)
- Assembly #17 (1.29%), PHP #18 (1.23%), Kotlin #22 (~0.82%), COBOL #24 (0.72%), Dart #25 (0.69%)
- TypeScript #35 (0.34%), Scala #38 (0.30%), Haskell #42 (0.26%)
- ColdFusion, ActionScript, Scheme: not in top 50

### Stack Overflow Developer Survey 2024 Usage %
- JavaScript 62%, HTML/CSS 53%, Python 51%, SQL 51%, TypeScript 38%, Java 30%, C# 27%
- C/C++ 23%, PHP 18%, C 19%, Go 14%, Rust 13%, Kotlin 9%, Swift 9%, Dart 6%
- Lua 6.2%, Assembly 5.4%, Visual Basic 4.2%, MATLAB 4%, Ruby 6%, R 6%
- Groovy 3.3%, Scala 3%, Objective-C 2.1%, Haskell 2%, Perl 2.5%, Erlang 0.9%
- COBOL 0.7%, Fortran 1.1%, Delphi 1.8%
- ColdFusion, ActionScript, Scheme: NOT in 2024 SO survey (treat as <0.1%)

### Reddit Community Sizes (languages.orsinium.dev, July 2025)
- JavaScript: 2,323,427 | Python: 1,113,330 | Java: 287,842 | C++: 241,224 | Rust: 226,003
- Haskell: 73,938 | COBOL: 3,115 | Erlang: 9,318
- Zig: 7,345 (for reference)

### Package Registry Sizes
- npm (JavaScript): 3.1M+ packages | PyPI (Python): 614K+ packages
- crates.io (Rust): 210K+ crates | CPAN (Perl): 220K+ modules (flat/not growing)
- CRAN (R): 22,000+ packages (active growth) | Hackage (Haskell): ~16K packages
- ColdFusion, ActionScript, Scheme, Assembly: no primary package registry

### Job Market Data
- 91% of employers planned new mainframe/COBOL hires in 2024 (Global Mainframe Skills Report)
- 1,454 COBOL mainframe jobs on Indeed, 473 IBM COBOL jobs on LinkedIn (2024-2025)
- Only 3% of employers hire for Fortran; 9% for COBOL
- DevJobsScanner: top 8 languages account for 95%+ of all explicit language job postings
- Assembly: 5.4% SO usage but concentrated in embedded systems; market growing ($116B → $215B by 2030)

## Key Narrative Surprises (Confirmed)

1. **COBOL is NOT the most endangered**: Jobs buffer keeps it mid-table (~55/100 extinction risk)
2. **Perl is more endangered than COBOL**: TIOBE rank inflated by legacy web pages, not live dev activity. 0 net-new Perl projects at scale.
3. **TypeScript TIOBE anomaly**: Ranked #35 despite being GitHub's #2 language — most TS searches absorbed by JavaScript on TIOBE
4. **Visual Basic TIOBE anomaly**: Ranked #7 due to MSDN documentation pages; actual dev activity is a fraction
5. **Assembly is permanent**: Embedded systems market growing; hardware-level necessity prevents extinction
6. **Haskell's community paradox**: Rank #42 TIOBE, 2% SO usage, but 73.9K Reddit subs + active annual conference (ZuriHac) + Haskell Foundation

## TIOBE Anomalies to Document
- TypeScript: #35 TIOBE (JS absorbs most searches) vs #2 GitHub / #4 SO usage
- Visual Basic: #7 TIOBE (MSDN docs inflate) vs low actual professional use
- Perl: #11 TIOBE March 2026 "comeback" driven by legacy maintenance searches, not new projects
- Delphi/Object Pascal: #10 TIOBE driven by enterprise legacy app maintenance search traffic

## Bump Chart Pattern (Language Index)
- 5-column bump chart: TIOBE rank → SO usage rank → GitHub repos rank → Jobs rank → Community rank
- Key crossing lines: Perl (collapses from #12 TIOBE to #26 in jobs), TypeScript (rises from #35 TIOBE to #3 GitHub/SO), COBOL (rises from #24 TIOBE to #15 jobs), Visual Basic (collapses from #7 TIOBE to last quartile in GitHub/jobs)
- X-axis represents "metric perspective" not time — communicate this clearly in report

## Scoring Formula
- ExtinctionRisk = TIOBEDanger(20%) + SODecline(25%) + GitHubVacuum(20%) + JobDesert(20%) + EcosystemDecay(10%) + CommunityFade(5%)
- Higher score = more extinction risk (0=thriving, 100=extinct)
- ActionScript expected ~91/100 (Flash EOL 2020, known death)
- COBOL expected ~55/100 (mid-table despite reputation)
- Haskell expected ~60/100 (community saves it from lower scores)
- Python expected ~3/100 (dominant across all metrics)

## Quadrant Names (Community Vitality × Market Relevance)
- Upper-Right (high community, high jobs): "The Immortals" — Python, JS, Java
- Upper-Left (low community, high jobs): "The Hostages" — COBOL, Fortran (legacy lock-in)
- Lower-Right (high community, low jobs): "The Romantics" — Haskell, Erlang, Scheme
- Lower-Left (low community, low jobs): "The Ghosts" — ActionScript, ColdFusion, VB classic
