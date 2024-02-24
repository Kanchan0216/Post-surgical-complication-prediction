# Post - Surgical Complication Prediction
### Problem Statement 
**Develop a machine learning model that utilizes patient demographic data and medical history to accurately predict the risk of postoperative complications.**
## What are postoperative complications? 
Complication is a term used by health professionals to refer to something which was not intended to happen. Postoperative complications are problems that can happen after you have had surgery but which were not intended. Doctors are aware of the risk of complications and take steps before, during and after surgery to reduce this risk. However, some complications are common and occur frequently despite precautions. Some postoperative complications are related to the exact surgery that you have had, but many (such as wound infection) may occur after any kind of surgery.
## Motivation:
Surgical patients are automatically at risk of suffering postoperative complications, despite decades of scientific and technological advancement. The accurate prediction of individual outcomes has the potential to completely reshape the future of postoperative management. Through such prediction, individual preoperative treatment and postoperative management can be tailored, allowing for more effective clinical decision-making.
### Objective
* To build machine learning model for predicting postsurgical complication
* To determine which factors have the greatest impact on postsurgical complications
### Data understanding
* Data Source : https://www.kaggle.com
* There are 25 variables and 14635 total datapoints.
* Target variable is complication 
     * Yes : Patient has postsurgical complication
     * No  : Patient does not have postsurgical complication
* The patient's demographic and medical historical data are independent variables.
     * BMI             : Body mass index of patient
     * Age 
     * mortality_rsi   : Mortality Risk Stratification Index used to predict risk of mortality
     * mort30          : Mortality within 30 days of surgery 
     * moonphase       : Phases of moon viz.New moon , First Quater , Full Moon , Third Quater
     * Month           : Month of the year in which surgery is performed.
     * hour            : The time of day at which surgery is performed.
     * Gender          : Whther patient is male or female.
     * dow             : The day of the week on which surgery is performed.
     * complication_rsi: The Complication Risk Stratification Index (RSI) 
     * ccsMort30Rate   : The 30-day mortality rate
     * ccsComplicationRate: The rate of postoperative complications based on the Clinical Classifications Software (CCS) is a measure of surgical quality and patient safety. 
     * ahrq_ccs        : The Agency for Healthcare Research and Quality (AHRQ) is a tool used to group diagnoses and procedures                          into clinically meaningful categories for research and analysis.
     * baseline_pulmonary: Baseline pulmonary disease.
     * baseline_psych    : psychological conditions, such as depression and anxiety.
     * baseline_osteoart : Baseline osteoarthritis.
     * baseline_digestive: Baseline digestive disease 
     * baseline_diabetes : Baseline diabetes. 
     * baseline_dementia : whether a patient has a diagnosis of dementia prior to surgery
     * baseline_cvd      :whether a patient has a cardiovascular disease prior to surgery
     * baseline_charlson : The Charlson Comorbidity Index (CCI)
     * baseline_cancer   : This feature indicates whether a patient has a diagnosis of cancer prior to surgery.
     * asa_status        : The American Society of Anesthesiologists used to access patients health status prior to the surgery.
     * race              : Whether patient is Caucasoid, Negroid, and Mongoloid.
## Exploratory Data Analysis (EDA):
EDA is an important step in visualizing datasets to find patterns, anomalies, and building assumptions or hypotheses based on data understanding.
* Missing Value Analysis: No missing values were found in the dataset.
* Duplicate Values: Duplicate records were removed to ensure accuracy.
* Univariate Analysis: Analysis of individual variables such as age, gender, moon phase, day of the week, etc.
### Feature selection:
Initially, models are constructed encompassing all 24 features. Then, employing a random forest classifier, 8 features are selected, elucidating approximately 95% of the significance to the target variable. Finally, the ultimate model is developed solely utilizing these 8 features.
### Model Building:
The entire data is split into two parts train data and test data
Oversampling is performed for the minority class (patients with complications) to address class imbalance.
The following models are built and compare their performance. 
## Logistic Regression:
A logistic regression model was built using balanced class weights to handle class imbalance. The model was trained on the oversampled training data and evaluated on the test data.
## Decision Tree:
A decision tree model was constructed to capture nonlinear relationships between features and the target variable. The model's hyperparameters were tuned using cross-validation.
## Random Forest:
 A random forest model was built to improve prediction accuracy by aggregating multiple decision trees. Hyperparameters were optimized using grid search with cross-validation.
## Performance Metrics:
Accuracy, recall, precision, and F1-score were calculated to evaluate the models' performance.
## Conclusion:
1.	Decision tree model performs better compared to random forest and logistic regression. Since F1 score for decision tree is 71.3%
2.	According to exploratory data analysis, people age between 57 to 73 have highest risk of postsurgical complications.
3.	The main factor affecting postsurgical complication is age, followed by complication risk index, complication rate and so forth.
