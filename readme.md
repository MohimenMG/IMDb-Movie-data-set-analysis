# TMDb dataset analysis

## Table of Contents
<ul>
<li><a href="#intro">Introduction</a></li>
<li><a href="#Preprocessing">Data Preprocessing</a></li>
<li><a href="#eda">Exploratory Data Analysis</a></li>
<li><a href="#conclusion">Conclusion</a></li>
</ul>

<a id='intro'></a>
## Introduction

### Dataset Description  [link](https://docs.google.com/document/d/e/2PACX-1vTlVmknRRnfy_4eTrjw5hYGaiQim5ctr9naaRd4V9du2B5bxpd8FEH3KtDgp8qVekw7Cj1GLk1IXdZi/pub?embedded=True)

	
This data set contains information about 10,000 movies collected from The Movie Database (TMDb), including user ratings and revenue. Certain columns, like ‘cast’ and ‘genres’, contain multiple values separated by pipe (|) characters.
There are some odd characters in the ‘cast’ column.
The final two columns ending with “_adj” show the budget and revenue of the associated movie in terms of 2010 dollars, accounting for inflation over time.


- **note:** _adj id used rather than actual value due to the change of the vlaue of the currancy through the years. this change in value is significant since the data available goes back to 1960

<a id='Preprocessing'></a>
## data Preprocessing
### inspecting the data:

the movie dataset contains: id columns unique to each movie, columns providing financial information like revenue, columns that provide rating features like popularity, and other columns include cast, production companies, and director.

**the following issues were discovered:**
1. almost **half** the dataset budget, budget_adj, revenue and revenue_adj column values are **"0"**.
2. 10% of the production_companies column rows are NaNs.
3. overview, keywords, tagline: needs a more advanced text analysis to provide useful data like pridecting good plots
4. release date: column format yy creates an issue, since dates start from 1960 to 2015.
5. id, imdb_id, homepage: doesnot provide any useful information.

### cleaning the data:
1. Removing zero value rows in budget and revenue columns and setting thier value in millions for easier readability.
2. Removing Null and duplicated rows
3. reformating the genre column

<a id='eda'></a>
## Exploratory Data Analysis

### 1)  what is the most produced movie genres?
### 2) what is the top production companies?
### 3)  who is the top actors?
### 4)  who is the top directors?
### 5)  Which genres are has highest popularity popularity form years to year? 
### 6)  investigating the popularity of movies from year to year?

**Year by year popularity distrbution with more popular years highligted:**
- it seams that the movie industry was growing slowly and started to preform above avarage above the ear 2000 excluding the year 2009, probably due to the economic conditions.
- there is an increase in popularity in the years 2014 and 2015, further data is needed to determine to detrmine if its a spike or an overall increase in popularity. 
- a quick google search about when did streaming become popular shows that netflix started streaming 2007 and became popular 2016. there maybe a corellation between popularity and streaming

### 7)  investigating the revenue of the most popular movies from year to year

**Year by year profit distrbution with more profitable years highligted:**

- yearly high profits are linked to the most popular movie of the year as almost all above avrage popularity movies before 2000 have above avrage profits 
- the dip in profit in 2010 might be correlated to the 2008 financial crisis

<a id='conclusion'></a>
### _Conclusion_:

the dataset contains alot of valuble data wich can lead to many finding with respect to the movie industry. however, there is some major limitation especially when working on the financial aspect; most of the budget and revenue data are set to zeros. these zeros affect the correlation results, thats why it was important to drop these values. further more alot of null are present in the production companies and cast datasets that needed to be droped to find the top actors like Robert de niro. action and adventure genres are tied as the most popular movie genres bieng the geres of the most popular movie of the year for more than 30 years. the distrbution of the above abarage most popular movie rating and above avrage revenue over the years reinforce the positive correletion between the revenue and the popularity of a movie 
