Task 1: Supermarket Transaction Analysis
Overview

The first task involved analysing a supermarket transaction dataset using Microsoft Excel.

The purpose of the task was to use transaction data to answer specific business questions and demonstrate how spreadsheet formulas and filtering can be used to extract useful information from a large dataset.

The analysis focused on products, quantities, transaction amounts, stores, payment methods, and customer types.

Dataset

The supermarket transaction dataset contained 50,783 transaction records and 12 columns.

The dataset included information relating to:

Products
Quantity
Unit price
Total transaction amount
Store
Payment method
Customer type
Transaction date
Transaction time
Other transaction-related information

The dataset was reviewed before analysis to understand its structure and identify the fields required to answer the questions.

No missing values were identified in the dataset.

Objectives

The main objectives of the task were to:

Explore the supermarket transaction dataset.
Understand the structure and contents of the data.
Use Microsoft Excel to analyse transaction records.
Apply conditional formulas to answer business questions.
Calculate quantities and spending based on specific conditions.
Extract useful information from the transaction data.
Demonstrate practical data analysis skills using Excel.
Analysis Approach

The analysis was completed using Microsoft Excel.

The following approach was used:

Reviewed the dataset and its columns.
Checked the number of transaction records.
Checked the dataset for missing values.
Identified the fields required for each question.
Applied filters and conditional calculations.
Used the SUMIFS function to calculate results based on multiple conditions.
Reviewed the results to ensure that the calculations answered the required questions.
Question 1: How Many Apples Were Purchased Using Cash?

The first question was to determine the total quantity of apples purchased using cash.

The analysis used two conditions:

Product: Apple
Payment method: Cash

The result was:

117 apples

The SUMIFS function was used to add the quantity of apples where the payment method was cash.

Example formula:

=SUMIFS(supermarket_transactions!H:H,supermarket_transactions!F:F,"apple",supermarket_transactions!J:J,"cash")

This formula calculates the total quantity where the product is apple and the payment method is cash.

Question 2: How Much Was Spent on Apples Using Cash?

The second question was to determine the total amount spent on apples where cash was used as the payment method.

The analysis used the following conditions:

Product: Apple
Payment method: Cash
Measure: Total transaction amount

The result was:

$537.03

This represents the total value of cash transactions involving apples.

The analysis demonstrated how transaction values can be filtered according to specific product and payment conditions.

Question 3: How Much Did Non-Members Spend at the Bakershire Store?

The third question was to determine the total amount spent by non-member customers at the Bakershire store across all payment methods.

The analysis used the following conditions:

Store: Bakershire
Customer type: Non-member
Measure: Total transaction amount

The result was:

$2,857.51

The SUMIFS function was used to calculate the total transaction amount for non-member customers at the Bakershire store.

Example formula:

=SUMIFS(supermarket_transactions!H:H,supermarket_transactions!I:I,"Bakershire",supermarket_transactions!L:L,"non-member")

This formula adds the transaction amounts where the store is Bakershire and the customer type is non-member.

Key Results
Analysis	Result
Cash purchases of apples	117
Cash spent on apples	$537.03
Bakershire spending by non-members	$2,857.51
Key Findings

The analysis demonstrated how transaction data can be used to answer specific business questions by combining different fields and applying conditions.

The analysis identified:

The quantity of apples purchased using cash.
The total value of cash purchases involving apples.
The total spending by non-member customers at the Bakershire store.
How product, payment method, store, and customer type can be used together to analyse transactions.
Business Applications

This type of analysis could be used by a supermarket to:

Monitor product sales.
Analyse customer spending.
Compare member and non-member purchasing behaviour.
Understand payment method usage.
Compare spending across stores.
Identify purchasing patterns.
Support inventory planning.
Support sales reporting.
Support business decision-making.
Tools and Techniques Used
Microsoft Excel

Excel was used to inspect, filter, and analyse the supermarket transaction data.

SUMIFS

The SUMIFS function was used to calculate totals based on multiple conditions.

Data Filtering

Filtering and conditional criteria were used to isolate the transactions relevant to each business question.

Data Inspection

The dataset was reviewed to understand its structure, records, and available variables before performing the analysis.

Skills Demonstrated
Data Analysis
Microsoft Excel
Data Inspection
Data Filtering
Conditional Calculations
SUMIFS
Business Analysis
Problem Solving
Analytical Thinking
Data Interpretation
Reporting
Conclusion

This task demonstrated how Microsoft Excel can be used to analyse a large supermarket transaction dataset and answer practical business questions.

By reviewing the dataset, identifying relevant variables, applying conditions, and using formulas such as SUMIFS, useful information could be extracted from thousands of transaction records.

The task provided practical experience in analysing structured transaction data and demonstrated how basic data analysis techniques can be used to support business reporting and decision-making.
