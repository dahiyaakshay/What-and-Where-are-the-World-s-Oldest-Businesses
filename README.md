<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>

<h1>What and Where are the World's Oldest Businesses</h1>

<p><strong>Brief Description:</strong><br>
This project aims to explore and analyze the oldest continuously operating businesses in the world, their founding years, categories, and geographical distribution.</p>

<h2>Table of Contents</h2>
<ol>
    <li><a href="#introduction">Introduction</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#notebook-overview">Notebook Overview</a></li>
    <li><a href="#dependencies">Dependencies</a></li>
    <li><a href="#contributing">Contributing</a></li>
</ol>

<h2 id="introduction">Introduction</h2>
<p>This project involves a detailed analysis of the world's oldest businesses, their historical significance, and their distribution across various countries and continents. Using SQL queries and visualizations, the notebook uncovers interesting insights about these businesses.</p>

<h2 id="usage">Usage</h2>
<p><strong>Guidelines to use or run the notebook:</strong></p>
<ol>
    <li>Open the Jupyter notebook:
        <pre><code>jupyter notebook "What and Where are the World's Oldest Businesses.ipynb"</code></pre>
    </li>
    <li>Run the cells sequentially to reproduce the analysis and results.</li>
</ol>

<h2 id="notebook-overview">Notebook Overview</h2>
<p><strong>Summary of the notebook structure and contents:</strong></p>

<h3>Cell Types and Count</h3>
<ul>
    <li><strong>Total Cells:</strong> 18</li>
    <li><strong>Cell Types:</strong>
        <ul>
            <li>Markdown: 9</li>
            <li>Code: 9</li>
        </ul>
    </li>
</ul>

<h3>Sections</h3>
<ol>
    <li><strong>Introduction and Objectives</strong>
        <ul>
            <li>Description and goals of the analysis.</li>
        </ul>
    </li>
    <li><strong>Data Loading and Preprocessing</strong>
        <ul>
            <li>Steps to load and clean the data.</li>
            <li>Example query:
                <pre><code>%%sql 
postgresql:///oldestbusinesses

-- Select the oldest and newest founding years from the businesses table
SELECT 
    MIN(founding_year) AS oldest,
    MAX(founding_year) AS newest
FROM businesses;</code></pre>
            </li>
        </ul>
    </li>
    <li><strong>Exploratory Data Analysis (EDA)</strong>
        <ul>
            <li>Visualizations and initial analysis of the data.</li>
        </ul>
    </li>
    <li><strong>Oldest Business Analysis</strong>
        <ul>
            <li>Count and details of businesses founded before 1000 AD.</li>
            <li>Example query:
                <pre><code>%%sql

-- Get the count of rows in businesses where the founding year was before 1000
SELECT 
    COUNT(*) 
FROM businesses
WHERE founding_year &lt; 1000;</code></pre>
            </li>
        </ul>
    </li>
    <li><strong>Category Analysis</strong>
        <ul>
            <li>Analysis of business categories and their distribution across continents.</li>
            <li>Example query:
                <pre><code>%%sql

-- Select the category and count of category (as "n")
-- arranged by descending count, limited to top 10
SELECT 
    category, 
    COUNT(*) AS n 
FROM businesses 
GROUP BY category 
ORDER BY n DESC 
LIMIT 10;</code></pre>
            </li>
        </ul>
    </li>
</ol>

<h2 id="dependencies">Dependencies</h2>
<p><strong>List of major libraries and dependencies used in the notebook:</strong></p>
<ul>
    <li>Python 3.6.7</li>
    <li>Jupyter Notebook</li>
    <li>SQLAlchemy</li>
    <li>Pandas</li>
    <li>Matplotlib</li>
    <li>Postgresql</li>
</ul>

<h2 id="contributing">Contributing</h2>
<p><strong>Instructions for contributing to the project:</strong></p>
<ol>
    <li>Fork the repository.</li>
    <li>Create a new branch (<code>git checkout -b feature/your_feature</code>).</li>
    <li>Commit your changes (<code>git commit -m 'Add your feature'</code>).</li>
    <li>Push to the branch (<code>git push origin feature/your_feature</code>).</li>
    <li>Open a pull request.</li>
</ol>

</body>
</html>
