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



