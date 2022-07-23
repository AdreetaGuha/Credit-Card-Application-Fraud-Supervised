# Credit-Card-Application-Fraud-Supervised
The dataset provided contains credit card application fraud data. The goal was to identify 
synthetic identity fraud among a million personal information records. The dataset had 
1,000,000 records and 10 data fields which contained several important information about the 
applicants such as the first name, last name, date of birth, social security number (SSN), 
address, and phone number. Our objective was to create a supervised fraud detection model 
with a high fraud detection rate. 
We performed exploratory data analysis on each of the 10 fields which were identified as 
categorical. Summary statistics of each field in terms of % populated, Unique values, and most 
common values were described. This helped us identify the data better and then during the data 
cleaning process, we were able to identify the frivolous and missing values and treat them at the 
start to avoid faulty predictions. 
To get a better insight of the data we engineered 1948 candidate variables which would help us 
identify fraudulent behaviors. The original categorical fields were concatenated to create 
different field combinations. Then for each combination, we calculated three more variable 
groups: the velocity candidate variables, the days-since candidate variables, and the relative 
velocity candidate variables.
Feature selection was then performed using select filter and wrapper methods to identify the top 
30 candidate variables as a part of minimizing dimensionality. In the filtering process, 
Kolmogorov-Smirnov (KS) and fraud detection rate (FDR) at 3% were used to eliminate 
variables. For our wrapper method, we used recursive feature elimination with cross-validation. 
Once the final variables were chosen, the data was divided in three sections: training, testing, 
and out-of-time. The out-of-time section represented the last two months of data. In addition, the 
first two weeks of the data was omitted to get the most accurate results possible as there was 
little to no data prior to each datapoint.
To find the best model, the variables were tested in several different models. First, since we had 
a supervised binary classification problem, logistic regression was used as a base model to 
predict fraud. Logistic regression caught 48.3% of fraud at a 3% FDR. Next, nonlinear models 
such as random forest, boosted trees, and neural network were used to get better results than 
the base model. Parameter tuning was also performed on each model to get better results. 
Overall, our best model was random forest trees which caught 53.6% of the fraudulent records 
in the testing set and 50.5 % of the fraudulent records in the validation set at a 3% FDR after 
parameter tuning.
