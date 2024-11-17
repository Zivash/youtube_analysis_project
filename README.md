# YouTube Video Data Analysis

This project performs web crawling, data cleaning, analysis, and machine learning on YouTube video data using **BeautifulSoup**, **Pandas**, **Matplotlib**, **Seaborn**, and **Scikit-learn**. The data is collected from the website **kworb.net**, which aggregates YouTube statistics. The goal is to analyze and predict YouTube video metrics such as views, likes, comments, and more.

## Table of Contents
1. [Usage](#usage)
2. [Data Acquisition](#data-acquisition)
3. [Data Cleaning & Transformation](#data-cleaning--transformation)
4. [Visualization](#visualization)
5. [Machine Learning](#machine-learning)

---

## Usage

1. **Run the Crawling:**
   - Collect data from **kworb.net**, performs data cleaning, creates visualizations, and applies regression models to predict YouTube video metrics.
   
   - Make sure to have the required libraries installed before running the script.
   
   - After running, it will generate a file named `Final Clean.csv` with the cleaned data and a series of visualizations for insights.

2. **Data Outputs:**
   - The cleaned data is saved in the CSV file `Final Clean.csv`.
   - Visualizations such as histograms, pie charts, scatter plots, and regression plots will be shown as output.

---

## Data Acquisition

This script collect the following data from the **kworb.net** website:

- **Top YouTube videos for a given year (e.g., 2022)**
- **Details for each video:**
  - Song Name
  - Channel Name
  - Duration
  - Views, Likes, Comments
  - Language
  - Published Date and Time
  - Allowed Countries
- **Channel Statistics:**
  - Subscribers Count
  - Total Views
  - Video Count

The script uses **BeautifulSoup** to extract data from the HTML content of web pages.

---

## Data Cleaning & Transformation

The script performs the following steps to clean and preprocess the scraped data:

1. **Handling Missing Data:**
   - Missing values in "Channel Country" are backfilled.
   - "Likes" and "Comments" are filled with the mean of their respective columns.

2. **Conversion of Columns:**
   - Converts "Song Name," "Published Date," "Published Time," and "Duration Time" into numeric formats.
   - Duration time is converted from minutes and seconds into a decimal value representing minutes.

3. **Label Encoding:**
   - The categorical features ("Language," "Channel Name," and "Channel Country") are converted to numeric labels using **LabelEncoder**.

4. **Filtering:**
   - Rows with missing "Duration Time" or "Channel Published Date" are removed.

---

## Visualization

The script generates various visualizations to explore the data:

1. **Histograms:**
   - Video count by "Published Date."
   - Frequency distribution of "Views" and "Duration Time."

2. **Pie Chart:**
   - Language distribution (English vs. Other Languages).

3. **Scatter Plot:**
   - Relationship between "Channel Published Date" and "Subscribers."

4. **Bar Chart:**
   - Average views per year.

5. **Heatmap:**
   - Correlation matrix between features like "Views," "Likes," "Comments," and "Video Count."

6. **Box Plot:**
   - Distribution of "Countries Allowed."

---

## Machine Learning

The script applies **Linear Regression** and **Random Forest Regression** models to predict the number of **Views** for YouTube videos based on features like:

- "Likes"
- "Comments"
- "Subscribes"
- "Published Date"
- "Language"
- "Channel Country"
- "Video Count"
- "Duration Time"

The models are trained on a training set and evaluated on a test set, with performance metrics (R-squared) outputted.
