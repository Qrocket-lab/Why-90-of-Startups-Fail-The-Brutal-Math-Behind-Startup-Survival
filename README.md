# Mission L-01: Sector Deep Dive & Survival Analysis

**Telemetry Pillar Theme:** Aligning internal goals with external reality (Market Intelligence).

## Executive Summary
Mission L-01 analyzes global startup outcomes using a high-volume funding dataset (66,368 organizations) to identify where market conditions support long-term survival. The project combines survival logic, sector segmentation, and funding diagnostics to translate raw startup signals into strategic market intelligence.

## Strategic Objective
The objective is to align internal strategy with external market reality by answering three practical questions:

1. Which sectors show stronger survival characteristics?
2. How does capital depth and funding cadence relate to longevity?
3. What market signals can guide portfolio or product prioritization?

## Dataset
- **Source Type:** Global startup/organization funding records
- **Scale:** **66k+ entities** (66,368 rows)
- **Core Fields Used:** `category_list`, `status`, `founded_at`, `funding_total_usd`, `funding_rounds`, geography fields
- **Engineering Note:** Analysis was designed to handle medium-large tabular data volumes with cleaning, coercion, feature derivation, and grouped aggregations across multiple dimensions.

## Methodology
### 1) Survival Analysis
- Computed company age from `founded_at`.
- Used operational outcome labels (`closed` vs non-`closed`) to derive survival behavior across age bands.
- Built a survival curve by age to observe where attrition is most concentrated.

### 2) Sector Segmentation
- Parsed multi-tag sector strings in `category_list` by splitting on `|`.
- Expanded tags into an analyzable long format for density and performance ranking.
- Compared top sectors by success score, funding profile, and outcome rates.

### 3) Funding Intelligence
- Cleaned and coerced `funding_total_usd` into numeric form.
- Modeled `funding_rounds` as a persistence signal.
- Examined links among funding intensity, funding frequency, and survival outcomes.

## Strategic Market Signals
- **Early attrition is real:** Survival probability falls fastest in early company years, making early-stage signal quality critical.
- **Capital depth matters, but sequencing matters more:** Total funding and number of rounds both correlate with better outcomes, suggesting capital timing and continuity are as important as amount.
- **Sector structure is uneven:** High-density sectors are not always the highest-survival sectors; crowding and survivability can diverge.
- **Outcome asymmetry is actionable:** `closed` versus active/success outcomes provides a robust binary market signal for risk-tiering and strategic allocation.

## Outputs
- Main sector/survival visual report: `mission_l01_sector_analysis.png`
- Additional dashboard artifact: `mission_l01_real_data_dashboard.png`

## Project Status
- **Completed:** Data cleaning, feature engineering, sector deep dive, survival and funding visualizations
- **Next Step:** Build an interactive **Power BI dashboard** for stakeholder-facing exploration and operational monitoring

## Repository Structure
- `03-main.ipynb` - Full analysis workflow
- `dataset/big_startup_secsees_dataset.csv` - Source dataset
- `mission_l01_sector_analysis.png` - Sector and survival output
- `mission_l01_real_data_dashboard.png` - Supporting dashboard image

## Why This Matters for Telemetry
This project operationalizes market intelligence into measurable signals. Instead of treating startup outcomes as anecdotal, Mission L-01 quantifies sector risk and survivability so internal planning can reflect external market truth.
