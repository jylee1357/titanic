# Titanic Survivor Prediction

### 🙋‍♂️ Goals
- Based on the traits of each titanic passengers, I tried to predict the survivors of titanic.

### 𝌞 Data Preprocessing
* Data (divided into train & test set)   
     |Variable|Definition|Key|
    |------|---|---|
    |survival|whether the passenger survived|0 = No, 1 = Yes|
    |pclass|seat number|1 = 1st, 2 = 2nd, 3 = 3rd|
    |sex|gender of a passenger|
    |age|age of a passenger|
    |sibsp|number of siblings|
    |parch|number of parents or children|
    |ticket|ticket's unique number|
    |fare|price of a ticket|
    |cabin|cabin's unique number|
    |embarked|Location of departure|C = Cherbourg, Q = Queenstown, S = Southampton|
* Preprocessing
  - 'sex', 'embarked' → Since they are categorical variables, I used one-hot encoder to transform them
  - 'fare' → Based on the fare, I separated them into multiple bins and created new variable called 'fare binned'
  - Based on passenger's honorifics (Mr/Mrs/Miss/Doctor), mean age was calculated to replace the null values in 'age' column 
* Kaggle dataset explanation   
  - Used 'fake_job_postings.csv' on Kaggle
  - Data based on 866 fake job postings
  - 16 independent variables & 1 dependent variable ('Fraudulent')
* Preprocessing (여기서부터 수정)
  - Through one-hot encoder, I transformed categorical variables ('location', 'employment type', 'required experience', 'required education')
     <img width="969" alt="Screen Shot 2022-06-14 at 10 27 53 PM" src="https://user-images.githubusercontent.com/98932859/173588765-d0a5d360-f72f-4aca-b84b-e07a50de586c.png">
  - Preprocessed Textual Data
     + ‘title’, ‘benefits’, ‘descriptions’, ‘company profile’, ‘function’, ‘industry’, ‘department’, ‘requirements’, ‘benefits’
     + Using simple imputer, null values were removed 
    
### ⌨️ Models
* Model
  - Train set: 75%, Test set: 25%
  - Logisitic Regression, Decision Tree, Random Forest Classifier, Neural Network were the selected models
    
* Model Performance  
    <img width="515" alt="Screen Shot 2022-06-14 at 10 33 59 PM" src="https://user-images.githubusercontent.com/98932859/173589965-90edb809-bac9-4fcf-8ad9-f9da33993e9e.png">  
      |Model|Accuracy|
    |------|---|
    |Decision Tree|0.986|
    |Random Forest Classifier|0.984|
    |Logistic Regression|0.981|
    |Neural Network|0.950|
* Model Performance after K-fold cross validation    
     |Model (with CV)|Accuracy|
    |------|---|
    |Decision Tree|0.986 → 0.989|
    |Random Forest Classifier|0.984 → 0.982|
    |Logistic Regression|0.981 → 0.978|
    |Neural Network|0.950 → 0.950| 
### 📍 Takeaway
* Feature Importance  
  <img width="711" alt="Screen Shot 2022-06-14 at 10 41 48 PM" src="https://user-images.githubusercontent.com/98932859/173591712-085e8c51-8189-44bd-8099-acbd8daa0306.png">
  - 'function' (your role in the company)
  - 'industry' (type of industry)
  - 'has_company_logo' (whether the company has a logo or not)
  - 'benefits' (incentives that company provides)
  - 'department' (department in a company)
* Limitations  

  - Since only four percent of the dataset were from actual fake job postings, the target variable was not enough
  - Could not perform sentiment analysis on textual data (with sentiment analaysis the result might have been different)


