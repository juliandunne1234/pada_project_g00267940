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
The objective of this part of the project is to assign a weighting to the values in each variable of the dataset. This weighting will then be used when determining if a person has died from CVD or not.