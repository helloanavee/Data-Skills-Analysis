### If Data is the New Oil, Where are the Oil Fields? 
# Identifying In-Demand Job Skill Segments in the Philippine Data Industry

## A Quick Overview
The Data industry has experienced substantial growth, creating opportunities for both companies and specialists. Navigating this dynamic field is a continual challenge as professionals adapt their skills to evolving industry demands.

**This study focuses on identifying pivotal skills for roles in the Philippine data industry**, providing aspiring professionals with insights for strategic skill development and targeted career growth. 

Ultimately, this study aims to address the question: **What are the current, in-demand job segments of the Philippine Data Industry, and what corresponding skills are most needed in each job segment?**

[Read the full report here](https://helloanavee.github.io/data-skills-analysis/data-skills.html)

## Data Source and Description
JobStreet PH, a prominent online hiring platform, was scraped. The data scraped contained different features, important of which are the:
- `jobTitle` - title of the job
- `classification` - or the industry of the job
- and the `jobDetails` - contains the description of the job post.

## Methodology
The methodology used to collect and analyze the data is summarized below:

1. Data Collection
<br> We first web-scraped job posting data from JobStreet, using “data” and “Philippines” as queries to filter relevant job posts. Job posts were further refined, as only postings that contained the word "data" in either the job title, job description, or teaser were used. This returned 2,681 rows of job posts.
   
2. Data Cleaning
<br> Second, we cleaned job details text and job data. The `jobDetails` field was cleaned to remove Unicode characters, and combined words were separated (eg. "skillProficient" to "skill Proficient"). Since the job details hold the key skills for analysis, cleaning this data was crucial.

3. Data Analysis
<br> The plan for this project was to use dimensionality reduction to analyze and segment the jobs and their corresponding skills. Because the data was a free-form text, various steps were taken to refine the results and the segmentation created.
<ul>
   <li> <b>Feature engineering</b>
   <br> The `jobDetails` is a freeform text for the company to write all about the job and the company, and as such also contains details about the company, benefits, working hours, and skills needed for the job. We realized that the results get muddled because of the words that come from this.
   <br>
   <br> We created a new feature `skill` from the `jobDetails` feature. All words after the word "skill" or "experience" are put in the column `skill` as companies tend to write about the skills needed for the job in the likes of "Preferably with experience in" or "Skill Required:".
   </li>
   <br>
   <li> <b>TF-IDF vectorization</b>
   <br> In the end, the analysis used 2 columns from the dataset: the `classification` and the `skills` columns. The words in the `skills` column were vectorized for data processing.
   <br>
   <br> The Stop words used in the vectorization included SKLearn's English words, and also customized stop words containing business words (eg. "retirement", "workday").
   </li>
   <br>
   <li> <b>Dimensionality reduction</b>
   <br> We used dimensionality reduction techniques, specifically Truncated SVD, to simplify the job post data and find the most important features (or words).
   <br>
   <br> The singular vectors of the words were turned into bar graphs, signifying the axis of the words defining that feature.
   <br>
   <br> The bar graphs were also turned into word clouds for easier analysis and comparison.
   </li>
</ul>

## Analysis and Key Insights
Word clouds containing the industry of the job and the related "skill" words show the skills of certain groups of industries. The key insights from the analysis show:

- The primary job segments in data-related positions emerge from the Accounting, Call Centre and Customer Service, and Information & Communication Technology domains.
- Working with clients and communication skills emerged as the persistent and prevailing skill wanted across many job segments.
- While career shifters and students focus on hard skills, it was shown here that employers value core competency and soft skills that help them solve their problems, rather than specific technical skills.

In the result, the study shows the importance of not only technical proficiency (SQL, Excel) but also soft skills and core competencies, such as strong communication, client interaction, and customer-centricity. It can be concluded that for professionals to thrive across industries in the Philippines, it is not only important to be technically knowledgeable, but also to have soft skills such as communication and client management.

[Read the full report here](https://helloanavee.github.io/data-skills-analysis/data-skills.html)

## About the Project
This project was done as part of our Data Mining and Wrangling class in our MS Data Science program at the Asian Institute of Management.

### Authors
- Paulo Medina
- Gregory Uy
- Ana Vasquez
- Gian Servanez

MSDS 2024
