# Female Literacy, Labor, and Income in the United States

Brandie Hatch


## Executive Summary

### Introduction 
According to the U.S. Census Bureau, the [definition of **sex**](https://www.census.gov/topics/population/age-and-sex/about.html) is based on the biological attributes of men and women (chromosomes, anatomy, and hormones). <br><br>
**Female persons in the United States account for 50.5%** of the population, from 331,449,281 total population estimates Census, April 1, 2020

- Please note the following from the U.S. Census Bureau's Age and Sex topic page: __Distinction between the concepts of gender and sex__<br>
"In general discussions, the concept of gender is often confused with the concept of sex, and the terms are used interchangeably. The meanings of these two concepts are not the same: *sex is based on the biological attributes of men and women (chromosomes, anatomy, hormones), while gender is a social construction whereby a society or culture assigns certain tendencies or behaviors to the labels of masculine or feminine.* These assignments may differ across cultures and among people within a culture, and even across time. Gender may or may not correspond directly to sex--depending on the society or culture or period. That means, for example, that people may associate themselves with femininity (as defined by their culture) while being biologically male. At the Census Bureau, the sex question wording very specifically intends to capture a person's biological sex and not gender. Ambiguity of these two concepts interferes with accurately and consistently measuring what we intend to measure--the sex composition of the population."

Data used in this project is from the US Census' American Community Survey (ACS) Public Use Microdata Sample (PUMS) files. <br>


### Problem, Goal, Questions

__Problem:__ 
- The average difference in the years of education attained between gender=1, gender=2 is zero. 
- The average difference in the years of education attained between gender=1, gender=2 is not zero. 
-   (gender 1 = male, gender 2 = female)

__Goal:__ Create a model that most accurately predicts Sex from school level, income, occupation, age, race, and marital status Census Data. 

__Question:__ As the gender gap in education (literacy) decreases, how does women’s participation in labor change?
How does women’s education levels and literacy change related to income, occupation, age, race, marital status and other factors?


### Data Dictionary

Data collected from the US Census' American Community Survey (ACS) Public Use Microdata Sample (PUMS) files. "The PUMS files allow users to create estimates for user-defined characteristics. The files contain a sample of the responses to the American Community Survey (ACS). The PUMS files include variables for nearly every question on the ACS survey. Additional variables are also created from other recoded PUMS variables to provide data users with useful derived variables (such as poverty status) while protecting confidentiality and providing consistency within the PUMS files." <br>
- [AMERICAN COMMUNITY SURVEY 2016-2020 5-YEAR PUMS File ReadMe](https://www2.census.gov/programs-surveys/acs/tech_docs/pums/ACS2016_2020_PUMS_README.pdf) <br> Prepared by American Community Survey Office, U.S. Census Bureau March 31, 2022<br>

Features used listed below:

| Feature   | Type | Numerical or Categorical | Description                                                                           |
|-----------|------|--------------------------|---------------------------------------------------------------------------------------|
| AGEP      | int  | N                        | Age: 1 to 99 years                                                                    |
| CIT       | int  | C                        | Citizenship status                                                                    |
| COW       | int  | C                        | Class of worker                                                                       |
| ENG       | int  | C                        | Ability to speak English                                                              |
| ESR       | int  | C                        | Employment status recode                                                              |
| FFSP      | int  | C                        | Yearly food stamp/Supplemental Nutrition Assistance Program (SNAP) recipient          |
| LANX      | int  | C                        | Language other than English spoken at home                                            |
| MAR       | int  | C                        | Marital Status                                                                        |
| MULTG     | int  | C                        | Multigenerational household                                                           |
| NOC       | int  | C                        | Number of own children in household (unweighted)                                      |
| OCCP      | int  | C                        | Occupation recode for 2018 and later based on 2018 OCC codes                          |
| PINCP     | int  | N                        | Total person's income                                                                 |
| POVPIP    | int  | C                        | Income-to-poverty ratio recode                                                        |
| RAC1P     | int  | C                        | Recoded detailed race code                                                            |
| SCH       | int  | C                        | School Enrollment                                                                     |
| SCHG      | int  | C                        | Grade Level Attending                                                                 |
| SCHL      | int  | C                        | Educational Attainment                                                                |
| SCIENGP   | int  | C                        | Field of degree science and engineering flag - NSF definition                         |
| SCIENGRLP | int  | C                        | Field of degree science and engineering related flag - NSF definition                 |
| SEMP      | int  | C                        | Self-employement income past 12 months                                                |
| SEX       | int  | C                        | Sex                                                                                   |
| WAGP      | int  | N                        | Wages or salary income past 12 months (use ADJINC to adjust WAGP to constant dollars) |
| WKEXREL   | int  | C                        | Work experience of householder and spouse                                             |
| WKL       | int  | C                        | When last worked                                                                      |
| WRK       | int  | C                        | Worked last week                                                                      |
| STATE     | int  | C                        | State code based on 2010 Census Definition                                            |



Create with https://www.tablesgenerator.com/markdown_tables# 



### Model Findings

Supervised Classification - likely a combination of Logistic Regression, KNN Classifier, Random Forest, Decision Trees, Naive Bayes, and SVM to see which one performs the best at accurately predicting male or female based on education attainment, labor types, income, etc.

| Best Score  | Train Score | Test Score  | Accuracy    | Recall      | Precision   | Specificity | F1          |
|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|
| 0.625516622 | 0.62785265  | 0.637049455 | 0.635770954 | 0.563139932 | 0.650887574 | 0.563139932 | 0.603842635 |

__Conclusion:__ 

Overall, in conclusion, women are getting more degrees than men. They are still paid less than men, even though they are in the workforce. Part of the delta is that females are not represented in the highest paying jobs (STEM)


__Problem Statement (Hypothesis):__ 
- The average difference in the years of education attained between gender=1, gender=2 is zero.
- The average difference in the years of education attained between gender=1, gender=2 is not zero.
- Gender 1 = male | Gender 2 = female
- The Null Hypothesis is accurate because the average difference in years of education between males and females is not zero.  The difference is 0.186681


__Next Steps__

1. Make sure that though females are getting more degrees than males,  they can make the same amount of money. 

2. Dive deeper into different forms of classification models to continue to explore the differences between males & females.


### Sources:

https://www.census.gov/topics/population/age-and-sex/about.html

https://ask.census.gov/prweb/PRServletCustom?pyActivity=pyMobileSnapStart&ArticleID=KCP-2950

https://www2.census.gov/programs-surveys/acs/tech_docs/pums/ACS2016_2020_PUMS_README.pdf

https://www.census.gov/programs-surveys/economic-census/guidance-geographies/levels.html#par_textimage_34


__Code Sources:__

Pull a smaller random sample from a large dataset: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.sample.html 

Why did the initial Gridsearch return nan: https://datascience.stackexchange.com/questions/91225/why-gridsearchcv-returns-nan

Logistic Regression scoring issues in Gridsearch: https://scikit-learn.org/stable/modules/model_evaluation.html

https://towardsdatascience.com/20-popular-machine-learning-metrics-part-1-classification-regression-evaluation-metrics-1ca3e282a2ce
