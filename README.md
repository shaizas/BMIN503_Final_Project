# BMIN503/EPID600 Final Project

This repository contains templates for your final written report and GitHub repository. Follow the instructions below to clone this repository, and then turn in your final project's code via a pull request to this repository.


1. To start, **fork** this BMIN503_Final_Project repository.
1. **Clone** the forked repository to your computer.
1. Modify the files provided, add your own, and **commit** changes to complete your final project.
1. **Push**/sync the changes up to your GitHub account.
1. Create a **pull request** on this, the original BMIN503_Final_Project, repository to turn in your final project.


Follow the instructions [here][forking] if you are unsure what the above steps mean.

DUE DATE FOR FINAL VERSION: 12/09/22 11:59PM. This is a hard deadline. Turn in whatever you have by this date.


<!-- Links -->
[forking]: https://guides.github.com/activities/forking/

>TITLE: Philadelphia Landscape Assessment of Social-Demographic Characteristics for Receiving Adequate Prenatal Care in 2020-2021

> ABSTRACT: This project utilized data from the Center for Disease (CDC) WONDER Database 2016-2020 (expanded version), which follows an ad-hoc query system for *the analysis of public health data.* Using a multiple logistic regression model, the study aimed to identify the relationship between four selected maternal characteristics and receiving adequate prenatal care services with an emphasis on migrant populations in Philadelphia County, PA (n=18,084) and compare results state-wide performance in Pennsylvania (n=118,531). 
                
>TEAM DETAILS: This project was discussed with the data team at the City of Philadelphia, Department of Public Health (PDPH) within the Maternal, Child, and Family Health Division (MCFH). Members of the data team, MH and AM, have been initialized for the team's privacy. (Names can be found in the discussion comments of the Canvas Submission). The team consisted of a quantitative data analyst specialist (MP) MPH, CPH and the City's chief medical officer MD, MPP. 

> MH MPH, CPH was involved in assisting the development of the statistical approach. Meetings involved discussion of the best statistical process for the data set. MH recommended using multiple logistic regression and determining if prenatal services have been provided adequately through a dichotomous approach (Y/N to receiving adequate prenatal care) to simplify data interpretation. She is in the process of cleaning the Live Births data for Philadelphia (n=20,000) from this past year so we can apply the coding methods to a more recent and (potentially more) accurate dataset. The intended dataset would specifically consider undocumented immigrants determined via insurance status which is recorded within birth certificate forms in Philadelphia County.  We are awaiting IRB approval in the meantime, the CDC dataset was used as a preliminary exercise to ensure the steps in code worked acurrately. 

>AM MD, MPP acted in a supervisory role as chief medical officer to guide the selection of maternal social characteristics for assessment and identify the project's social impact. There is currently very little understanding of migrant research and their respective health outcomes in Philadelphia, especially for maternal care.. 

>The coding material is intended to be used with a different dataset to utilize the findings to identify potential social barriers. The information from this project will ideally help confirm the need for a larger strategy proposal by acting as a *City Landscape Assessment* for developing a healthcare service delivery model for prenatal care for migrant individuals and/or undocumented immigrants. 

>https://github.com/shaizas/BMIN503_Final_Project 

### Introduction 
Describe the problem addressed, its, and some background to motivate the problem. Explain why your problem is interdisciplinary, what fields can contribute to its understanding, and incorporate background related to what you learned from meeting with faculty/staff.

>Comprehensive prenatal care has been shown to lead to improved health outcomes for both mothers and newborns.1 If sought early in a birthing person’s pregnancy, prenatal care can be used as an effective preventative measure for adverse health outcomes, such as severe maternal morbidity and low neonatal birth weight.2,3 Services are typically established within the first six to eight weeks of pregnancy, following twelve to fifteen visits in total after the initial visit.4 The current model practiced within the United States recommends that patients visit monthly until twenty-eight weeks, bi-weekly until thirty-two weeks, and weekly until delivery.4 Visits are critical to promoting a safe delivery by effectively monitoring the patient's progress and development of the fetus. Healthcare providers are responsible for providing supportive care through medical screenings, lab testing for birth anomalies, image testing, and education (parenting, pregnancy materials, infant feeding).2 Services often include psychosocial support to address substance use, resources for domestic violence, mental health services, avenues for financial aid, and nutritional needs.4

> The City of Philadelphia has a highly urban landscape, with individuals belonging to diverse social and cultural backgrounds that may hinder access to quality prenatal care. In 2020, only 52% of birthing persons sought care within the first trimester in Philadelphia, which is comparatively much lower than the national average of 77%.5,6 The Philadelphia Maternal Mortality Review Committee (MMRC) found that 32% of all pregnancy-associated deaths occurred in birthing persons who didn’t opt in for prenatal care or were too late (third trimester).6  Of these deaths, 69% of individuals, had multiple co-morbidities that would have been screened and identified appropriately had the patient attended regular prenatal visits.6 These statistics capture the challenges from potential barriers patients may face to receiving adequate maternal and child care in Philadelphia.  Common barriers include financial constraints, transportation access, lifestyle limitations (childcare, paid time off from work), and overall distrust of the medical field stemming from perceived discrimination and cultural practice.7 Social indicators such as race, age, education levels, socio-economic status have shown to have associations with receiving adequate prenatal care, however nativity has never been explored in the literature for Philadelphia.  

> Identifying currently underserved populations that are receiving inadequate access to prenatal services is critical for equitably promoting better maternal and child outcomes. However, there is very limited research in identifying potential social barriers migrant populations face in Philadelphia County.

>**This project aims to determine the relationship between maternal demographic characteristics for birthing persons, especially immigrant populations, to assess which demographic of individuals may be undeserved in receiving adequate prenatal care services.**  *This project specifically used a multiple logistic regression approach to assess the social indicators of race, age, and education level, and maternal nativity (Born in the US vs. Born outside of the US) with receiving adequate prenatal care (Y/N: >=10 visits made during pregnancy)* For comparative interest, results were compared from a state to city point-of-view to highlight differences in trends-- but not intended for the use of my capstone. 

>Evaluations will require an intersectional approach for analysis. Biomedical informatics can be an effective tool for statistical analysis for identify the gravity of public health issues. The results can be helpful to many stakeholders within the maternal and child health sector, from community organizations to large-scale hospital systems. An improved understanding of prenatal care adequacy is critical for identifying barriers to eliminating current issues through robust program implementation. 

>The findings of this project will potentially be incorporated into a larger strategy proposal for the City of Philadelphia, which aims to propose a series of recommendations that the Department of Public Health can modify for implementation in Philadelphia to improve antenatal services to undocumented residents through insurance status. 

### Methods
Describe the data used and general methodological approach. Subsequently, incorporate full R code necessary to retrieve and clean data, and perform analysis. Be sure to include a description of code so that others (including your future self) can understand what you are doing and why. 

>DATABASE DETAILS: The quantitative assessment utilized data from the CDC’S WONDER Database, which collects information on an ad-hoc basis for a variety of public health variables and demographic characteristics. The newest dataset was drawn from the Natality online database, which is compiled of data primarily obtained from birth certificates issued in 2016 to 2020 (most updated version) 

>The social indicators of race, age, education level, and maternal nativity (born in the US versus born outside of the US) were selected to determine if adequate prenatal care had been provided to Philadelphia birthing person populations in 2020-2021 using the Kotelchuck Index in a dichotomous format. According to the American College of Obstetricians and Gynecologists (ACOG) Adequate prenatal care is determined by two variables obtained from birth certificates which include when prenatal care was started and the number of prenatal visits until delivery. On average, a patient will complete twelve to fifteen prenatal visits in total. Typically, adequate care is achieved if a patient has completed 80% or roughly ten appointments. While the Kotelchuck Index cannot determine the quality of prenatal care or accurately be applied for high-risk pregnancies, it remains a commonly utilized method for determining if prenatal care services have been adequately provided. **Using the ACOG guidelines, adequate prenatal care was defined by if a patient had ten visits or more visits (visits>=10).** A linear regression will be used later for the future evaluation with the new dataset for more specified answers. 

### Results 

### Conclusion

### Limitations & Future Steps 

### References 
