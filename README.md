# EMPLOYEE-PERFORMANCE-ANALYTICS-USING-PYTHON

Project Report
Submitted by: Jetlin Joseph
Batch:DA 55
Institution: Entri
Academic Year: 2026


1. Abstract
Employee performance analytics is an important application of data analysis that helps organizations understand workforce performance, employee satisfaction, training participation, compensation, and employee attrition.
This project analyzes an employee performance and HR analytics dataset using Python. The dataset originally contained 3,570 employee records. Following duplicate removal and data preprocessing, the working dataset contained 3,500 records and 19 columns.
The analysis was performed using Pandas and NumPy for data manipulation, Matplotlib and Seaborn for data visualization, and Plotly for interactive analysis. Data cleaning, descriptive statistics, categorical frequency analysis, correlation analysis, department-level comparisons, and attrition analysis were conducted.
The project aims to identify patterns in employee performance, salary distribution, job satisfaction, training hours, and attrition. The results can help demonstrate how data analytics supports evidence-based HR decision-making. The conclusions and recommendations are based on the patterns observed in the dataset and should be interpreted within the limitations of the available data.
 
2.Introduction
Human Resource Management plays a significant role in organizational performance. Employees contribute to productivity, operational efficiency, innovation, and business growth. Understanding employee-related data can help organizations identify workforce trends and areas that may require further investigation.
Employee Performance Analytics applies statistical techniques and data visualization to employee information. It can help HR teams examine performance scores, compensation, job satisfaction, training participation, work hours, absenteeism, and attrition.
In this project, Python is used to explore an employee HR analytics dataset. The analysis focuses on understanding the distribution of employee characteristics, comparing departments, examining relationships between numerical variables, and visualizing workforce indicators.
The project demonstrates how data cleaning, exploratory data analysis, and visualization can convert raw employee records into useful information for organizational decision-making.

3. Problem Statement
Organizations may collect large volumes of employee information without having a clear understanding of the patterns within that information. Without systematic analysis, it can be difficult to compare departmental performance, understand employee satisfaction, examine compensation differences, or identify patterns in employee attrition.
The problem addressed by this project is how to use Python-based data analytics techniques to explore employee information, identify meaningful patterns, and present the results in a clear and understandable format.
The project also aims to demonstrate the importance of data quality, appropriate statistical methods, and responsible interpretation when analyzing HR data.

4. Project Objectives
The main objectives of this project are:
To load and examine an employee HR analytics dataset using Python.
To clean the dataset by handling missing values and duplicate records.
To standardize column names and correct data types.
To identify potential outliers and investigate invalid or inconsistent values.
To perform descriptive statistical analysis of numerical variables.
To examine the distribution of employees across departments, job roles, and education levels.
To compare salary, performance, and job satisfaction across departments.
To calculate attrition rates using records with known attrition outcomes.
To visualize relationships between variables such as training hours and performance scores.
To create interactive visualizations that support further exploration.
To derive practical recommendations where the data provides sufficient evidence.

5. Dataset Description
5.1 Dataset source
The dataset was loaded from a CSV file hosted on GitHub.
Dataset URL:
https://raw.githubusercontent.com/Jetlin-joseph/Employee-Performance-Analytics-Project/main/employee_performance_hr_analytics_3570.csv

5.2 Dataset dimensions
Attribute
Description
Original records
3,570
Records after duplicate removal
3,500
Columns in the cleaned dataset
19
Duplicate rows after cleaning
0
Missing values after preprocessing
0

5.3 Important columns
Column
Description
employee_id
Employee identifier
age
Employee age
gender
Recorded gender category
department
Department to which the employee belongs
job_role
Employee's job role
experience_years
Years of professional experience
education_level
Recorded education level
monthly_salary
Monthly salary
work_hours_per_week
Weekly working hours
overtime_hours
Overtime hours
performance_score
Recorded performance score
projects_completed
Number of completed projects
training_hours
Training hours
job_satisfaction
Recorded job satisfaction score
absence_days
Number of absence days
promotion_last_5_years
Promotion indicator
attrition
Recorded employee attrition status
joining_year
Year the employee joined
employee_tenure
Calculated employee tenure

The employee_tenure column was derived using the reference year 2026 minus the joining year. This calculation assumes that tenure is measured in calendar years; it may differ from exact completed years of service.

6. Tools and Technologies Used
Python: Programming language used for data analysis.
Google Colab: Cloud-based notebook environment used to execute Python code.
Pandas: Used for data loading, data cleaning, grouping, aggregation, and tabular analysis.
NumPy: Used for numerical operations and analytical calculations.
Matplotlib: Used to create charts and plots.
Seaborn: Used for statistical visualizations, including boxplots, bar charts, and correlation heatmaps.
Plotly: Used to create interactive visualizations.
GitHub: Used to host and retrieve the CSV dataset.

7. Data Cleaning and Preprocessing
Data cleaning was performed before conducting exploratory analysis to improve consistency and reliability.
7.1 Loading the dataset
The CSV file was imported into a Pandas DataFrame using pd.read_csv(). The dataset dimensions, column names, data types, missing values, and duplicate records were examined.
7.2 Standardizing column names
Column names were converted to lowercase, leading and trailing spaces were removed, and spaces between words were replaced with underscores. This made the column names easier to use consistently in Python.
7.3 Removing duplicate records
Duplicate rows were identified and removed. The original dataset contained 3,570 rows, and the cleaned dataset contained 3,500 rows after removing 70 duplicate records.
7.4 Handling missing values
Missing numerical values in selected columns, including age, monthly salary, work hours, overtime hours, performance score, training hours, job satisfaction, and absence days, were handled using median imputation.
Missing categorical values in selected columns were replaced with the label Unknown. This preserved the fact that the original value was unavailable instead of assigning an unsupported category.
7.5 Correcting data types
Numerical columns were converted to appropriate numerical types, and the employee identifier was retained as a text-based identifier where applicable. Correct data types support reliable aggregation and visualization.
7.6 Identifying outliers using the IQR method
Potential numerical outliers were investigated using the Interquartile Range method.
The interquartile range is calculated as:
IQR = Q3 − Q1
The conventional lower and upper boundaries are:
Lower boundary = Q1 − 1.5 × IQR
Upper boundary = Q3 + 1.5 × IQR
Values outside these boundaries are flagged as potential outliers. Such values are not automatically errors. Salary, overtime, and training observations outside the boundaries should be investigated before deciding whether any correction is justified.
7.7 Checking invalid values and inconsistencies
Numerical ranges and categorical values should be reviewed for implausible values, spelling inconsistencies, unexpected categories, and invalid indicators. Categories such as Yes, No, and Unknown must be treated consistently.
A zero-missing-value result after preprocessing does not by itself prove that every value is valid. Validation rules should be checked separately and documented according to the checks actually performed.
7.8 Creating employee tenure
Employee tenure was calculated from the joining year using 2026 as the reference year:
Employee Tenure = 2026 − Joining Year
This derived column supports comparisons of workforce experience and tenure.
7.9 Final validation
After preprocessing, the working dataset contained 3,500 rows and 19 columns, with zero missing values and zero duplicate rows.

8. Exploratory Data Analysis (EDA)
Exploratory Data Analysis was performed to understand the characteristics of the dataset and identify patterns that could be examined further.
8.1 Numerical descriptive statistics
Descriptive statistics were calculated for numerical columns, including the mean, median, minimum, maximum, and standard deviation.
Selected results from the cleaned dataset include:
Variable
Mean
Median
Minimum
Maximum
Age
33.87
34.0
21
60
Experience (years)
11.01
11.0
0
35
Monthly salary
₹85,486.99
₹83,862.50
₹22,000
₹294,275
Weekly work hours
42.06
42.0
30
78
Overtime hours
4.90
3.9
0
57
Performance score
3.15
3.1
1.4
4.8
Projects completed
10.04
10.0
0
25
Training hours
20.77
18.6
0.7
80
Job satisfaction
4.33
4.4
2
5
Absence days
5.12
5.0
0
17

These statistics describe the distribution of the recorded variables. The salary and overtime ranges also indicate that additional distribution and outlier checks can be useful.

8.2 Categorical analysis
Frequency counts were calculated for categorical variables such as gender, department, education level, promotion status, and attrition.
The department counts were:
Department
Employees
IT
688
Operations
601
Sales
568
Finance
517
Marketing
458
Customer Support
337
HR
331

IT has the largest number of records, while HR has the smallest number among the listed departments. These counts describe the dataset and do not necessarily represent the workforce composition of a real organization.

8.3 Correlation analysis
A correlation matrix was created for numerical variables to examine the strength and direction of their linear relationships.
Correlation can help identify variables that move together. However, correlation alone does not demonstrate causation, and a weak linear correlation does not rule out other types of relationships.

8.4 Department comparisons
Department-level summaries were prepared to compare average salary, performance scores, and job satisfaction. These comparisons can identify differences that may warrant further investigation.

8.5 Attrition analysis
Attrition was examined using records with known outcomes. Employees whose attrition status was Unknown were excluded from the attrition-rate denominator.
The cleaned dataset contains 163 records marked Yes, 3,267 marked No, and 70 marked Unknown. Based on known outcomes only, the overall recorded attrition rate is approximately 4.75%.
This rate describes the available dataset and should not be generalized to other organizations without further evidence.

9. Data Visualization
The following visualizations were created or planned as part of the analysis.

9.1 Employee count by department
A bar chart was created to compare the number of employee records in each department. IT had the largest count, with 688 records, while HR had the smallest count, with 331.

9.2 Monthly salary distribution
A histogram was used to examine the distribution of monthly salaries. This visualization helps reveal the concentration and spread of salary values and whether the distribution is skewed.

9.3 Monthly salary by department
A boxplot was created to compare salary distributions across departments. The observed departmental medians appeared broadly similar, around ₹80,000–₹85,000, while some high salary values extended toward ₹290,000. These observations should be confirmed against the chart and detailed summary statistics before making further conclusions.

9.4 Training hours versus performance score
A scatter plot was used to explore the relationship between training hours and performance scores. The visualization allows potential patterns to be examined, but it does not establish that training causes performance changes.

9.5 Attrition distribution

A pie chart was created using known attrition outcomes only. Records marked Unknown were excluded to avoid treating missing outcomes as either employees who left or employees who stayed.

9.6 Numerical correlation heatmap

A correlation heatmap was used to visualize relationships among numerical variables. The heatmap supports identification of potentially related variables for further investigation.

9.7 Average salary by joining year

A line chart was created to compare average monthly salary across employee joining-year cohorts. This represents a comparison between cohorts, not an individual's salary progression over time.

9.8 Attrition rate by department

A department-level bar chart was added to compare the percentage of known employee outcomes marked Yes. The table accompanying the chart includes known employee counts to help readers interpret the percentages.

9.9 Average performance score by department

A bar chart was added to compare average performance scores by department. Department-level employee counts should be reviewed alongside the averages.

9.10 Job satisfaction by department

A boxplot and summary statistics were used to examine job satisfaction across departments. These show differences in recorded scores and their distributions without assuming that departmental membership caused those differences.

9.11 Interactive Plotly visualization

An interactive scatter plot was created using Plotly. Training hours appear on the horizontal axis, performance score on the vertical axis, and color represents department. Hover information includes job role, employee tenure, and job satisfaction.
This interactive chart supports detailed exploration of individual records and comparison between departments.

10. Key Findings and Insights
The following findings are supported by the dataset summaries available at this stage:
Data quality: The working dataset contains 3,500 rows and 19 columns, with no missing values or duplicate rows after preprocessing.
Department distribution: IT has the largest department count at 688, while HR has the smallest at 331.
Age and experience: The mean employee age is 33.87 years, and mean professional experience is 11.01 years.
Compensation: The mean monthly salary is approximately ₹85,487, with a median of ₹83,862.50.
Working hours: Mean weekly work hours are approximately 42.06, and mean recorded overtime hours are 4.90.
Performance: The mean performance score is 3.15.
Training: Mean training hours are approximately 20.77.
Job satisfaction: The mean recorded job satisfaction score is 4.33 on the dataset's scale.
Attrition: Of records with known attrition outcomes, approximately 4.75% are marked Yes.
Further investigation: Departmental differences in attrition, performance, salary, and job satisfaction should be reported using the actual summary tables and charts.
The highest- and lowest-performing departments, the highest departmental attrition rate, and the strength of relationships between training and performance should be inserted after reviewing the corresponding outputs.

11. Recommendations
The following recommendations are proposed as areas for investigation rather than proven interventions.
Review departmental attrition: Investigate departments with comparatively high attrition rates, taking known employee counts into account.
Examine performance differences: Review departments with comparatively lower average performance scores to identify whether additional context, support, or resources may be needed.
Evaluate training effectiveness: Compare training participation with performance outcomes and, where possible, use longitudinal or controlled analyses before concluding that training improves performance.
Monitor employee satisfaction: Use department-level satisfaction patterns to guide further employee feedback and engagement assessments.
Review compensation distributions: Investigate salary differences while accounting for job role, experience, seniority, and other relevant factors.
Validate outliers: Review extreme salary, overtime, and training values before deciding whether they are valid observations or data errors.
Improve data quality: Maintain clear validation rules, consistent categorical labels, and documented handling of missing values.
Develop a recurring HR dashboard: Consider using an interactive dashboard to monitor performance, attrition, training, and satisfaction indicators over time.
Recommendations should be prioritized only after the relevant results have been verified and additional organizational context is available.

12. Conclusion
    
This project demonstrated the application of Python-based data analytics to an employee HR dataset. The workflow included loading and cleaning data, removing duplicate records, handling missing values, examining descriptive statistics, comparing categories, and creating static and interactive visualizations.
The final working dataset contained 3,500 records and 19 columns. Exploratory analysis provided an overview of employee demographics, compensation, work patterns, performance scores, training participation, job satisfaction, and attrition outcomes.
The project also demonstrated how department-level summaries and visualizations can support the investigation of workforce patterns. The analysis provides a foundation for further research and reporting, although descriptive patterns should not be interpreted as causal relationships.
Overall, the project achieved its core objective of demonstrating how data analysis and visualization can make employee information easier to understand and evaluate.

13. Limitations and Future Scope
    
13.1 Limitations
The analysis is based on a single dataset, and its representativeness of an actual organization's workforce is not established.
Missing values were imputed, which can affect distributions and statistical summaries.
Categorical values marked Unknown remain uncertain even though the cleaned dataset contains no null values.
The attrition rate is based only on records with known outcomes.
The reference year 2026 was used to calculate tenure; this should be documented and updated if a different reporting period is required.
The IQR method identifies potential outliers but does not determine whether they are errors.
Department-level averages may conceal differences between job roles, seniority levels, or other employee groups.
Correlation and descriptive statistics do not establish causation.

13.2 Future scope
Future improvements could include:
Building an interactive HR dashboard with filters and key performance indicators.
Performing statistical significance tests for departmental comparisons where assumptions are satisfied.
Developing and evaluating an attrition prediction model if the data quality, sample size, and target definition support it.
Comparing performance by job role, experience, training participation, and tenure.
Investigating outliers and validating questionable values with reliable source records.
Incorporating additional time periods to study changes in attrition, compensation, and performance.
Using explainable analytical models to investigate potential drivers of employee outcomes.
Reviewing fairness and privacy considerations before using employee analytics to inform HR decisions.

14. References
15. 
GitHub. Employee Performance HR Analytics Dataset.
https://raw.githubusercontent.com/Jetlin-joseph/Employee-Performance-Analytics-Project/main/employee_performance_hr_analytics_3570.csv
Pandas Documentation.
https://pandas.pydata.org/docs/
NumPy Documentation.
https://numpy.org/doc/
Matplotlib Documentation.
https://matplotlib.org/stable/
Seaborn Documentation.
https://seaborn.pydata.org/
Plotly Python Documentation.
https://plotly.com/python/
Google Colab.
https://colab.research.google.com/
