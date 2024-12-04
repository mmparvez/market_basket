# market_basket
# Market Basket Analysis for Customer Sales Optimization

## Objective
To analyze customer purchasing patterns and identify product associations to optimize sales strategies, improve inventory management, and enhance customer experience.

## Introduction
Market Basket Analysis (MBA) is a data mining technique used to uncover the relationships between items purchased together. This project implements MBA using association rule mining algorithms to provide actionable insights for a retail business.

## Data Collection
- **Source**: Collected last 10 years sales data from a retail business's database in csv format.
- **Description**: The dataset includes transaction IDs, product IDs, and timestamps.

## Data Preprocessing
1. **Data Cleaning**: Handle missing values, remove duplicates, and filter irrelevant data.
2. **Data Transformation**: Convert the dataset into a suitable format for analysis (e.g., a transaction matrix).

## Methodology
1. **Association Rule Mining**:
   - **Algorithms**: Implement Apriori and FP-Growth algorithms to identify frequent itemsets.
   - **Metrics**: Calculate support, confidence, and lift for the association rules.
2. **Evaluation**:
   - **Frequent Itemsets**: Identify sets of items that frequently appear together.
   - **Association Rules**: Generate rules that indicate the likelihood of purchasing one item given the purchase of another.

## Tools and Technologies
- **Programming Language**: Python
- **Libraries**: pandas, mlxtend, apyori, matplotlib, seaborn

## Implementation Steps
1. **Load and Explore Data**:
   ```python
   import pandas as pd
   data = pd.read_csv('path_to_dataset.csv')
   print(data.head())
   
2. **Preprocess Data**:
   ```python
   # Example of data transformation
   from mlxtend.preprocessing import TransactionEncoder
   te = TransactionEncoder()
   te_ary = te.fit(data).transform(data)
   df = pd.DataFrame(te_ary, columns=te.columns_)
   
3. **Apply Apriori Algorithm**:
   ```python
   from mlxtend.frequent_patterns import apriori, association_rules
   frequent_itemsets = apriori(df, min_support=0.01, use_colnames=True)
   rules = association_rules(frequent_itemsets, metric="lift", min_threshold=1)
   print(rules.head())
   
4. **Save Results**:
   ```python
   frequent_itemsets.to_csv("market_basket.csv")
   
4. **Visualize Results**:

   Used Power BI to read the dataset and create an inetactive visualization.
   
   ![image](https://github.com/user-attachments/assets/6900c322-33ed-4c6b-948e-ae0128e95845)
      
## Results
1. **Frequent Itemsets**: List and describe the most frequent itemsets found.
2. **Association Rules**: Present the top association rules with their support, confidence, and lift values.
3. **Insights**: Discuss the implications of the findings for inventory management, marketing strategies, and customer experience.

## Conclusion
Summarize the key findings and their potential impact on the retail business. Suggest further improvements and potential areas for future research.

## References
Analytics Vidhya Guide on Market Basket Analysis
GitHub Repositories on Market Basket Analysis
