# Programming for Data Analysis Project:

|Name           |Email         |
|---------------|--------------|
|Julian Dunne   |G00267940@gmit.ie   

## Create a data set by simulating a real-world phenomenon

The purpose of this project is to create a data set by simulating a real-world phenomenon. Model and synthesise such data related to the phenomenonu using Python. The project should include:
- Choose a real-world phenomenon that can be measured and collect at least one-hundred data points across at least four different variables.
- Investigate the types of variables involved, their likely distributions, and their relationships with each other.
- Synthesise/simulate a data set as closely matching their properties as possible.
- Detail your research and implement the simulation in a Jupyter notebook – the data set itself can simply be displayed in an output cell within the notebook.
***
## Project Plan:
The subject chosen for this project is Cardiovascular diseases (CVD). The reason for this was that there is many different attributing factors that can lead to the development of the disease so it seemed like a logical choice.

### Dataset Variables:
Variables to be used in the dataset either directly attribute to the development of CVD or may be coincidental: 
- Age of a person
- Gender of a person
- Tobacco user
- Body Mass Index classification

### CVD Assumptions:
- This project will assume that all CVD's are the same.
- This project focuses only on population distributions that would be applicable to Ireland and the United Kingdom.
- This project only lists a person as either a smoker or a non-smoker. There is no differentiation between heavy/light tobacco use.
- This project only includes persons with a BMI classification in the "Normal-weight", "Over-weight" or "Obese" categories.

## Creating the Variables:
- Variable 1 - Age: Using the Ireland 2020 dataset it was possible to determine the percentage of the population per age group. This was then used as a probability in the random choice method to create the variable age data series.
- Variable 2 - Gender: As this is either female or male it was possible to use the random binomial method to generate this data series. A gender probability was applied to each age group as ratio of female/male varied.
- Variable 3 - Tobacco Use: Using the random choice method, the population distribution of smoker vs non-smoker for each age group was created whereby a probability of using tobacco was assigned for each age group.

## Assessing the project:
Until this point it had been assumed that it would be straight forward to convert the variable values for each age group into actual individual data entries e.g. 143 m_smoker for 16-24 age group needed to be 143 different entries. 

The author was having difficutly writing the code execute this so it was decided that all work up until this point would be reviewed and the dataset in its entirety would be populated. If necessary different methods would need to be applied to generate the data.

### Creating the dataset df_cvd:
- df_cvd['age_group']: This variable uses the different age groups and applies the sim['pop'] values generated in Variable 1 to create the data series.
- df_cvd['gender']: This variable uses the random binomial method to return a data series of male female values. <b>Note:</b> It was not possible to assign gender probabilities for each age group as was done in section Variable 2 - Gender. Instead it will now be assumed that the distribution of male/female is even for each age group in the population.
- df_cvd['smoker']: This variable uses the random choice method and assigns a probability that a person smokes for each age group in the population. There is no differentiation between light/heavy smokers.
- df_cvd['BMI']: Body Mass Index (BMI) classification to be used to determine the weight category each subject in the dataset is in. This variable uses the truncated normal distribution whereby the data is truncated so that BMI values under 18.5 are not included in the data.
***
### Determing the cause of death:
The objective of this part of the project is to assign a weighting to the values in each variable of the dataset using a risk assessment approach. This weighting known as the 'correlation' variable will then be used when determining if a person has died from CVD or not.

Once the 'correlation' values are created, the notebook then uses these values to assign a probability that either the cause of death is 'cvd' or 'other'. The higher the correlation value the likelier that the person has died from cardiovascular disease. The random choice method is used for generating the 'cause_of_death' variable which completes the dataset. A seperate final_cvd_df is generated where the 'correlation' variable is dropped. This is just to display the dataset in full.
***
## Project Summary & Lessons Learned:
While generating the dataset the author had to change direction several times as there was many difficulties trying to write the code that would generate the desired output. It was possible to overcome one issue by reattempting the variables and their format as explained above, however some of the code in these variables is fairly long winded as the author was having difficulty looping through multiple lists and arrays. This will be an area the author will look to make improvements for personal development.

The dataset in its final format is not what the author had initially planned. Following the population distribution of a living population is not actually suitable for this dataset in which all of the sample size actaully dies. The dataset has 50% of the age groups below 45 years of age. Cardiovascular disease does not have as great of an impact on people below this age and therefore the dataset shows a lower number of people dying from the disease than would be expected in a population. However for the purposes of the dataset, the results do make sense in that it shows less people died from the disease.

Finally, creating graphs that showed the impact each variable had on the cause of death has not been easy. Instead it was decided that using the 'correlation' variable would act as a substitute as this value was determined based on the combination of values for each of the variables.

***