# Data Engineering Part-1


## **Installation**

---
### For Ubuntu


First of all, make sure that python is correctly installed on your computer:
```bash
python --version
```

Then start installing the required packages:
```bash
sudo apt-get install python3-pip    # Install pip3 if you don't have it
pip3 install pandas
```

### For Windows and Mac

First of all, make sure that python is correctly installed on your computer:
```bash
python --version
pip3 install --upgrade pip
```

Then start installing the required packages:
```bash
pip install pandas
```

# Data Pipeline Steps

---

Data pipelines allow us to transform raw data into a format more suitable for analysis. We can think of it as a series of steps, each refining or enhancing the data, to make it more useful or to adapt it to our needs. Steps can involve removing redundant data, reformatting data, or even enhancing data by adding additional information.

In this workshop, we will extract data from a CSV file, clean it, transform it, analyze it, and finally, load it into an SQLite database.


## 1. Data Collection

---

The first step in a data pipeline is data collection. This is the step where you collect the data that you will be working on.
The data can be collected from a database, a csv file, or even a website.
In this project, we will be working with a csv file, so we will be using the pandas library to load the csv file into a dataset.
We will be using the csv file that is available in the repository.

To read a csv file and load it into a dataset, we will be using the pandas library. The pandas library is a library that is used to manipulate data in python.
It has a method that allows you to load csv, it is called read_csv. Use it to load the csv file into a dataset.

```python
import pandas as pd

df = pd.read_csv('data.csv')
```

If you want to see what the dataframe looks like, you can print it with the print() function combined with the head() function to only see the first rows.
The dataframe shoud look something li

| Index | Organization Id | Name          | Website                      | Country                  | Description                            | Founded | Industry              | Number of employees |
|:-----:|-----------------|---------------|------------------------------|--------------------------|----------------------------------------|---------|-----------------------|---------------------|
|   2   | AAC4f9aBF86EAeF | Orr-Armstrong | https://www.chapman.net/     | Algeria                  | Ergonomic radical budgetary management | 1970    | Import / Export       | 7994                |
|   4   | D76BB12E5eE165B | Bauer-Weiss   | https://gillespie-stout.com/ | United States of America | Synergistic maximized definition       | 2015    | Dairy                 | 9069                |
|   5   | 2F31EddF2Db9aAE | Love-Palmer   | https://kramer.com/          | Denmark                  | Optimized optimizing moderator         | 2010    | Management Consulting | 6991                |

## 2. Data Cleaning

---

The second step in a data pipeline is data cleaning. This is the step where you clean the data that you will be working on.
The data can be cleaned by removing empty values, or by reformatting the data to a more readable format.
This is the most important part of a data pipeline, because if the data is not cleaned properly, the results will not be accurate.
Right now, it is your turn to clean values, I will give you a list of all the transformations you will have to do a good dataset:

- Remove all the rows that have empty values
- Remove all the rows that have "Inc" in their name
- Remove all the rows that have website that have "http" as they might not be safe
- Remove all the rows that have a number of employees that is less than 1000
- Remove all the rows that come from spanish speaking countries (Spain, Mexico, Argentina, etc...)
- Remove all the rows that were founded before 1980
- Remove all the rows that are in the "Textiles" industry

## 3. Data Transformation

---

The third step in a data pipeline is data transformation.
The data can be transformed by adding new columns, or by reformatting the data to a more readable format.
This is the most important part of a data pipeline, because if the data is not transformed properly, the results will not be accurate.
Right now, it is your turn to transform values, I will give you a list of all the transformations you will have to do a good dataset:

- Add a new column called "Revenue" that is the number of employees multiplied by 1000
- Filter the companies that have less than 
- Add a new column called "Age" that is the current year minus the year the company was founded
- Add a new column called "Website" that is the website of the company without the "http://" part
- Transform all the rows with "United States of America" as their country to "USA"
- Add a new column called "Size" based on the 'Number of employees' column, the size should be "Small", "Medium", "Large" or "Very Large". The formula is: 
    - "Small" if the number of employees is less than 1000
    - "Medium" if the number of employees is between 1000 and 5000
    - "Large" if the number of employees is between 5000 and 10000
    - "Very Large" if the number of employees is more than 10000
- Create a new dataframe called "companies" that only contains the columns "Name", "Country", "Industry", "Revenue", "Age", "Size" and "Website"
- Create a new column called "Success Score" that is calculated thanks to the Revenue, Number of employees and Age columns. The formula is: Revenue / (Number of employees * Age)


## Conclusion

---

Congratulations, you have finished the first part of the workshop, you now know how to create a data pipeline in python.
You can now use this knowledge to create your own data pipelines and work on your own datasets.