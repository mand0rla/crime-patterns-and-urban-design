# Crime Patterns and Urban Design: Louisville Analysis

An exploratory data analysis of Louisville Metro crime data, examining patterns that may influence business investment decisions, public perception of safety, and urban walkability.

## Project Overview

This project investigates how crime patterns relate to urban planning, business locations, and pedestrian activity in Louisville, KY. The ultimate goal is to build an evidence base demonstrating the relationship between urban investment (green spaces, walkable infrastructure, livable city design) and community safety outcomes. Drawing corrolaries between data points could help make the case for local business investment in urban revitalization.

Crime data serves as the starting point, with plans to incorporate additional datasets on walkability, green space access, and economic indicators.

## Data Source

**Louisville Metro KY - Crime Data 2024**  
Louisville Open Data Portal  
https://data.louisvilleky.gov/datasets/a220289a40c945298d7f9d5c8dc7b3c0_0/explore

The dataset contains approximately 70,000 reported crime incidents with fields including offense classification, location (ZIP code, block address, LMPD beat/division), date/time occurred, and location category.

## Key Findings

### Crime Category Distribution

Crimes were grouped into three categories relevant to business decisions and public safety perception:

| Category | Incident Count |
|----------|----------------|
| Property Crime | 18,919 |
| Interpersonal (Public-Facing) | 12,186 |
| Quality of Life / Public Disorder | 8,721 |

### Geographic Patterns

Analysis of the top 5 ZIP codes by crime volume reveals distinct patterns:

- **40202 (Downtown)**: Highest proportion of property crime (54%), likely reflecting commercial density
- **40211**: Highest rate of interpersonal crime among top ZIPs (36%)
- **40219**: Highest rate of quality-of-life offenses (28%), notably above other areas

### Visualizations

- Stacked bar chart comparing crime type proportions across high-volume ZIP codes
- Heatmap showing crime intensity by type across the top 25 ZIP codes
- Line chart displaying prevalence of crime set against 24-hour clock (2024)

## Methodology

1. **Data Cleaning**: Reviewed duplicate incident numbers (none) and records that include missing block addresses (~1,100 rows)
2. **Feature Engineering**: Extracted temporal features (month, day of week, hour) from occurrence timestamps for future temporal analysis
3. **Crime Bucketing**: Grouped 50+ offense classifications into three categories based on relevance to business/public safety concerns:
   - *Quality of Life / Public Disorder*: Vandalism, shoplifting, trespassing, disorderly conduct
   - *Property Crime*: Auto theft, theft from vehicle, burglary, larceny
   - *Interpersonal (Public-Facing)*: Simple/aggravated assault, robbery, intimidation

## Project Structure

```
crime-patterns-and-urban-design/
├── data/
│   └── lmpd_crime.csv
├── notebooks/
│   └── W1_lmpd_crime.ipynb
├── requirements.txt
└── README.md
```

## Requirements

- Python 3.13+
- pandas
- matplotlib
- seaborn
- numpy

Install dependencies:
```bash
pip install -r requirements.txt
```

## Future Directions

- Integration of walkability scores and green space data
- Correlation analysis between urban design factors and crime patterns
- Business district-specific deep dives

## Author

Megan Scott

## License

This project uses publicly available data from Louisville Metro Government's Open Data Portal.
