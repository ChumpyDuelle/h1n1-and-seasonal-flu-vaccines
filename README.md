![vaccine](images/vaccine.png)

# H1N1 and Seasonal Flu Vaccines

**Authors**: Ian Butler, Red the dog

## Overview

A one-paragraph overview of the project, including the business problem, data, methods, results and recommendations.

## Business Problem

Summary of the business problem we are trying to solve, and the data questions that we plan to answer to solve them.

***

Questions to consider:

* What are the business's pain points related to ths project?
    * The business's pain points related to this project are these:
        * **Primary**: can we predict whether people got H1N1 vaccines using data collected in the National 2009 H1N1 Flu Survey?
        * **Secondary**: can we infer which variables of this survey are most causing a change in vaccination status for H1N1?
        * **Tertiary**: can we provide actionable recommendations to improve the rate of innoculation against H1N1?
* How did we pick the data analysis question(s) that we did?
    * With respect to each of the above questions, we picked the questions as a result of the following thought process:
        * Ultimately, what we would like to be able to do is increase the population's rate of innoculation against highly infectious respiratory diseases. In order to know what would have to be done to take action in this way, we have to understand what variables are most causing a change in vaccination status for individuals, as well as which of those variables we can actually control. Finally, we can confirm whether or not our understanding of these relationships can be used to accurately predict vaccination status for individuals.
* Why are these questions important from a business perspective?
    * These questions are important from a business perspective because they allow public health officials to make informed decisions about what actions they can take to attempt to improve the resiliency of the population against highly infectious respiratory diseases.

***

## Data Understanding

Describe the data being used for this project.

***

Questions to consider:

* Where did the data come from?
    * The data comes from the National 2009 H1N1 Flu Survey.
* How do they relate to the data analysis questions?
    * The National 2009 H1N1 Flu Survery relates to the data analysis questions in that this survey was specifically designed to develop an understanding of how people’s backgrounds, opinions, and health behaviors are related to their personal vaccination patterns.
* What do the data represent?
    * Each entry in the data represents the survey responses of one individual.
* Who is in the sample?
    * The sample is comprised of individuals from various psychographics and demographics across the United States.
* What variable are includeed?
    * The variables included are as follows:
    * For all binary variables: 0 = No; 1 = Yes.
        * **respondent_id**
            * a unique and random identifier
        * **h1n1_concern** - Level of concern about the H1N1 flu.
            * 0 = Not at all concerned;
            * 1 = Not very concerned;
            * 2 = Somewhat concerned;
            * 3 = Very concerned.
        * **h1n1_knowledge** - Level of knowledge about the H1N1 flu.
            * 0 = No knowledge;
            * 1 = A little knowledge;
            * 2 = A lot of knowledge.
        * **behavioral_antiviral_meds** - Has taken antiviral medications.
            * (binary)
        * **behavioral_avoidance** - Has avoided close contact with other with flu-like symptoms.
            * (binary)
        * **behavioral_face_mask** - Has bought a face mask.
            * (binary)
        * **behavioral_wash_hands** - Has frequently washed hands or used hand sanitizer.
            * (binary)
        * **behavioral_large_gatherings** - Has reduced time at large gatherings.
            * (binary)
        * **behavioral_outside_home** - Has reduced contact with people outside of own household.
            * (binary)
        * **behavioral_touch_face** - Has avoided touching eyes, nose, or mouth.
            * (binary)
        * **doctor_recc_h1n1** - H1N1 flu vaccine was recommended by doctor.
            * (binary)
        * **doctor_recc_seasonal** - Seasonal flu vaccine was recommended by doctor.
            * (binary)
        * **chronic_med_condition** - Has any of the following chronic medical conditions: asthma or an other lung condition, diabetes, a heart condition, a kidney condition, sickle cell anemia or other anemia, a neurological or neuromuscular condition, a liver condition, or a weakened immune system caused by a chronic illness or by medicines taken for a chronic illness.
            * (binary)
        * **child_under_6_months** - Has regular close contact with a child under the age of six months.
            * (binary)
        * **health_worker** - Is a healthcare worker.
            * (binary)
        * **health_insurance** - Has health insurance.
            * (binary)
        * **opinion_h1n1_vacc_effective** - Respondent's opinion about H1N1 vaccine effectiveness.
            * 1 = Not at all effective;
            * 2 = Not very effective;
            * 3 = Don't know;
            * 4 = Somehwat effective;
            * 5 = Very effective.
        * **opinion_h1n1_risk** - Respondent's opinion about risk of getting sick with H1N1 flu without vaccine.
            * 1 = Very low;
            * 2 = Somewhat low;
            * 3 = Don't know;
            * 4 = Somewhat high;
            * 5 = Very high.
        * **opinion_h1n1_sick_from_vacc** - Respondent's worry about getting sick from taking H1N1 vaccine.
            * 1 = Not at all worried;
            * 2 = Not very worried;
            * 3 = Don't know;
            * 4 = Somewhat worried;
            * 5 = Very worried.
        * **opinion_seas_vacc_effective** - Respondent's opinion about seasonal flu vaccine effectiveness.
            * 1 = Not at all effective;
            * 2 = Not very effective;
            * 3 = Don't know;
            * 4 = Somehwat effective;
            * 5 = Very effective.
        * **opinion_seas_risk** - Respondent's opinion about risk of getting sick with seasonal flu without vaccine.
            * 1 = Very low;
            * 2 = Somewhat low;
            * 3 = Don't know;
            * 4 = Somewhat high;
            * 5 = Very high.
        * **opinion_seas_sick_from_vacc** - Respondent's worry about getting sick from taking seasonal flu vaccine.
            * 1 = Not at all worried;
            * 2 = Not very worried;
            * 3 = Don't know;
            * 4 = Somewhat worried;
            * 5 = Very worried.
        * **age_group** - Age group of respondent.
        * **education** - Self-reported education level.
        * **race** - Race of respondent.
        * **sex** - Sex of respondent.
        * **income_poverty** - Household annual income of respondent with respect to 2008 Census poverty thresholds.
        * **marital_status** - Marital status of respondent.
        * **rent_or_own** - Housing situation of respondent.
        * **employment_status** - Employment status of respondent.
        * **hhs_geo_region** - Respondent's residence using a 10-region geographic classification defined by the U.S. Dept. of Health and Human Services. Values are represented as short random character strings.
        * **census_msa** - Respondent's residence within metropolitan statistical areas (MSA) as defined by the U.S. Census.
        * **household_adults** - Number of *other* adults in household, top-coded to 3.
        * **household_children** - Number of children in household, top-coded to 3.
        * **employment_industry** - Type of industry respondent is employed in. Values are represented as short random character strings.
        * **employment_occupation** - Type of occupation of respondent. Values are represented as short random character strings.
* What is the target variable?
    * There are two target variables in this dataset:
        * **h1n1_vaccine** - Whether respondent received H1N1 flu vaccine.
        * **seasonal_vaccine** - Whether respondent received seasonal flu vaccine.
    * **This project will focus on the h1n1_vaccine target, specifically.**
* What are the properties of the variables you intend to use?
    * We intend to use all of the available variables, at least until any given variable is shown to be statistically insignificant.
    * Most of the variables have numeric data types and will likely be left as-is. The variables which do not have numeric data types will likely be transformed using ordinal encoding or one hot encoding, as appropriate.

***

The above descriptions of the features in this dataset were taken from DrivenData at the following URL:

https://www.drivendata.org/competitions/66/flu-shot-learning/page/211/#features_list

The 10 HHS geographic classification regions:

![regional-offices.png](images/regional-offices.png)

The above image was taken from the U.S. Department of Health and Human Services at the following URL:

https://www.hhs.gov/about/agencies/iea/regional-offices/index.html

A brief word on MSA:

The United States Office of Management and Budget (OMB) delineates metropolitan and micropolitan statistical areas according to published standards that are applied to Census Bureau data. The general concept of a metropolitan or micropolitan statistical area is that of a core area containing a substantial population nucleus, together with adjacent communities having a high degree of economic and social integration with that core. Currently delineated metropolitan and micropolitan statistical areas are based on application of 2010 standards (which appeared in the Federal Register on June 28, 2010) to 2010 Census and 2011-2015 American Community Survey data, as well as 2018 Population Estimates Program data. Current metropolitan and micropolitan statistical area delineations were announced by OMB effective March 2020.

The above excerpt on MSA was taken from the United States Census Bureau at the following URL:

https://www.census.gov/programs-surveys/metro-micro/about.html

## Methods

Describe the process for analyzing or modeling the data.

***

Questions to consider:

* How did you prepare, analyze or model the data?
    * We prepared the data in the following ways:
        * Dropped variables which were either missing half of their values or more than 10% of their values, with no good answer for imputing new values:
            * health_insurance
            * employment_industry
            * employment_occupation
            * income_poverty
        * Executed a OneHotEncoder for all features of the object data type. Given that there was no inherent rank to any of the object features, a OneHotEncoder was applied universally to those data types in lieu of using an OrdinalEncoder for any of them.
    * We analyzed the data in the following ways:
        * Simple dataframe manipulation:
            * Observed measures of central tendency for varioues features
            * Observed distribution of the features and of the target
            * Observed correlation of features to target and features to features
        * Visualized correlation of features and target via heatmapping
    * We modeled the data with the following algorithms:
        * Dummy Classifier
        * Logistic Regression
        * Random Forest
* Why is this approach appropriate given the data and the business problem?
    * The approaches were appropraite given the data and the business problem because they allowed us to eliminate features which could not rightly contribute toward the inference or prediction of the target without arbitrarily skewing the distribution of those features.
***

## Results

Present your key results. For Phase 1, this will be findings from your descriptive analysis.

***
Questions to consider:
* How do you interpret the results?
* How confident are you that your results would generalize beyond the data you have?
***

Here is an example of how to embed images from your sub-folder:

### Visual 1
![graph1](./images/viz1.png)

## Conclusions

Provide your conclusions about the work you've done, including any limitations or next steps.

***
Questions to consider:
* What would you recommend the business do as a result of this work?
* What are some reasons why your analysis might not fully solve the business problem?
* What else could you do in the future to improve this project?
***

## For More Information

Please review our full analysis in [our Jupyter Notebook](./dsc-phase1-project-template.ipynb) or our [presentation](./DS_Project_Presentation.pdf).

For any additional questions, please contact **name & email, name & email**

## Repository Structure

Describe the structure of your repository and its contents, for example:

```
├── README.md                           <- The top-level README for reviewers of this project
├── dsc-phase1-project-template.ipynb   <- Narrative documentation of analysis in Jupyter notebook
├── DS_Project_Presentation.pdf         <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code
```
