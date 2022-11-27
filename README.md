# Predicting Loan Elgibility

### [Assignment](assignment.md)

## Project/Goals
 Problem Statement: We are given the object of automating the loan eligibility process based on customer data provided as online application forms that are being filled. 

## Hypothesis
There are numerous factors that can factor in a lenders decision in approving a loan application. For instance, some possible factors can be:
1. Income
2. Assets/Collateral held
3. Term of loan considered
4. Credit score
5. Education
6. Family status

#### Possible hypotheses
From the possible factors listed above, we can hypothesizes as to why they would affect the probability of a lender approving a loan application. 

1. **Income**: A higher income can be used as a proxiy for an individuals ability to pay
2. **Assets/Collateral**: Adequate assets/collateral for loans would allow greater risk tolerance by a lender, with respect to a prospective loanee
3. **Loan Term**: shorter term loans result to less exposure to changes in financial circumstances for the lender. Furthermore, shorter term loans usually also mean higher monthly payments so lender recoups more money immediately.
4. **Credit Score**: past data to infer your "trustworthiness" as debtor. Thus, higher credit score may result in greater willingness for a lender to loan money
5. **Education**: generally, there is a positive correleation between education and lifetime income that may make graduation a proxy for your earning capacity and thus abaility to pay loan. 
6. **Family Status**: By this we mean whether the applicant has a family. This may affect the type of loan to be requested by an applicant. For instance, an applicant with a family may be more likely to apply for loans that are related to more longer term investments like housing and education, which correspond to loans that either will have correpsonding collateral or result in returns for the applicant that will result in greater abillity to pay. 

## EDA 
Among the things I found was:
1. Postitve relationship between loan amount and number of dependents, which persisted acros property type
2. That graduate applicants had greater number of dependents and also, as a result, also has greater loan amounts in their application
3. This gap in loan amounts requested between graduate and non-graduate applicants held across property type
3. A great disparity in average income between graduate and non-graduate applicants, in favour of graduates, which also held across property type.
4. That graduate applicants were over-represented in the data and that they also were overepresented when it came to favorable credit scores. 

The above facts suggest, in accordance with our hypothesis regarding income, education, dependents/family status, credit scores that graduate's would be more likely to get approved for loans and that, given their over-representation in the data, a good model should expect to show a higher distribution of applicants being classified as approved (i.e., we should have higher distribution of True Positives then True Negatives). 

## Process
The process for this project consisted of a sequence of the following steps:
1. Feature Extraction
> Here we created a class and a correspondent function in which we create a variable for Total Applicant Income and drop irrelevant variables.
2. Preprocessing
> Here we utilize a ColumnTransformer object to do impute missing values for numeric (with column means) and categorical (with column mode) variables. We also apply scaling (i.e., normalize the data) on numeric variables as well as one-hot-encode our categorical variables
3. Feature Engineering
> We follow the above steps with some PCA on the features to reduce the dimensions of our data and then apply forward selection to extract the PCA variables with greatest explanatory power.
4. Model Fit
> At the end we fit a Random Forest Classifier to the resultant dataset, and conduct Grid-Search and Cross Validation to evaluate and select the best model. 


## Results/Demo
The resulting model is characterized by an accuracy 0.82, Precision 0f 0.80 and a Recall of 0.98. We are left with an F1-Score of 0.88

## Challenges 
Most of the greatest challeneges were with the deployment of my model. Though I could get the API working I had diffculty in getting the response I wanted from my requests. After making some changes to my pipelines, the issue then turned to an inability of my api file to find a custom classes created and integrated into the pipeline. 

## Future Goals
My biggest goal is to address the lingering issues with my deployment and get a test run working. 
