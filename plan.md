#Project 1 

##Interim Analysis

**Tables**  
* Comparison of included and excluded patients  
  - Note that significance of ICV and sex makes sense clinically - some males may have heads too large for equipment  

**Visuals**  
* Scatterplot matrices for each outcome against all predictors  
  - Look into `gpairs` function - Matt mentioned is does scatterplot matricies but better displays for categorical variables  
  - Possible variable transformations to improve model fit  
* Boxplots for the distribution of each predictor of interest (outlier detection)  

**Predictors of Interest**
* SBP rising  
* SBP prewaking   
* Nocturnal difference  

**Covariates**  
* Age (cts)  
* Sex  
* Race  
* Education (cts)  
* apoe4 allele  
* Hypertension medication  
* Diagnosis  
* ICV or appropriate `ma.` variable for ROI volume  
* Indicator of >39 measurements? (pending response from Jacquelyn)  


Other variables in dataset: comorbidities like diabetes, smoking, CVD, A-fib, LV
Won't adjust for these unless data exploration provides strong evidence that we should

##Final Analysis

**Primary Objective**  
* Regression (linear or allow nonlinearity with transformations/rcs)  

 * We should consider multiple imputation as a means of mitigating loss - complete case analysis could eliminate too many patients. I believe we are excluding those patients who do not have complete measurements on the outcomes, which would eliminate issues such as "no data on people with big heads." Thus, it might be reasonable to assume MAR for patients *not excluded from analysis*.  

**Secondary Objective**  
* Pay attention to both statistical significance and magnitude of effects  
* If all models are the same, may be able to use standard errors to test if the 3 predictor measurements have coefficients that are statistically different from one another  