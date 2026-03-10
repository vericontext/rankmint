# RankMint - Automated Ranking Content Factory

## Project Rules

### Data Integrity
- **Never fabricate data.** All numbers must come from actual collection by scripts or WebFetch
- Intermediate data must be saved as CSV (raw_data.csv → scored_data.csv)
- Data sources must be cited in report.md

### Data Source Priority
1. Official APIs (REST, GraphQL)
2. Wikipedia tables
3. Public datasets (World Bank, OECD, etc.)
4. Web scraping (respect robots.txt)

### Data Collection Strategy (WebFetch-first)
1. **Primary**: WebFetch tool — fetch pages directly, parse in-context. No Python script needed
2. **Fallback**: `requests + BeautifulSoup` Python script (only when WebFetch fails or data requires complex multi-page crawling)
3. **Last resort**: Playwright MCP (JS-rendered pages only)
4. Playwright is for page exploration/structure discovery; final data extraction should use WebFetch or Python

### No Python Policy
- **Python is NOT used in this project.** No .py scripts for collection, scoring, or charts
- Data collection: WebFetch + in-context processing
- Scoring: inline by Claude Code agents
- Charts: interactive HTML files using ECharts (CDN), written directly via Write tool
- All chart templates are in `templates/` as `.html` files

### Output Rules
- All output goes to `output/<topic-slug>/` directory
- topic-slug: lowercase English, hyphen-separated (e.g., `netflix-labor-index`)
- Required output files: `plan.md`, `raw_data.csv`, `scored_data.csv`, `report.md`, `chart.html`, `index.html`, `card.html`, `social.md`
- Site-wide files: `output/index.html` (site index), `output/feed.xml` (RSS)

### CSV Rules
- UTF-8 without BOM
- First row is header
- No comma formatting in numeric columns
- Missing values as empty string

### Storytelling Rules
- Reports are **narrative-first**: open with a hook and thesis, NOT a table
- Tables go at the bottom, not the top
- Group items into meaningful categories with creative names (e.g., "Caffeine Zombies" vs "Nordic Chill")
- Every report must surface at least one counter-intuitive finding
- Use `templates/report_structure.md` as the report template

### Layout Rules
- `.container` must use `max-width: 1200px; margin: 0 auto; padding: 0 20px;`
- **CRITICAL**: ALL content sections (`.chart-section`, `.taxonomy`, `.full-table`, `.find-yourself`, `.methodology`, `.findings`, etc.) MUST use `margin: Npx auto` — NEVER `margin: Npx 0`. Using `0` instead of `auto` breaks center alignment on desktop viewports.
- Landing pages (`index.html`) must have a home nav bar: `← RankMint Home` linking to `../`
- Chart pages (`chart*.html`) must have back nav: `← RankMint Home` (→ `../`) + `← Back to Rankings` (→ `index.html`)

### Chart Rules
- All charts are **interactive HTML** using Apache ECharts via CDN
- Chart HTML files are self-contained (single file, no external dependencies except CDN)
- 6 chart templates available in `templates/`:
  - `chart_bar.html` — bar/lollipop ranking (always used as primary)
  - `chart_scatter.html` — scatter/quadrant analysis
  - `chart_radar.html` — radar/spider multi-dimensional comparison
  - `chart_tier.html` — S/A/B/C/D tier list (most viral on SNS)
  - `chart_race.html` — weight slider with animated re-ranking
  - `chart_heatmap.html` — items × metrics grid
- Charts must include: hover tooltips, zoom, responsive sizing, animation on load
- All charts must have OG/Twitter Card meta tags and "RankMint" watermark
- Embed CSV data directly as JSON in the HTML file
- Use 6 named palettes: `gold-steel`, `sunset`, `forest`, `ocean`, `berry`, `ember`
- Include `<!-- __ANALYTICS_SNIPPET__ -->` placeholder in all HTML files
- The storyteller agent picks 2-3 chart types for each topic from the template gallery
