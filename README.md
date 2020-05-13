# Glassdoor 'Data Science' jobs salary estimator: Project Overview

- Created a tool that estimated data science salary(MAE ~ $ 11.7 k) which estimates data scientists negotiate their income when they get a job in USA.
- Scraped over 1000 job descriptions from glassdoor using python and selenium
- Engineered features from the text of each job description to quantify the value companies put on python, excel, aws, and spark.
- Optimized Linear, Lasso, and Random Forest Regressors using GridsearchCV to reach the best model.

## Code and Resources Used
- Packages: pandas, numpy, sklearn, matplotlib, seaborn, selenium, flask, json, pickle
- Scraper Github: https://github.com/arapfaik/scraping-glassdoor-selenium
- Scraper Article: https://towardsdatascience.com/selenium-tutorial-scraping-glassdoor-com-in-10-minutes-3d0915c6d905

## Web Scraping
Tweaked the web scraper github repo (above) to scrape 1000 job postings from glassdoor.com. With each job, we got the following:

- 'Unnamed: 0' - Data which has no importance
- 'Job Title' - job title
- 'Salary Estimate' - Salary range estimated
- 'Job Description' - Description of job
- 'Rating' - Rating of company
- 'Company Name' - Company name
- 'Location' - Location of job
- 'Headquarters' - Headquarters of company that posted job
- 'Size' - Size of company
- 'Founded' - Company founded in year
- 'Type of ownership' - Type of company ownership
- 'Industry'- Inds=ustry in which job is posted
- 'Sector' - Sector of company that posted job
- 'Revenue' - Annual revenue of company
- 'Competitors' - Names of potential competetors of company

## Data Cleaning

After scraping the data, I needed to clean it up so that it was usable for our model. I made the following changes and created the following variables:

- Parsed numeric data out of salary
- Made columns for employer provided salary and hourly wages
- Removed rows without salary
- Parsed rating out of company text
- Made a new column for company state
- Added a column for if the job was at the company’s headquarters
- Transformed founded date into age of company
- Made columns of different skills were listed in the job description: - Python, RStudio, PySpark, Machine Learning, BigData
- Created a column to find the requirement of advanced degrees
- Column for simplified job title and Seniority
- Column for description length

## Exploratory Data Analysis

