# Google Merch Store Analysis Project

## Overview
This project provides an exploratory data analysis, insightful visualizations, and predictive modeling of the Google Merchandise Store sales data. The data set includes over 900,000 entries spanning the period from August 1, 2016, to August 1, 2017, providing detailed insights into customer behavior, revenue streams, and the impact of holidays on sales.

## Project Contributors
- Eli Andrae
- Sergio Bacon
- Ted McKee

## Data Source
The Google Merchandise Store dataset was selected for its comprehensive coverage and relevance in reflecting typical online consumer behavior patterns. The data was enriched with a global holiday data set for comparative analysis of sales performance.

## Libraries & Tools
- R programming environment
- Tidyverse
- GGplot2
- Broom
- Caret
- Lubridate
- Bigquery
- rlang
- Dplyr
- GGstats
- Corrplot
- Countrycodes
- Scales
- Jsonlite

## Visualizations
Key visualizations included:
- Bar charts (`geom_bar`) depicting browser revenue streams
- Line graphs (`geom_line`) demonstrating holiday impact on sales
- Correlation plots (`cor()` and `corrplot`) showcasing relationships between variables
- Model plots (`modelplot`) to illustrate logistic regression findings

## Analysis Highlights
- **Revenue Streams**: Chrome browser and direct traffic sources generated the highest revenue, notably:
  - Direct (Chrome): $1,262,755
  - Google (Chrome): $236,031

- **Geographic Insights**:
  - Highest revenue countries: United States, Venezuela, Canada

- **Holiday Sales Impact**:
  - Significant increase in sales observed 4-21 days before holidays
  - Recommended marketing strategy: targeted promotions and expedited shipping within a week before major holidays

## Predictive Modeling
- **Purchase Prediction Model**:
  - Achieved 98% accuracy with high specificity
  - Useful for targeting likely buyers and optimizing marketing spend

- **Bounce Prediction Model**:
  - Achieved 63% accuracy
  - Provided useful insights despite challenges in prediction accuracy

## Recommendations
- Prioritize last-minute promotions to leverage holiday sales peaks.
- Focus marketing budget on proven high-value channels and browser sources.
- Utilize predictive models to refine targeting strategies and reduce unnecessary marketing expenditures.

## Files in Repository
- `DataPreparation.Rmd`: Details on data cleaning and preparation.
- `PrelimProject.Rmd`: Initial exploratory analysis and insights.
- `Final.Rmd`: Comprehensive final analysis with detailed findings and visualizations.
- `Google Store Presentation.pptx`: Presentation summarizing findings and recommendations.

## Usage
Clone or download the repository to explore the detailed analysis, models, visualizations, and R Markdown documents.

```bash
git clone <repository_link>
cd <repository_directory>
git clone https://github.com/Elijah-Andrae56/Google_Merch_Store_Analysis_MKTG415.git
cd Google_Merch_Store_Analysis_MKTG415
```

Review the `.Rmd` files for detailed explanations, code snippets, and visualizations to better understand the analysis process and outcomes.

---

This analysis project effectively demonstrates actionable insights and robust predictive modeling strategies applicable to online retail environments, emphasizing strategic marketing optimization and enhanced consumer engagement.
