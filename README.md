# Heroes of Pymoli

## Background

An independent gaming company has requested an analysis of the data for their most recent fantasy game **Heros of Pymoli**. 

Like many other games in its genre, **Heros of Pymoli** is free-to-play, but users are encouraged to purchase optional items that enhance their playing experience. As a first task, the gaming company wants a generated report that breaks down the game's purchasing data into meaningful insights.

## Technology 

Jupyter Notebooks was used to write the code. Python version 3.7.6 is used, as well as Pandas Python library, to create DateFrames and perform analyses. 

## Table of Contents 
* [Player Count](#player-count)
* [Purchasing Analysis (Total)](#purchasing-analysis-total)
* [Gender Demographics](#gender-demographics)
  * [Purchasing Analysis (Gender)](#purchasing-analysis-gender)
* [Age Demographics](#age-demographics)
  * [Purchasing Analysis (Age)](#purchasing-analysis-age)
* [Top Spenders](#top-spenders)
* [Most Popular Items](#most-populat-items)
* [Most Profitable Items](#most-profitable-items)
* [Observable Trends](#observable-trends)

## Player Count 
By doing an `nunique()` on the "SN" (screennames) column of the purchase_data dataframe created from the [purchase_data.csv](https://github.com/cveras33/pandas-challenge/blob/master/Resources/purchase_data.csv) file, the total count of players is determined to be **576**. 

## Purchasing Analysis (Total)

To obtain the data for the derived dataframe for Purchasing Analysis, an `nunique()` was performed on the "Item Name" column of the original dataframe to get number of unique items, `mean()` was performed on the "Price" column to get the average price for unique items, `count()` was performed on the "Purchase ID" column to determine the total number of purchases made by players (even for non-unique items), and `sum()` was performed on the "Price" column to get total revenue. 

The table for the derived dataframe for Purchasing Analysis can be seen below. 

![purchasing_analysis](https://github.com/cveras33/pandas-challenge/blob/master/Images/purchasing_analysis.png)

## Gender Demographics

A dataframe which dropped any duplicate screennames, by performing a `drop_duplicates()` on the subset "SN", was derived from the original dataframe in order to do the data analysis for gender demographics, to ensure each player was only counted once. 

The counts for gender were obtained by performing a `value_counts()` on the "Gender" column, and the percentages were obtained by performing a `value_counts(normalize = True)` where `normalize = True` in the parenthesis calculated a percentage.

The table for the derived dataframe for Gender Demographics can be seen below. 

![gender_demographics](https://github.com/cveras33/pandas-challenge/blob/master/Images/gender_demographics.png)

### Purchasing Analysis (Gender)

For Purchasing Analysis by gender, each of the functions had `groupby(['Gender'])` come before the function of interest was performed on the dateframe so that the functions would be performed for each gender grouping. The gender groups are broken down into 3 seprate groupings: Male, Female, Other/Non-Disclosed. A `count()` is then done on the "Purchase ID" column to obtain the amount of purchases each respective gender group made. The `mean()` function was then used on the "Price" column, as well as the `sum()` function. Since these two rows are both currencies, to properly format the calculations done by the functions, `map("${:.2f}".format` was performed on the results. The last function performed was again a `sum()` function, but rather than finding the sum of all purchases, this was to find the average purchase price **per person**, so this result was then divided by the gender count from the gender demographics section. 

The table for the derived dataframe for Gender Purchasing Analysis can be seen below. 

![gender_purchasing_analysis](https://github.com/cveras33/pandas-challenge/blob/master/Images/gender_purchasing_analysis.png)

## Age Demographics

Similarly to the gender demographics, age demographics were requested to be analyzed as well. Since there are serveral more age groups than gender groups, the age groups were separated by binning. Ages below 10 are their own group, then groups are separated by every 5 years from 10-39, and anyone age 40+ is also in their own group. After separating the players in each age group into their respective 'bin', the same functions used in the Gender Demographics section are performed on the age demographics data. 

The table for the derived dataframe for Age Demographics can be seen below. 

![age_demographics](https://github.com/cveras33/pandas-challenge/blob/master/Images/age_demographics.png)

### Purchasing Analysis (Age)

Please reference Purchasing Analysis for Gender, as all the same functions and formatting are used for the Age Purchasing Analysis as well. 

The table for the derived dataframe for Age Purchasing Analysis can be seen below. 

![age_purcase_analysis](https://github.com/cveras33/pandas-challenge/blob/master/Images/age_purchase_analysis.png)

## Top Spenders

In order to determine which screennames are the top 5 spenders, first the data must be grouped by "SN", so all purchases and money spent per screenname are grouped together. To do this, a `groupby(['SN'])` is done, then the dataframe is sorted by the value of the sum of "Price" column for each screenname, in descending order, bringing the biggest spenders to the top of the dataframe. The average each player spent, as well as the total are also then calculated, and formatted as currency. How this is done has been discussed in previous sections (reference Purchasing Analysis (Gender)). 

The top 5 spenders can be seen below. 

![top_spender](https://github.com/cveras33/pandas-challenge/blob/master/Images/top_spenders.png)

## Most Popular Items

Similarly to the top spenders section, the data is first grouped by two attributes this time, "Item Name" and "Item ID". After that, all functions performed on the data are exactly the same as in the top spenders section. 

The 5 most popular items can be seen below. 

![popular](https://github.com/cveras33/pandas-challenge/blob/master/Images/most_popular_items.png)

## Most Profitable Items

Lastly, most profitable items are determined in the same mannor as the top spenders and the most popular items. 

The 5 most profitable items can be seen below. 

![profitable](https://github.com/cveras33/pandas-challenge/blob/master/Images/most_profitable_items.png)

## Observable Trends
* Most users are between the ages of 15 and 24.
* Althought most players are in the age ranges of 15-19 and 20-24 these are not the age rangers spending the most money playing the game. Rather, the age ranges spending the most money are those under 10 and between 35 and 39.
* Males make up a majority of players.

#### Status 
This project is *complete*. 

#### Contact 
Chloe Veras  
[Email](chloemveras@gmail.com)  
[LinkedIn](https://www.linkedin.com/in/chloeveras/)
