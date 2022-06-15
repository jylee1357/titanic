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

### ⌨️ Models
* Model
  - Multi-Layer Perceptron
     <img width="814" alt="Screen Shot 2022-06-15 at 8 48 52 PM" src="https://user-images.githubusercontent.com/98932859/173820254-1a4e3fff-05b3-4454-8afb-fa3ffec85413.png">

  - Grid SearchCV
     + When hidden layer size = (10,10,10) & max_iter = 60, accuracy turned out to be the highest.
     <img width="815" alt="Screen Shot 2022-06-15 at 8 51 29 PM" src="https://user-images.githubusercontent.com/98932859/173820669-724b65cd-0f11-49bd-97de-ea0f14ee4dce.png">

### 📍 Takeaway
* Feature Importance  
  - In feature importance, 1st: 'Sex' 2nd: 'Age' 3rd: 'Pclass' 4th: 'Sibsp'
  - 74% of female survied and only 18% of male survived
  - Age 0-5 showed the highest survival rate followed by Age 50-65
     + It could be clearly seen that the children and elders escaped first
  - Pclass = 1 (62.9%), Pclass = 2 (47.2%), Pclass = 3 (24.2%) → survival rate of each class
     + Pclass = 1 was like the first class at that time and there were a significant number of important figures in pclass = 1
     
