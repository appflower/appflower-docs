# The Database Query Tool
AppFlower Studio provides a built-in tool that allows you to ***query the database*** and ***browse the information*** stored herein. Using this tool, you may check the contents of any of the tables as well as their structure and perform various operations on them.

# Starting the DB tool
Click Tools -> DB Query. This starts up the DB browser.
   	 
# Browsing data with DB tool
<div class="image_medium" style="float:right;"><a href="/uploads/book/dbquery/01_dbquery_table_content.png" rel="prettyPhoto" title=""><img alt="dbQuery Table Content" src="/uploads/book/dbquery/01_dbquery_table_content.png" hspace="5" vspace="5"></a></div> 

The left pane contains the list of all available tables. First of all, you have to select the one you want to work with. 


Mark the desired table by double-clicking its name. 


This activates the right pane, which has two tabs:
    
 - The Data tab contains the data browser. For now, it lists all the records stored in the given table. It can handle large number of records efficiently and has paging controls too, to make browsing fast and smooth. 

Here you can do a number of things: browse your data page by page, order the list by a particular column (click column title -> Sort..) or show / hide certain columns (click column title -> Columns menu). 


Whenever some error occurs or you a make a mistake, the data tab displays a descriptive error message.

<div class="image_medium" style="float:right;"><a href="/uploads/book/dbquery/02_dbquery_table_structure.png" rel="prettyPhoto" title=""><img alt="dbQuery Table Structure" src="/uploads/book/dbquery/02_dbquery_table_structure.png" hspace="5" vspace="5"></a></div> 

 - The Structure tab displays the table structure, it shows you how the given table was constructed. 

It is read-only, you cannot change the structure or the indexes here. To do that, you must load the Model into the <a href="/doc/1_1/learn_model_create" >Model editor</a>.
    
# DB Queries

<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/dbquery/03_dbquery_making_queries.png" rel="prettyPhoto" title=""><img alt="dbQuery Performing SQL Queries" src="/uploads/book/dbquery/03_dbquery_making_queries.png" hspace="5" vspace="5"></a></div> 

The data browser can show you all the records in a table, but this is not always the best solution. Sometimes you may want to see only a subset of the records, those that meet a certain criteria. You may also need to add or update records. To perform these operations, you have to write a query.

Click the large input area at the top of the DB tool. 


This is where you type the query. It supports two syntaxes at the moment:
    
***SQL:*** If query type is "SQL", a valid standard ***SQL or MySQL*** statement is expected. For instance:

<pre class="brush: plain">
SELECT * FROM products WHERE name="MacBook Pro";
</pre>
    
NOTE: SQL stands for ***Structured Query Language***. It is a way to work with databases. SQL commands can retrieve, insert, delete or update data. It is a very powerful, yet easy to understand technology that works with nearly all database engines out there.
    

For a quick overview, please follow the link:
<a href="http://w3schools.com/sql/sql_intro.asp" >http://w3schools.com/sql/sql_intro.asp</a>


We suggest you to read the part about ***SQL Basics*** first, which covers the most frequently used commands. This should be enough for all basic needs and you can move on to the Advanced part later.
    
***Propel:*** if the query type is "propel", ***Propel 1.5+*** compatible PHP code is expected. An example:
    
<pre>
ProductsQuery::create()->where("products.name = 'MacBook Pro'", 1)->find();
 </pre>

NOTE: Propel is another way to work with databases, using the PHP programming language. This is an advanced topic, if you're not familiar with programming, we suggest you to choose SQL instead.

    
For those of you already comfortable with PHP, but new to Propel,  a quick overview of the syntax can be found at
<a href="http://www.propelorm.org/wiki/Documentation/1.6/BasicCRUD" >http://www.propelorm.org/wiki/Documentation/1.6/BasicCRUD</a>


The entire Propel documentation is available at
<a href="http://www.propelorm.org/wiki/Documentation/1.6" >http://www.propelorm.org/wiki/Documentation/1.6</a>


Please keep in mind that the DB tool understands ***only*** Propel 1.5+ code. Old, ***Criteria kind of stuff won't work!***


Finally, click Query button to execute the query. 

The data browser shows up shortly, but this time it contains only the selected records.

Naturally, the DB tool supports all kind of DB operations that can be described by a query. Besides SELECT, you can also perform INSERT, UPDATE, DELETE and many more.