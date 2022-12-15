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
title = "5 steps to query the data"

+++
\[mind the 2nd person / third person\]

Data Scientists ask questions among themselves to search for meaningful data from large databases and to find hidden patterns. All these questions are in the native language rather than any database understandable language like SQL(Structured Query Language). 

Database Management System(DBMS) manages the data storage and provides an interface for data scientists to fetch the data from the storage. SQL standards are supported by most DBMS software programs and these standards are capable enough to convert any native language query into a DBMS understandable SQL query. 

This series of blog posts covers the multi-step approach that can convert these native questions into a SQL query. I tried to keep these steps friendly to the native reader rather than explaining each and every concept that SQL standards contain.

You need to understand how data is represented in the data stores before proceeding further. \[soften the tone\]

TABLE:

COLUMN:

ROW:

The rule of thumb is \[better words\]

* Your data is stored in one or multiple tables
* Your questions are framed based on the column data
* Your answers are in the form of rows, which will be provided by your database system.

\[input/output diagram\]

\[example\]

Below posts will help you understand how you can use the table and column data to fetch the required result set. \[re-intro need to correct\]

SQL clause has a dedicated operation for this, which will be used to interact with the database engine.

The query we are considering for this is,

Consider social media ad campaign, wants to know the number of active ad campaigns of each promoter name by region in each month in this year.

\[ Consider ending_date of the campign as final campign date.\] (move this to table description)

The expected result set should be in below format.

| promoter_name | region | active_campigns_count | month |

\[include relatable tables\]

Below 5 step process deal with the most useful SQL clauses.

The order of these clauses is also important which will define the syntax of the SQL query.

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