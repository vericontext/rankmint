# Disney Villain CEO Index

## Overview
- **Slug**: `disney-villain-ceo-index`
- **Description**: A boardroom fitness ranking of 30 Disney and Pixar villains scored across 7 CEO-relevant competencies — because the real question isn't whether they're evil, it's whether they could run a Fortune 500.
- **Items**: 30 villains from Disney animated films and Pixar (1937–2024)

---

## Narrative Angle

- **Thesis**: Corporate leadership literature has spent decades describing the traits of great CEOs — strategic vision, resource management, crisis resilience, charisma, innovation. Disney villains, inadvertently, are a stress-test laboratory for exactly those traits. Some of the most iconic "scary" villains are actually terrible executives. Some of the comedic sidekick-villains are frighteningly competent ones.

- **Expected surprise**: The average viewer would name Maleficent, Jafar, or the Evil Queen as top-ranked villains. In practice, **Hades** (who administers an entire afterlife bureaucracy with finite resources and impossible KPIs) and **Syndrome** (a self-funded R&D founder who built a private army from scratch) score higher on the formula. Meanwhile **Gaston** — widely beloved as a confident alpha — ranks as a Populist Demagogue: great at rallying crowds, zero capacity for long-term planning. And **Maleficent** falls mid-tier because rage-cursing an infant over a party invite is a catastrophic overreaction that tanks her Crisis Management and Emotional Intelligence scores.

- **Hook**: *Your company's next board seat might be best filled by the god of the dead — and the data backs it up.*

---

## Scoring Formula

### Formula
```
CEO Score = (SV × 0.25) + (RM × 0.20) + (CP × 0.15) + (CM × 0.15) + (IA × 0.12) + (EI × 0.08) + (RI_adj × 0.05)
```

Where:
- All raw scores are 0–10 (assigned by qualitative analysis of canonical film appearances)
- **RI_adj** (Ruthlessness Index, adjusted) = `10 − |raw_ruthlessness − 6|`
  - A raw score of 6 = optimal CEO ruthlessness (decisive but not PR-toxic) → RI_adj = 10
  - A raw score of 10 = sociopathic → RI_adj = 6
  - A raw score of 0 = pushover → RI_adj = 4
- Maximum possible CEO Score = 10.0

### Variables

| Metric | Code | Weight | Direction | Rationale |
|--------|------|--------|-----------|-----------|
| Strategic Vision | SV | 25% | Higher = better | Long-term planning, multi-step schemes, patience |
| Resource Management | RM | 20% | Higher = better | Managing minions, money, assets, infrastructure |
| Charisma & Persuasion | CP | 15% | Higher = better | Rallying followers, negotiating, manipulation |
| Crisis Management | CM | 15% | Higher = better | Composure, adaptation when plans fail |
| Innovation & Adaptability | IA | 12% | Higher = better | Creative problem-solving, tech/magic leverage |
| Emotional Intelligence | EI | 8% | Higher = better | Self-awareness, reading others, strategic empathy |
| Ruthlessness Index (adjusted) | RI_adj | 5% | Optimal at 6 | Moderate ruthlessness = decisive; extremes = liability |

### Scoring Rubric (for data-collector agent)

Each metric is scored 0–10 based on canonical film evidence only. Use these anchors:

**Strategic Vision (SV)**
- 9–10: Multi-year scheming with contingency plans (Scar, Syndrome)
- 6–8: Clear goal with coherent multi-step plan (Ursula, Hades)
- 3–5: Short-term reactive planning (Jafar — adapts well but plan was opportunistic)
- 0–2: No plan beyond "get the thing" (Captain Hook, LeFou-level)

**Resource Management (RM)**
- 9–10: Commands vast infrastructure, manages large workforce (Hades, Ursula)
- 6–8: Maintains loyal capable lieutenants, controls meaningful assets (Scar, Facilier)
- 3–5: Has minions but loses control frequently (Yzma, Evil Queen)
- 0–2: Solo operator with no meaningful resource base (Gaston, Syndrome early stage)

**Charisma & Persuasion (CP)**
- 9–10: Effortlessly commands rooms, manipulates multiple parties simultaneously (Gaston, Ursula)
- 6–8: Compelling but relies on fear or deception (Scar, Facilier)
- 3–5: Has influence but limited genuine appeal (Jafar, Maleficent)
- 0–2: Alienates followers, cannot persuade without coercion (Yzma, Ratigan when unmasked)

**Crisis Management (CM)**
- 9–10: Calm, pivots strategy quickly, never loses the thread (Hades, Facilier)
- 6–8: Adapts with visible effort, minor panic spikes (Jafar, Ursula)
- 3–5: Loses composure regularly but recovers (Scar, Evil Queen)
- 0–2: Full meltdown at first setback (Prince John, Hook, Maleficent)

**Innovation & Adaptability (IA)**
- 9–10: Invents novel solutions, redefines the problem space (Syndrome, Hades)
- 6–8: Uses available tools creatively (Ursula, Yzma)
- 3–5: Conventional methods with minor creative tweaks (Scar, Gaston)
- 0–2: Rigid single-solution thinker (Evil Queen, Captain Hook)

**Emotional Intelligence (EI)**
- 9–10: Master reader of others; exploits emotional needs surgically (Mother Gothel, Ursula)
- 6–8: Understands others well enough to manipulate effectively (Hades, Facilier)
- 3–5: Some self-awareness, inconsistent empathy mapping (Scar, Syndrome)
- 0–2: Emotionally reactive; projects; cannot read the room (Maleficent, Prince John)

**Raw Ruthlessness (before adjustment)**
- 10: Will murder anyone including allies without hesitation (Maleficent, Scar)
- 7–9: Eliminates obstacles with minimal sentiment (Syndrome, Ursula)
- 5–6: Ruthless when necessary, restrained otherwise — CEO-optimal (Hades, Facilier)
- 3–4: Threatens more than acts; hesitates at the last moment (Jafar, Gaston)
- 0–2: Mostly bark, rarely bites (Prince John, Yzma)

---

## Villains List (30 items)

These 30 villains are drawn from Disney animated canon and Pixar. Each must be scored individually by the data-collector agent using the rubric above.

1. Scar — *The Lion King* (1994)
2. Maleficent — *Sleeping Beauty* (1959)
3. Ursula — *The Little Mermaid* (1989)
4. Hades — *Hercules* (1997)
5. Jafar — *Aladdin* (1992)
6. Gaston — *Beauty and the Beast* (1991)
7. Syndrome — *The Incredibles* (2004), Pixar
8. Yzma — *The Emperor's New Groove* (2000)
9. Captain Hook — *Peter Pan* (1953)
10. Evil Queen — *Snow White and the Seven Dwarfs* (1937)
11. Mother Gothel — *Tangled* (2010)
12. Claude Frollo — *The Hunchback of Notre Dame* (1996)
13. Cruella de Vil — *101 Dalmatians* (1961)
14. Dr. Facilier (Shadow Man) — *The Princess and the Frog* (2009)
15. Prince John — *Robin Hood* (1973)
16. Ratigan — *The Great Mouse Detective* (1986)
17. Shan Yu — *Mulan* (1998)
18. Governor Ratcliffe — *Pocahontas* (1995)
19. Hans — *Frozen* (2013)
20. King Candy (Turbo) — *Wreck-It Ralph* (2012)
21. Bellwether — *Zootopia* (2016)
18. Tamatoa — *Moana* (2016)
23. Charles Muntz — *Up* (2009), Pixar
24. Lotso — *Toy Story 3* (2010), Pixar
25. AUTO — *WALL-E* (2008), Pixar
26. Stinky Pete — *Toy Story 2* (1999), Pixar
27. Bill Sykes — *Oliver & Company* (1988)
28. Percival McLeach — *The Rescuers Down Under* (1990)
29. The Horned King — *The Black Cauldron* (1985)
30. Alameda Slim — *Home on the Range* (2004)

---

## Chart Strategy

Four charts are recommended. The storyteller agent should produce all four as separate HTML files.

### Primary: Tier List (`chart_tier.html`)
- **Type**: `tier` — S / A / B / C / D tier rows with villain name cards
- **Why**: This is the single most shareable format for pop culture rankings. "Scar is A-tier, fight me" generates engagement loops.
- **Tier thresholds** (based on CEO Score out of 10):
  - S-Tier: Score ≥ 8.0 — "Fortune 500 Ready"
  - A-Tier: 7.0–7.99 — "Strong C-Suite Material"
  - B-Tier: 6.0–6.99 — "Middle Management Overachiever"
  - C-Tier: 5.0–5.99 — "Promising Hire, Needs Coaching"
  - D-Tier: < 5.0 — "Please Don't Give This Villain a Budget"

### Secondary: Bar Chart (`chart_bar.html`)
- **Type**: `bar` — horizontal lollipop/bar, all 30 villains sorted by CEO Score descending
- **Why**: Gives the definitive ranked list — the anchor chart for the report
- **Color**: Use villain-appropriate color gradient (deep purples/reds at top, fading toward grey at bottom)
- **Tooltip**: Show all 7 sub-scores on hover

### Tertiary: Radar Chart (`chart_radar.html`)
- **Type**: `radar` — 7-axis spider/radar with dropdown to compare any two villains
- **Why**: The head-to-head format is the most argumentative — "Hades vs. Scar in a boardroom" is a conversation starter
- **Axes**: Strategic Vision, Resource Management, Charisma, Crisis Management, Innovation, Emotional Intelligence, Ruthlessness (adjusted)
- **Default comparison**: Hades vs. Maleficent (the biggest surprise pairing)

### Quaternary: Heatmap (`chart_heatmap.html`)
- **Type**: `heatmap` — rows = 30 villains (sorted by CEO Score), columns = 7 metrics
- **Why**: Reveals the full data texture — which metric has the widest variance? Who is one-dimensional vs. well-rounded?
- **Color scale**: 0 = light grey, 10 = deep crimson
- **Bonus**: Color the RI_adj column differently (gold scale) since it's an inverted metric

### Scatter (bonus, embedded in report): Strategic Vision × Charisma Quadrant
- **Type**: `scatter` — X-axis = Strategic Vision, Y-axis = Charisma & Persuasion
- **Bubble size**: CEO Score overall
- **Quadrant labels**:
  - Upper-right (SV ≥ 6, CP ≥ 6): **"Board Room Sharks"** — the full package threat
  - Upper-left (SV < 6, CP ≥ 6): **"Populist Demagogues"** — crowd-pleasers with no long game (Gaston lives here)
  - Lower-right (SV ≥ 6, CP < 6): **"Evil Geniuses"** — frighteningly effective behind the scenes, terrible at town halls
  - Lower-left (SV < 6, CP < 6): **"Middle Management Material"** — not dangerous enough to be interesting

---

## Narrative Categories (for report taxonomy)

These replace the quadrant labels in the written report's "Taxonomy" section:

| Category | Villains (anticipated) | Trait |
|----------|----------------------|-------|
| **The C-Suite Predators** | Hades, Scar, Syndrome, Ursula | Scored ≥ 7.5 — the genuinely dangerous executives |
| **The Charming Frauds** | Gaston, Hans, Bellwether | High charisma, strategic vacuum — every startup has one |
| **The Micromanagers from Hell** | Frollo, Cruella, Yzma | Total conviction, catastrophic execution |
| **The PowerPoint Villains** | Prince John, Hook, Ratcliffe | Endless grievance, no follow-through — they'd survive one board meeting |

---

## Data Sources

All scores are assigned by qualitative analysis of each villain's canonical Disney/Pixar film appearances. No external data collection is required. The data-collector agent reads the rubric above and assigns scores 0–10 for each villain on each metric, then computes CEO Score using the formula.

| Metric | Source | Collection Method |
|--------|--------|-------------------|
| Strategic Vision (0–10) | Villain's film screenplay / plot behavior | Qualitative rubric (see above) |
| Resource Management (0–10) | Villain's minion count, assets, infrastructure shown in film | Qualitative rubric |
| Charisma & Persuasion (0–10) | Villain's on-screen influence over other characters | Qualitative rubric |
| Crisis Management (0–10) | Villain's response to mid-film setbacks | Qualitative rubric |
| Innovation & Adaptability (0–10) | Novel solutions, use of magic/technology, pivots | Qualitative rubric |
| Emotional Intelligence (0–10) | Demonstrated ability to read and exploit others' emotions | Qualitative rubric |
| Raw Ruthlessness (0–10) | Willingness to harm; transformed to RI_adj in formula | Qualitative rubric |
| CEO Score (computed) | — | Formula: (SV×0.25)+(RM×0.20)+(CP×0.15)+(CM×0.15)+(IA×0.12)+(EI×0.08)+(RI_adj×0.05) |

Reference films available via Disney+ or standard home video. No web scraping required. All scoring is done in-context by the data-collector agent.

---

## Inversion Test

**Would the average person guess the top 3?**

Most people would predict: Maleficent #1, Jafar #2, Scar #3.

Expected actual top 3 from the formula:
1. **Hades** — maxes Resource Management (runs a bureaucratic underworld), strong Crisis Management (weathers constant setbacks with dark humor), and hits the CEO-optimal ruthlessness band. Maleficent fans will riot.
2. **Scar** — genuinely multi-year strategic patience earns him the SV crown, but ego-driven CM collapses get him docked.
3. **Syndrome / Ursula** — both score 9–10 on Innovation (Syndrome) and EI (Ursula); the formula rewards well-rounded profiles.

**Maleficent's fatal flaw**: A single emotional outburst (cursing an infant over a snubbed party invitation) is disqualifying evidence for Crisis Management (score: 2) and Emotional Intelligence (score: 2). High Ruthlessness raw score also pushes RI_adj down. She's a C-Tier CEO by the numbers — a finding that will generate immediate, passionate disagreement, which is exactly the point.

---

## Social Hook

**Twitter/X**: "We ranked 30 Disney villains as Fortune 500 CEOs using 7 leadership metrics. Hades beats Maleficent. Gaston is a Populist Demagogue. Syndrome would've been a unicorn founder. The data is not on your side. #DisneyVillainCEO #RankMint"

**LinkedIn hook**: "The leadership consulting industry could learn something from the god of the dead."
