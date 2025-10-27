# propofol-dosage-analysis-IU-Health-Ball-Memorial-Hospital

# Project Background
IU Health Ball Memorial Hospital (BMH), a leading regional teaching hospital within the Indiana University Health system, serves as a major referral center for East Central Indiana. Collaborating with the Director of Pharmacy Services and the Critical Care Research Team, I conduct an analysis to evaluate sedation and pain management patterns in the ICU, specifically examining why propofol infusion rates at BMH are consistently higher than those observed across other IU Health hospitals. Using data extracted from the electronic medical record (EMR) system, this project explores patient characteristics, co-administered sedatives, and propofol outcome measures to uncover patterns driving high-dose propofol use. The resulting insights will inform recommendations to align clinical practice with evidence-based guidelines and support safer, more consistent sedation strategies across the health system.

Insights and recommendations are provided on the following key areas:

•	**Propofol Outcome Measures:** An analysis of the duration and frequency of high dose propofol use (>50 mcg/kg/min), including total infusion hours/days on infusion.

•	**Patient Characteristics Analysis:** Evaluation of demographic factors: sex, age, height, and weight.

•	**Co-Administered Sedatives:** An assessment of pain management effectiveness (measured by RASS or CPOT) in conjunction with sedatives such as dexmedetomidine and fentanyl.

•	**IU Health Hospitals Comparisons:** An evaluation of propofol and co-administered sedatives across IU Health hospitals to identify system-wide variation.


The R Code used to create the cleaned analysis dataset, perform the exploratory data analysis, perform variable selection, fit the GLM, and evaluate evidence of interaction can be found here: [Propofol Dosage Analysis R Code](https://github.com/jasminsc16/propofol-dosage-analysis-IU-Health-Ball-Memorial-Hospital/blob/main/Propofol%20Dosage%20Analysis%20IU%20Health%20Ball%20Memorial%20Hospital.Rmd)



# Data Structure & Initial Checks

The hospital's extracted data from the electronic medical record (EMR) system as seen below consists of one table with a total row count of 72 and a total column count of 44. IBW, COVID, IVDA_Hx, Triglyc_Max, Creatinine, CrCl, Map_Range, and HR_Range_low will all be dropped from the final analysis dataset since they are not relevant to the analysis being completed. So, the official total column count is 36. A description of the table can be found here: [Propofol Dosage Analysis Data Structure Table](https://github.com/jasminsc16/propofol-dosage-analysis-IU-Health-Ball-Memorial-Hospital/blob/main/Propofol%20Project_Data%20Structure%20Table.jpeg)

To prepare the dataset for analysis, an initial data cleaning process was conducted. Variables not relevant to the study’s objectives — including IBW, COVID, IVDA_Hx, Triglyc_Max, Creatinine, CrCl, Map_Range, and HR_Range_low — were removed to streamline the analysis dataset. Placeholder entries “x” and “X” were standardized to NA values to ensure consistency in identifying missing data.

Patterns of missingness were then visualized using vis_miss(), and appropriate replacements were applied based on variable context (e.g., “Missing” for Height and “NotApp” for non-applicable clinical measures such as Min_Rass, Dex_ord, and Prop_dose_when_Dex).

Prior to this stage, the dataset was recovered from a corrupted RDS file and automatically transferred to Excel using an AI-assisted data extraction workflow (Claude), ensuring data integrity and preserving all relevant records for subsequent analysis.

