## ASSIGNMENT-LAB INTRODUCTION
## ACTIVITY 1:

## 1. Write a Python program to select the 'name' and 'score' columns from the following DataFrame.

       Sample DataFrame:

              exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],

               'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],

              'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1] }
## CODE
```
import pandas as pd
import numpy as np

#Sample DataFrame
exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],
             'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],
             'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1]}

df = pd.DataFrame(exam_data)

#Select the 'name' and 'score' columns
selected_columns = df[['name', 'score']]

#Display the result.
print(selected_columns)
```
## OUTPUT
![image](https://github.com/user-attachments/assets/1bff9ce8-38d5-4cbf-b2af-63b8edfd7efd)

## 2. For the above dataframe, Write a program to select the data who's attempt is greater than 3.

## CODE
```
attempts_greater_than_3 = df[df['attempts'] > 3]

print(attempts_greater_than_3)
```
## OUTPUT
![image](https://github.com/user-attachments/assets/19f3ac87-2c85-4ced-86b2-7916fee51991)

## 3. Write python code for indexing rows and columns based on the following conditions:

Assume we have the following dataframe:

data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],

        'age': [25, 35, 40, 28],

        'gender': ['F', 'M', 'M', 'M'],

        'salary': [50000, 70000, 60000, 80000]}

df = pd.DataFrame(data)

a. Select rows where age is greater than 30:

b. Select rows where name contains 'e':

c. Select rows where gender is 'M' and salary is greater than 65000:

d. Select columns 'name' and 'age'
## CODE

```
import pandas as pd

# Sample DataFrame
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],
        'age': [25, 35, 40, 28],
        'gender': ['F', 'M', 'M', 'M'],
        'salary': [50000, 70000, 60000, 80000]}

df = pd.DataFrame(data)

# a. Select rows where age is greater than 30
age_greater_than_30 = df[df['age'] > 30]
print("Rows where age is greater than 30:\n", age_greater_than_30)

# b. Select rows where name contains 'e'
name_contains_e = df[df['name'].str.contains('e')]
print("\nRows where name contains 'e':\n", name_contains_e)

# c. Select rows where gender is 'M' and salary is greater than 65000
male_salary_greater_than_65000 = df[(df['gender'] == 'M') & (df['salary'] > 65000)]
print("\nRows where gender is 'M' and salary is greater than 65000:\n", male_salary_greater_than_65000)

# d. Select columns 'name' and 'age'
name_and_age = df[['name', 'age']]
print("\nSelected columns (name and age):\n", name_and_age)
```
## OUTPUT
![image](https://github.com/user-attachments/assets/4d778902-db77-4c0b-907e-195b97bd810c)


## ACTIVITY 2:
## 1. Write python code for indexing rows and columns using iloc or loc method based on the following conditions:

a.  select the rows where clients with primary education have subscribed to a deposit?

b.  select the rows where clients who have not subscribed to a deposit?

c. select the rows where clients who have subscribed to a deposit either have a housing or a personal loan?

d. select the rows where clients with secondary education who have not subscribed to a deposit?

e. select the rows where  clients who have subscribed to a term deposit as an outcome of the successful marketing campaign? 

f. select the rows where unemployed clients who have not subscribed to deposit?

e. Select columns 'name' and 'salary' where age is less than or equal to 30:

## CODE
```
import pandas as pd

# Sample DataFrame (based on assumed columns)
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],
        'age': [25, 35, 40, 28],
        'salary': [50000, 70000, 60000, 80000],
        'education': ['primary', 'secondary', 'tertiary', 'secondary'],
        'deposit': ['yes', 'no', 'yes', 'no'],
        'housing': ['yes', 'no', 'yes', 'no'],
        'personal': ['no', 'yes', 'no', 'no'],
        'job': ['unemployed', 'self-employed', 'student', 'unemployed'],
        'campaign_outcome': ['success', 'failure', 'success', 'failure']}

df = pd.DataFrame(data)

# a. Select the rows where clients with primary education have subscribed to a deposit
primary_education_deposit = df.loc[(df['education'] == 'primary') & (df['deposit'] == 'yes')]
print("Clients with primary education who subscribed to a deposit:\n", primary_education_deposit)

# b. Select the rows where clients who have not subscribed to a deposit
not_subscribed_deposit = df.loc[df['deposit'] == 'no']
print("\nClients who have not subscribed to a deposit:\n", not_subscribed_deposit)

# c. Select the rows where clients who have subscribed to a deposit either have a housing or a personal loan
deposit_with_loans = df.loc[(df['deposit'] == 'yes') & ((df['housing'] == 'yes') | (df['personal'] == 'yes'))]
print("\nClients who subscribed to a deposit with either housing or personal loan:\n", deposit_with_loans)

# d. Select the rows where clients with secondary education who have not subscribed to a deposit
secondary_no_deposit = df.loc[(df['education'] == 'secondary') & (df['deposit'] == 'no')]
print("\nClients with secondary education who have not subscribed to a deposit:\n", secondary_no_deposit)

# e. Select the rows where clients who have subscribed to a term deposit as an outcome of the successful marketing campaign
successful_campaign_deposit = df.loc[(df['deposit'] == 'yes') & (df['campaign_outcome'] == 'success')]
print("\nClients who subscribed to a deposit after a successful marketing campaign:\n", successful_campaign_deposit)

# f. Select the rows where unemployed clients who have not subscribed to a deposit
unemployed_no_deposit = df.loc[(df['job'] == 'unemployed') & (df['deposit'] == 'no')]
print("\nUnemployed clients who have not subscribed to a deposit:\n", unemployed_no_deposit)

# g. Select columns 'name' and 'salary' where age is less than or equal to 30
name_salary_age_30 = df.loc[df['age'] <= 30, ['name', 'salary']]
print("\nClients with name and salary where age is less than or equal to 30:\n", name_salary_age_30)
```
## OUTPUT
![image](https://github.com/user-attachments/assets/df762549-5e45-472b-8083-f843d9cf6fc7)




