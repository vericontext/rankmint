# Data Collector Agent Memory

## Reliable WebFetch Sources (confirmed accessible)

- **TIOBE Index**: `https://www.tiobe.com/tiobe-index/` — returns top 50 languages with rank and % rating directly in page content
- **Stack Overflow 2024 Survey**: `https://survey.stackoverflow.co/2024/technology` — returns all language usage % for "all respondents"
- **Reddit language stats**: `https://languages.orsinium.dev/` — returns language, subreddit, subscriber count table for ~40 languages
- **Subreddit subscriber counts**: `https://subredditstats.com/r/<subreddit>` — returns JSON with subscriberCount field; works for smaller subs not on orsinium.dev
- **DevJobsScanner job demand**: `https://www.devjobsscanner.com/blog/top-8-most-demanded-programming-languages/` — returns top 8 languages with job count and % (JS/TS combined ~31%, Python ~20%, Java ~18%, C# ~12%, PHP ~10%, C/C++ ~8%, Ruby ~4%, Go ~2%)
- **Packagist stats**: `https://packagist.org/statistics.json` — returns JSON with `totals.packages` field; 445,580 as of March 2026

## Known Package Registry Sizes (as of early 2026)
- npm (JS): ~3.1M packages
- PyPI (Python): ~614K packages
- Packagist (PHP): ~445K packages
- CPAN (Perl): ~220-250K modules
- crates.io (Rust): ~210K crates
- RubyGems (Ruby): ~190K gems
- Hackage (Haskell): ~16K unique packages (145K is across all versions — misleading)
- CRAN (R): ~21K packages
- pub.dev (Dart): ~33K packages

## Sites That BLOCK WebFetch
- `www.reddit.com` — always returns access error; use subredditstats.com instead
- `www.devjobsscanner.com/blog/top-programming-languages-in-demand-in-2024/` — 500 error; use the `/top-8-most-demanded-programming-languages/` URL instead

## GitHub Octoverse 2024 Language Rankings (confirmed top 10)
1. Python, 2. JavaScript, 3. TypeScript, 4. Java, 5. C#, 6. C++, 7. PHP, 8. Shell, 9. C, 10. Go
Note: Octoverse does not publish exact percentages — only ordinal rankings. Use relative scale (1-100) for github_pct column.

## TIOBE Known Anomalies (March 2026)
- TypeScript ranks #35 despite massive usage (JS searches absorb TS)
- Visual Basic ranks #7 (MSDN docs inflate it; real dev activity minimal)
- Perl ranks #11 (legacy web presence, not net-new projects)
- Pascal/Delphi ranks #10 (legacy enterprise maintenance search traffic)
- Assembly rank #17 shared with MATLAB and Go (all at 1.29%)
- Groovy not in TIOBE top 50 (estimate ~55)
- ColdFusion not in TIOBE top 50 (estimate ~90)
- ActionScript not in TIOBE top 50 (estimate ~100+)

## SO 2024 Survey: Languages NOT Listed
ColdFusion, ActionScript — treat so_usage_pct as 0.1 (not detected)
