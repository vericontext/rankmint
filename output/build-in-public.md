# RankMint — Build in Public: X Post Playbook

## Strategy

- **Week 1**: System reveal + best tier lists (hook the AI/dev crowd)
- **Week 2**: Individual rankings with controversy hooks (hook niche communities)
- **Rule**: NEVER post a link as the main content. Image first, link in reply.
- **Hashtags**: #BuildInPublic #ClaudeCode #AI (only on system posts, not ranking posts)

---

## WEEK 1: System Reveal (AI/Dev Audience)

### Day 1 — The Hook (System Demo)

**Post:**
```
I built a system where I type one command and get a full data-driven ranking site.

"/rank Boss Fight Fairness Index"

→ researches the topic
→ collects real data
→ scores & ranks items
→ writes a narrative report
→ generates interactive charts
→ deploys a landing page

All automated. Zero Python. Just Claude Code + agents.

Here's what it produced:
```

**Images (2장 첨부):**
1. Claude Code 터미널에서 `/rank Boss Fight Fairness Index` 타이핑한 화면 스크린샷
2. `output/boss-fight-fairness-index/tier_preview.png`
→ X에서 이미지 2장 동시 첨부하면 자동으로 나란히 표시됨

**Reply (link):**
```
Live site: rankmint.io

8 rankings so far, all generated this way.

Building this in public — will share the system, the failures, and the lessons.
```

---

### Day 2 — Architecture Reveal

**Post:**
```
How my AI ranking factory works (no Python, no database):

1. Research agent → picks topic angle, finds data sources
2. Data collector agent → WebFetch, no scripts
3. Scoring → weighted formula, normalized 0-100
4. Storyteller agent → narrative report + interactive ECharts
5. Site generator → landing page + tier list + social cards

All orchestrated by one Claude Code skill file.
The entire "backend" is a markdown file.
```

**Image:** `.claude/skills/rank/SKILL.md` 파일을 VS Code나 에디터에서 열고 Step 1~5가 보이게 스크린샷

**Reply:**
```
The agents argue with each other sometimes.

The storyteller agent once put Bed of Chaos in B tier.
The scoring agent had it at 1.50/10.

I had to add a "tier list deduplication" rule after that bug.
```

---

### Day 3 — The Controversial Take

**Post:**
```
I ranked 30 game bosses by FAIRNESS, not difficulty.

Result: Malenia (Elden Ring) is A-tier fair.
Bed of Chaos (Dark Souls) is the worst designed boss in gaming history.

The hardest bosses are often NOT the most unfair.
Fairness is a design virtue independent of difficulty.
```

**Image:** boss-fight-fairness-index/tier_preview.png

**Reply:**
```
Metrics used:
- Telegraph clarity (do attacks have readable tells?)
- Recovery window (can you heal after mistakes?)
- Camera behavior (does the camera fight you?)
- Hitbox honesty (do hitboxes match animations?)
- RNG dependency (is it skill or luck?)

Full interactive breakdown: rankmint.io/boss-fight-fairness-index/
```

---

### Day 4 — Startup Graveyard (Tech Twitter bait)

**Post:**
```
I ranked 30 dead startups by how AVOIDABLE their death was.

S-tier "Hall of Shame":
- Juicero (6.25) — $120M for a juice bag squeezer
- Theranos (7.95) — fraud isn't a business model
- Quibi (7.66) — who asked for 10-min mobile-only shows?

The most painful one? Vine at D-tier.
Its death was almost unavoidable. Twitter killed it.
```

**Image:** startup-graveyard-index/tier_preview.png

**Reply:**
```
The "Avoidable Death Score" measures:
- Was the market real?
- Was the product real?
- Did they ignore obvious warnings?
- Was it fraud vs. honest failure?

Some failures deserve respect. Most don't.

Full breakdown: rankmint.io/startup-graveyard-index/
```

---

### Day 5 — Disney Villain CEO (Viral bait)

**Post:**
```
I evaluated 30 Disney villains as corporate CEOs.

Hades: Fortune 500 ready. Delegation skills, strategic patience, workforce management.

Gaston: 39.0. Peak middle management. All charisma, zero strategy.

The villain you'd actually want as your boss might surprise you.
```

**Image:** disney-villain-ceo-index/tier_preview.png

**Reply:**
```
7 leadership metrics:
- Strategic vision
- Resource management
- Delegation ability
- Crisis handling
- Team retention
- Long-term planning
- Adaptability

Ursula scored higher than Scar. Think about that.

rankmint.io/disney-villain-ceo-index/
```

---

### Day 6 — Anime Sensei (Anime community)

**Post:**
```
I ranked 30 anime teachers by ACTUAL TEACHING COMPETENCE.

Koro-sensei: S-tier. Individualized curriculum, measurable student growth, genuine care.

Kakashi: C-tier. Late to class, reads porn during lessons, plays favorites.

Goku's teacher Roshi? D-tier. Enough said.
```

**Image:** anime-sensei-competence-index/tier_preview.png

**Reply:**
```
This isn't "who's the coolest sensei."
This is "who would survive a parent-teacher conference."

Biscuit Krueger teaching Gon and Killua Nen?
Textbook scaffolded instruction. S-tier.

rankmint.io/anime-sensei-competence-index/
```

---

### Day 7 — K-Drama Binge Trap + Week Recap

**Post:**
```
Week 1 of building an AI ranking factory in public:

→ 8 data-driven rankings live
→ 1 command generates everything
→ 0 lines of Python
→ ~2,400 lines of agent instructions
→ Countless tier list arguments with Claude

Most popular so far: Disney Villain CEOs
Most controversial: Boss Fight Fairness

Next week: opening the system for anyone to try.
```

**Images (4장 첨부 — X 최대):**
`boss-fight`, `startup-graveyard`, `disney-villain-ceo`, `anime-sensei`의 `tier_preview.png` 4장
→ X가 자동으로 2x2 그리드로 표시함. 나머지 2개는 리플라이에 추가.

---

## WEEK 2: Niche Community Posts

### K-Drama Binge Trap (K-Drama community)

**Post:**
```
Data says Crash Landing on You is the #1 binge trap in K-Drama.

"I'll just watch one episode" → 4am, crying, texting your ex.

Squid Game is S-tier too but for different reasons.
Hospital Playlist at D-tier? It's a slow burn, not a trap.
```

**Image:** kdrama-binge-trap-index/tier_preview.png

**Reply:**
```
Binge Trap Score = cliffhanger density + emotional hooks + episode pacing + "one more episode" factor

The Glory at A-tier makes sense.
But Business Proposal beating Vincenzo? Fight me.

rankmint.io/kdrama-binge-trap-index/
```

---

### City Ramen Value (Food/Travel community)

**Post:**
```
I ranked 30 cities worldwide by ramen value.

Fukuoka #1. Not Tokyo.

Seoul (#6) beats New York (#17).
Portland (#11) is the best ramen city in the US.

LA at #13 is a crime. But the data doesn't lie.
```

**Image:** city-ramen-value-index/tier_preview.png

**Reply:**
```
City Ramen Value Index =
affordability + density + quality + variety + cultural depth

Tokyo has the best ramen, but Fukuoka's cost-to-quality ratio is unbeatable.

Sapporo at #5 purely on miso ramen dominance.

rankmint.io/city-ramen-value-index/
```

---

## Screenshot Guide

### What to capture for each post:

1. **Day 1 — 터미널 스크린샷:**
   - Claude Code에서 `/rank Boss Fight Fairness Index` 타이핑 → Cmd+Shift+4로 캡처
   - 팁: 실행 전 타이핑만 한 상태가 제일 깔끔함

2. **Day 2 — SKILL.md 스크린샷:**
   - VS Code에서 `.claude/skills/rank/SKILL.md` 열기
   - Step 1~5 파이프라인이 보이게 캡처

3. **Day 3~6 — 랭킹별 포스트:**
   - 각 `output/<slug>/tier_preview.png` 바로 업로드 (2x Retina 준비 완료)

4. **Day 7 — 회고:**
   - 4개 tier_preview.png를 X에 동시 첨부 (자동 2x2 그리드)

---

## Engagement Rules

1. **Reply to EVERY comment** in the first hour
2. **Quote RT hot takes** — "Malenia is fair?!" → "The data says so. Here's why:"
3. **Never be defensive** — embrace disagreement, it's free engagement
4. **Post between 9-11am EST** (peak X engagement for tech/gaming)
5. **Pin the Day 1 system post** to your profile

---

## Community Targets

| Ranking | Communities to share in |
|---------|----------------------|
| Boss Fight | Soulsborne, gaming, game design |
| Anime Sensei | anime, manga, MyAnimeList |
| K-Drama Binge | kdrama, hallyu, Asian drama |
| Startup Graveyard | startups, VC, tech twitter |
| Disney Villain CEO | Disney fans, MBA twitter, leadership |
| City Ramen | food, travel, Japan, ramen |
| Global Nap | remote work, productivity, culture |
| Hangover Recovery | travel, nightlife, health |

---

## KPI Targets (Week 1)

- Impressions: 5,000+ (realistic from 25 followers if one post hits)
- Profile visits: 100+
- New followers: 20-50
- Site visits: 50+
- Best case: one post gets 50+ likes → algorithm boost → 50K+ impressions
