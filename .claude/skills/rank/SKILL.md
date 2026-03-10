---
name: rank
description: Ranking content generation pipeline. Creates data-driven ranking reports with interactive charts from any topic.
disable-model-invocation: true
argument-hint: "[topic]"
---

# Ranking Content Pipeline

Given a topic, research it, collect data, score items, and generate a narrative-driven ranking report with interactive charts.

## Usage

```
/rank <topic>
```

Examples:
- `/rank Netflix Labor Index`
- `/rank Programming Language Popularity`
- `/rank Zombie Survival City Ranking`

## Pipeline

Run 5 steps sequentially. After each step, verify required output files exist.

### Step 1: Research & Design

Launch the `research-and-design` agent.

**Prompt:**
```
Topic: "$ARGUMENTS"

Research this topic and design an original ranking index.
Save the result to output/<slug>/plan.md.
The plan MUST include "## Narrative Angle", "## Chart Strategy" (with recommended chart types from: bar, scatter, radar, tier, race, heatmap), and "## Data Sources" sections.
```

**Verification:** `output/<slug>/plan.md` exists AND contains `## Narrative Angle` and `## Chart Strategy`

### Step 2: Data Collection

Launch the `data-collector` agent.

**Prompt:**
```
Read output/<slug>/plan.md and collect data for every item listed.

PRIMARY METHOD: Use WebFetch to fetch pages and extract data in-context.
Write the collected data directly to output/<slug>/raw_data.csv using the Write tool.
Only write a Python collection script as a FALLBACK if WebFetch cannot handle the data sources.

Result must be saved to output/<slug>/raw_data.csv with at least 15 rows and at least 2 numeric columns.
```

**Verification:** `output/<slug>/raw_data.csv` exists, ≥15 rows, ≥2 numeric columns

### Step 3: Inline Scoring

Score the data directly in-context (no separate agent needed).

1. Read `output/<slug>/plan.md` to get the scoring formula
2. Read `output/<slug>/raw_data.csv` to get the raw data
3. Apply the formula: normalize each metric to 0-100, apply weights, compute final score
4. Add `rank` and `score` columns (score on 0-100 scale)
5. Sort by score descending
6. Write result to `output/<slug>/scored_data.csv` using the Write tool

**Inversion test:** Would the average person guess the top 3? If yes, adjust the formula weights to surface more surprising results.

**Verification:** `output/<slug>/scored_data.csv` exists, has `rank` and `score` columns, scores in 0-100 range

### Step 4: Storytelling

Launch the `storyteller` agent.

**Prompt:**
```
Read output/<slug>/plan.md and output/<slug>/scored_data.csv, then:

1. Create interactive chart(s) as self-contained HTML files using ECharts CDN.
   Reference templates in templates/ directory (chart_bar.html, chart_scatter.html, chart_radar.html, chart_tier.html, chart_race.html, chart_heatmap.html).
   Choose 2-3 chart types based on the data and plan.md recommendations.
   Write chart HTML directly to output/<slug>/chart.html (primary) and additional chart files.
   NO Python scripts — just HTML files written via the Write tool.
   All charts must have OG meta tags and RankMint watermark.
2. Write output/<slug>/report.md following the narrative structure in templates/report_structure.md.
   The report must be narrative-first — NO table in the opening. Tables go at the bottom.
   Include Social Excerpts section (Twitter 280 chars + LinkedIn 2200 chars).
   Link to chart.html and other chart files in the report.
3. Write output/<slug>/index.html — landing page referencing templates/landing.html.
   Must include: OG meta tags, hero with counter animation, surprise callout, inline chart,
   taxonomy cards, Find Yourself dropdown with chart highlight, full sortable table, share bar.
4. Write output/<slug>/card.html — social card (1200x630) referencing templates/card.html.
   Must include: index name, hook, top 3 items with medals, RankMint watermark.
5. Write output/<slug>/social.md — Twitter (280 chars) + LinkedIn (2200 chars) excerpts.
6. Write output/<slug>/newsletter.md — 500-word summary with "View interactive version" CTA.
```

**Verification:**
- `output/<slug>/report.md` exists + report does NOT start with a table
- At least 2 `.html` chart files exist
- `output/<slug>/index.html` exists + contains `og:title` meta tag
- `output/<slug>/card.html` exists
- `output/<slug>/social.md` exists

### Step 5: Site Index

Regenerate the site-wide index page and RSS feed.

1. Scan all `output/*/plan.md` files to collect ranking metadata (title, hook, slug, date, #1 item)
2. Read `templates/site_index.html` and generate `output/index.html` with a card for each ranking
3. Read `templates/feed.xml` and generate `output/feed.xml` with an `<item>` for each ranking
4. Each card links to `<slug>/index.html`

**Verification:** `output/index.html` exists + `output/feed.xml` exists

## Completion

After all steps complete, summarize:

```
RankMint pipeline complete!

Output directory: output/<slug>/
  - plan.md (index design + narrative angle)
  - raw_data.csv (raw data, N rows)
  - scored_data.csv (scored data, N rows)
  - report.md (narrative ranking report)
  - chart.html + additional charts (interactive charts — open in browser)
  - index.html (landing page — open in browser)
  - card.html (social card — screenshot for OG image)
  - social.md (Twitter + LinkedIn excerpts)
  - newsletter.md (newsletter-ready export)

Site index: output/index.html
RSS feed: output/feed.xml
```

## Error Handling

- Agent failure: report error to user, offer to retry from that step
- Insufficient data: if row count < 15, ask data-collector to try alternative sources
- Verification failure: re-run the failing step
