# Predicting Content Decline for SEO Content Refresh Prioritization

## Abstract

Maintaining high-performing content is an ongoing challenge because search performance naturally changes over time. This project investigates whether historical search performance signals can help identify pages that may require a content refresh. A Random Forest classifier was trained using anonymized search performance features from the FlyRank ML Internship dataset and compared with a rule-based baseline. The results indicate that combining multiple observable search signals provides a more informative prioritization strategy than relying on manual rules alone. These findings are presented as decision support for human reviewers rather than automated publishing decisions.

---

## Introduction

Content teams often manage thousands of pages, making it difficult to determine which pages deserve attention first. Rather than reviewing every page manually, this project explores whether machine learning can prioritize content using historical search performance metrics.

The objective is not to predict Google's ranking algorithm. Instead, the goal is to identify pages that show observable patterns associated with declining performance so they can be reviewed earlier by SEO specialists and content teams.

This work follows the **Refresh / Content Opportunity Scoring** lane of the FlyRank Machine Learning Internship.

## Data

This project uses the anonymized **FlyRank ML Internship dataset**, which contains historical search performance and content-level signals collected from production SEO environments. The dataset was designed for educational and research purposes, with all client identifiers pseudonymized to protect privacy.

The analysis focuses on the **Refresh / Content Opportunity Scoring** lane. Each row represents a single content page and includes observable search performance metrics such as impressions, clicks, click-through rate (CTR), average search position, engagement rate, scroll rate, content age, and update history.

For this project, pages were classified using the provided **trend_direction** field. A binary label was created where pages with a **"down"** trend were treated as declining content. Fields that directly describe the outcome, such as **trend_pct**, were excluded from the feature set to avoid data leakage.

No client names, website URLs, search queries, or other sensitive production information were used in this research.

## Methodology

The project follows a supervised machine learning workflow to prioritize content pages that may benefit from a content refresh.

### Feature Engineering

The feature set consists of observable search performance and content metrics that are available before a refresh decision is made. These include:

- Impressions (90-day)
- Clicks (90-day)
- Click-through rate (CTR)
- Average search position
- Engagement rate
- Scroll rate
- Word count
- Content age
- Days since last update
- Search volume
- Competition

Missing numerical values were imputed using the median, while additional indicator variables were created to preserve information about missing content-related fields.

### Label Definition

The target label was derived from the `trend_direction` field. Pages labeled **"down"** were assigned a value of 1 (declining), while all other trend categories were assigned 0.

### Baseline

Before training a machine learning model, a rule-based baseline was created using manually selected search performance signals. This provided a simple benchmark for comparison.

### Model Selection

A Random Forest classifier was selected because it can model non-linear relationships between multiple search performance features while remaining relatively interpretable through feature importance analysis. Compared with a single decision tree, Random Forest generally provides more stable predictions by combining multiple decision trees.

### Validation

An 80/20 stratified train-test split was used to preserve the class distribution between training and testing data. Additional validation considered potential feature leakage by excluding outcome-derived variables such as `trend_pct`. Model claims are presented as observed predictive performance rather than evidence of causal relationships.

## Results

The Random Forest classifier was evaluated against the Week 4 rule-based baseline using the same dataset and evaluation workflow. While the baseline relied on manually defined search performance rules, the Random Forest model learned patterns across multiple features simultaneously.

The machine learning model demonstrated stronger predictive capability than the rule-based approach by combining several observable search performance signals rather than relying on a single threshold. The model is intended to rank pages for review rather than replace human decision-making.

### Model Comparison

| Approach | Description |
|-----------|-------------|
| Week 4 Baseline | Manual rule-based prioritization |
| Random Forest | Supervised machine learning classifier |

The evaluation showed that the Random Forest classifier provided a more informative ranking strategy for identifying potentially declining pages.

### Feature Importance

The feature importance analysis indicates that search performance metrics contributed most to the model's predictions. Features such as impressions, clicks, click-through rate (CTR), average search position, and engagement-related metrics were among the strongest contributors.

The figure below summarizes the relative importance of each feature.

![Feature Importance](figures/feature_importance.png)

These feature importance values describe how much each variable contributed to the model's predictions within this dataset. They should not be interpreted as evidence that any individual feature causes a page to improve or decline.
