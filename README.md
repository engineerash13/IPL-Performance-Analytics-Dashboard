# IPL Performance Analytics Dashboard (2008–2020)

A Tableau-based case study analyzing 13 seasons of Indian Premier League (IPL) data using ball-by-ball and match-level datasets. The project explores team dominance, toss strategy impact, batting milestones (Orange Cap), and bowling performance (Purple Cap) through interactive visualizations and LOD calculations.

**Author:** Ashwin Suryawanshi | **Tool:** Tableau Desktop

---

## Files in This Repository

| File | Description |
|------|-------------|
| `IPL_CASE_STUDY.twbx` | Packaged Tableau workbook — 13 worksheets, 2 data sources, all visualizations |

---

## Tools & Technologies

- **Tableau Desktop** — worksheets, calculated fields, LOD expressions, donut charts, grouped fields
- **Data Sources:** IPL Matches 2008–2020, IPL Ball-by-Ball 2008–2020

---

## Datasets

Two connected datasets covering IPL seasons 2008 to 2020:

**IPL Matches Dataset**

| Column | Description |
|--------|-------------|
| `Id` | Unique match ID |
| `Date` | Match date |
| `City` | City where match was played |
| `Venue` | Stadium name |
| `Team1` / `Team2` | Competing teams |
| `Toss Winner` | Team that won the toss |
| `Toss Decision` | Bat or field |
| `Winner` | Match winner |
| `Result` | Win by runs or wickets |
| `Result Margin` | Margin of victory |
| `Player Of Match` | Best performer |
| `Umpire1` / `Umpire2` | Match officials |
| `Eliminator` | Eliminator match flag |
| `Method` | DLS method flag |
| `Neutral Venue` | Neutral ground flag |

**IPL Ball-by-Ball Dataset**

| Column | Description |
|--------|-------------|
| `Inning` | Innings number |
| `Over` / `Ball` | Over and ball number |
| `Batsman` / `Non Striker` | Batting pair |
| `Bowler` | Bowler name |
| `Batting Team` / `Bowling Team` | Teams per delivery |
| `Batsman Runs` | Runs scored off bat |
| `Extra Runs` / `Extras Type` | Wides, no-balls, etc. |
| `Total Runs` | Total runs on delivery |
| `Is Wicket` | Wicket flag (0/1) |
| `Dismissal Kind` | Caught, bowled, LBW, etc. |
| `Player Dismissed` | Dismissed batsman |
| `Fielder` | Fielder involved in dismissal |
| `Non Boundary` | Non-boundary delivery flag |

---

## Worksheets (13 total)

| Sheet | Analysis | Key Fields |
|-------|----------|------------|
| **IPL WINNER BY MANUAL CALCULATION** | Seasons won per team — manual calculated field | Winner, Date (Year) |
| **IPL WINNER BY FIXED LOD** | Seasons won per team — LOD FIXED expression | Winner, Calculation2 (FIXED DATE) |
| **IPL WINNER BY FIXED LOD (2)** | Alternative LOD approach for title count | Winner, Date |
| **MATCHES WON AS PER TOSS** | Count of matches won by toss winner vs non-toss winner | Winner (group), Toss Decision, Count of Winner |
| **% WINNING AS PER TOSS** | Win percentage when toss is won — field vs bat | Toss Decision, Winner, Date |
| **DONUT CHART** | Toss decision split (bat vs field) as a donut chart | AVG(0) calculated fields, Toss Decision |
| **ORANGE CAP** | Top run-scorers per season (Orange Cap winners) | Batsman, Batsman Runs, Date |
| **ORANGE CAP (2)** | Alternative view of season-wise batting leaders | Batsman, Batsman Runs, Date |
| **PURPLE CAP** | Top wicket-takers per season (Purple Cap winners) | Bowler, Is Wicket, Dismissal Kind, Date |
| **PURPLE CAP (2)** | Alternative view of season-wise bowling leaders | Bowler, Is Wicket, Dismissal Kind, Date |
| **4s PER SEASON** | Season-wise boundary (4s) count | Batsman Runs, Date |
| **6s PER SEASON** | Season-wise sixes count | Batsman Runs, Date |
| **Sheet 13** | Exploratory / working sheet | — |

---

## Tableau Techniques Used

| Technique | Where Used |
|-----------|------------|
| **LOD FIXED expression** | IPL Winner by Fixed LOD — count titles per team independent of view filters |
| **Manual calculated field** | IPL Winner by Manual Calculation — custom title count logic |
| **Grouped field** | Matches Won as Per Toss — Winner (group) to classify toss winner vs loser |
| **Donut chart** | Toss decision breakdown — dual-axis AVG(0) technique |
| **Date truncation (Year)** | Season-level analysis across all time-series charts |
| **Filtering by Batsman Runs** | 4s (=4) and 6s (=6) filtered from ball-by-ball data |
| **Dismissal Kind filter** | Purple Cap — isolates genuine wickets from ball-by-ball data |

---

## Key Insights

- **Mumbai Indians** are the most successful franchise across 2008–2020
- **Toss advantage** — teams winning the toss and choosing to field win more frequently
- **Peak scoring seasons** — 6s and 4s counts reveal which seasons had the most aggressive batting
- **Orange Cap** — top run-scorer per season identified using Batsman Runs aggregated by year
- **Purple Cap** — top wicket-taker per season using Is Wicket flag and Dismissal Kind filter
- **Toss decision trend** — majority of toss winners opt to field, shown clearly in the donut chart

---

## Project Workflow

1. Connected two data sources — Matches and Ball-by-Ball datasets
2. Built season-level team title analysis using both manual and LOD FIXED approaches
3. Analyzed toss impact — matches won, win %, and bat vs field decision distribution
4. Identified Orange Cap (top batsmen) and Purple Cap (top bowlers) per season
5. Tracked boundary trends (4s and 6s) season-by-season
6. Packaged all worksheets into a single `.twbx` file

---

## Topics

`tableau` `ipl` `cricket` `data-analysis` `sports-analytics` `lod-expressions` `data-visualization` `eda`
