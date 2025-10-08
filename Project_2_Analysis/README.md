
# Project 2 Analysis

## Introduction

This second project was created to help job seekers better understand the most valuable skills and roles in the data science market. It aims to identify which skills top employers are looking for and how these skills influence salary levels.   
[Project_2_Analysis.xlsx](Project_2_Analysis.xlsx)

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via [Excel for Data Analytics - Full Course for Beginners](https://www.youtube.com/watch?v=pCJ15nGFgVg&t=35268s), which provides a foundation for analyzing data using Excel. 

It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_all & 🛠️ data_job_skills

         <img width="244" height="328" alt="2_Project_Analysis_Screenshot1" src="https://github.com/user-attachments/assets/f2db319f-2ced-4d13-bef9-ca074d6f3c91" /> <img width="244" height="328" alt="2_Project_Analysis_Screenshot2" src="https://github.com/user-attachments/assets/4c51f597-3b22-433f-8c61-708bf6fb721d" />


#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot3.png](/0_Resources/Images/2_Project_Analysis_Screenshot3.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot4.png](/0_Resources/Images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

#### 💡 Insights

- 📈 There is a clear link between the number of skills required in job postings and the median salary. Jobs like Senior Data Engineer and Data Scientist, which ask for more skills, tend to offer higher pay.
- 💼 Roles that need fewer skills, such as Business Analyst, usually have lower salaries, showing that specialized skills are more valuable in the job market.
    ![2_Project_Analysis_Chart1.png](/0_Resources/Images/2_Project_Analysis_Chart1.png)

#### 🤔 So What

- This trend shows that learning multiple relevant skills can help people reach higher-paying jobs.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles such as Senior Data Engineer and Data Scientist offer higher median salaries both in the US and abroad, showing the global demand for advanced data skills.
- 💰 The salary gap between US and non-US roles is especially noticeable in tech positions, likely due to the large number of tech companies based in the US.

    ![2_Project_Analysis_Chart2.png](/0_Resources/Images/2_Project_Analysis_Chart2.png)

#### **🤔 So What**

- These salary insights are useful for career planning and negotiations, helping both professionals and employers align their expectations with market standards and regional differences.
## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    ![2_Project_Analysis_Screenshot5.png](/0_Resources/Images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    ![2_Project_Analysis_Screenshot6.png](/0_Resources/Images/2_Project_Analysis_Screenshot6.png)

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![2_Project_Analysis_Chart3.png](/0_Resources/Images/2_Project_Analysis_Chart3.png)

#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    ![2_Project_Analysis_Chart4.png](/0_Resources/Images/2_Project_Analysis_Chart4.png)

### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

In this Project I use Excel to uncover valuable insights about the data science job market. I used a dataset from real job postings to analyze job titles, salaries, locations, and key skills. Using Excel tools like Power Query, PivotTables, DAX, and charts, I found that jobs requiring multiple skills—especially in Python, SQL, and cloud technologies—tend to pay more.

