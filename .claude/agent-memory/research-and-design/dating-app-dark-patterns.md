# Dating App Dark Pattern Index — Research Notes

## Confirmed Accessible Data Sources
- `mozillafoundation.org/en/privacynotincluded/hinge/` — accessible; returns full privacy analysis with specific violations
- `mozillafoundation.org/en/privacynotincluded/grindr/` — accessible; returns 1,024 trackers stat, GDPR fine, HIV status sharing
- `mozillafoundation.org/en/privacynotincluded/tantan/` — accessible; Chinese regulator 2019 cite, biometric concerns
- `essyknopf.com/dark-patterns-in-gay-apps/` — accessible; detailed dark pattern breakdown for Grindr-style apps
- `captaincompliance.com` — accessible; Match Group $14M FTC settlement breakdown
- `therecord.media` — accessible for privacy/FTC coverage

## Blocked Sources
- `uxplanet.org` — returns 403
- `adapty.io/blog` — returns JS-only, no article content
- `needleinthehaystack.substack.com` — returns 404

## Confirmed Key Facts (cite-ready)
- Match Group $14M FTC settlement (2025 final order): fake love-interest emails from flagged fraudulent accounts used to drive paid subscriptions; must simplify cancellation
- Match Group 2024 class action (Valentine's Day filing): "recognized dopamine-manipulating product features"; "perpetual pay-to-play loop"; Hinge "designed to be deleted" vs. actual business model cited
- Tinder co-founder Jonathan Badeen: publicly stated swipe mechanic inspired by BF Skinner pigeon experiments (variable-ratio reward)
- Grindr: $6.12M Norwegian GDPR fine upheld 2023; Wall Street Journal 2022 location data sales expose; BuzzFeed 2018 HIV status sharing; 1,024 trackers per Mozilla; Catholic organization bought Grindr location data to track gay priests
- OkCupid: admitted running experiment telling bad-match users they were 90% compatible — users sent more messages to fake matches; no informed consent
- Badoo: $40M biometric class action settlement (Bumble Inc.)
- Feeld: March 2024 Fortbridge research found API flaw let users give themselves premium features without paying; real-time location leaked publicly; 6-month disclosure gap before patch
- FTC 2024 global sweep (642 apps): 76% used at least one dark pattern; 81% couldn't disable auto-renewal; 70% gave no cancellation info
- Thursday: shut down app, pivoted to events; subscription auto-renewed; matches deleted at midnight; opened once/week
- Bumble Boost pricing: $29.99/month, $59.99/3mo, $99.99/6mo (2024)
- Bumble timer: 24hr for women to message, paid Boost lets you extend — literally selling back time the free mechanic took

## Scoring Notes (confirmed per research)
- Tinder: highest overall (93.8) — all 8 metrics in top range; fake scarcity + blur paywall + Elo throttling all documented
- Hinge: 77.5 — surprise #3 because paywall manipulation at emotional peak moments (blurred likers, "rose jail") + Match Group data practices + visibility throttling
- Match.com: 76.3 — highest SubscriptionTrap (10/10) and NotificationSpam (10/10); FTC settlement evidence
- Bumble: 75.0 — highest FOMOMechanics (10/10); timer IS the dark pattern; sold premium = selling you back the time they took
- Grindr: mid-table 58.8 — low Swipe/Paywall/FOMO; DataHarvesting 10/10 is its unique danger signature
- eHarmony: 56.3 — low addiction metrics, very high SubscriptionTrap; difficult cancellation is its defining dark pattern

## Inversion Pattern for This Index
- The "obvious" ranking (Tinder > Grindr > Match) is WRONG on the combined score
- Hinge's brand makes it the most ironic #3 — "designed to be deleted" app more manipulative than Grindr
- Thursday's core concept IS FOMO but it's transparent FOMO, not deceptive FOMO → scores low overall despite high FOMOMechanics
- Data Harvesting as a standalone axis separates Grindr from the addiction-focused manipulators

## Quadrant Naming (Addiction vs. Monetization Predation)
- Upper-right (high addiction + high monetization): "The Dopamine Cartel" — Tinder, Hinge, Match.com, Bumble
- Upper-left (low addiction + high monetization): "The Toll Road" — eHarmony, The League, Coffee Meets Bagel
- Lower-right (high addiction + low monetization): "The Crack Dealer" — Badoo, Tantan, Happn
- Lower-left (low addiction + low monetization): "The Reluctant Profiteers" — Raya, Archer, Feeld, Thursday
