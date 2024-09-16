# OJ Dataset Analysis: Pre-Pruning vs. Post-Pruning

## Overview

This project involves an analysis of the OJ dataset using decision tree models. The analysis compares the performance of an unpruned decision tree with a pruned tree to evaluate the trade-off between fitting the training data and generalizing to new data.

## Objective

The primary goals of this analysis are:
1. To evaluate and compare the performance of an unpruned decision tree and a pruned decision tree on the OJ dataset.
2. To demonstrate the benefits of pruning in reducing overfitting and improving model generalization.

## Dataset

The analysis uses the OJ dataset from the ISLP package. The dataset includes various features and a binary response variable, `Purchase`, which indicates whether a purchase was made.

## Analysis

### Unpruned vs. Pruned Tree

**Unpruned Tree:**
- **Training Error Rate:** 0.0075
- **Characteristics:** The unpruned tree fits the training data almost perfectly, with a very low training error rate. This indicates that the model is complex enough to capture all the details, including noise and outliers.

**Pruned Tree:**
- **Tree Size:** 29 nodes
- **Training Error Rate:** 0.1338
- **Cross-Validation Error Rate:** Lowest among different tree sizes
- **Characteristics:** The pruned tree, which was trimmed to a size of 29 nodes, has a higher training error rate compared to the unpruned tree. However, this higher training error is expected as pruning simplifies the model, reducing its complexity and improving its ability to generalize to new data.

### Test Performance

- **Unpruned Tree Test Error Rate:** 0.2778
- **Pruned Tree Test Error Rate:** 0.2444

The pruned tree demonstrates better performance on the test set with a lower error rate compared to the unpruned tree. This supports the typical machine learning trade-off between model complexity and generalizability. The pruned tree's superior test performance indicates that pruning has effectively enhanced the model's ability to predict new, unseen data.

### Confusion Matrix Analysis

- **Pruned Tree Confusion Matrix:**
  - **True Positives (121), False Positives (38)**
  - **True Negatives (74), False Negatives (37)**

While the confusion matrix shows the number of correct and incorrect predictions, the test error rate of 0.2444 provides a better measure of the pruned tree's overall prediction accuracy. The pruned tree's confusion matrix indicates that it has a reasonable capacity for prediction.

### Optimal Model Complexity

The plot of tree size versus cross-validated classification error rate suggests that increasing tree size beyond a certain point does not improve performance. Instead, performance tends to plateau or even worsen, illustrating the concept of diminishing returns with increased model complexity. This underscores the importance of selecting an appropriately sized model to avoid overfitting and ensure better generalization.

## Conclusion

Pruning is an effective technique for improving decision tree models by preventing overfitting and enhancing generalization. In this analysis, the pruned tree with 29 nodes emerged as the superior model, demonstrating lower error rates on both the test set and in cross-validation. This validates pruning as a crucial step in optimizing decision tree models for better performance on unseen data.

## Files

- **`OJ_Analysis.ipynb`**: R script containing the analysis code.

## How to Run

1. Ensure you have the required packages installed (`ISLP`, `rpart`, `ggplot2`, etc.).
2. Load the dataset and run the script `OJ_Analysis.ipynb` to perform the analysis.
3. Review the results and visualizations.
