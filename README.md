# Lead-Conversion-Optimization:
 A Data-Driven Approach for X Education's Online Course Sales,  A Logistic Regression Analysis for Enhancing Lead Conversion in X Education's Online Courses

 ## Description

An education company named X Education sells online courses to industry professionals. On any given day, many professionals who are interested in the courses land on their website and browse for courses. The company markets its courses on several websites, search engines, and even social media sometimes.Once these people land on the website, they might browse the courses, fill out a form for the course, or watch some videos. When these people fill out a form with their email address or phone number, they are classified as leads. Moreover, the company also gets leads through past referrals. Once these leads are acquired, employees from the sales team start making calls, writing emails, etc. Through this process, some of the leads get converted into successful sales, while most of the leads do not. The typical lead to successful sale conversion rate at X education is around 30% .he CEO, in particular, has given a ballpark estimate of the target lead conversion rate as being around 80%.

## Objective

The primary objective of this data science project is to employ logistic regression modeling techniques to analyze and optimize the lead conversion process for X Education's online courses. By leveraging historical data on website interactions, form submissions, and sales outcomes, the project aims to identify key factors influencing lead conversion. Ultimately, the goal is to develop a predictive model that can assist in prioritizing leads and implementing targeted strategies, with the aim of achieving the CEO's target lead conversion rate of 80%.


## Dataset
[Leads.csv](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/files/13882886/Leads.csv)

[Leads Data Dictionary.xlsx](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/files/13882885/Leads.Data.Dictionary.xlsx)

## Language and Libraries
Language : Python

Libraries
- Numpy
- Pandas
- Matplotlib
- Seaborn
- statsmodel
- Sklearn

## Project Approach

### **Data Exploration**
     - Dataset informationa and description
![Dataset](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/72bb613c-959f-4fc7-82b7-038827c4340a)
![descrition](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/5494c387-2b04-422b-9fc8-795b9b10e4b8)
![data_info](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/06836f2e-7128-434b-83de-92dc469cf9dd)
### **Data Processing and Exploratory data Analysiss**
Different features vs convered(target veriable)
- Categorical Variables vs Target Variable(Converted)
  
![country](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/0f21598d-fa78-4c25-b965-a10927bfe3bd)
![city](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/f1abb9c0-b86b-4c75-91fa-7ebe90519fd2)
![specialization](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/9cf7a4f6-7573-4c0d-829f-045e5e23ece1)
![whats occupation](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/893f8ef7-bfea-447c-9021-fa17fc5ac804)
![what matters](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/58be90b9-382f-48bb-a107-ac2a05d8188d)
![Tags](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/020ba48c-e0ec-4169-9f98-bfabf65dbe2e)
![Lead_source](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/af9ae317-2c94-4b2e-af27-d1c85a5ec4ef)
![Lead_Origin](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/d461cd09-9222-46f3-8758-28a322be1630)
![Last Notable Activity](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/a7352bd8-7f25-4a5d-a053-b0ca16c9db5e)

- Numarical Variables vs Target Variables (Converted)
  
  ![Total_visits](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/fa9902ec-6f2a-4b71-9d73-ac1009d92057)
![N_total_timespent](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/a49482f9-58cf-4c98-b2f9-5662f731b6d4)
![n_page_view](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/cf5274cb-dde0-4f7a-a710-8b842e1186d7)

- After, removing the columns with more than 40% null values and taking dummy variables total fetaures became 57 

### **Model Building**

- used RFE (Recursive Feature Elimination) from sklearn library for getting top 15 features
  ![Top_15_features](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/df7b5347-fbca-440e-b17f-8b1449596c5a)
- used statsmodel library for performing logistic regression and getting p-values and VIF (variance_inflation_factor)
- After removing some features having the high P-value and VIF final feauture summary look like following
- finding optimum cutoff for prediction between probabilites 0.1 to 0.9
  
  ![Optimum_cutoff_teable](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/4d6e64fd-818a-4b4f-a950-9507f4e243e9)
- plotting accuracy sensitivity and specificity for various probabilities
  
  ![PSA_curve](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/813684d8-aa08-4c6e-afa2-9c487d5ab81a)
- by taking Optimum cuttoff as 0.3
- **Accuracy : 92.29%**
- **Sensitivity : 88.21%**
- **Specificity : 95.13%**
- **Precision : 0.88**
- **Recall : 0.91**
- Precession_Recall curve
  
  ![PR_curve](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/e4bac278-1a9f-4a5e-882b-14e2a752230a)
- ROC Curve
  
  ![ROC_curve](https://github.com/SaurabhJaurat7030/Lead-Conversion-Optimization/assets/154229876/53c059b7-a181-4bde-91ae-c5e6b90dde7a)
- Prediction on test data results
  
- **Accuracy : 92.78%**
- **Sensitivity : 91.98%**
- **Specificity : 93.26%**
- **Precision : 0.89**
- **Recall : 0.91**

### **Summary**

1. X Education , An education company named sells online courses to industry professionals. Many interested professionals land on their website.

2. The company markets its courses on several websites like Google. Once these people land on the website, they might browse the courses or fill up a form for the course or watch some videos. When these people fill up a form providing their email address or phone number, they are classified to be a lead

3. Once these leads are acquired, employees from the sales team start making calls, writing emails, etc. Through this process, some of the leads get converted while most do not
The typical lead conversion rate at X education is around 30%

4. X Education gets a lot of leads but its lead conversion rate is very poor . To make this process more efficient, the company wishes to identify the most potential leads, also known as ‘Hot Leads’.

5. If they successfully identify this set of leads, the lead conversion rate should go up as the sales team will now be focusing more on communicating with the potential leads rather than making calls to everyone. We will help them to select the most promising leads, i.e. the leads that are most likely to convert into paying customers.

6. We are required to build a model wherein we need to assign a lead score to each of the leads such that the customers with higher lead score have a higher conversion chance

7. The CEO, in particular, has given a ballpark of the target lead conversion rate to be 80%.

8. To solve this problem we need to use Logistic Regression Model to probability of lead to join the course

9. The provided test data has lots of missing values so we needed to remove first columns with more than 45% null values then null values treatment and combining low frequency values in categorical column and then after doing Univariate and Bivariate analysis we found that
- Total Time Spent on Website
- Last Activity_SMS Sent
- Lead Source_reference
These are the top three variables in my model, that contribute towards lead conversion are

10. The top three variables in my model, that should be focused are:
- Last Activity_SMS Sent 2. Last Source_Direct Traffic 3. Lead Source_Olark Chat

Our Logistic Regression Model is decent and accurate enough, with 92.78% Accuracy on Test Set, 91.98 % Sensitivity and 93.26 % Specificity.

  
   







