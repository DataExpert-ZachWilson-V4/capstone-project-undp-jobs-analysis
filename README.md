
# Project Proposal: United Nations Development Programme Jobs Analysis 

## Project Overview

**Project Name:** United Nations Development Programme Jobs Analysis 

**Team**
- Jonas Nothnagel 


**Background and Objective:** 
The United Nations Development Programme (UNDP), founded in 1965, is one of the largest UN entities spanning over 177 countries. Interestingly, UNDP has been publicly posting all their vacancies since 2006. This makes up to over 120000 job postings in 177 countries.
The purpose of this capstone project is to build a data engineering framework that automatically scrapes all available job postings, transforms the data into an actionable dataset, investigates the dataset and ultimately visualises the data and insights from the analysis in an interactive web application.
The main objective is to build the robust data engineering backend but also to understand how the job market for international development has evolved over the last years - for example whether technical jobs have become more promiment or what skillsets are most sought after now compared to a few years ago.


**Key Features and Components:**
1. **Data Retrieval:** Automate the retrieval of UNDP job postings. This will include writing a web scraper (Python) and scrape the full dataset. Additionally, the scraper shall be automatically re-run periodically adding any new datapoints to the raw dataset. 
    - **Python** Python for building the web scraper - mostly using request and beautifulsoup.

2. **Data Storage:** Store the scraped raw data in a Cloud database. I am aiming to store the data in Microsoft Azure since it is most relevant for my work. One initial idea was to write the raw data from scraping in a datalake first and then store the transformed structured data into a datawarehouse and expose the final (gold-standard) dataset from a Azure Datawarehouse to the web application. 
    - **Microsoft Azure (SQL)** Microsoft Azure Datalake, Datawarehouse, DataFactory - to be determined what serves my purpose best. But I am planning to store the data on Azure.
    - **Apache Airflow:** Automate the data retrieval and storage processes using Airflow DAGs to ensure data is updated periodically.  

3. **Data Transformation:** ETL. This step will include the ETL - mostly transformation of the data. Currently, I am thinking of cleaning and transforming the data using Python. Once the data is in a clean structured format I would like to write a few SQL scripts that exposes partitioned data for analysis. These could be set up with DBT potentially. 
    - **Python** For initial cleaning and transformation.
    - **SQL, DBT** For additional ETL scripting and serving data for analysis.

4. **Data Analysis:** Perform advanced data analysis to uncover insights and answer a few questions I will define along the way. Data analysis will be conducted with Python. Since a lot of the data is in text form the analysis will be NLP heavy. 
 

5. **Interactive Web Application:** The main insights of the transformed data as well as insights from the data analysis shall be displayed in a web application. I am planning to use streamlit for this and make it interactive for the user. 
    - **Streamlit** For web deployment and interactive application.

### Dataset

The dataset will be scraped from https://jobs.undp.org/cj_view_job.cfm?cur_job_id=115937 whereas the scraper must iterate over the job_id. 

There are currently around 120000 job postings online which will result in a multi-dimensional dataset with the same amount of rows. Columns will feature dimensions such as:

	job_id	job_description	title	country	region	year	type_of_contract	post_level	languages_required	staff_category	background	duties_responsibilities	competencies	skills_experiences	language
    
The Capstone project requires a dataset with at least 1Mio rows - but I hope that this is also acceptable since it will require additional scraping effort and the use-case is of relevance for me. 
 


## Potential Use Cases

1. **Real-Time Economic Monitoring:** Continuously monitor and analyze the economic indicators and financial markets to provide real-time insights for economists, policymakers, and financial analysts.
2. **Predictive Analytics:** Use historical data to develop predictive models that forecast future economic and financial trends.
3. **Risk Management:** Help financial institutions and businesses manage risk by understanding the impact of economic changes on financial markets.
4. **Investment Strategies:** Inform investment strategies by identifying correlations between macroeconomic indicators and market performance.
5. **Policy Impact Analysis:** Evaluate the impact of government interventions on the economy and financial markets, providing valuable insights for policy-making.
6. **Credit Card Risk Analysis:** Assess credit card volume and delinquency trends to inform risk management strategies for financial institutions.


**Next Steps:**
- Finalize the project plan.
- Map out all components and add a high-level overview of the components and the interactive (visualisation).
- Set up Azure credits and choose most suiting products. 
- Write web scraper and write data to Azure.
- Set up Airflow to run web scraping periodically. 
- write data cleaning and transformation script and add to automated workflow such that is triggered by Airflow when new data is added.
- Test robustness of first environment: Scraping - storing - transforming - storing gold standard transformed data.
- Write analytic scripts.
- Serve analytic insights and data to Streamlit.

**Final Remarks:**
- I am in the self-paced learning group so I hope the data size and perhaps small-scale project is acceptable. 
- This is the first time I am working on a data engineering backend. I think I am confident in the single components but I am not certain on how to "chain" everything together as well as automating scripting with Airflow. This will be the greatest challenge for me. 


