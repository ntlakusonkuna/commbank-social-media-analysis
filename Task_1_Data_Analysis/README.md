# Task 1: Supermarket Transaction Analysis

## Overview

The first task involved analysing a supermarket transaction dataset using Excel.

The purpose of the task was to use transaction data to answer specific business questions and demonstrate the use of spreadsheet formulas for data analysis.

The dataset contained supermarket transactions from Australia covering approximately three years.

---

## Dataset

The dataset contained 50,783 transaction records and 12 columns.

The information included fields such as:

- Product
- Quantity
- Unit price
- Total amount
- Store
- Payment method
- Customer type
- Transaction date and time

The dataset did not contain missing values.

---

## Analysis Performed

The analysis was completed using Excel and focused on answering specific questions from the transaction data.

### Question 1: Cash Purchases of Apples

The first question was to determine how many apples were purchased using cash.

The result was:

**117 apples**

The analysis used a `SUMIFS` formula to filter the transactions by product and payment method.

Example formula:

```excel
=SUMIFS(supermarket_transactions!H:H;supermarket_transactions!F:F;"apple";supermarket_transactions!J:J;"cash")
