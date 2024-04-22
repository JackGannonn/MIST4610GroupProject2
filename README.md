# MIST4610GroupProject2

TEAM NAME:
------
Sp24_21484_Group3


TEAM MEMBERS:
----
1. Brendan Rice
2. Areez Shaikh
3. Roshan Maganti
4. Brayden Keller
5. Ella Gunning
6. Jack Gannon


DESCRIPTION OF DATASET:
----
Our dataset includes the sale data for hundreds of thousands of car sales. We obtained our dataset through the Kaggle website (https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data). This vast dataset has many different attributes that we can use to visualize this data. Each sale includes data about the car's make, model, trim, year, state of sale, odometer, color, sale price, and sale date, among a few others that were not used fully in our analysis. The numeric type data includes the dimensions year, odometer, and sale price. These are numbers that we can look at sums, averages, or counts of which may be useful in our analysis. The string data includes those with characters such as make, model, color, etc. State of sale is a string but has a geographic role, which can allow us to visualize our data on a map with the generated latitude and longitude fields. We also transformed the sale date data column from a string to a date, which is described below in data manipulation. A combination of this dataset's size and description of each sale can help us look at different trends in the car market. The data is diverse and includes a broad range of makes, models, and years which will allow for more accurate aggregate data that limits the effect of outliers.

QUESTION 1:
---
For the Southeast region (for our defintion - Georgia, Florida, Tennessee, South Carolina, and North Carolina), how do the average sale prices of the 5 most popular manufacturers differ? We want to separate them by under 50,000 miles, between 50-100,000 miles, and over 100,000 miles to account for depreciation.

IMPORTANCE:

Say you're looking at this data from a consumer perspective. Dealerships can sometimes mark up their cars, so you want to see what you should be paying for a certain kind of car. This kind of dashboard can show you what the average price is of each of the top 5 most popular car brands at different mileage points. Additionally, you can also use this table as a prospective car buyer to see how depreciation affects each of these car brands. If you want to buy a car that holds it's value, you can look at the price difference between those under 50k miles and those over 100k miles. 

This table would also be helpful for someone like a car dealership. For example, a used car dealership could look at these average sale prices among different makes in the southeast and see which ones are worth buying and what they could potentially sell it for. 

ANALYSIS:

<img width="976" alt="Screenshot 2024-04-21 at 5 46 05 PM" src="https://github.com/brendanr14/MIST4610GroupProject2/assets/149964823/6ecfc9d4-be8f-4482-951f-4b97e7ecf13e">


Additionally, here is a map of the biggest car markets in the Southeast for these 5 brands.

<img width="1426" alt="Screenshot 2024-04-21 at 9 10 34 PM" src="https://github.com/brendanr14/MIST4610GroupProject2/assets/149964823/7ec128bb-1734-432b-96e7-7a2920748d67">


QUESTION 2:
---



DATA MANIPULATION:
---
There were a few different manipulation procedures we had to go through before visualizing our data. First, the first column in the table was all null. This was an easy fix, as we simply excluded the data. We also had to manipulate the data by creating calculated fields. The first of those is NormMake. The original Make column had some inconsistencies and resulted in multiple different rows for the same make (ex: bmw and BMW). Additionally, there were also some duplicate makes, such as Ford and Ford Truck, or VW and Volkswagen. To fix this, we created a calculated that first set all the Make strings to all uppercase. This would combine the rows that had a difference in capitalization. Then, we used a nested if/else statement to convert any additional Makes to their original (Ford Truck combines with Ford). Because of this, we can now look at all the data together and more cleanly.

The next calculated field we made was NormState. After filtering out the data that align well with our column, it was as simple as using the UPPER command to get all states to be uppercase. There was the same issue where for example there would be both 'ga' and 'GA'. This calculated field fixed that issue of separation. 

Lastly, the most difficult manipulation was the date data. Using the DATEPARSE function, we had to code the format of the string to allow Tableau to convert it to date data. We also had to include nested function that ignored the time zone part of the original string, as it was in a format that Tableau would not recognize.
