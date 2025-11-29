# Fairness Analysis in Job Recruiment

## Overview
The experiment's core objective is to evaluate fairness in the task of predicting recruitment outcomes using a dataset containing potential sensitive attributes. The methodology involves training and comparing various machine learning classification models, such as Logistic Regression, Support Vector Machines (SVM), Decision Trees, Random Forest, and Gradient Boosting, on this data. Crucially, the study tests two versions of most models: one using all available features and one where sensitive features (Gender, Nationality, Age) are excluded, to assess the trade-off between predictive performance (measured by F1, ACC, AUC-ROC) and fairness (measured by DP, EO, ABROCA) for different demographic groups.

## Experiments and Insight
As model performance improves, particularly in F1, Accuracy, AUC-ROC, and AUC-PR, there is a noticeable trend that fairness metrics worsen for certain sensitive attributes. Linear models like Logistic Regression and SVM (linear) start with moderate predictive performance, but their fairness gaps (DP, EO, ABROCA) remain relatively controlled, meaning they discriminate less across groups. However, as we move to more powerful models such as SVM RBF, Random Forest, and Gradient Boosting, predictive metrics increase substantially (F1 up to ~0.79–0.85, AUC up to ~0.93), but this improvement often comes with higher disparities, particularly on Gender, where DP and EO increase sharply, indicating the model relies more heavily on patterns linked to sensitive demographics.

Even when sensitive features are removed ("no sensitive" versions), fairness does not necessarily improve. In several cases, DP and EO become worse, suggesting that models may infer sensitive traits indirectly through correlated features.

This reflects a core fairness-performance trade-off: The more expressive the model, the more likely it captures hidden correlations with sensitive attributes—boosting accuracy while amplifying bias.

The report (in Vietnamese) contained the full result and information to highlight these findings. You can view it here: [Vietnamese Report](Report.docx)