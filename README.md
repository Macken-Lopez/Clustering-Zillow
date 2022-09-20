# Project_3
## Clustering Regression Project


#### By Richard Macken & Lazaro Lopez 





***
[[Project Description](#project_description)]
[[Project Planning](#planning)]
[[Key Findings](#findings)]
[[Data Dictionary](#dictionary)]
[[Data Acquire and Prep](#wrangle)]
[[Data Exploration](#explore)]
[[Statistical Analysis](#stats)]
[[Modeling](#model)]
[[Conclusion](#conclusion)]
___
## <a name="project_description"></a>Project Description:
For this project we will continue working with the zillow dataset. Using the 2017 properties and predictions data for single unit / single family homes.

In addition to continuing work on our previous project, we have incorporated clustering methodologies on this project.

Our audience for this project is a data science team. Our presentation will consist of a notebook demo of the discoveries made and illustrating the work we have done related to uncovering what the drivers of log error in the zestimate are.

We documented code, processing (data acquistion, preparation, exploratory data analysis, and statistical testing, modeling, and model evaluation), findings, and reporting key takeaways in a Jupyter Notebook Final Report.

Created modules (acquire.py, prepare.py) that make our process repeateable and our report (notebook) easier to read and follow.

We asked exploratory questions of the data that helped us understand more about the attributes and drivers of log error. We also answer questions through charts and statistical tests.

We constructed a model to predict log error of homes using clustering techniques.

Be prepared to answer panel questions about your code, process, findings and key takeaways, and model.

# Our Overall Goal for this Project is to Predict Logerror. 

### Questions we will be asking:

Is there a correlation between square footage of a home and log error?

Is there a relationship between tax rate and log error?

Is Log error is significantly different among the counties of LA County, Orange County and Ventura County?

Does log error vary by the age of the house ?





[[Back to top](#top)]

***
## <a name="planning"></a>Project Planning: 
a)Create deliverables:
- README
- final_report.ipynb
- working_report.ipynb

b) Build functional wrangle.py, explore.py, and model.py files

c) Acquire the data from the Code Up SQL database via the wrangle.acquire functions

d) Prepare and split the data via the wrangle.prepare functions

e) Explore the data and define hypothesis. Run the appropriate statistical tests in order to accept or reject each null hypothesis. Document findings and takeaways.

f) Create a baseline model in predicting log error .

g) Fit and train regression models to predict log error on the train dataset.

i) Evaluate the models by comparing the train and validation data.

j) Select the best model and evaluate it on the train data.

k) Develop and document all findings, takeaways, recommendations and next steps.


[[Back to top](#top)]

### Project Outline:
Acquire data
Prepare Data
Explore Data
Create Hypothesis
Test Model 
Conclusion

        
### Hypothesis
---
# Hypothesis 1
Is there a correlation between square footage of a home and log error?


## $H_0$: Square footage has a dependent relationship with the log error of a property 

## $H_a$ : Square footage  is independent of the log error of a property 

---

# Hypothesis 2
Is there a relationship between tax value and log error?

## $H_0$: Tax Rate has a dependent relationship with the log error of a property 

## $H_a$ : Tax Rate is independent of  the log error of a property 

---
# Hypothesis 3
Log error is different among the counties of LA County, Orange County and Ventura County?

## $H_0$:  There is no significant difference in logerror for properties in LA County vs Orange County vs Ventura County

## $H_a$ :  Log error is significantly different among the counties of LA County, Orange County and Ventura County.
---
# Hypothesis 4
Does log error vary by the age of the house?

## $H_0$: Tax Value has a dependent relationship with a homes age.

## $H_a$ : Tax Value is independent of a homes age.
---
### Target variable
Log Error

### Need to haves (Deliverables):
acquire.py
prepare.py
Final_notebook.ipybn
this readme.md


### Nice to haves (With more time):




***

## <a name="findings"></a>Key Findings:
## There is more than one way to predict but simple is better and diving to deep will cause you to drown.

# Cursory Cluster was not benifical caused what appears to be over fitting. Our models are likely overfit because it is a 6 Degree Polynomial.


[[Back to top](#top)]


***

## <a name="dictionary"></a>Data Dictionary  


### Data Used
| Attribute | Definition | Data Type |
| ----- | ----- | ----- |
|acres|Amount of Acres for property|float64 |
|acres_bin|Bin of Acres Feature|float64 |
|age|Age of the property from Build Date|float64 |
|age_bin|Bin of Age|float64 |
|assessmentyear|Year the taxes were assessed on the property|float64|
|bathroomct|Count of Bathrooms for the property|float64|
|bedroomcnt|Count of Bedrooms for the property|float64|
|bath_bed_ratio|Combinded feature|float64 |
|calculatedfinishedsquarefeet|Area of the property in square feet|float64|
|cola|County of Los Angles |int64   |
|county|County the property is in |object|
|fips|Federal Information Processing Standard code|int64|
|land_dollar_per_sqft|Cost per Sqft of land |float64 |
|landtaxvaluedollarcnt|Value of Land for Taxation purpose   |float64 |
|latitude|Latitude of the middle of the parcel divided by 10e6|float64|
|logerror|The log difference between Zillow's Zestimate and the property sale price|float64|
|longitude|Longitude of the middle of the parcel divided by 10e6|float64|
|lotsizesquarefeet| Sqft of Lot of property not building|float64|
|lot_dollar_sqft_bin|          |float64 |
|parcelid|Unique identifier for parcels (lots)|float64|
|regionidcity |City for Property|float64 |
|regionidcounty|County associated with Property|float64 |
|regionidzip| Zip associated with Property     |float64 |
|structure_dollar_per_sqft|    |float64 |
|structure_dollar_sqft_bin|   |float64 |
|sqft_bin|Sqft Bin|float64 |
|taxamount|Amount of Tax|float64 |
|taxrate|Rate of Tax |float64 |
|taxvaluedollarcnt|Tax Value Dollar Count|float64 |
|yearbuilt|The Year the Property was Built|float64|

---

***
[[Back to top](#top)]
## <a name="wrangle"></a>Data Acquisition and Preparation
[[Back to top](#top)]

![]()


### Wrangle steps: 
Try to Make pretty pictures
Repeat until you get something you understand.

*********************

## <a name="explore"></a>Data Exploration:
[[Back to top](#top)]
- Python files used for exploration:

    - explore.py



### Takeaways from exploration:


***

## <a name="stats"></a>Statistical Analysis
[[Back to top](#top)]


# Stats Test 1: Pearsons

# Hypothesis 1
Is there a correlation between square footage of a home and log error?


## $H_0$: Square footage has a dependent relationship with the log error of a property 

## $H_a$ : Square footage  is independent of the log error of a property 
 

#### Alpha value: 

- alpha = 1 - confidence, therefore alpha is 0.05

#### Results:
Yes, we observe that structure_dollar_sqft_bin and logerror show observable correlation by pearsons R:
Our r value is:-0.037313842378546944
Hence, we reject our null hypothesis


***
----------
# Stats Test 2: Pearsons

# Hypothesis 2
Is there a relationship between tax value and log error?

## $H_0$: Tax Rate has a dependent relationship with the log error of a property 

## $H_a$ : Tax Rate is independent of  the log error of a property 

#### Alpha value: 

- alpha = 1 - confidence, therefore alpha is 0.05

#### Results:
Yes, we observe that taxrate and logerror show observable correlation by pearsons R:
Our r value is:0.020205900971801253
Hence, we reject our null hypothesis



***
----------
# Stats Test 3: Idependant T Test
# Hypothesis 3
Does log error vary by the age of the house?

## $H_0$: Tax Value has a dependent relationship with a homes age.

## $H_a$ : Tax Value is independent of a homes age.

#### Alpha value:
- alpha = 1 - confidence, therefore alpha is 0.05

#### Results:
Since age is actually a categorical, we explored every unique age with a sample size of greater than 100.

(a conservative sample size to ensure our tests are significant).
We ran the levene test then a ttest for indpendence respective to the levene test results. The net results give us a bit more detail than an ANOVA which would allow for deeper inspection.


#### Summary:
While I still do not fully grasp this process it was completed
***
-------
# Stats Test 4: Independant T Test

# Hypothesis 4
Log error is different among the counties of LA County, Orange County and Ventura County?

## $H_0$:  There is no significant difference in logerror for properties in LA County vs Orange County vs Ventura County

## $H_a$ :  Log error is significantly different among the counties of LA County, Orange County and Ventura County.
---

#### Alpha value:
- alpha = 1 - confidence, therefore alpha is 0.05

#### Results:
No, we observe that ventura_train and orange_train are statistically the same:
Hence, we fail to reject our null hypothesis

No, we observe that ventura_train and train_la are statistically the same:
Hence, we fail to reject our null hypothesis

Yes, we observe that orange_train and train_la are statistically different
Hence, we reject our null hypothesis
We see that LA and OC come from statistically different populations. However Ventura is not indepedent of LA or OC.

***
----------

----------
## <a name="model"></a>Modeling:
[[Back to top](#top)]

### Model Preparation:

### Baseline

---

|	                                |Train|	        Validate|	diff|	        abs_diff|	abs_percent_change|
|---|---|---|---|---|---| 
|RMSE for degree6 Polynomial Model|	0.162950|	0.162608|	0.000342|	0.000342|	0.209789|
|RMSE for degree5 Polynomial Model|	0.163366|	0.151804|	0.011561|	0.011561|	7.077024|
|RMSE for degree4 Polynomial Model|	0.163870|	0.151262|	0.012608|	0.012608|	7.693663|
|RMSE for degree3 Polynomial Model|	0.164080|	0.151316|	0.012764|	0.012764|	7.779134|
|RMSE using Median	          |      0.164701|	0.151908|	0.012792|	0.012792|	7.767078|
|RMSE using Mode	                   |     0.164701|	0.151908|	0.012792|	0.012792|	7.767078|
|RMSE using Mean                 	|0.164499|	0.151660|	0.012839|	0.012839|	7.804708|
|RMSE for Elastic Net Model|	        0.164499|	0.151660|	0.012839|	0.012839|	7.804708|
|RMSE for Lasso + Lars	   |             0.164499|	0.151660|	0.012839|	0.012839|	7.804708|
|RMSE for 2nd Degree Polynomial Model|	0.164262|	0.151367|	0.012896|	0.012896|	7.850614|
|RMSE for ARDRegression	        |        0.164418|	0.151518|	0.012900|	0.012900|	7.845845|
|BayesianRidge	                |        0.164411|	0.151486|	0.012925|	0.012925|	7.861316|
|RMSE for OLM	                |        0.164399|	0.151459|	0.012940|	0.012940|	7.870953|
|RMSE for LassoLarsIC	        |        0.164399|	0.151459|	0.012940|	0.012940|	7.870953|
|RMSE for degree7 Polynomial Model|	0.162225|	0.420686|	-0.258461|	0.258461|	159.323123|
|RMSE for degree8 Polynomial Model|	0.161256|	14.234101|	-14.072845|	14.072845|	8727.025312|
***

### Models and R<sup>2</sup> Values:
- Will run the following regression models:

    

- Other indicators of model performance with breif defiition and why it's important:

    


## Selecting the Best Model:

|| Train| Validate|	Test|Train_to_Val_diff|	Train_to_Val_abs_diff|Train_to_Test_diff|Train_to_Test_abs_diff|
|---|---|---|---|---|---|---|---|
|RMSE for degree6 Polynomial Model|	0.16295     |    0.162608|	0.271169|	0.000342	|        0.000342	|-0.10822|	0.10822|





***

## <a name="conclusion"></a>Conclusion:
Cursory Cluster was not benifical caused what appears to be over fitting. Our models are likely overfit because it is a 6 Degree Polynomial. 

With more time we would like to 
---
### Steps to Reproduce
Your readme should include useful and adequate instructions for reproducing your analysis and final report.

For example:

1)You will need an env.py file that contains the hostname, username and password of the mySQL database that contains the titanic_db.passengers table. Store that env file locally in the repository.

2)clone my repo (including the wrangle.py, explore.py, and model.py) (confirm .gitignore is hiding your env.py file)

3)libraries used are pandas, matplotlib, seaborn, numpy, sklearn,scipy, math.

4)you should be able to run Similar Log Error Preditions.


[[Back to top](#top)]
