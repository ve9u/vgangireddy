+++
author = "Venu Gangireddy"
authorimage = "../assets/images/global/author.webp"
categories = "sql"
date = 2022-11-12T18:30:00Z
description = ""
draft = true
featured_image = "../assets/images/featured/featured-img-placeholder.png"
language = "en"
summary = ""
tags = ["SQL", "5 Steps"]
title = "5 steps to fetch the data"

+++
Data Scientists meaningful data from large data stores to find hidden patterns. SQL can be used to fetch the only required data from the.

This chapter covers multi-step approach to convert given query into SQL format.

SQL clause has a dedicated operation for this, which will be used to interact with the database engine.

The query we are considering for this,

Consider social media ad campaign, wants to know number of active ad campaigns of each promoter name by region in each month in this year. 

\[ Consider ending_date of the campign as final campign date.\] (move this to table description)

The expected result set should be in below format.

| promoter_name | region | active_campigns_count | month |

\[include relateable tables\]

Below 5 step process deal with most useful SQL clauses.

These are building block for constituting more complex queries in further chapters.

The order of these clauses also importent which will define the syntax of the SQL query. 

\## Basic clauses:

\### SELECT: 

This clause defines the list of columns should be present in the result set.

SELECT clause followed by list of expected column in the result set.

The expected column can be one of the below three types compare to the the relateable columns present in the given tables.

1\. Column: The required information can be present as  column in one of the given table.

For example, 

a. The expected promoter_name as part of result set, directly present in the Promoter table as promoter_name column.

b. The region as part of result set, directly present in the Adcampign table as region column.

The coloumn information can be projected directly in the result set.

2\. Transformed Column: The required information not present in any of tables, but can be derived from the one or more coloumn present in a table. 

For example, 

a. The campine month information not present as column in any table, but can be derived from the end_date of the camping, by extracting MONTH from the date field. 

These kind of extraction / transformation operations can be performed by functions defined in the database engine. 

The function take column as input and perform the defined transformation on each entry of the coloumn and project transformed result in the final result set. 

Most commonly used function on date field are,

MONTH(), YEAR() \[add table here\]

\`MONTH(end_date)\` could get us required month value.

2\. Aggregated Information: The required information not present in any of tables, but can be derived from by aggregateing or combining values from one or multiple coloumns in given tables.

For example: There is no column can replace active_campign_count, but couting number of campign_id from AdCampign can replace active_campign_count.

Aggregated operation combine set of column entries into one single value, unlike normal function the end result will be single value.

1\. Count:

2\. Min:

3\. Max:

4\. Sum:

Gather all required column information and which tables these columns are belongs to.

| Column |  Type | Table | source | function |

| --- | ----------- |------- | -------- | ----- |

| promoter_name | Direct | Promoter | promoter_name | |

| region  | Direct | AdCampign | region | |

| month | Transformed | AdCampign | end_date | MONTH() |

| active_campign_count | Aggregated | AdCampign | campign_id | COUNT() |

Above table can be used to compose SELECT clause, this can be done by appling appropriate function on the source column. 

SELECT promoter_name, region, MONTH(end_date), COUNT(campign_id)

The project coloumn will be same as projected coloumn with the same header name. It will be like below.

| promoter_name | region | COUNT(campign_id) | MONTH(end_date) |

These names are not user friendly, we can mention the alias name by adding as next to it.

SELECT promoter_name, region, MONTH(end_date) AS month, COUNT(campign_id) AS active_campigns_count

As a syntatical suger we can ignore AS from the statement. This book further won't use AS, and the final SELECT statement will look like,

SELECT promoter_name, region, MONTH(end_date) month, COUNT(campign_id) active_campigns_count

\### FROM : What tables data been stored

This clause represents in what tables the information is resides. 

Place all the tables from above list in this clause. 

It is possible that required columns are from different tables, but there is only one results set. Database engine do this magic of combining the data from different table called JOIN operation. We need to learn how to use this JOIN operation. We learn only simple JOIN(Natural JOIN) operation now, we will learn other flavors of in next chapters. 

Natural JOIN: 

This will combine the same columns of different tables based on JOIN predicate.

1\. Tables involved in JOIN operation.

2\. JOIN Predicate: The general rule of thumb is JOIN predicate happens between primary key and foreign key.

Predicate: True or False.

explain equal predicate

Example:

FROM TABLE-A JOIN TABLE-B ON 

\### Where: 

These will be used to add additional predicates

1\. Less than

2\. Greater than 

3\. Not equal

4\. equal

\### GROUP BY: Rest of the fields which are not participating in the aggregate operations

These columns will group the result set into subset before applying aggregation operations, so that aggregated operation will happen in the groups.

The general rule of thumb, all non-aggregated cloumns in the 

\### Having: Filter on aggregated fields.

This filed apply predicate condition over aggregated columns in the result-set.

\## Additional Basic Clauses:

1\. Sort the result set. 

Sometime results set need to present in a meaningful way by sorting based on different column values. 

ORDER BY clause will be used to sort the result set. 

based on subset of columns mentioned in the SELECT clause. 

Example:

2\. Only need top results:

Only interested in top results

LIMIT 10 OFFSET

\### Practice questions

\`\`\`{r tables}

dbListTables(mysqlconnection)

\`\`\`

Sales

Orders

Products

Employees: employee_id, employee_name,

Login

1\. Write SQL query to get all data from the Employee table. 

Follow 5 rules.

a. Project all columns

SELECT *

Introduce *:

Not recommended considering dealing with large volume of data. 

Get some estimate before doing actual operation

Introduce EXPLAN

2\. How many total columns in Employee table. 

Follow 5 rules.

Introduce count(*):

Introduce explain

2\. Select most recent login times

select the most recent login time by values from the login_info table

 

\`\`\`SQL

 CREATE TABLE login_info (

 user_id INT,

 login_time DATETIME

 );

\`\`\`

3\. Write a SQL query to find all duplicate emails in the Employee table.

4\. Write SQL query to find all duplicates in sales table.

5\. Authors: author_name,	book_name (1M)

  Books: book_name, sold_copies.(1M)

  

  Top 3 authors with most sold copies

  

6\. Select max. salary of each department.

7\. Write an SQL Query to find the number of employees according to gender whose DOB is between 01/01/1960 to 31/12/1975.

Read more: [https://www.java67.com/2013/04/10-frequently-asked-sql-query-interview-questions-answers-database.html#ixzz7ZKBhuirc](https://www.java67.com/2013/04/10-frequently-asked-sql-query-interview-questions-answers-database.html#ixzz7ZKBhuirc "https://www.java67.com/2013/04/10-frequently-asked-sql-query-interview-questions-answers-database.html#ixzz7ZKBhuirc")

8\. Write an SQL Query to find an employee whose salary is equal to or greater than 10000.

Read more: [https://www.java67.com/2013/04/10-frequently-asked-sql-query-interview-questions-answers-database.html#ixzz7ZKBnVubE](https://www.java67.com/2013/04/10-frequently-asked-sql-query-interview-questions-answers-database.html#ixzz7ZKBnVubE "https://www.java67.com/2013/04/10-frequently-asked-sql-query-interview-questions-answers-database.html#ixzz7ZKBnVubE")