# Predicting_Drug_Mortality
Regression Analysis of U.S. drug mortality rates by county.

#### Title: Predicting drug overdose mortality rates by county level in the U.S.

**Problem:** According to data collected by the Centers for Disease Control and Prevention (CDC) there were more than 63,000 drug overdose deaths in 2016. More than 66% of those involved an opioid. On October 26, 2017 the opioid crisis was officially declared a national Public Health Emergency under federal law. The economic burden of prescription opioid misuse is estimated by the CDC to be more than $78 billion a year.

County level services such as hospitals, crisis centers, and local planning boards are in need of predictive models to inform planning, preparation, and resource allocation. This model can be used to better estimate the needs of the county to address this crisis. Examples include how many overdose kits hospitals need to have on stock, how many full-time crisis prevention professionals to employ, how many drug rehabilitation centers need to be established or funded, etc. Local employers are also stakeholders in this crisis. Reports suggest that companies in regions of high opioid usage are unable to maintain employees that can pass prerequisite drug tests for employment. This model can be used as a trends indicator for able local workers.

Knowing what key variables play a role in predicting drug overdoses, and how those may vary across counties having different rates of overdose, can help counties invest wisely in therapeutic resources. Examples would be that a set of counties having particular predicted conditions would require a different set of responses than a set of counties with another set of predicted conditions, and a model could optimize (or customize) those responses. An example of this would be that counties with high overdose rates would see better results by increasing the number of mental health doctors while counties with moderate overdose rates would see better results by encouraging more job growth. Or, that the coefficients of the same set of variables would differ, requiring differing intensities of responses. For example, a new group home vs a new mental hospital. I will explore different machine learning algorithms to attend to different planning needs. 

The above accounts for responsive planning and action, but a model like this can be useful for preventative action as well. Policy decisions can be informed by models such as this where key predictors can point to strategic areas regarding investment in infrastructure for education, social services, and economic growth, should those sectors prove to have a positive outcome on reducing drug overdose mortality.

Finally, nearly half of the counties in the U.S. have missing data for drug overdose mortality in the publicly available databases. This gives an incomplete picture of the crisis at a national level. This model will be used to estimate those missing values for a more accurate (complete) visualization.

**Data:** County level data of drug overdose mortality rates and social, economic, and demographic indicators are available for this model from the The County Health Rankings dataset, a collaboration between the Robert Wood Johnson Foundation and the University of Wisconsin Population Health Institute.This database was built predominantly from the following:  The Behavioral Risk Factor Surveillance System (BRFSS), the National Center for Health Statistics, and the CDC WONDER mortality data.

For a full account of how data for each variable was attained see: http://www.countyhealthrankings.org/sites/default/files/resources/2017_Measures_DataSourcesYears.pdf

Variables are all reported as percentages, rates per 100,000, ratios, or similar population adjusted measures. After data cleaning, they are all of numerical type float or integer. Output data will be in the form of a float for regression analyses, and character for classification and clustering algorithms. 

The following is a table with sample input and output variables and their selected summary statistics.

**Title:  Sample input and output variables with summary statistics.**

| Variable Name | Description | Min Value | Max Value | Mean Value |
| --------------|-------------|-----------|-----------|------------|
| Output:  Drug Overdose Mortality|Deaths per 100,000 population.|3|93|18.16|
|Input: Mentally Unhealthy Days|Health Outcomes: average number of mentally unhealthy days reported in the past 30 days.|2.3|5.8|3.78|
|Input: High School Graduation Rate|Economic Environment:  percentage of ninth-grade cohort that graduates in four years.|30|100|86.28|
|Input: Housing Problems|Physical Environment:   percentage of households with at least 1 of 4 housing problems: overcrowding, high housing costs, or lack of kitchen or plumbing facilities.|1|62|14.47|

**Example Model:** A simple linear regression model applied to the above data for these variables yields the following equation for 37 reporting counties in Alabama.

Drug Overdose Mortality = 16.8 + 6.17(Mentally Unhealthy Days) - 0.2(High School Graduation) - 0.78(Housing Problems)

We can see from this equation (for this sample) that the strongest positive predictor is “Mentally Unhealthy Days”. For the first mentally unhealthy day reported, drug overdose mortality is 22.97 and increases by 6.17 for every day after. This is a simplified model, but provides an example for the results this model can provide.

**Approach:** Because several key variables are expected to aid in the prediction of mortality rates per county, a supervised regression algorithm is a good fit for this model. A multivariate approach to analysis will take numerical inputs and predict a numerical output. Predictors are population adjusted percentages and ratios within the following categories: Premature death, physical health, mental health, nutrition, social indicators, environmental factors, disease screening, race, gender, and economic indicators. A regression analysis will output predictions (response variable) for drug overdose mortality rate (per 100,000 people in the population).

Another supervised learning model I will use is a classification algorithm. This can be used to classify counties as high, medium, or low risk for drug overdose mortality. This would be useful in cases where there was missing data for preceding years in a county. Once they are classified as such, analysis can take place within each level to determine what set of characteristics they share, and between each level to determine how they differ.

Finally, I will conduct an unsupervised clustering analysis to explore how an algorithm would create categories for analysis. Traditional aggregation for many databases is by geographic region to determine if there is a difference in predictors between the Northeast and the South for example. However, drawing lines on a map is an arbitrary classification schema. An algorithm may find a more optimal way to cluster the data that would give more information about how predictors vary across the U.S.

**Deliverables:** 
1. Code: loading data, data cleaning, data visualization, exploratory data analysis, machine learning algorithms. 
2. Report on the project. 
3. Presentation.
