# 面试总结之Database / SQL

* [database/学习笔记之Database-SQL at main · haoran119/database](https://github.com/haoran119/database/tree/main/%E5%AD%A6%E4%B9%A0%E7%AC%94%E8%AE%B0%E4%B9%8BDatabase-SQL)

## DATABASE

* [Solve Databases | HackerRank](https://www.hackerrank.com/domains/databases)
* [What is a Columnar Database? - GeeksforGeeks](https://www.geeksforgeeks.org/what-is-a-columnar-database/?ref=gcse)
* 什么是数据库事务？
  * [数据库事务_百度百科](https://baike.baidu.com/item/%E6%95%B0%E6%8D%AE%E5%BA%93%E4%BA%8B%E5%8A%A1/9744607?fr=aladdin)
  * 一个逻辑工作单元要成为事务，必须满足所谓的ACID（原子性（atomicity，或称不可分割性）、一致性（consistency）、隔离性（isolation，又称独立性）、持久性（durability)）属性。
* 索引如何实现？
  * [数据库索引_百度百科](https://baike.baidu.com/item/%E6%95%B0%E6%8D%AE%E5%BA%93%E7%B4%A2%E5%BC%95/8751686?fr=aladdin)
  * 存储为文件
* lock
  * [What is lock (database)? - SQL Server Comparison Expert](http://www.databasecompare.com/What-is-lock-(database).html)
  * [详解面试中常考的数据库「锁」问题](https://mp.weixin.qq.com/s/QI4ahAkPzrpprLCDDi4oDA)
* What is Cursor?
  * Cursor is a database object used by applications to manipulate data in a set on a row-by-row basis, instead of the typical SQL commands that operate on all the rows in the set at one time.
  * In order to work with a cursor we need to perform some steps in the following order:
    * Declare cursor
    * Open cursor
    * Fetch row from the cursor
    * Process fetched row
    * Close cursor
    * Deallocate cursor (Read More Here)
* What is Collation?
  * Collation refers to a set of rules that determine how data is sorted and compared. Character data is sorted using rules that define the correct character sequence, with options for specifying case sensitivity, accent marks, kana character types and character width. (Read More Here)
* What is User Defined Functions? What kind of User-Defined Functions can be created?
  * User-Defined Functions allow defining its own T-SQL functions that can accept 0 or more parameters and return a single scalar data value or a table data type.
  * Different Kinds of User-Defined Functions created are: 
    * Scalar User-Defined Function
      * A Scalar user-defined function returns one of the scalar data types. Text, ntext, image and timestamp data types are not supported. These are the type of user-defined functions that most developers are used to in other programming languages. You pass in 0 to many parameters and you get a return value.
    * Inline Table-Value User-Defined Function
      * An Inline Table-Value user-defined function returns a table data type and is an exceptional alternative to a view as the user-defined function can pass parameters into a T-SQL select command and in essence provide us with a parameterized, non-updateable view of the underlying tables.
    * Multi-statement Table-Value User-Defined Function
      * A Multi-Statement Table-Value user-defined function returns a table and is also an exceptional alternative to a view as the function can support multiple T-SQL statements to build the final result where the view is limited to a single SELECT statement. Also, the ability to pass parameters into a TSQL select command or a group of them gives us the capability to in essence create a parameterized, non-updateable view of the data in the underlying tables. Within the create function command you must define the table structure that is being returned. After creating this type of user-defined function, It can be used in the FROM clause of a T-SQL command unlike the behavior found when using a stored procedure which can also return record sets. (Read Here For Example)
* Window Functions
  * [Window functions in SQL - GeeksforGeeks](https://www.geeksforgeeks.org/window-functions-in-sql/?ref=gcse)
    * Window functions applies aggregate and ranking functions over a particular window (set of rows). OVER clause is used with window functions to define that window. OVER clause does two things : 
      * Partitions rows into form set of rows. (PARTITION BY clause is used) 
      * Orders rows within those partitions into a particular order. (ORDER BY clause is used) 
    * Note – If partitions aren’t done, then ORDER BY orders all rows of table. 
  * [Window Functions](https://www.sqlite.org/windowfunctions.html)
    * A window function is an SQL function where the input values are taken from a "window" of one or more rows in the results set of a SELECT statement.
    * Window functions are distinguished from other SQL functions by the presence of an OVER clause. If a function has an OVER clause, then it is a window function. If it lacks an OVER clause, then it is an ordinary aggregate or scalar function. Window functions might also have a FILTER clause in between the function and the OVER clause.
* What is Difference between Function and Stored Procedure?
  * UDF can be used in the SQL statements anywhere in the WHERE/HAVING/SELECT section where as Stored procedures cannot be. UDFs that return tables can be treated as another rowset. This can be used in JOINs with other tables. Inline UDF’s can be thought of as views that take parameters and can be used in JOINs and other Rowset operations.
* What is sub-query? Explain properties of sub-query?
  * Sub-queries are often referred to as sub-selects, as they allow a SELECT statement to be executed arbitrarily within the body of another SQL statement. A sub-query is executed by enclosing it in a set of parentheses. Sub-queries are generally used to return a single row as an atomic value, though they may be used to compare values against multiple rows with the IN keyword.
  * A subquery is a SELECT statement that is nested within another T-SQL statement. A subquery SELECT statement if executed independently of the T-SQL statement, in which it is nested, will return a resultset. Meaning a subquery SELECT statement can standalone and is not depended on the statement in which it is nested. A subquery SELECT statement can return any number of values, and can be found in, the column list of a SELECT statement, a FROM, GROUP BY, HAVING, and/or ORDER BY clauses of a T-SQL statement. A Subquery can also be used as a parameter to a function call. Basically a subquery can be used anywhere an expression can be used. (Read More Here)
* [CTE in SQL - GeeksforGeeks](https://www.geeksforgeeks.org/cte-in-sql/?ref=gcse)
  * The Common Table Expressions (CTE) were introduced into standard SQL in order to simplify various classes of SQL Queries for which a derived table was just unsuitable.
  * We can define CTEs by adding a WITH clause directly before SELECT, INSERT, UPDATE, DELETE, or MERGE statement. The WITH clause can include one or more CTEs separated by commas. 
  * Thus CTEs can be a useful tool when you need to generate temporary result sets that can be accessed in a SELECT, INSERT, UPDATE, DELETE, or MERGE statement.
* What are different Types of Join?
  * Cross Join
    * A cross join that does not have a WHERE clause produces the Cartesian product of the tables involved in the join. The size of a Cartesian product result set is the number of rows in the first table multiplied by the number of rows in the second table. The common example is when company wants to combine each product with a pricing table to analyze each product at each price.
  * Inner Join
    * A join that displays only the rows that have a match in both joined tables is known as inner Join.  This is the default type of join in the Query and View Designer.
  * Outer Join
    * A join that includes rows even if they do not have related rows in the joined table is an Outer Join.  You can create three different outer join to specify the unmatched rows to be included:
  * Left Outer Join: 
    * In Left Outer Join all rows in the first-named table i.e. “left” table, which appears leftmost in the JOIN clause are included. Unmatched rows in the right table do not appear. 
  * Right Outer Join: 
    * In Right Outer Join all rows in the second-named table i.e. “right” table, which appears rightmost in the JOIN clause are included. Unmatched rows in the left table are not included.
  * Full Outer Join: 
    * In Full Outer Join all rows in all joined tables are included, whether they are matched or not.
  * Self Join
    * This is a particular case when one table joins to itself, with one or two aliases to avoid confusion. A self join can be of any type, as long as the joined tables are the same. A self join is rather unique in that it involves a relationship with only one table. The common example is when company has a hierarchal reporting structure whereby one member of staff reports to another. Self Join can be Outer Join or Inner Join. (Read More Here)
* What are primary keys and foreign keys?
  * Primary keys are the unique identifiers for each row. They must contain unique values and cannot be null. Due to their importance in relational databases, Primary keys are the most fundamental of all keys and constraints. A table can have only one Primary key.
  * Foreign keys are both a method of ensuring data integrity and a manifestation of the relationship between tables.
  * [Difference between Primary key and Unique key - GeeksforGeeks](https://www.geeksforgeeks.org/difference-between-primary-key-and-unique-key/)
    * Key Differences Between Primary key and Unique key: 
      * Primary key will not accept NULL values whereas Unique key can accept NULL values.
      * A table can have only primary key whereas there can be multiple unique key on a table.
      * A Clustered index automatically created when a primary key is defined whereas Unique key generates the non-clustered index.

|Parameter |	PRIMARY KEY |	UNIQUE KEY|
|-|-|-|
|	Basic	|	Used to serve as a unique identifier for each row in a table.	|	Uniquely determines a row which isn’t primary key.|	
|	NULL value acceptance	|	Cannot accept NULL values.	|	Can accepts NULL values.|	
|	Number of keys that can be defined in the table	|	Only one primary key	|	More than one unique key|	
|	Index	|	Creates clustered index	|	Creates non-clustered index|	

* How to ensure integrity ?
  * constraint and foreign keys ?
* What is Identity?
  * Identity (or AutoNumber) is a column that automatically generates numeric values. A start and increment value can be set, but most DBA leave these at 1. A GUID column also generates numbers; the value of this cannot be controlled. Identity/GUID columns do not need to be indexed.
* 机器Crash之后数据如何备份恢复？
* 大文件如何读取到数据库？
  * ? Cache
* 如何分析SQL语句执行很慢？
  * ? SQL explain
* 提供一套关于地址的数据，包含街道 / 区 / 城市 / 州 / 邮编。但是没有国家。然后提供n个function，每个function对应一个国家，你把数据输入进去，会返回true false。问怎么最快速的辨别每个数据的国家。
  * ？以这些数据做为feature，建模进行机器学习。E.g. zip code 2000对应Australia。
  * ？Hashmap
* 提供一组以tree的形式展示的数据，区域+cost，计算每个大区的总和
  * How to implement a hierarchical dataset using SQL
  * [Hierarchical database model - Wikipedia](https://en.wikipedia.org/wiki/Hierarchical_database_model)
  * [Hierarchical Data in SQL: The Ultimate Guide - Database Star](https://www.databasestar.com/hierarchical-data-sql/)
    * What is Hierarchical Data?
    * Adjacency List
      * Adjacency List is a design method for implementing hierarchical data. It’s achieved by storing the ID of the related record on the desired record. You add one column to your table, and set it as a foreign key to the same table’s primary key.
      * This is the method that I recommend using for most cases.
      * Pros
        * It’s easy to implement. It just involves adding a new column that refers to the ID of the parent record in the same table.
        * It’s easy to add new items.
        * It’s easy to move items to a different place in the hierarchy.
        * It’s fairly easy to remove items.
      * Cons
        * The query to fetch data is complicated. In most databases you need to write a WITH clause with two queries inside it.
        * The query to fetch the entire tree, or subset of the tree, can be slow to run with a large amount of records.
        * It can be hard to find the path of a record from the root to the current record.
        * Deleting items that have children causes the children’s relationship to break, or the delete will fail, depending on the constraint settings. You’ll need to update the children to move them to a new parent before deleting.
    * Nested Set
    * Flat Table
    * Bridge Table or Closure Table
    * Lineage Column or Path Enumeration
    * Summary of Methods
    * Which Method Should I Use?
    * Conclusion
* [腾讯面试：一条SQL语句执行得很慢的原因有哪些？](https://mp.weixin.qq.com/s/2o0iS4LVzl5PDz1zTILnLw)
* [面试官：数据量很大，分页查询很慢，怎么优化？](http://uusama.com/458.html)
* [面试官：给我讲一下分库分表方案](https://www.cnblogs.com/littlecharacter/p/9342129.html)
* [一个高频面试题：怎么保证缓存与数据库的双写一致性？](https://blog.csdn.net/chang384915878/article/details/86756463)
* [【字节二面】缓存一致性如何保证？ (qq.com)](https://mp.weixin.qq.com/s/-hvhV3GFef4BeDRRUFY6yw)
* [面试常考！缓存三大问题及解决方案](https://juejin.im/post/5b604b9ef265da0f62639001)
* [高并发之存储篇：关注下索引原理和优化吧！ (qq.com)](https://mp.weixin.qq.com/s/xmAhtJXFNkmOR4Cko9e-cQ)
* [面试官：数据库自增ID用完了会怎么样？ (qq.com)](https://mp.weixin.qq.com/s/iZPBpq2hVL6NdbGz-gcPTw)

## DATA WAREHOUSE

* What is DataWarehousing?
  * Subject-oriented, meaning that the data in the database is organized so that all the data elements relating to the same real-world event or object are linked together;
  * Time-variant, meaning that the changes to the data in the database are tracked and recorded so that reports can be produced showing changes over time;
  * Non-volatile, meaning that data in the database is never over-written or deleted, once committed, the data is static, read-only, but retained for future reporting.
  * Integrated, meaning that the database contains data from most or all of an organization’s operational applications, and that this data is made consistent.
* OLAP v.s. OLTP
  * [OLTP vs OLAP: Difference Between OLTP and OLAP](https://www.guru99.com/oltp-vs-olap.html)
  * What is OLAP?
    * Online Analytical Processing, a category of software tools which provide analysis of data for business decisions. OLAP systems allow users to analyze database information from multiple database systems at one time.
    * The primary objective is data analysis and not data processing.
  * What is OLTP?
    * Online transaction processing shortly known as OLTP supports transaction-oriented applications in a 3-tier architecture. OLTP administers day to day transaction of an organization.
    * The primary objective is data processing and not data analysis
  * Example of OLAP
    * Any Datawarehouse system is an OLAP system. 
  * Example of OLTP system
    * An example of OLTP system is ATM center. 
  * KEY DIFFERENCE between OLTP and OLAP:
    * Online Analytical Processing (OLAP) is a category of software tools that analyze data stored in a database whereas Online transaction processing (OLTP) supports transaction-oriented applications in a 3-tier architecture.
    * OLAP creates a single platform for all type of business analysis needs which includes planning, budgeting, forecasting, and analysis while OLTP is useful to administer day to day transactions of an organization.
    * OLAP is characterized by a large volume of data while OLTP is characterized by large numbers of short online transactions.
    * In OLAP, data warehouse is created uniquely so that it can integrate different data sources for building a consolidated database whereas OLTP uses traditional DBMS.
* ETL v.s. ELT
  * [Extract, transform, load - Wikipedia](https://en.wikipedia.org/wiki/Extract,_transform,_load#ETL_Vs._ELT)
    * In computing, extract, transform, load (ETL) is the general procedure of copying data from one or more sources into a destination system which represents the data differently from the source(s) or in a different context than the source(s). The ETL process became a popular concept in the 1970s and is often used in data warehousing.[1]
    * Data extraction involves extracting data from homogeneous or heterogeneous sources; data transformation processes data by data cleaning and transforming them into a proper storage format/structure for the purposes of querying and analysis; finally, data loading describes the insertion of data into the final target database such as an operational data store, a data mart, data lake or a data warehouse.[2][3]
    * A properly designed ETL system extracts data from the source systems, enforces data quality and consistency standards, conforms data so that separate sources can be used together, and finally delivers data in a presentation-ready format so that application developers can build applications and end users can make decisions.[4]
    * Since the data extraction takes time, it is common to execute the three phases in pipeline. While the data is being extracted, another transformation process executes while processing the data already received and prepares it for loading while the data loading begins without waiting for the completion of the previous phases.
    * ETL systems commonly integrate data from multiple applications (systems), typically developed and supported by different vendors or hosted on separate computer hardware. The separate systems containing the original data are frequently managed and operated by different employees. For example, a cost accounting system may combine data from payroll, sales, and purchasing.
  * [Extract, load, transform - Wikipedia](https://en.wikipedia.org/wiki/Extract,_load,_transform)
    * Extract, load, transform (ELT) is an alternative to extract, transform, load (ETL) used with data lake implementations. In contrast to ETL, in ELT models the data is not transformed on entry to the data lake, but stored in its original raw format. This enables faster loading times. However, ELT requires sufficient processing power within the data processing engine to carry out the transformation on demand, to return the results in a timely manner. Since the data is not processed on entry to the data lake, the query and schema do not need to be defined a priori (although often the schema will be available during load since many data sources are extracts from databases or similar structured data systems and hence have an associated schema). ELT is a data pipeline model.[1]
  * [Data lake - Wikipedia](https://en.wikipedia.org/wiki/Data_lake)
    * A data lake is a system or repository of data stored in its natural/raw format,[1] usually object blobs or files. A data lake is usually a single store of data including raw copies of source system data, sensor data, social data etc.,[2] and transformed data used for tasks such as reporting, visualization, advanced analytics and machine learning. A data lake can include structured data from relational databases (rows and columns), semi-structured data (CSV, logs, XML, JSON), unstructured data (emails, documents, PDFs) and binary data (images, audio, video).[3] A data lake can be established "on premises" (within an organization's data centers) or "in the cloud" (using cloud services from vendors such as Amazon, Microsoft, or Google).
    * A data swamp is a deteriorated and unmanaged data lake that is either inaccessible to its intended users or is providing little value.[4]
* [ETL vs ELT: Key Differences, Side-by-Side Comparisons, & Use Cases (rivery.io)](https://rivery.io/blog/etl-vs-elt/)
  * ETL (Extract, Transform, Load) and ELT (Extract, Load, Transform) are both data integration methods that transfer data from a source to a data warehouse. Despite similarities, ETL and ELT differ in fundamental ways. Here’s a quick comparison of ETL and ELT (ETL vs ELT).
  * What is ETL (Extract, Transform, Load)?
    * Extract, transform, and load (ETL) is a data integration methodology that extracts raw data from sources, transforms the data on a secondary processing server, and then loads the data into a target database.
  * What Is ELT (Extract, Load, Transform)?
    * Unlike ETL, extract, load, and transform (ELT) does not require data transformations to take place before the loading process.
    * ELT loads raw data directly into a target data warehouse, instead of moving it to a processing server for transformation.
    * Cloud data warehouses such as Snowflake, Amazon Redshift, Google BigQuery, and Microsoft Azure all have the digital infrastructure, in terms of storage and processing power, to facilitate raw data repositories and in-app transformations.
  * ETL vs ELT: How is ETL Different from the ELT Process?
    * ETL and ELT differ in two primary ways. One difference is where the data is transformed, and the other difference is how data warehouses retain data.
      * ETL transforms data on a separate processing server, while ELT transforms data within the data warehouse itself.
      * ETL does not transfer raw data into the data warehouse, while ELT sends raw data directly to the data warehouse.
  * ETL vs ELT: Side-by-Side Comparison

|Category | ETL | ELT|
|- | - | -|
Definition | Data is extracted from a source system, transformed on a secondary processing server, and loaded into a destination system. | Data is extracted from a source system, loaded into a destination system, and transformed inside the destination system. 
Extract | Raw data is extracted using API connectors. | Raw data is extracted using API connectors.
Transform | Raw data is transformed on a processing server. | Raw data is transformed inside the target system. 
Load | Transformed data is loaded into a destination system. | Raw data is loaded directly into the target system.
Speed | ETL is a time-intensive process; data is transformed before loading into a destination system. | ELT is faster by comparison; data is loaded directly into a destination system, and transformed in-parallel.
Code-Based Transformations | Performed on secondary server. Best for compute-intensive transformations & pre-cleansing.  | Transformations performed in-database; simultaneous load & transform; speed & efficiency.
Maturity | Modern ETL has existed for 20+ years; its practices & protocols are well-known and documented. | ELT is a newer form of data integration; less documentation & experience. 
Privacy | Pre-load transformation can eliminate PII (helps for HIPPA). | Direct loading of data requires more privacy safeguards.
Maintenance | Secondary processing server adds to the maintenance burden. | With fewer systems, the maintenance burden is reduced.
Costs | Separate servers can create cost issues. | Simplified data stack costs less.
Requeries | Data is transformed before entering destination system; therefore raw data cannot be requeried. | Raw data is loaded directly into destination system and can be requeried endlessly.
Data Lake Compatibility  | No, ETL does not have data lake compatibility.  | Yes, ELT does have data lake compatibility. 
Data Output | Structured (typically). | Structured, semi-structured, unstructured.
Data Volume  | Ideal for small data sets with complicated transformation requirements.  | Ideal for large datasets that require speed & efficiency.

  * A Brief History: ETL & ELT Processes
  * Which is Better: ETL or ELT?

## MYSQL

* [CASE() Function in MySQL - GeeksforGeeks](https://www.geeksforgeeks.org/case-function-in-mysql/?ref=gcse)
```SQL
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```
* [MySQL | Regular expressions (Regexp) - GeeksforGeeks](https://www.geeksforgeeks.org/mysql-regular-expressions-regexp/)
  * MySQL supports another type of pattern matching operation based on the regular expressions and the REGEXP operator.
* [RIGHT() Function in MySQL - GeeksforGeeks](https://www.geeksforgeeks.org/right-function-in-mysql/?ref=gcse)
  * RIGHT() function in MySQL is used to extract a specified number of characters from the right side of a given string. Second argument is used to decide, how many characters it should return.
  * Syntax :
    * RIGHT( str, len )
* [面试官：谈谈你对MySQL索引的认识？](https://mp.weixin.qq.com/s/NRapquVpiqynt4BOUCwCoQ)
* [面试小知识：MySQL索引相关 - 数据库开发](https://mp.weixin.qq.com/s/j-meke0QMqTgPInj118UZA)
* [面试官：为什么 MySQL 的索引要使用 B+ 树，而不是其它树？比如 B 树？](https://mp.weixin.qq.com/s/k1BqFgc2ck_HR5Q6HmnNWQ)
  * https://www.cnblogs.com/leefreeman/p/8315844.html
* [【面试现场】为什么 MySQL 数据库要用B+树存储索引？](https://mp.weixin.qq.com/s/XN8PyiRFOyHAh6HLuTlD1Q)
* [MySQL 如何查找删除重复行？ - 数据库开发](https://mp.weixin.qq.com/s/qKoXTjdupjY25k6_-7PwxA)
* [面试官：MySQL 表设计要注意什么？](https://mp.weixin.qq.com/s/TGvLTVUIg6Lam9CfjALLGQ)
* [MySQL 优化面试解析](https://mp.weixin.qq.com/s/awRZ3fmN879MtuuZ2cb9pw)
  * http://www.zhenganwen.top/articles/2018/12/25/1565048860202.html
* [面试 | 巧用 explain 优化 MySQL 语句](https://mp.weixin.qq.com/s/OnfMdisiJ_f-HgIyOvc0qw)
* [什么是MySQL的执行计划（Explain关键字）？ (qq.com)](https://mp.weixin.qq.com/s/E8wJQvldwEAzxK5mEuFhog)
* [MySQL 面试，必须掌握的 8 个知识点](https://mp.weixin.qq.com/s/MKOoKuymUr-ZUVOT6jKfQg)
* [MySQL的COUNT语句](https://mp.weixin.qq.com/s/UZgBdR_j1Oi2KK8XN7tGbQ)
* [100 道 MySQL 数据库经典面试题解析 (qq.com)](https://mp.weixin.qq.com/s/0Rahp4jZIngs14HFh2mToQ)
* [很用心的为你写了 9 道 MySQL 面试题 (qq.com)](https://mp.weixin.qq.com/s/6FKthnz2NaykgB1nrGjI4Q)
* [MySQL 海量数据优化（理论+实战）(qq.com)](https://mp.weixin.qq.com/s/z7iiHa-dLoHf651Gx52SQA)
* [为什么 MySQL 使用 B+ 树 (qq.com)](https://mp.weixin.qq.com/s/71PL1-0hx7MFwlJhvKLHpg)
* [Mysql 夺命连环 13 问，你能抗住多少题？ (qq.com)](https://mp.weixin.qq.com/s/ovNswH3FrnqO4RZ7TItRaA)
* [阿里二面，为什么MySQL选择Repeatable Read作为默认隔离级别？ (qq.com)](https://mp.weixin.qq.com/s/bbtrO4ZP-5KnQ_XWXQh1sA)

## REDIS

* [Redis 常见面试题请收好 | 原力计划 (qq.com)](https://mp.weixin.qq.com/s/a_OU80touv7RVXosy6YULw)
* [美团二面：Redis与MySQL双写一致性如何保证？ (qq.com)](https://mp.weixin.qq.com/s/N4LZwRRvj95ZavZewG0adw)

## SQL

* [Solve SQL | HackerRank](https://www.hackerrank.com/domains/sql?badge_type=sql)
* [破解面试难题8个角度带你解读SQL面试技巧！ (qq.com)](https://mp.weixin.qq.com/s/BvGSzmKBSBBcnS84xh_M7w)
* [我说 SELECT COUNT(*) 会造成全表扫描 (qq.com)](https://mp.weixin.qq.com/s/NZjPYa2YA3K7OY_-hqdmhA)
* [数据科学家常见的5个SQL面试问题 (qq.com)](https://mp.weixin.qq.com/s/7n8EC3qqpZfWa4OybLPCMA)
* [经典 SQL 笔试面试题：求解连续区间 (qq.com)](https://mp.weixin.qq.com/s/i2gnSquBWh_HKKiy4OUQCQ)

1. 现有一张学生表，有只有一个列是名字，请选出其中的重名的学生的名字
```SQL
select name from student group by name having count(*) > 1
```
2. 从公司员工工资表中选出所有部门平均工资大于公司平均工资的部门里的所有员工记录
```SQL
select * from company where department in (select department 
from company 
group by deparment 
having avg(salary) > (select avg(salary) from company)
) 
```
3. Given the two following tables.
Names
Name Number
Wayne Gretzky 99
Jaromir Jagr 68
Bobby Orr 4
Bobby Hull 23
Brett Hull 16
Mario Lemieux 66
Steve Yzerman 19
Claude Lemieux 19
Mark Messier 11
Mats Sundin 13

Points
Name Points
Wayne Gretzky 244
Jaromir Jagr 168
Bobby Orr 129
Bobby Hull 93
Brett Hull 121
Mario Lemieux 109
Joe Sakic 94

Write SQL statement to display the player’s Names, numbers and points for all players represented by an entry in both tables?
```SQL
SELECT names.name, names.number, points.points FROM names INNER JOIN points ON names.name=points.name
```
4. Given

STAFF
id INTEGER
name CHAR(20)
dept INTEGER
job CHAR(20)
years INTEGER
salary DECIMAL(10, 2)
comm. DECIMAL(10, 2)

Write a SQL sentence to retrun total number of employees in each department with corresponding department id under the following conditions:
Only return departments with at least one employee receiving a commission greater than 5000. The results should be sorted by the department count from most to least
```SQL
SELECT dept, COUNT (*) FROM staff GROUP BY dept HAVING comm.>5000 ORDER BY 1 DESC
```
5. Given the two following table definitions

ORG
deptnumb INTEGER
deptname CHAR(30)
manager INTEGER
division CHAR(30)
location CHAR(30)

STAFF
id INTEGER
name CHAR(30)
dept INTEGER
job CHAR(20)
years INTEGER
salary DECIMAL(10, 2)
comm DECIMAL(10, 2)

Write a SQL statement to display each department by name, and the total salary of all employees in the department?
```SQL
SELECT a.deptname, SUM(b.salary) FROM org a, staff b WHERE a.deptnumb=b.dept GROUP BY a.deptname
```

### Understanding of table, view and index.
Given tables as follows:

T1
Col1 Col2
1 10
2 20
3 20
4 30
5 30
6 30

T2
Col1 Col2
1 10
2 20
3 30
4 40
5 50
6 60

1. Please write a query based on T1 and T2 which produces:
ColA ColB
1 10
2 20
3 20
3 30
4 30
4 40
5 30
5 50
6 30
6 60
(Hint: the result set is produced from merging T1 and T2 together, without duplicate values)

2. Please write a query based on T1 which produces:

Col2

20

30

Note that DON'T use hard coded 'where clause' to simply 'select distinct col2 from t1 where col2 = 20 or col2 = 30'.

( Hint: 20 and 30 apprear more than once in col2 of T1)

3. Please write the result of the following query:
select A.col1, B.col1, A.col2, B.col2 from T1 A FULL OUTER JOIN T2 B ON (A.col2 = B.col2);

4. Please list the database objects you know (for example, table is one of the objects). Describe how to use them and why do you use them.

5. How many kinds of keys in database? How to use them?

6. We want to prevent the users from inserting the values larger than 100 for col1 in T1 (above table). How do you do that?

7. User A is doing some modifications on T1, and he does not want other users to know what he has changed until he commit all his work. What options could he have?

8. How to return values from a store procedure? How to return result set from a store procedure?

9. How do I add another column Col3 to T1, with data type integer and default value 100?

10. Describe how to use 'CURSOR' in SQL procedure. Please write a procedure that uses CURSOR to return result set with 'select col1 from t1'.
