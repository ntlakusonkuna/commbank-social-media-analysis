
# Task 2: Data Anonymisation

## Overview

The second task focused on anonymising customer data to protect personal and sensitive information while retaining useful information for analysis.

The dataset contained customer information such as names, email addresses, addresses, dates of birth, employment information, salary information, and credit card details.

The objective was to remove or transform information that could directly identify customers while keeping the dataset useful for analytical purposes.

## Dataset

The original dataset was provided as:

`mobile_customers.xlsx`

The dataset contained:

- 10,000 customer records
- 19 columns

The original fields included customer identifiers, personal information, demographic information, employment information, salary information, and credit card information.

## Objectives

The main objectives of the task were to:

- Identify personally identifiable information (PII).
- Identify sensitive customer information.
- Remove unnecessary personal information.
- Replace customer identifiers with synthetic IDs.
- Convert detailed information into broader analytical categories.
- Produce a dataset that is safer to use for analysis.
- Maintain useful information for future analytical work.

## Data Anonymisation Approach

The anonymisation process was completed in Microsoft Excel.

The main steps were:

1. Reviewed the structure of the original dataset.
2. Identified personal and sensitive fields.
3. Created a separate `Anonymised_Data` sheet.
4. Removed direct personal identifiers and sensitive credit card information.
5. Replaced the original customer ID with a synthetic anonymous ID.
6. Converted registration dates into registration years.
7. Converted exact ages into age groups.
8. Converted exact salaries into salary bands.
9. Converted formulas into values.
10. Removed the original detailed values.
11. Checked the final dataset before saving it.

## Information Removed

The following fields were removed from the final dataset:

- `username`
- `name`
- `address`
- `email`
- `birthdate`
- `current_location`
- `residence`
- `employer`
- `credit_card_number`
- `credit_card_security_code`
- `credit_card_expire`

These fields were removed because they contained personal or sensitive information that was not required for the intended analysis.

## Synthetic Customer IDs

The original customer ID was replaced with a synthetic identifier.

Example:

`CUST_000001`

`CUST_000002`

`CUST_000003`

The synthetic IDs allow records to be distinguished without using the original customer identifiers.

## Registration Year

The exact registration date was replaced with the year in which the customer registered.

The Excel `YEAR` function was used:

`=YEAR(D2)`

The resulting values were converted from formulas to values before the original registration date was removed.

This retained useful time-based information while removing the exact registration date.

## Age Grouping

Exact customer ages were replaced with broader age groups.

The categories used were:

- Under 18
- 18-24
- 25-34
- 35-44
- 45-54
- 55-64
- 65+

The following Excel formula was used:

`=IF(G2<18;"Under 18";IF(G2<25;"18-24";IF(G2<35;"25-34";IF(G2<45;"35-44";IF(G2<55;"45-54";IF(G2<65;"55-64";"65+"))))))`

The resulting age groups were converted to values and the original exact age field was removed.

## Salary Banding

Exact salary information was replaced with broader salary bands.

The categories used were:

- Below 30,000
- 30,000-49,999
- 50,000-74,999
- 75,000-99,999
- 100,000-149,999
- 150,000+

The following Excel formula was used:

`=IF(H2<30000;"Below 30,000";IF(H2<50000;"30,000-49,999";IF(H2<75000;"50,000-74,999";IF(H2<100000;"75,000-99,999";IF(H2<150000;"100,000-149,999";"150,000+")))))`

The salary bands were converted to values and the original exact salary field was removed.

## Final Dataset

The final anonymised dataset contained the following columns:

| Column | Description |
|---|---|
| `anonymous_customer_id` | Synthetic customer identifier |
| `registration_year` | Year the customer registered |
| `gender` | Customer gender |
| `job` | Customer occupation |
| `age_group` | Broader customer age category |
| `salary_band` | Broader salary category |
| `credit_card_provider` | Credit card provider |

The final dataset contained 10,000 customer records.

## Privacy Measures

The anonymisation process focused on reducing the amount of directly identifiable information in the dataset.

The following measures were applied:

- Removed names and usernames.
- Removed addresses and locations.
- Removed email addresses.
- Removed exact birthdates.
- Removed employer information.
- Removed credit card numbers.
- Removed credit card security codes.
- Removed credit card expiry dates.
- Replaced customer IDs with synthetic identifiers.
- Replaced exact registration dates with registration years.
- Replaced exact ages with age groups.
- Replaced exact salaries with salary bands.

## Data Quality Checks

After anonymisation, the dataset was reviewed to ensure that:

- The expected number of records remained.
- The final columns were correct.
- Removed personal information was no longer present.
- Synthetic customer IDs were included.
- Age groups were correctly categorised.
- Salary bands were correctly categorised.
- Registration years were retained.
- The dataset remained suitable for analysis.

## Final Output

The final anonymised dataset was saved as:

`mobile_customers_anonymized.csv`

The original customer dataset should not be uploaded to a public GitHub repository because it contains personal and sensitive information.

## Tools and Techniques

- Microsoft Excel
- Data anonymisation
- Data cleaning
- Data transformation
- `YEAR` function
- `IF` functions
- Conditional categorisation
- Filtering
- Paste as Values
- Column removal
- Data quality checking

## Skills Demonstrated

- Data Anonymisation
- Data Privacy
- Data Cleaning
- Data Transformation
- Microsoft Excel
- Data Classification
- Data Quality Checking
- Privacy-Aware Data Management
- Analytical Data Preparation
- Problem Solving
- Attention to Detail

## Conclusion

This task demonstrated how personal and sensitive customer information can be transformed into a more privacy-conscious dataset while retaining useful information for analysis.

The process involved identifying sensitive fields, removing unnecessary personal information, creating synthetic identifiers, and converting detailed values such as age, salary, and registration date into broader categories.

The resulting dataset provides a more suitable structure for analytical work while reducing the exposure of sensitive customer information.
