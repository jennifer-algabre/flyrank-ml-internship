# Predicting Content Decline for SEO Content Refresh Prioritization

## Abstract

Maintaining high-performing content is an ongoing challenge because search performance naturally changes over time. This project investigates whether historical search performance signals can help identify pages that may require a content refresh. A Random Forest classifier was trained using anonymized search performance features from the FlyRank ML Internship dataset and compared with a rule-based baseline. The results indicate that combining multiple observable search signals provides a more informative prioritization strategy than relying on manual rules alone. These findings are presented as decision support for human reviewers rather than automated publishing decisions.

---

## Introduction

Content teams often manage thousands of pages, making it difficult to determine which pages deserve attention first. Rather than reviewing every page manually, this project explores whether machine learning can prioritize content using historical search performance metrics.

The objective is not to predict Google's ranking algorithm. Instead, the goal is to identify pages that show observable patterns associated with declining performance so they can be reviewed earlier by SEO specialists and content teams.

This work follows the **Refresh / Content Opportunity Scoring** lane of the FlyRank Machine Learning Internship.
