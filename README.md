# Louisville Crime Data Analysis: CPTED Corridor Assessment

**Author:** Megan Scott, Data Analysis Student  
**Project Date:** 2024  
**Location:** Louisville, Kentucky

---

## Project Overview

This project analyzes 2024 crime data for Louisville, KY to identify high-crime corridors between popular neighborhoods and advocate for safety improvements using **Crime Prevention through Environmental Design (CPTED)** principles.

### Purpose

Compel local business owners and everyday citizens to invest in corridor improvements between thriving neighborhoods—including NuLu, Butchertown, Whiskey Row, and the Riverfront—by presenting data-driven evidence of safety concerns that impact foot traffic and commerce.

### Target Audience

- **Business owners** concerned about customer safety and foot traffic
- **City planners** evaluating infrastructure improvements
- **Community advocates** promoting neighborhood connectivity
- **Local government** considering CPTED interventions

---

## Crime Classification System

This analysis groups Louisville crime incidents into three strategic categories designed to capture offenses that affect public perception of safety and business decisions:

### Property Crime
- Auto Theft
- Theft from Vehicle
- Theft from Building
- Burglary
- Larceny
- Other Theft

### Interpersonal (Public-Facing)
- Simple Assault
- Aggravated Assault
- Robbery
- Intimidation

### Quality of Life / Public Disorder
- Vandalism
- Shoplifting
- Trespassing
- Disorderly Conduct

---

## Key Findings

### High-Crime ZIP Codes
Analysis of the top 25 ZIP codes by total crime volume reveals:

- **40202** (downtown business district): 5th overall for total crime but **highest for Property Crime**, indicating potential vulnerability for businesses and tourists
- Crime composition varies significantly across ZIP codes, suggesting different intervention strategies may be needed

### Spatial Patterns
- High null values in `block_address` correlate with crimes occurring in **alleys, sidewalks, and parking lots**—critical transitional spaces between neighborhoods
- These "in-between" areas represent prime opportunities for CPTED improvements (lighting, visibility, maintenance)

### Temporal Considerations
The `date_occurred` field includes granular timestamp data, enabling future analysis of:
- Crime spikes during specific hours (e.g., after-dark incidents)
- Seasonal patterns that affect perceived safety
- Peak tourism times vs. crime rates

---

## Methodology

### Data Source
2024 crime incident data from Louisville Metro Police Department

### Data Cleaning
**Dropped columns:**
- `date_reported` – redundant with occurrence date
- `badge_id` – not relevant to geographic/categorical analysis  
- `ObjectId` – system-generated identifier with no analytical value

**Retained for analysis:**
- `zip_code` – primary geographic unit
- `block_address` – spatial context (despite nulls)
- `date_occurred` – temporal patterns
- Crime classification fields

### Analysis Approach
1. **Crime Bucketing:** Categorized offenses into three strategic groups based on public impact
2. **Geographic Aggregation:** Grouped incidents by ZIP code to identify hotspots
3. **Volume Sorting:** Ranked ZIPs by total crime descending to prioritize high-impact areas
4. **Visual Analysis:** Heat maps and stacked bar charts to reveal patterns in crime composition

---

## Visualizations

### 1. Crime Intensity Heat Map
Displays all three crime categories across the top 25 ZIP codes, sorted by total crime volume (descending). Uses color intensity to highlight concentration patterns.

**Key Insight:** Property Crime dominates in 40202 despite moderate overall ranking

### 2. Crime Composition Bar Chart
Stacked percentage bars show relative proportions of each crime type within the top 5 ZIP codes.

**Key Insight:** Crime profiles vary—40202 is 54% Property Crime vs. 40219's more balanced distribution

---

## Installation & Setup

### Requirements
- Python 3.8+
- Jupyter Notebook
- Libraries:
  ```
  pandas
  matplotlib
  seaborn
  numpy
  ```

### Running the Analysis
1. Clone this repository
2. Install dependencies:
   ```bash
   pip install pandas matplotlib seaborn numpy
   ```
3. Place the crime data CSV in the project root directory
4. Open `crime_analysis.ipynb` in Jupyter Notebook
5. Run all cells sequentially

---

## Project Structure

```
louisville-crime-analysis/
│
├── README.md                 # This file (place in root directory)
├── crime_analysis.ipynb      # Main analysis notebook
├── data/
│   └── louisville_crime_2024.csv
├── visualizations/
│   ├── heatmap_crime_intensity.png
│   └── bar_crime_composition.png
└── requirements.txt          # Python dependencies
```

**📍 README Placement:** Save this file as `README.md` in the **root directory** of your project folder (same level as your notebook file). This is GitHub standard practice—the README will automatically display when someone visits your repository.

---

## Next Steps

### Phase 2: Spatial Mapping
- Overlay high-crime ZIPs onto Louisville street map
- Identify specific corridor segments between NuLu, Butchertown, Whiskey Row, and Riverfront
- Map null `block_address` incidents to locate problematic alley/sidewalk zones

### Phase 3: Environmental Correlation
Acquire and integrate:
- **Streetlight coverage data** (Louisville Metro)
- **Vacant/blighted property records** (Open Data Portal)
- **Pedestrian traffic counts** (Downtown Partnership)
- **Business licensing density** (Metro Government)

### Phase 4: CPTED Recommendation Package
- Before/after street view documentation
- Evidence-based lighting/maintenance proposals
- Cost-benefit analysis for corridor improvements
- Stakeholder presentation materials

---

## Limitations

- Analysis limited to reported crimes (unreported incidents not captured)
- 2024 data only—no multi-year trend comparison yet
- ZIP code aggregation masks block-level nuance
- Missing `block_address` data reduces precision for corridor identification

---

## License

This project is for educational purposes. Crime data sourced from Louisville Metro Police Department public records.

---

## Contact

**Megan Scott**  
Data Analysis Student  
[Add your preferred contact method or LinkedIn URL]

---

## Acknowledgments

- Louisville Metro Police Department for public crime data
- Data analysis coursework and mentors
- Louisville community advocates inspiring this work