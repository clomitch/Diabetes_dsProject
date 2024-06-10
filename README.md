## Project Objective
Gain practical experience in the entire data science workflow by exploring and manipulating the dataset found to create a model to predict diabetes.

## The Dataset
The Behavioral Risk Factor Surveillance System (BRFSS) is a key health-related telephone survey system that gathers state-specific data on U.S. adults to track preventive health behaviours and risks associated with chronic diseases, injuries, and some preventable infectious diseases. Launched in 1984 and now encompassing all 50 states, the District of Columbia, and three U.S. territories, the BRFSS assesses various factors including tobacco use, health care coverage, knowledge of HIV/AIDS prevention, physical activity levels, and fruit and vegetable consumption. It is the largest continuously conducted health survey system in the world, completing over 400,000 adult interviews each year, providing critical data to guide health policies and programs.
The 2015 dataset will be used for this project since it is the most recent dataset published in a format with which could be easily manipulated with the available tools.

## Preprocessing the Data
All columns were encoded by the CDC and corresponding documentation for the dataset was published with their dataset. Though some columns did not have missing values they are instances of a label code for a missing value. For present null values in numerical columns they were filled with the mean and for missing categorical data they were filled with the mode of the column. In the case of the target variable however, null values (encoded or not) were removed from the dataset and converted to a binary column (having only one of two values in each entry).

## Feature Selection and Engineering
The published dataset has a total of 330 columns. Columns to be used in the creation of a predictive model were selected based on known information on diabetes and the completeness of the data within the column. As such columns with predominantly null values were eliminated. A total of 18 columns were selected for the training of the predictive model. The columns selected and the data they are capturing are as follows:


Variable | Data Being Captured | Value Label
---------|------------------------------------------|-------------------------
SEX | The gender of the respondent | 1: Male 2: Female
_RFHLTH | Adults with good or better health | 1: Good or Better Health; 2: Fair or Poor Health; 9: Don’t know/Not sure, Refused or Missing
_HCVU651 | Adults aged 18-64 who have any form of healthcare coverage | 1: Have Healthcare Coverage; 2: Do not have Healthcare Coverage; 9: Don’t know/Not Sure, Refused or Missing; 
_RFHYPE5 | Adults who have been told they have high blood pressure by a doctor, nurse, or other health professional | 1: No; 2: Yes; 9: Don’t know/Not Sure, Refused or Missing
_RFCHOL | Adults who have had their cholesterol checked and have been told by a doctor, nurse, or other health professional that it was high | 1: No; 2: Yes; 9: Don’t know/Not Sure, Refused or Missing
_MICHD | Respondents that have ever reported having coronary heart disease (CHD) or myocardial infarction (MI) | 1: No; 2: Yes; 9: Not asked or Missing
_ASTHMS1 | Computed asthma status | 1: Current; 2: Former; 3: Never; 9: Don’t know/Not Sure, Refused or Missing
_DRDXAR1 | Respondents who have had a doctor diagnose them as having some form of arthritis | 1: Diagnosed with arthritis; 2: Not diagnosed with arthritis
_AGEG5YR | Fourteen-level age category | 1: Age 18 to 24; 2: Age 25 to 29; 3: Age 30 to 34; 4: Age 35 to 39; 5: Age 40 to 44; 6: Age 45 to 49; 7: Age 50 to 54; 8: Age 55 to 59; 9: Age 60 to 64; 10: Age 65 to 69; 11: Age 70 to 74; 12: Age 75 to 79; 13: Age 80 or older; 14: Don’t know/Refused/Missing
_BMI5CAT | Four-categories of Body Mass Index (BMI) | 1: Underweight; 2: Normal Weight; 3: Overweight; 4: Obese
_INCOMG | Income categories | 1 Less than $15,000; 2: $15,000 to less than $25,000; 3: $25,000 to less than $35,000; 4: $35,000 to less than $50,000; 5: $50,000 or more; 9: Don’t know/Not sure/Missing 
_SMOKER3 | Four-level smoker status: Everyday smoker, Someday smoker, Former smoker, Non-smoker | 1: Current Smoker - now smokes every day; 2: Current Smoker - now smokes some day; 3: Former Smoker; 4: Never Smoked; 9: Don’t know/Refused/Missing
_DRNKWEK | Calculated total number of alcoholic beverages consumed per week | 0: Did not drink; 1-98999: Number of drinks per week; 99900: Don’t know/Not Sure/Refused/Missing
_FRUTSUM | Total fruits consumed per day | 0-99998: Number of fruits consumed per day
_VEGESUM | Total vegetables consumed per day | 0-99998: Number of vegetables consumed per day
_PACAT1 | Physical Activity Categories | 1: Highly Active; 2: Active; 3: Insufficiently Active; 4: Inactive; 9: Don’t know/Not Sure/Refused/Missing
_PAREC1 | Aerobic and Strengthening Guideline | 1: Met Both Guidelines; 2: Met Aerobic Guidelines Only; 3: Met Strengthening Guidelines Only; 4: Did not meet Either Guidelines; 9: Don’t know/Not Sure/Refused/Missing
DIABETE3 | Diagnosed with diabetes | 0: Not diagnosed with Diabetes; 1: Diagnosed with Diabetes


# Project Findings and Insights
Known habitual/risk behaviours were not generally found among respondents who are diabetics. This is as a result of the respondents awareness of their illness and are taking the necessary measures to manage their illness. Other findings include:
A higher percentage of respondents with BMI Category Obese had diabetes when compared to the other BMI Categories.
A larger percentage of respondents who have reported a Coronary Heart Disease or Myocardial Infarction also had diabetes whilst a much lower percentage was observed in those who did not report CHD or MI.

Given that the data collected and compiled in this dataset was done so with multiple chronic illnesses in mind the data is not necessarily specific to any of the chronic illnesses.

The final model created was a Gradient Boosting Machine with an accuracy of 85.3% and precision 81.99%.


