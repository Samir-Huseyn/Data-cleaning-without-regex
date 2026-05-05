# Data-cleaning-without-regex

🎤 Concert Tour Data Cleaning & Analysis
This project demonstrates a complete data cleaning and analysis pipeline using Python and Pandas. The primary objective was to take a "raw" and "messy" dataset (scraped from Wikipedia or similar sources) and transform it into a clean, analysis-ready format using logic-based string manipulation instead of complex Regular Expressions (Regex).

🚀 Overview
The script processes a dataset containing the highest-grossing concert tours by female artists. It handles common data issues such as:

Inconsistent column naming.

Currency symbols and thousands separators.

Wikipedia-style citations and footnotes (e.g., [a], †, ‡).

Missing values (NaNs).

🛠 Tech Stack
Python: The core programming language.

Pandas: For high-performance data manipulation and cleaning.

Matplotlib: For generating visual insights through charts.

🧹 Data Cleaning Highlights
The cleaning process was performed using an "algorithmic" approach without Regex:

Financial Sanitization: Dollar signs ($) and commas (,) were removed using successive .str.replace() calls. Footnotes like [b] or [e] were specifically targeted and removed before converting the data to float.

Footnote Stripping: Wikipedia markers like †, ‡, and * were removed using .str.split().str[0]. This effectively "cuts" the string at the first sign of a special character, keeping only the clean title.

Reference Removal: Citation brackets like [1] were removed by splitting the string at the open bracket [ and selecting the first part of the result.

Missing Data Management: Statistical columns like peak and all time peak were filled with 0 using .fillna(0) to ensure mathematical operations wouldn't fail.

📊 Analysis & Visualization
The script performs the following analyses:

Artist Performance Grouping: Aggregates the total actual gross, total shows, and mean average gross for each artist.

Efficiency Ranking: Sorts tours by the average gross to see which artists earn the most per individual show.

Visual Summary: A Bar Chart is generated to compare the total gross revenue across all artists in the dataset.

📂 How to Run
Ensure you have the required libraries:

Bash
pip install pandas matplotlib
Place your my_file (1).csv in the project directory.

Run the script:

Bash
python main.py
📈 Sample Result
The output includes a cleaned summary table and a bar chart showing that Taylor Swift leads the total gross revenue, followed by artists like Madonna and Beyoncé, once all numeric values are properly formatted.

Pro-Tip for your GitHub:
If you want to make this even better, use plt.savefig('gross_summary.png') in your code and then add ![Artist Gross](gross_summary.png) to this README to show people your results immediately!
