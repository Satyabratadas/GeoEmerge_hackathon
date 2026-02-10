## Bias and Uncertainty in Reported Mosquito Habitat Data
Analyzing structural bias and data incompleteness in community-reported mosquito habitat observations using GLOBE Observer data.

This project investigates how missing environmental context, contributor behavior, and uneven spatial sampling limit predictive modeling of mosquito habitats. Rather than directly training a prediction model, we focus on diagnosing data quality and proposing improvements to future collection pipelines.

## Motivation
Mosquito-borne diseases pose a major public health risk. Community science platforms like GLOBE Observer provide large volumes of mosquito observations—but predictive modeling depends on consistent environmental features, not just outcome labels.

This project asks:
- Are we collecting the right data, in the right way, to build reliable mosquito habitat models?

## Key Findings
- 87.64% of mosquito observations lack paired land cover data
- Severe contributor bias: small number of users dominate extreme larval counts
- Spatial clustering creates geographic sampling imbalance
- Structural missingness prevents meaningful habitat modeling
- These issues significantly reduce downstream ML usefulness.

## Approach
We analyzed:
- Mosquito Habitat Mapper observations
- Land Cover observations

Workflow:
1. Pull data via GLOBE API
2. Filter spatially to Florida
3. Perform EDA on:
    - Missingness
    - Contributor behavior
    - Spatial clustering
    - Feature availability
4. Merge datasets on ```site_id```
5. Visualize coverage and outliers using GeoPandas 
Rather than fitting models, we diagnose systemic data limitations.

## Tech Stack
- Python 3.9+
- Pandas
- GeoPandas
- NumPy
- Matplotlib / Seaborn
- Jupyter Notebook

## Repository Structure
```
.
├── data/                  # Raw + processed CSVs (not tracked if large)
├── final_analysis.ipynb
├── globe_api.py           # Data retrieval helpers
├── requirements.txt
└── README.md

```

## How to Run Locally

### 1. Clone the Repository
```
git clone https://github.com/yourusername/geomerge-mosquito-bias.git
cd geomerge-mosquito-bias
```

### 2. Create Virtual Environment (Recommended)
```
python -m venv venv
source venv/bin/activate   # macOS / Linux
# or
venv\Scripts\activate      # Windows

```

### 3. Install Dependencies
```
pip install -r requirements.txt

```
If GeoPandas causes issues, install via conda:
```
conda create -n mosquito python=3.9 geopandas jupyter pandas matplotlib seaborn
conda activate mosquito

```
### 4. Run the Final Analysis Notebook
```
jupyter notebook
```
Then open:
```
notebooks/final_analysis.ipynb

```
Run cells top-to-bottom.
This notebook contains:
- Data ingestion
- Spatial filtering
- Missingness analysis
- Contributor bias detection
- Visualization

## Dataset

Data retrieved from:
- GLOBE Mosquito Habitat Mapper
- GLOBE Land Cover observations
via public GLOBE API.

## Known Limitations
- Majority of mosquito records lack environmental context
- Heavy contributor skew
- No rainfall / temperature integration
- Not suitable for supervised ML without structural improvements

## Future Work
- Enforce joint mosquito + land cover submissions
- Contributor weighting
- Integrate NOAA rainfall + temperature
- Build probabilistic habitat risk model
- Active learning for sampling guidance

## Hackathon
Built for **GeoMerge Hackathon 2026**

**Theme**: Data quality before modeling.
