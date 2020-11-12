# Heroes of Pymoli

## Background

An independent gaming company has requested an analysis of the data for their most recent fantasy game **Heros of Pymoli**. 

Like many other games in its genre, **Heros of Pymoli** is free-to-play, but users are encouraged to purchase optional items that enhance their playing experience. As a first task, the gaming company wants a generated report that breaks down the game's purchasing data into meaningful insights.

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

![gender_purchasing_analysis](https://github.com/cveras33/pandas-challenge/blob/master/Images/gender_purchasing_analysis.png)

## Age Demographics

![age_demographics](https://github.com/cveras33/pandas-challenge/blob/master/Images/age_demographics.png)

### Purchasing Analysis (Age)

![age_purcase_analysis](https://github.com/cveras33/pandas-challenge/blob/master/Images/age_purchase_analysis.png)

## Top Spenders

![top_spender](https://github.com/cveras33/pandas-challenge/blob/master/Images/top_spenders.png)

## Most Popular Items

![popular](https://github.com/cveras33/pandas-challenge/blob/master/Images/most_popular_items.png)

## Most Profitable Items

![profitable](https://github.com/cveras33/pandas-challenge/blob/master/Images/most_profitable_items.png)

## Observable Trends
* Most users are between the ages of 15 and 24.
* Althought most players are in the age ranges of 15-19 and 20-24 these are not the age rangers spending the most money playing the game. Rather, the age ranges spending the most money are those under 10 and between 35 and 39.
* Males make up a majority of players.

#### Status 
This project is *complete*. 
