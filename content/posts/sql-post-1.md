---
title: First step to query the database
date: 2022-06-18T11:10:36.000+08:00
language: en
featured_image: "../assets/images/featured/featured-img-placeholder.png"
summary: ''
description: ''
author: Venu Gangireddy
authorimage: "../assets/images/global/author.webp"
categories: sql
tags:
- SQL
- 5 Steps
draft: true

---
\## Basic clauses:

\### SELECT:

This clause defines the list of columns that should be present in the result set.

SELECT clause followed by a list of the expected column in the result set.

The expected column can be one of the below three types compared to the relatable columns present in the given tables.

1\. Column: The required information can be present as a column in one of the given tables.

For example,

a. The expected promoter_name as part of the result set, is directly present in the Promoter table as a promoter_name column.

b. The region as part of the result set, is directly present in the Adcampign table as a region column.

The column information can be projected directly in the result set.

2\. Transformed Column: The required information is not present in any of the tables, but can be derived from one or more columns present in a table.

For example,

a. The campine month information is not present as a column in any table but can be derived from the end_date of the camping, by extracting MONTH from the date field.

This kind of extraction/transformation operations can be performed by functions defined in the database engine.

The function takes a column as input and performs the defined transformation on each entry of the column and projects the transformed to result in the final result set.

The most commonly used functions on date field are,

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