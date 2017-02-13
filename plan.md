#Project 1


##For Final Draft

**Brooklyn**   

- Change variable names back to unaltered states    
- Table 1 broken down by diagnosis group
- Histograms of predictors by disease category  
- Add text to descriptive statistics
  * Draw attention to outliers (provide ID if someone is repeatedly the outlier)
  * Push right hemisphere to second line of boxplots so that lobe regions aren't separated
- Inclusion/exclusion criteria (line by line, tell how many people were excluded at each step - do Dementia first)

**Hannah**  

- Missingness table right before imputations are performed (Hannah - move the missingness table)
- Write up results interpretations
- Perform sensitivity analysis with linear regression and provide interpretation
- Write up summary of results





**Next Meeting: Monday, February 6th**

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
* Appropriate `ma.` variable for ROI volume  
* Check about diabetes


Other variables in dataset: comorbidities like diabetes (?), smoking, CVD, A-fib, LV
Won't adjust for these unless data exploration provides strong evidence that we should

##Final Analysis

**Primary Objective**  

* Regression (linear or allow nonlinearity with transformations/rcs)  

* We should consider multiple imputation as a means of mitigating loss - complete case analysis could eliminate too many patients. I believe we are excluding those patients who do not have complete measurements on the outcomes, which would eliminate issues such as "no data on people with big heads." Thus, it might be reasonable to assume MAR for patients *not excluded from analysis*.  

**Secondary Objective**  

* Pay attention to both statistical significance and magnitude of effects  
* If all models are the same, may be able to use standard errors to test if the 3 predictor measurements have coefficients that are statistically different from one another  


**Analysis Plan**  
*Primary Aim*  

1. Multiple imputation for predictors of interest. Separate imputation model for each of the 3 predictors. Imputation models will include all variables to be included in regressions plus all outcomes (lobe-specific, don't have enough df to include all 14 outcomes) - new variable for imputed data so we can use each for sensitivity analysis    
2. Fit linear models with all covariates. Covariates all linear, except potentially blood pressure measurements (could model with splines to allow for non-linearity?)  
3. Table with regression coefficients, CI, p-values (significance markers)  
4. Plots with adjusted predictor-outcome associations  
5. Predicted vs actual (residual plot)  
6. Multiple comparisons adjustment for 14 models on 3 predictors (bonferroni?)


*Secondary Aim*  

1. Looking at magnitude and statistical significance, SEs from regressions performed in primary aim.  
2. Test if estimates for each predictor to see if they are statistically different from one another  



*Follow-up*  

1. Sensitivity analysis: Present results based on complete-case analysis to support imputation.  


**Tasks**  

* Brooklyn: Do multiple imputation analysis   
* Hannah: Fit models and generate tables/plots
* General: Start writing sections for the final report


##Write-up  

* Background: Hannah  
* Inclusion/exclusion criteria: Brooklyn    
* Methods  
  -  Descriptives: Brooklyn  
  -  Analysis (including imputations): Hannah  
* Results  
* Discussion
