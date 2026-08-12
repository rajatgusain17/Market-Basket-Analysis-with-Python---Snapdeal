# Snapdeal Customer Purchasing Behavior & Recommendation Analysis


## Google Collab Notebook        
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1yoC6q6WJWUY8UkQPFnOyEXeGkgYXiUrU?usp=sharing)



## Overview
A customer insights analysis project simulating the role of a Customer Insights Analyst at Snapdeal, a large e-commerce platform. The goal was to understand customer purchasing behavior, product affinities, and satisfaction drivers using survey data, and translate findings into actionable business recommendations for personalization, promotions, and inventory strategy.

## Dataset
- ~800 survey responses covering demographics, browsing habits, purchase frequency, cart behavior, review engagement, and satisfaction levels.
- Cleaned to 686 valid responses after removing entries with unrealistic ages (<13 years).

## Objectives
- Identify cross-selling opportunities and product affinities
- Understand how purchasing patterns vary across customer segments
- Segment customers by behavior for targeted promotions
- Evaluate what drives (or fails to drive) customer satisfaction and loyalty

## Approach

**1. Data Cleaning**
- Fixed misformatted/duplicate columns (trailing whitespace, ambiguous duplicate fields)
- Handled missing values in `Product_Search_Method` (19% missing) by encoding as an explicit "Not Specified" category rather than imputing
- Removed 114 rows with invalid ages (<13) as a documented data-quality decision
- Standardized inconsistent categorical entries and converted rating columns to numeric types

**2. Exploratory Data Analysis**
- Demographic and behavioral summaries (age, gender, purchase frequency, browsing habits, cart abandonment)
- Visualizations: histograms, bar charts, pie charts, and a correlation heatmap (seaborn/matplotlib)

**3. Customer Segmentation**
- Rule-based segmentation into Frequent Buyers, Occasional Shoppers, and At-Risk Customers using purchase frequency + satisfaction
- K-Means clustering (scikit-learn) on scaled behavioral features to validate and extend the manual segments
- Clustering revealed two distinct sub-types within the "At-Risk" group that manual rules had merged into one

**4. Recommendation & Review Insights**
- Correlation analysis between recommendation helpfulness, review trust, and shopping satisfaction
- Cross-tabulation of recommendation exposure vs. perceived helpfulness

## Key Findings
- Customer segments are driven by **behavior, not demographics** — age and gender showed no meaningful difference across segments
- Recommendation **frequency doesn't build trust** — heavily-exposed customers were barely more likely to find recommendations helpful than rarely-exposed ones
- Satisfaction correlates weakly to not-at-all with recommendation helpfulness, review reliability, or rating accuracy (all correlations near 0)
- **Price and shipping costs** are the dominant driver of cart abandonment across all segments, including the most loyal customers
- K-Means clustering uncovered two distinct types of dissatisfied customers requiring different engagement strategies

## Tech Stack
- Python, pandas, NumPy
- seaborn, matplotlib (visualization)
- scikit-learn (K-Means clustering, StandardScaler)


## Visualizations

### Age Distribution
Customer ages span 13–67, with no single dominant bracket — a broad, non-concentrated demographic base.

![Age Distribution](https://github.com/rajatgusain17/Market-Basket-Analysis-with-Python---Snapdeal/blob/main/Age%20Distribution.png?raw=true)

### Purchase Categories
Most purchased: Clothing and Fashion, followed by Beauty and Personal Care, Home and Kitchen

![Purchase Categories](https://github.com/rajatgusain17/Market-Basket-Analysis-with-Python---Snapdeal/blob/main/Product%20Categories.png?raw=true)

### Browsing Frequency Distribution
Browsing habits are evenly split across all four frequency levels (~24–26% each) — no dominant browsing style.

![Browsing Frequency](https://github.com/rajatgusain17/Market-Basket-Analysis-with-Python---Snapdeal/blob/main/Browsing%20Frequency.png?raw=true)

### Shopping Satisfaction Levels
Satisfaction centers around the midpoint, mean ~3.0/5, indicating a largely neutral customer base

![Shopping Satisfaction](https://github.com/rajatgusain17/Market-Basket-Analysis-with-Python---Snapdeal/blob/main/Shopping%20Satisfaction.png?raw=true)

### Correlation Heatmap — Satisfaction vs. Recommendation Metrics
Recommendation helpfulness, rating accuracy, and recommendation frequency all show near-zero correlation with shopping satisfaction — none of these factors meaningfully drive it on their own.

![Correlation Heatmap](https://github.com/rajatgusain17/Market-Basket-Analysis-with-Python---Snapdeal/blob/main/Coorelation%20Heatmap.png?raw=true)     



## Recommendations
1. Invest in recommendation *relevance* (using purchase/browsing history) over recommendation frequency
2. Address pricing transparency and shipping costs directly — a bigger lever for satisfaction than the recommendation engine
3. Target the two distinct At-Risk customer sub-clusters with different engagement strategies
4. Use behavior-based (not demographic) segmentation for future personalized promotions



## Author
[RAJAT GUSAIN] 
