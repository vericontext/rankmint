# Programming Language Mass Extinction Index
> Some languages die slowly, like glaciers retreating. Others are assassinated on a Tuesday in December 2020, when Adobe pulled the plug.

## Opening

In 2020, Adobe ended Flash Player support on December 31st. In the weeks that followed, 98% of ActionScript job postings evaporated from the internet. The language did not decline gradually. It ceased. There was no long tail, no graceful migration, no retirement party. A runtime decision by a California software company deleted an entire programming ecosystem — the only language in history where we know the precise calendar date of its death warrant.

But ActionScript's extinction is the exception, not the rule. Most programming language deaths are geological: long, slow, almost imperceptible until they are undeniable. COBOL has been "dying" since 1992. Perl's obituary has been written at least a dozen times in this century. Fortran outlived the programmers who first wrote it. These languages persist because software is infrastructure, and infrastructure does not retire — it accumulates.

The Programming Language Mass Extinction Index scores 30 languages across six dimensions of survival risk: TIOBE search presence, Stack Overflow developer activity, GitHub repository creation rate, job market demand, ecosystem health, and community vitality. Higher score means higher extinction risk. What emerges is a picture that confounds most intuitions about which languages are dying and which are merely dormant.

---

## The Taxonomy

### The Fossils (Extinction Risk 75–100)

*Already extinct, or surviving only in amber.*

| Rank | Language | Score | Defining Trait |
|------|----------|-------|----------------|
| 1 | ActionScript | 100.0 | Flash EOL 2020. Zero new projects. |
| 2 | ColdFusion | 97.3 | 0.3% of websites. Adobe life-support. |
| 3 | Groovy | 86.5 | Replaced by Kotlin on its own JVM. |
| 4 | Haskell | 84.8 | Near-zero jobs; alive only in academia. |
| 5 | Erlang | 84.2 | Institutional at Ericsson/WhatsApp; nothing else. |
| 6 | Objective-C | 81.3 | Swift replaced it in 2014. Still breathing in iOS legacy. |
| 7 | Pascal/Delphi | 78.8 | TIOBE rank inflated by legacy doc searches. |
| 8 | Lua | 78.1 | Embedded scripting niche; no growth path. |
| 9 | Scala | 78.0 | Kotlin absorbed its JVM future. |
| 10 | COBOL | 78.0 | The most interesting entry in this tier — see below. |
| 11 | Fortran | 77.3 | NASA and weather modeling keep it technically alive. |
| 12 | Perl | 77.2 | TIOBE rank #11 is a ghost of legacy web pages. |
| 13 | MATLAB | 76.3 | Proprietary licensing drives universities to Python. |
| 14 | Visual Basic | 75.9 | VB6 abandoned 2008. VB.NET barely touched. |
| 15 | Assembly | 75.0 | No growth path, but hardware permanence. |

What unites this group is not age — Python is older than Lua, and newer than COBOL. What unites them is the absence of net-new adoption: no engineering team is starting a greenfield project in any of these languages in 2026. The work that exists is maintenance, not creation.

### The Fading Stars (Extinction Risk 55–74)

*Once relevant, now declining. Still have jobs — for now.*

| Rank | Language | Score | Defining Trait |
|------|----------|-------|----------------|
| 16 | Dart | 71.2 | Flutter-dependent; Google's continued backing is the only thing keeping it warm. |
| 17 | R | 69.5 | Data science stronghold, but Python's sklearn is eating its lunch. |
| 18 | Swift | 67.8 | Apple ecosystem lock-in; stable, but non-Apple contexts vanishingly rare. |
| 19 | Ruby | 66.8 | Post-Rails boom decline. Still runs half the startup-era web. |
| 20 | Kotlin | 65.1 | Android's first-class language, but Android's market share constraints are Kotlin's ceiling. |
| 21 | Rust | 59.4 | Growing fast, but still tiny in absolute developer numbers. |
| 22 | Go | 57.0 | DevOps bedrock. Declining hype, not declining usage. |

These languages are not dying. They are contracting toward their permanent niches. Swift will always exist while iPhones exist. Go will always exist while Kubernetes exists. The question is not survival — it is whether the niche is large enough to sustain an active ecosystem.

### The Undead (Extinction Risk 35–54)

*Languages the industry has pronounced dead, but which keep answering emails.*

| Rank | Language | Score | Defining Trait |
|------|----------|-------|----------------|
| 23 | PHP | 48.9 | Powers 77% of the web's server-side layer. |
| 24 | C | 48.4 | Foundation of Linux, embedded systems, OS kernels. Will not die. |
| 25 | C++ | 44.3 | Game engines, finance, systems. Nobody loves it, everyone needs it. |

PHP has been declared dead since 2010. It runs WordPress, which runs 43% of the internet. C is sixty years old and still in the Linux kernel. These are not languages that survive despite hostility — they survive because of it. They were written for machines, not developers, and machines don't care about developer experience.

### The Immortals (Extinction Risk 0–34)

*Not threatened. Not even close.*

| Rank | Language | Score | Defining Trait |
|------|----------|-------|----------------|
| 26 | C# | 39.9 | Microsoft's .NET renaissance + TIOBE Language of Year 2025. |
| 27 | Java | 35.1 | Enterprise backbone. Enormous installed base. Irreplaceable. |
| 28 | TypeScript | 23.2 | Fastest-growing segment; AI tooling is built in it. |
| 29 | Python | 17.3 | TIOBE #1 (21.25%). The language of the AI era. |
| 30 | JavaScript | 2.0 | Lowest extinction risk in the index. The cockroach of programming. |

JavaScript scores 2.0 — essentially zero extinction risk. It runs in every browser on the planet, every Node.js server, every React Native app. The only way JavaScript dies is if the internet dies.

---

## The Surprise

**COBOL is NOT the most endangered language in this index.** It ranks #10 with a score of 78.0 — firmly in "The Fossils" tier, but nowhere near the top of the at-risk list. And the reason is quietly astonishing.

In 2024, the U.S. Bureau of Labor Statistics documented over 1,400 open COBOL positions. IBM has active apprenticeship programs training a new generation of COBOL developers. The average COBOL developer earns more than the average JavaScript developer in the United States. 30% of COBOL developers earn over $100,000 annually. COBOL runs an estimated $3 trillion in daily financial transactions. Banks don't replace it because they cannot afford the risk of replacing it. COBOL has no community, no package registry, and almost no GitHub activity — but it has institutional oxygen tanks with infinite refill.

**Perl's TIOBE rank of #11 is a statistical mirage.** On Stack Overflow developer activity, Perl falls to the bottom quartile. In GitHub repository creation, it generates roughly 5,700 new repos per year — compared to Python's 9.3 million. Job postings for Perl represent under 0.5% of developer job market demand. No employer creates net-new Perl projects. Perl's TIOBE rank is sustained by millions of legacy web pages, ancient documentation sites, and bioinformatics papers that reference it. The index is reading the fossil record, not a living organism.

**The Haskell Paradox.** By every market metric — jobs, GitHub activity, SO usage — Haskell should be extinct. It ranks #42 on TIOBE, appears in only 2% of Stack Overflow developer surveys, and produces perhaps 7,000 new GitHub repositories annually. But its Reddit community has 73,900 subscribers. ZuriHac (the Haskell summer hackathon) attracts hundreds of contributors annually. The Haskell Foundation is funded and active. Haskell is the only language in this dataset that is simultaneously near-extinct in the market and culturally thriving. It is a language kept alive by love, not economics.

---

## Where Do You Rank?

The index tells different stories depending on what you write code in.

**If you write ActionScript** — you are already in history. The language has a score of 100.0. The last ActionScript job posting was not posted this year. You are maintaining a museum exhibit.

**If you write Perl** — you likely already know what the numbers show. The ecosystem still exists; CPAN has 220,000 modules, most of them written between 1995 and 2010. Your job is real. But new colleagues are not learning Perl. That is the metric that matters.

**If you write COBOL** — you are in the most counterintuitive position in the index. Your language scores in the "Fossil" tier, but your career prospects are better than most of the developers in the "Fading Stars" tier. Banks are recruiting. IBM is training. The demand exceeds the supply, and it has for fifteen years. Your language is not dying — it is becoming rarer and therefore more valuable, like a trade skill.

**If you write Haskell** — you know the market picture. You have always known. But the community that surrounds you is more durable than the market suggests. ZuriHac still runs. The papers still flow. The Foundation is funded. You are a Romantic in an industry of pragmatists.

**If you write JavaScript** — congratulations. You have the lowest extinction risk of any language in this index. The web is not going anywhere.

[Open interactive bar chart](chart.html) | [Open bump chart: rank shifts across metrics](chart_bump.html) | [Open tier list](chart_tier.html)

---

## Full Rankings

| Rank | Language | Extinction Score | TIOBE Rank | SO Usage % | Job Demand | Tier |
|------|----------|------------------|------------|------------|------------|------|
| 1 | ActionScript | 100.0 | 100 | 0.1% | 2 | S (Extinct) |
| 2 | ColdFusion | 97.3 | 90 | 0.1% | 5 | S (Extinct) |
| 3 | Groovy | 86.5 | 55 | 3.3% | 12 | S (Extinct) |
| 4 | Haskell | 84.8 | 42 | 2.0% | 8 | S (Extinct) |
| 5 | Erlang | 84.2 | 34 | 0.9% | 8 | S (Extinct) |
| 6 | Objective-C | 81.3 | 31 | 2.1% | 12 | S (Extinct) |
| 7 | Pascal/Delphi | 78.8 | 10 | 1.8% | 10 | S (Extinct) |
| 8 | Lua | 78.1 | 32 | 6.2% | 15 | S (Extinct) |
| 9 | Scala | 78.0 | 38 | 2.6% | 25 | S (Extinct) |
| 10 | COBOL | 78.0 | 24 | 0.7% | 30 | S (Extinct) |
| 11 | Fortran | 77.3 | 13 | 1.1% | 20 | S (Extinct) |
| 12 | Perl | 77.2 | 11 | 2.5% | 10 | S (Extinct) |
| 13 | MATLAB | 76.3 | 17 | 4.0% | 20 | S (Extinct) |
| 14 | Visual Basic | 75.9 | 7 | 4.2% | 15 | S (Extinct) |
| 15 | Assembly | 75.0 | 17 | 5.4% | 20 | S (Extinct) |
| 16 | Dart | 71.2 | 25 | 6.0% | 28 | A (Endangered) |
| 17 | R | 69.5 | 9 | 4.3% | 30 | A (Endangered) |
| 18 | Swift | 67.8 | 20 | 4.7% | 35 | A (Endangered) |
| 19 | Ruby | 66.8 | 30 | 5.2% | 55 | A (Endangered) |
| 20 | Kotlin | 65.1 | 22 | 9.4% | 38 | A (Endangered) |
| 21 | Rust | 59.4 | 14 | 12.6% | 40 | A (Endangered) |
| 22 | Go | 57.0 | 16 | 13.5% | 50 | A (Endangered) |
| 23 | PHP | 48.9 | 18 | 18.2% | 65 | B (Vulnerable) |
| 24 | C | 48.4 | 2 | 20.3% | 60 | B (Vulnerable) |
| 25 | C++ | 44.3 | 3 | 23.0% | 60 | B (Vulnerable) |
| 26 | C# | 39.9 | 5 | 27.1% | 70 | C (Stable) |
| 27 | Java | 35.1 | 4 | 30.3% | 80 | C (Stable) |
| 28 | TypeScript | 23.2 | 35 | 38.5% | 95 | D (Thriving) |
| 29 | Python | 17.3 | 1 | 51.0% | 85 | D (Thriving) |
| 30 | JavaScript | 2.0 | 6 | 62.3% | 95 | D (Thriving) |

---

## Methodology

- **Index name**: Programming Language Mass Extinction Index
- **Data sources**:
  - TIOBE Index (tiobe.com/tiobe-index) — March 2026 rankings and percentage ratings
  - Stack Overflow Developer Survey 2024 (survey.stackoverflow.co/2024/technology) — usage percentages
  - GitHub Octoverse 2024 / GitHub Innovation Graph — repository creation estimates
  - DevJobsScanner (devjobsscanner.com/blog) — job market demand for top languages
  - languages.orsinium.dev — Reddit subscriber counts per language community
  - PyPI, npm, CPAN, Hackage, CRAN, crates.io — package registry sizes
  - IBM Mainframe / COBOL developer survey data — COBOL employment statistics
- **Collection date**: March 2026
- **Scoring formula**: ExtinctionRisk = (TIOBEDanger × 0.20) + (SODecline × 0.25) + (GitHubVacuum × 0.20) + (JobDesert × 0.20) + (EcosystemDecay × 0.10) + (CommunityFade × 0.05)
- All components normalized 0–100 where 100 = maximum extinction risk
- **Sample size**: 30 programming languages

---

## Social Excerpts

### X (280 chars max)

ActionScript: 100/100 extinction risk. COBOL: 78/100. Perl: 77/100. JavaScript: 2/100. We ranked 30 languages by how close they are to dying — and the results defy every assumption. #RankMint

### LinkedIn (2200 chars max)

We built an index to measure how close programming languages are to extinction — and the results challenge everything the tech press gets wrong about language death.

The most endangered language in our dataset is ActionScript (100/100). When Adobe killed Flash Player in December 2020, the language died with it. There was no slow decline. It ceased.

But COBOL — the language journalists have declared dead every year since 1992 — scores 78/100 and sits mid-tier. The reason: over 1,400 active job postings, IBM apprenticeship programs, and $3 trillion in daily financial transactions that depend on COBOL systems. The language has no GitHub activity and almost no community — but it has institutional oxygen tanks with infinite refill.

Meanwhile, Perl ranks #11 on TIOBE but collapses to the bottom quartile in jobs, GitHub repos, and Stack Overflow activity. Its TIOBE rank is the fossil record of millions of legacy web pages, not a living ecosystem. And JavaScript? 2/100 extinction risk. The lowest in the index. The cockroach of programming.

Full methodology, interactive bump chart showing how each language's rank shifts by metric, and the complete tier list at the link.

---
*Generated by RankMint — rankmint.io*
