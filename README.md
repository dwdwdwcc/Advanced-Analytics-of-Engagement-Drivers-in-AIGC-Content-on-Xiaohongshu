# README: Predicting Engagement Drivers for AIGC Content on Xiaohongshu
## ACC102 Track 1 - Advanced Analytics Project

---

## Project Overview
This end-to-end analytics project identifies key drivers of user engagement for AIGC content on Xiaohongshu, using Python-based statistical analysis, regression modeling, and data visualization. It delivers actionable content and posting strategies to maximize engagement, and defines core traits of high-performing content.

---

## Core Research Questions
1.  What factors predict higher user engagement (likes) for Xiaohongshu content?
2.  What is the optimal content and posting strategy for maximum engagement?
3.  What are the key characteristics of viral/high-engagement content?

---

## Dataset Overview
| Dataset | Initial Scale | Final Cleaned Scale |
|---------|---------------|---------------------|
| Comments | 65,097 rows | 64,436 rows |
| Posts | 1,582 rows | 1,461 valid rows |

### Preprocessing Steps
- Standardized string-formatted like counts to numeric values
- Removed records with missing core metrics
- Applied 99th percentile capping to mitigate outlier impact
- Converted timestamps to standardized datetime format for temporal analysis

---

## Analysis Pipeline
1.  **Feature Engineering**: Created temporal (posting time, weekend/evening flags) and content (text length, punctuation/emoji flags) features, plus normalized engagement target variables
2.  **Descriptive Statistics**: Analyzed distribution of engagement, text length, and posting time trends
3.  **Statistical Testing**: Used non-parametric Mann-Whitney U and Kruskal-Wallis tests to validate engagement differences across groups
4.  **Correlation & Regression**: Measured feature-engagement relationships via Spearman correlation, and built a robust OLS regression model to quantify feature impact
5.  **Visualization**: Generated core plots for distribution, correlation, and engagement trends

---

## Key Findings
### Top Engagement Drivers
1.  **Comment text length**: Strongest positive predictor of engagement (r=+0.2327, p<0.001), with very long comments earning ~7.5x more likes than very short ones
2.  **Content format**: Video posts deliver ~2x higher average likes than standard image/text posts
3.  **Posting time**: Evening (19:00-23:00) and weekend content significantly outperforms weekday/non-evening posts

### Optimal Strategy
- Best posting window: Sunday 19:00 (peak average engagement)
- Prioritize longer, detailed comments and video content for higher reach

---

## Dependencies & Usage
### Required Libraries
```
pandas, numpy, matplotlib, seaborn, scipy, statsmodels
```
### Usage
1.  Upload `Comment.csv` and `Posts.csv` to your Colab/Jupyter environment
2.  Run `track1.ipynb` cells sequentially
3.  Cleaned datasets and visualizations will auto-export upon completion

---

## Output Files
- Cleaned datasets: `final_cleaned_comments.csv`, `final_cleaned_posts.csv`
- Visualizations: `distribution_analysis.png`, `correlation_analysis.png`, `advanced_visualizations.png`

---

**Note**: All statistical tests use a 0.05 significance threshold; robust standard errors are applied to the regression model to address heteroscedasticity.
