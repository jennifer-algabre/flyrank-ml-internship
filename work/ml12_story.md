# ML-12 Tell the Story

## 5-Minute Demo Outline

## 1. Problem / Question

Content teams manage many pages, making it difficult to decide which pages should be reviewed first.

This project asks:

Can machine learning help prioritize content pages that may need a refresh using observable search performance signals?

The goal is to support human decision-making rather than automatically make SEO changes.

---

## 2. Method

This project follows the Refresh / Content Opportunity Scoring lane.

The workflow included:

- Defining the content page as the unit of analysis
- Selecting observable search performance features
- Training a Random Forest classifier
- Comparing the model against a rule-based baseline
- Performing validation and leakage checks
- Creating a ranked content review queue with reason codes

---

## 3. Key Visualization

The main visualization is the Random Forest feature importance chart.

It highlights which observable signals contributed most to the model's predictions.

The chart is used for interpretation and does not prove that any feature directly causes content performance changes.

---

## 4. Result

The model showed that combining multiple search performance signals can provide a more structured prioritization approach compared with manual rules alone.

The results are interpreted as decision support for identifying pages that may deserve human review.

The model does not automatically determine which pages should be rewritten, removed, or updated.

---

## 5. Recommendation

The final output is a ranked content review queue.

Human reviewers can investigate pages with signals such as:

- Low click-through performance
- Weak search visibility
- Lower engagement signals
- Potentially outdated content

Human review remains necessary before making content decisions.


# Shareable Cut: Social Post

I built a machine learning workflow for SEO content refresh prioritization as part of the FlyRank ML Internship.

The project explored how observable search performance signals can help identify pages that may require review. Instead of attempting to predict search engine algorithms, the goal was to create a decision-support tool for content teams.

The workflow included feature preparation, Random Forest modeling, validation checks, feature interpretation, and a ranked action queue designed for human review.

A key lesson from this project is that reliable ML systems require not only models, but also careful validation, honest limitations, and clear communication.


# Shareable Cut: Employer Summary

I built a machine learning pipeline that prioritizes content pages for potential refresh opportunities using anonymized search performance data from the FlyRank ML Internship dataset.

The project involved data preparation, feature engineering, Random Forest modeling, baseline comparison, validation auditing, leakage checks, and converting model outputs into actionable content recommendations.

The final system provides a decision-support workflow that helps content teams identify pages worth reviewing based on observable search performance patterns.
