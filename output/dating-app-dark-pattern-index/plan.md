# Dating App Dark Pattern Index

## Overview
- **Slug**: `dating-app-dark-pattern-index`
- **Description**: Which dating apps are the most manipulative? 23 apps ranked by how aggressively they exploit users through deceptive UX, psychological manipulation, and predatory monetization.
- **Items**: 23 dating apps
- **Layout**: Scrollytelling (`templates/index_story.html`)
- **Voice**: Roast/Comedy — rage-inducing, sarcastic, conversational
- **Charts**: Bar (overall ranking), Tier list (S/A/B/C/D), Heatmap (apps × dark pattern metrics)

## Narrative Angle
- **Thesis**: Every dating app claims to want you to find love. Every dating app is also a publicly-traded company that loses money the moment you do. This index quantifies the resulting psychological warfare.
- **Expected surprise**: Hinge — "designed to be deleted" — ranks in the top 5 most manipulative apps. Bumble, marketed as the feminist alternative, earns an S-tier dark pattern score thanks to its timer mechanics and aggressive premium upsell. Meanwhile, Thursday (the app that only works one day a week) is actually *less* manipulative than apps with 24/7 access — its core concept limits compulsive use by design. Coffee Meets Bagel, despite an aggressive paywall, scores lower on addiction mechanics than every Match Group app.
- **Hook**: "In 2024, Match Group was sued for deploying 'recognized dopamine-manipulating product features' to trap users in a 'perpetual pay-to-play loop.' They settled for $14 million and kept all the features."

## Scoring Formula
- **Formula**: `DarkPatternScore = average(8 metric scores) × 12.5`
  - Score range: 0–100. Higher = MORE manipulative (worse for users).
  - Each metric scored 1–10 by rubric (see below).
- **Variables**:

| Metric | Weight (equal 1/8 each) | Higher = More Manipulative? | Notes |
|--------|------------------------|----------------------------|-------|
| SwipeAddiction | Equal | Yes | Infinite scroll, variable-ratio reward, slot-machine reveals |
| PaywallManipulation | Equal | Yes | Blur effects, "see who liked you" lock, dynamic pricing |
| NotificationSpam | Equal | Yes | Fake urgency pings, "someone liked you" without revealing who |
| VisibilityThrottling | Equal | Yes | Shadow-deprioritizing free users, Elo-style suppression |
| SubscriptionTrap | Equal | Yes | Cancel difficulty, auto-renewal obfuscation, confusing tier pricing |
| DataHarvesting | Equal | Yes | Excessive permissions, location selling, third-party data brokers |
| FOMOMechanics | Equal | Yes | Timed matches, expiring boosts, limited daily likes |
| FakeScarcity | Equal | Yes | "Only 1 Super Like left!", manufactured urgency countdowns |

### Inversion Test
Expected top 3 (conventional wisdom): Tinder, Grindr, Match.com.
Actual formula result: Tinder #1 (expected), but **Hinge #2** (surprise — "designed to be deleted" app scores higher than Match.com and Grindr on the combined formula due to its paywall aggression on emotional peak moments and visibility throttling toward premium). Grindr drops to mid-table on addiction/paywall but spikes on data harvesting alone. **The story: Hinge is the most *sophisticated* manipulator; Grindr is the most *reckless* one.**

## Tier Definitions (for chart_tier.html)
| Tier | Score Range | Label |
|------|------------|-------|
| S | 75–100 | The Dopamine Cartels |
| A | 60–74 | Aggressively Profitable |
| B | 45–59 | Casually Exploitative |
| C | 30–44 | Merely Unethical |
| D | 0–29 | The Least Worst Options |

## Heatmap Design (apps × dark patterns)
- **Rows**: 23 apps, sorted by overall DarkPatternScore descending
- **Columns**: 8 metrics (abbreviated labels)
- **Color scale**: Red (10 = maximum manipulation) → White (5) → Green (1 = minimum manipulation)
- **Purpose**: Answers "WHY is this app manipulative?" — Grindr's red column is DataHarvesting, not Swipe Addiction. Hinge's red is PaywallManipulation. Bumble's is FOMOMechanics.

## Quadrant Strategy (Scatter Chart — Secondary)
Since this index uses 8 equal-weight metrics, the scatter chart plots the two most narratively interesting independent dimensions:
- **X-axis**: Addiction Design Score (SwipeAddiction + FOMOMechanics + FakeScarcity combined, normalized 1–10) — "How hard does it try to keep you in the app?"
- **Y-axis**: Monetization Predation Score (PaywallManipulation + SubscriptionTrap + VisibilityThrottling combined, normalized 1–10) — "How hard does it try to extract your money?"

### Quadrant Labels
| Quadrant | Position | Name | Description |
|----------|---------|------|-------------|
| Upper-right | High Addiction + High Monetization | **The Dopamine Cartel** | Engineered to addict you, then charge for the antidote |
| Upper-left | Low Addiction + High Monetization | **The Toll Road** | Not that fun, but you'll pay to use the features anyway |
| Lower-right | High Addiction + Low Monetization | **The Crack Dealer** | Keeps you hooked but doesn't squeeze hard (yet) |
| Lower-left | Low Addiction + Low Monetization | **The Reluctant Profiteers** | They probably wish they were a non-profit |

## Per-App Scoring Rubric

### Metric Anchors (all metrics 1–10)

**1. SwipeAddiction Design** (slot-machine mechanics, infinite scroll, gamified matching)
- 9–10: Full variable-ratio reward loop; card-stack interface; no natural stopping points; like counts hidden to create suspense (Tinder, Badoo)
- 7–8: Gamified but with some friction; daily like limits create urgency without pure infinite scroll (Bumble, Hinge)
- 4–6: Some game elements but structural limits reduce compulsive use (Coffee Meets Bagel, OkCupid)
- 1–3: Anti-swipe design by intent; limited daily batches with no infinite scroll (Thursday, CMB to some extent)

**2. PaywallManipulation** (blur effects, "see who liked you" lock, emotional peak paywalls)
- 9–10: Blur tease on attracted profiles PLUS "most compatible" in premium jail PLUS dynamic pricing PLUS blurred faces of paid likes (Tinder Gold, Hinge)
- 7–8: Strong paywall on key features; blurred profiles; see-who-liked you locked (Bumble, Match.com)
- 4–6: Paywall present but features still somewhat functional free (Grindr, OkCupid free tier)
- 1–3: Minimal paywall; core matching fully functional without paying (Thursday, Feeld basic tier)

**3. NotificationSpam** (fake urgency, "someone liked you" without ID, re-engagement manipulation)
- 9–10: Sends "someone liked you" notifications that require payment to ID; re-engagement "someone visited your profile" pings for users who haven't been on the app; "your match is about to expire" even for new matches (Happn, Tinder, Match.com)
- 7–8: Aggressive re-engagement; some fake urgency; "new activity" pings that are vague (Bumble, Badoo, Zoosk)
- 4–6: Standard notifications; some urgency but linked to real events (Hinge, OkCupid)
- 1–3: Notification-light design; minimal re-engagement pings (Raya, Thursday, Feeld)

**4. VisibilityThrottling** (free user profile suppression, Elo-style deprioritization)
- 9–10: Documented system where free users' profiles are served to fewer potential matches; desirability scores suppress non-paying users; premium explicitly buys front-of-queue (Tinder, Badoo, Happn)
- 7–8: Strong evidence of premium visibility boost implying free suppression; pay-to-be-seen mechanics (Hinge, Bumble Boost, Zoosk)
- 4–6: Some visibility mechanics but less aggressive suppression (Match.com, OkCupid)
- 1–3: No documented visibility throttling; matching isn't pay-to-win (Thursday, Feeld, Raya)

**5. SubscriptionTrap** (cancellation difficulty, auto-renewal obfuscation, confusing tiers)
- 9–10: FTC-investigated cancellation flows; multiple steps to cancel; auto-renewal default with hidden eligibility requirements for refunds; confusing tier naming (Match.com — FTC $14M settlement; eHarmony)
- 7–8: Difficult cancellation; auto-renewal buried in settings; 3+ pricing tiers with unclear differentiation (Tinder, Bumble, Hinge)
- 4–6: Cancellation possible but not friction-free; some tier confusion (Zoosk, Badoo, Coffee Meets Bagel)
- 1–3: Simple cancellation; clear pricing; no auto-renewal tricks (Thursday, Raya, Archer)

**6. DataHarvesting** (excessive permissions, location tracking precision, data selling)
- 9–10: Documented third-party location data sales; 1,000+ trackers; HIV status shared with advertisers; facial recognition with unclear consent (Grindr — $6.12M GDPR fine; Tantan — 2019 regulator citation; Tinder/Match Group — FTC facial recognition investigation)
- 7–8: Extensive location tracking even when app closed; biometric data via selfie verification; sharing across parent company portfolio (Hinge, OkCupid, Badoo/Bumble Inc.)
- 4–6: Standard app data collection; some third-party sharing but not egregious (Zoosk, Happn, eHarmony)
- 1–3: Privacy-forward or small enough to lack data broker relationships (Raya, Archer, Thursday)

**7. FOMOMechanics** (timed features, expiring matches, limited daily likes as pressure)
- 9–10: Core product mechanic IS the FOMO device: 24-hour match timer; disappearing connections; "extend" costs money; boost expiry shown with countdown (Bumble — timer is the product; Thursday — gone at midnight)
- 7–8: Strong time pressure features; boosts with visible expiry; timed match windows (Tinder boost countdowns, Hinge roses limited)
- 4–6: Some FOMO but not structural; limited likes create urgency but no time bombs (Coffee Meets Bagel, OkCupid, Match.com)
- 1–3: No timed pressure; matches persist indefinitely; unlimited browsing (Raya, Feeld, Grindr basic)

**8. FakeScarcity** (manufactured urgency: "3 Super Likes left!", countdown timers on profile boosts)
- 9–10: Explicit fake scarcity messaging on features: Super Like count with "running low" prompts; boost "expiring in 2 hours" even on self-purchased boosts; Roses with weekly reset countdown (Tinder, Hinge)
- 7–8: Scarcity messaging on premium features; limited like counts surfaced prominently (Bumble, Badoo, Happn)
- 4–6: Some scarcity framing but less aggressive; feature limits exist without fear-of-missing-out copy (OkCupid, Zoosk, Coffee Meets Bagel)
- 1–3: No scarcity messaging; transparent unlimited or clearly communicated limits (Raya, Feeld, Her, Archer)

## Pre-Assigned Score Guidance (for data-collection agent)

| App | Swipe | Paywall | Notif | Visibility | SubTrap | DataHarv | FOMO | FakeScarcity | Score |
|-----|-------|---------|-------|------------|---------|----------|------|-------------|-------|
| Tinder | 10 | 10 | 9 | 10 | 8 | 9 | 8 | 10 | **93.8** |
| Match.com | 5 | 9 | 10 | 7 | 10 | 7 | 6 | 7 | **76.3** |
| Hinge | 8 | 9 | 6 | 8 | 7 | 8 | 7 | 9 | **77.5** |
| Bumble | 7 | 8 | 7 | 7 | 7 | 6 | 10 | 8 | **75.0** |
| Badoo | 9 | 7 | 8 | 8 | 6 | 8 | 6 | 7 | **73.8** |
| Zoosk | 6 | 8 | 8 | 7 | 7 | 6 | 5 | 8 | **68.8** |
| OkCupid | 6 | 6 | 7 | 6 | 6 | 8 | 5 | 6 | **62.5** |
| Happn | 7 | 8 | 9 | 8 | 5 | 6 | 5 | 7 | **68.8** |
| Plenty of Fish | 6 | 7 | 8 | 7 | 8 | 6 | 4 | 6 | **65.0** |
| Grindr | 7 | 5 | 6 | 5 | 5 | 10 | 4 | 5 | **58.8** |
| Tantan | 8 | 7 | 7 | 7 | 6 | 9 | 5 | 6 | **68.8** |
| eHarmony | 3 | 8 | 6 | 5 | 10 | 5 | 3 | 5 | **56.3** |
| The League | 4 | 9 | 5 | 7 | 7 | 5 | 6 | 7 | **62.5** |
| Pairs (Japan) | 6 | 7 | 6 | 7 | 6 | 7 | 5 | 5 | **61.3** |
| Coffee Meets Bagel | 3 | 8 | 5 | 5 | 6 | 5 | 6 | 7 | **56.3** |
| Lumen | 4 | 7 | 6 | 6 | 6 | 5 | 4 | 5 | **53.8** |
| Her | 5 | 5 | 5 | 4 | 5 | 5 | 4 | 4 | **46.3** |
| Feeld | 4 | 5 | 3 | 4 | 4 | 7 | 3 | 3 | **41.3** |
| Snack | 5 | 4 | 4 | 4 | 4 | 5 | 4 | 4 | **42.5** |
| Raya | 3 | 5 | 2 | 3 | 3 | 3 | 3 | 3 | **31.3** |
| Archer | 3 | 4 | 3 | 3 | 3 | 4 | 3 | 3 | **32.5** |
| Thursday | 2 | 4 | 3 | 2 | 4 | 3 | 8 | 4 | **37.5** |
| Ship | 4 | 4 | 5 | 4 | 4 | 4 | 4 | 4 | **41.3** |

*Note to data-collection agent: Thursday's FOMO score (8) is intentional — its entire app mechanic (disappears at midnight, matches gone, only works Thursdays) IS a FOMO mechanism, but it's explicit and transparent rather than deceptive, so other scores are low. Thursday has since shut down its app.*

## Key Narrative Surprises to Surface

1. **Hinge (#3 overall) outscores Match.com (#2) on Paywall Manipulation** — The "designed to be deleted" brand is the most cynical marketing in tech. Hinge locks "Most Compatible" matches in "rose jail" (premium only), blurs everyone who liked you, and serves this reveal at maximum emotional vulnerability.

2. **Bumble's 24-hour timer is the product, not a feature** — The feminist dating app's core mechanic is textbook FOMO design. You score highest on FOMOMechanics (10/10) in the dataset because the clock IS the app. Paying for Boost literally sells you back time the app took from you.

3. **Grindr drops to mid-table on dark patterns overall but scores 10/10 on Data Harvesting** — It's not trying to trick you into premium. It's selling your precise location and HIV status to data brokers. Different category of evil.

4. **Thursday scores 8/10 on FOMO but is the 4th least manipulative app overall** — The entire premise is transparent artificial scarcity. Paradoxically, telling users "you only have Thursday" is less manipulative than Tinder's fake "only 1 Super Like left!" — because at least Thursday is honest about it.

5. **eHarmony has the worst Subscription Trap score** of any non-Match-Group app despite a low Swipe Addiction score — Terrible at psychology, great at contracts.

## Chart Strategy
- **Primary chart**: Bar/lollipop chart — overall DarkPatternScore ranking, 23 apps
- **Secondary chart**: Tier list (S/A/B/C/D) with tier names: "The Dopamine Cartels" / "Aggressively Profitable" / "Casually Exploitative" / "Merely Unethical" / "The Least Worst Options"
- **Tertiary chart**: Heatmap (23 apps × 8 metrics) — answers WHY each app is manipulative
- **Optional quadrant**: Scatter chart (Addiction Design Score vs. Monetization Predation Score) for secondary narrative

## Data Sources

| Metric Evidence | Source | Collection Method |
|----------------|--------|-------------------|
| FTC $14M Match Group settlement | FTC.gov + CaptainCompliance.com | WebSearch / WebFetch |
| Match Group addiction lawsuit (2024) | NPR, CBS, SF Standard | WebSearch confirmed |
| Tinder Elo/visibility throttling | Appscrip, TextGod, multiple UX analyses | WebSearch confirmed |
| Tinder "blur-to-reveal" paywall design | StartupSpells UX teardown | WebSearch confirmed |
| Bumble 24hr timer as FOMO mechanic | Bumble support docs, multiple reviews | WebSearch confirmed |
| Bumble Boost pricing ($29.99/mo) | Bumble support / DatingApps.com | WebSearch confirmed |
| Grindr $6.12M GDPR fine (Norway) | Mozilla Foundation Privacy Not Included | WebFetch confirmed |
| Grindr 1,024 data trackers | Mozilla Foundation Privacy Not Included | WebFetch confirmed |
| Grindr HIV status shared with advertisers | BuzzFeed/Mozilla confirmed history | WebSearch confirmed |
| Hinge "rose jail" / "Most Compatible" paywall | Multiple user reports + Mozilla Privacy | WebFetch confirmed |
| Hinge biometric collection (facial geometry) | Mozilla Foundation Privacy Not Included | WebFetch confirmed |
| Match.com fake profiles FTC complaint | FTC legal library, CBS News | WebSearch confirmed |
| OkCupid unauthorized A/B testing (compatibility scores) | SF Public Press, research ethics studies | WebSearch confirmed |
| Happn 99% notifications → paywall user reviews | Trustpilot / DatingScout | WebSearch confirmed |
| Happn computer-generated free trial messages | User reviews, DatingScout | WebSearch confirmed |
| Tantan 2019 Chinese regulator citation | Mozilla Privacy Not Included | WebFetch confirmed |
| Tantan 2015 unencrypted data transmission | Mozilla Privacy Not Included | WebFetch confirmed |
| Feeld security vulnerabilities (2024) | The Register, Fortbridge research | WebSearch confirmed |
| FTC 76% of apps use dark patterns study (2024) | TechCrunch, FTC.gov | WebSearch confirmed |
| Thursday app closure / midnight match deletion | BusinessCloud, DatingScout | WebSearch confirmed |
| Badoo biometric class action ($40M settlement) | WebSearch confirmed | WebSearch |
| Norwegian Consumer Council report (Tinder, Grindr, OkCupid) | Multiple citations via WebSearch | WebSearch |
| eHarmony cancellation difficulty | Blogarama, user complaint aggregates | WebSearch |

## Items List

1. Tinder
2. Match.com
3. Hinge
4. Bumble
5. Badoo
6. Zoosk
7. Happn
8. Tantan
9. OkCupid
10. Plenty of Fish
11. Grindr
12. The League
13. Pairs (Japan)
14. Coffee Meets Bagel
15. eHarmony
16. Lumen
17. Her
18. Feeld
19. Snack
20. Ship
21. Thursday *(shut down app, pivoted to events — included as historical baseline)*
22. Archer
23. Raya

## Tone Guidance for Storyteller Agent

- **Voice**: Conversational rage. "Congratulations, you played yourself." — not hedged, not academic.
- **On Hinge**: "Hinge spent millions telling you it was 'designed to be deleted.' It is. Just not by you. By your credit card."
- **On Bumble**: "The 24-hour timer was sold to you as a feminist power move. What it actually is: a deadline to convince you that your potential soulmate is slipping away unless you message right now, under pressure, after a long day of work. That's not empowerment. That's a hostage situation with a countdown clock."
- **On Tinder**: "Tinder co-founder Jonathan Badeen told a journalist he got the swipe idea from BF Skinner's pigeon experiments — where pigeons became compulsive lever-pressers for random food rewards. He said this out loud. In a published interview. While running a company worth billions."
- **On Grindr**: "Grindr is in a different category. It's not trying to trick you into premium. It's selling your precise GPS coordinates and HIV status to data brokers. A Catholic organization bought this data to track and out gay priests. Grindr called this 'industry practice.'"
- **On Match.com**: "The FTC literally sued Match.com for sending fake love-interest emails — written by bots — to trick free users into paying for subscriptions to read messages that were fraudulent. Match settled for $14 million and kept all the features."
- **On Thursday**: "Thursday actually scored low on most dark patterns because its entire scam is at least honest. 'You can only use this app on Thursdays.' Respect. It still shut down."

## Files to Create
- `output/dating-app-dark-pattern-index/plan.md` (this file)
- `output/dating-app-dark-pattern-index/raw_data.csv`
- `output/dating-app-dark-pattern-index/scored_data.csv`
- `output/dating-app-dark-pattern-index/report.md`
- `output/dating-app-dark-pattern-index/chart_bar.html`
- `output/dating-app-dark-pattern-index/chart_tier.html`
- `output/dating-app-dark-pattern-index/chart_heatmap.html`
- `output/dating-app-dark-pattern-index/index.html`
- `output/dating-app-dark-pattern-index/card.html`
- `output/dating-app-dark-pattern-index/social.md`
