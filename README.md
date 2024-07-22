What and Where are the World's Oldest Businesses
Brief Description:
This project aims to explore and analyze the oldest continuously operating businesses in the world, their founding years, categories, and geographical distribution.

Table of Contents
Introduction
Installation
Usage
Notebook Overview
Dependencies
Contributing
License
Acknowledgements
Introduction
This project involves a detailed analysis of the world's oldest businesses, their historical significance, and their distribution across various countries and continents. Using SQL queries and visualizations, the notebook uncovers interesting insights about these businesses.

Installation
Instructions to set up the project locally:

Clone the repository:
bash
Copy code
git clone https://github.com/your_username/your_repository.git
Navigate to the project directory:
bash
Copy code
cd your_repository
Create and activate a virtual environment:
bash
Copy code
python3 -m venv venv
source venv/bin/activate   # On Windows, use `venv\Scripts\activate`
Install the required dependencies:
bash
Copy code
pip install -r requirements.txt
Usage
Guidelines to use or run the notebook:

Open the Jupyter notebook:
bash
Copy code
jupyter notebook "What and Where are the World's Oldest Businesses.ipynb"
Run the cells sequentially to reproduce the analysis and results.
Notebook Overview
Summary of the notebook structure and contents:

Cell Types and Count
Total Cells: 18
Cell Types:
Markdown: 9
Code: 9
Sections
Introduction and Objectives
Description and goals of the analysis.
Data Loading and Preprocessing
Steps to load and clean the data.
Example query:
sql
Copy code
%%sql 
postgresql:///oldestbusinesses

-- Select the oldest and newest founding years from the businesses table
SELECT 
    MIN(founding_year) AS oldest,
    MAX(founding_year) AS newest
FROM businesses;
Exploratory Data Analysis (EDA)
Visualizations and initial analysis of the data.
Oldest Business Analysis
Count and details of businesses founded before 1000 AD.
Example query:
sql
Copy code
%%sql

-- Get the count of rows in businesses where the founding year was before 1000
SELECT 
    COUNT(*) 
FROM businesses
WHERE founding_year < 1000;
Category Analysis
Analysis of business categories and their distribution across continents.
Example query:
sql
Copy code
%%sql

-- Select the category and count of category (as "n")
-- arranged by descending count, limited to top 10
SELECT 
    category, 
    COUNT(*) AS n 
FROM businesses 
GROUP BY category 
ORDER BY n DESC 
LIMIT 10;
Dependencies
List of major libraries and dependencies used in the notebook:

Python 3.6.7
Jupyter Notebook
SQLAlchemy
Pandas
Matplotlib
Postgresql
