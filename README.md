# Lab 6: Association Rule Mining with Apriori and FP-Growth

## Purpose of the Lab Work
The goal of this lab is to explore and implement association rule mining techniques using real-world transactional data. By utilizing the Apriori and FP-Growth algorithms, this project uncovers hidden purchasing patterns, identifies frequent itemsets, and generates actionable association rules. Visualizations built with Seaborn are used to interpret the co-occurrence of items and evaluate rule metrics like support, confidence, and lift.

## Dataset
* **Source:** Online Retail Dataset (UCI Machine Learning Repository)
* **Scope:** Filtered to French transactions to maintain computational efficiency while providing robust market basket analysis.

## Key Insights
1. **Algorithm Efficiency:** FP-Growth vastly outperformed the Apriori algorithm in execution time. By utilizing the FP-tree structure, it bypassed the computationally expensive candidate-generation steps required by Apriori.
2. **Purchasing Behaviors:** The generated barplots and heatmaps highlight specific clusters of items (e.g., complementary paper crafts and novelties) that are frequently purchased together.
3. **Rule Strength:** The Confidence vs. Lift scatterplot reveals several highly actionable rules. Products with a lift > 5 indicate a very strong positive correlation, meaning a customer buying the antecedent item is highly likely to buy the consequent item.

## Challenges and Decisions
* **Memory Constraints:** Converting the entire UCI transactional dataset into a sparse, one-hot encoded matrix caused significant memory spikes. 
    * *Decision:* I subset the data by a specific country ('France') which stabilized the matrix size and improved computation speeds while preserving real-world transactional logic.
* **Data Noise:** The dataset contained administrative codes like 'POSTAGE' and 'C' (Cancellations).
    * *Decision:* I removed cancelled orders and dropped 'POSTAGE' from the itemsets to ensure the generated rules were based strictly on actual product associations, preventing skewed confidence metrics.

## Files in this Repository
* `lab6.ipynb` - The complete Jupyter Notebook containing the code, analysis, and visualizations.
* `README.md` - This file.
