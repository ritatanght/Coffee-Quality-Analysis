# Coffee Quality Analysis

TThis project explores the factors that influence the quality of Arabica coffee beans, using a dataset provided by the [Coffee Quality Institute (CQI)](https://www.coffeeinstitute.org/), to uncover insights into factors affecting coffee quality. The analysis leverages data visualization, descriptive statistics, and hypothesis testing to identify meaningful patterns and relationships.


## Dataset
Source: [Kaggle - Coffee Quality Data](https://www.kaggle.com/datasets/fatihb/coffee-quality-data-cqi)

Contains sensory evaluation scores (Total Cup Points, Flavor, Aroma, etc.) alongside metadata (altitude, origin, processing method, etc.)

## Data Cleaning & Preparation
- Removed irrelevant or duplicate columns (e.g., Farm Name, Defects, Status).

- Standardized categorical values for:

   - `Variety` → grouped into major types, Blend, and Others

   - `Color` → reduced to five consistent terms

   - `Processing Method` → grouped into Washed, Natural, Honey, and Others
- Extracted and converted Altitude values:

   - Ranges were averaged

   - Feet values were converted to meters for consistency

   - Categorized into Low, Medium, High, and Very High

- Calculated Total Weight using Bag Weight × Number of Bags

## Key Insights

- Most coffee beans in the dataset demonstrate **high quality**, with *Total Cup Points* ranging between **80–88**.
- Higher altitude cultivation shows a **weak positive correlation** with better cup scores — confirming known trends but indicating that altitude alone does not fully determine quality.
- Interestingly, beans from *Low* altitude exhibited slightly higher average scores than those from *High* altitude, suggesting further exploration is needed (potential sample size imbalance).
- **Ethiopian** coffee dominates both in quality (top average *Total Cup Points*) and production volume (though heavily influenced by one company, *yhaenu plc*).
- **Washed** is the most common processing method (~60% of samples), but no statistically significant difference in *Flavor* was found across processing methods.

## Interactive Dashboard

Explore the interactive dashboard for this project on [Looker Studio](https://lookerstudio.google.com/s/hXu661SlnJU).

## Statistical Analysis

- **ANOVA** confirmed significant differences in *Total Cup Points* across altitude groups.
- **Pearson correlation** (r ≈ 0.17) between altitude and *Total Cup Points* indicates a weak but positive relationship.
- No significant difference in *Flavor* scores was found across different processing methods.


## Challenges & Limitations

1. **Inconsistent Altitude units**  
   The dataset contains inconsistencies in altitude measurements. Some outlier altitude values appear unusually high. Through external research and contextual clues, it is reasonably assumed that these values are recorded in **feet** rather than **meters**, introducing potential inaccuracies in altitude-related analyses.

2. **Sparse Variety data**  
   There are many different coffee varieties in the dataset, including numerous blends. Some blends appear only once, making it difficult to draw reliable, generalizable conclusions about the impact of specific varieties on coffee quality.

3.  **Limited dataset scope**  
   This dataset represents a curated sample and is not broad enough to generalize the results to all coffee produced worldwide or by other farms or mills. The findings should be interpreted within the context of the available data.

## Technologies Used

- **Python**: Pandas, NumPy, SciPy, Matplotlib, Seaborn
- **Notebook Environment**: Jupyter Notebook (Google Colab)
