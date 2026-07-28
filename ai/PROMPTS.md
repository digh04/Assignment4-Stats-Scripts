# Prompts Log

This file records the assignment prompt used to generate the AI analysis in this folder.

---

## User Prompt (Assignment A–D)

A. In the Assignment4-Stats-Scripts/ai/ folder, I want you to produce an analysis using the dataset brain_size.csv unless otherwise specified in the notebooks folder in the manual folder, the overarching question of how statistical analysis in Python is done under the setting of several samples or observations portrayed by various features or attributes, and the description given. Save as ai/stats_python.ipynb. Use the stats-env environment and make sure to check the spelling. Use markdown cells for titles and explanations, comments in Python, and separate code cells properly.

B. Use the following prompt-driven walkthrough:

B.1. Create a data table. Use pandas.DataFrame to read the csv file, create arrays with numpy and expose them, manipulate the data using data and groupby, and create boxplots. Find the entire population’s mean VIQ, the study’s number of males and females, and MRI_Count males and females average in log units. Create scatter matrices for Weight, Height, MRI_Count; PIQ, VIQ, FSIQ; males only; and females only. Assess whether the two sub-populations of IQ metrics show any correlation with gender.

B.2. Use scipy to create a 1-sample t-test, 2-sample t-test, and paired test. Also, use a 2-sample test to compare the three IQ metrics PIQ, VIQ, and FSIQ. Use repeated measures test and 1-sample test on the difference. Use a Wilcoxon signed-rank test. Look at weight differences between males and females. Look at males and females again, but this time in reference to VIQ differences using non parametric statistics. Come up with a conclusion.

B.3. This step is broken up into parts B.3.a. and B.3.b. Step B.3.b. is the only time you will use iris.csv in the notebooks folder in the manual folder, understand?

B.3.a. Use the equation y = x * coef + intercept + e. Use statsmodels to create a simple linear regression, fit a linear model using ordinary least squares, look at model summary, and assess whether there is a non zero coef. From this model, obtain estimated parameters. Now, return to brain_size.csv. Follow this by demonstrating categorical variables using IQ and gender. Specify the model further using forcing categorical. Compare the different types of IQ using a long-form table. Then, obtain these values for t-test and respective p-values. Also, look at whether VIQ changes based on gender when Height, Weight, and brain size effects are removed using ANOVA.

B.3.b. Use the equation z = xc1 + yc2 + i + e and the csv file iris.csv to showcase a multiple regression and model summary. Create an analysis. Create an ANOVA with F-test. Assess whether this is a significant difference.

B.4. Use seaborn and wages.txt in the notebooks folder. Steps B.4. and B.5. will be the only times you use wages.txt, understand? Display in a table. Create a pairplot to showcase a scatter matrix. Take categorical variables and plot them as the hue. Then, use matplotlib settings. After, create a lmplot. Also, use a robust model.

B.5. Use seaborn and wages.txt in the notebooks folder. Steps B.4. and B.5. will be the only times you use wages.txt, understand? Use an interaction to look at slope variance across females and males as populations. There should be two different fits and a summary of the results. Assess whether there are increased wages for education in males than education in females. Also, assess whether males benefit more from education than females.

C. Also, create one extension to extend the analysis with one method that is not in the described data and question such as bootstrap CI, robust regression, mixed-effects model, Bayesian alternative, your choice. Save as ai/stats_extension.ipynb. Create a prompts log using this prompt I have given you and save as ai/PROMPTS.md. Create a customized README.md to explain all of your work and save to ai folder.

D. This is the goal. I want you to now plan this out. Brainstorm if needed and present to me a plan in plain English with each phase laid out. Do not use my work in manual or my README.md in manual. Never locally or remotely delete a branch, merge, commit to GitHub, or do anything without my permission.

---

## Follow-up Prompt

read from notebooks in manual, you can choose the extension method yourself, brain_size.csv is in the notebooks folder which is in the manual folder so read it from there. you may start building in the ai/ folder only.

---

## Implementation Notes

- Data path: `../manual/notebooks/` (relative to `ai/`)
- Environment: `stats-env` (Python 3.10, numpy, scipy, pandas, matplotlib, statsmodels, seaborn)
- Extension method chosen: **Bootstrap confidence intervals** for the male–female VIQ mean difference
