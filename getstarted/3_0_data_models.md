# Storing Data (Databases and Models)

Before introducing you to the AppFlower data handling mechanism Models we want you to take a quick look at ***databases***, since this is the technology used in the background to store and manage the data. 

NOTICE: : This chapter is for those totally unfamiliar with RDBMS systems and the related basic concepts. If you already know all this, you should jump to the <a href="http://www.appflower.com/doc/1_1/learn_model_create">Creating the Song Model</a> chapter.

# What is a Database?

A database is a tool that ***stores information*** in a ***structured*** way. It's almost like having several spreadsheets linked together.

Typically, a database is made up of multiple tables, each containing specific information (_data_) stored in a specific structure. A table consist of several rows and columns. 

A row (or record) is an entry in a table. It is the information we want to store. For example, in case of an address book, this means _all details of an individual_.

Columns (or fields) are small pieces of information that make up a record. They could be called properties or details of the record. For instance, the address book we mentioned above would have fields like _first name, last name, cell phone, address_ and so on. 

A table may store many records using this kind of structure. The collection of all tables is called a database.

# So What? Why is This So Important?

Well, databases have many benefits.: They are _fast_, can handle very large amount of data _efficiently_, can store basically _any kind_ of data and so on. But their biggest achievement is definitely their ability to construct dynamic views. In other words: they store the information in a ***particular structure***, but they can ***show it in many different ways***!

What does this mean? The following example will help us understand:

In the next chapter we'll start to build a real AppFlower application, a ***Music Catalog***. This will be a tool for cataloging your home music collection, all the songs from your CDs, DVDs and other sources. The application will use a ***database table*** to store the details of the songs, which will look like this:  

<pre class="brush: plain">
Song Title                       Artist            Genre		    Album	

Enter Sandman (radio edit)       Metallica         Heavy Metal	
Forever Young                    Alphaville        Pop	
Sounds like a melody	         Alphaville        Pop
Going Home                       Runrig            Rock
Rhythm of my heart               Rod Stewart       Rock             Story so far	
...
</pre>

As you can see, the songs are stored in a particular structure. If we've used a _text file_ or an _MS Word document_ for cataloging, this would be the _only view_ you could see. 

However, thanks to the dynamic nature of databases, you can see this list in many ways! For instance, you could ask the questions below:

_
 - What songs do I have from Alphaville?
 - What rock songs do I have in my collection?
 - What's the contents of the Album “Story so far” by Rod Stewart?
 - On which CD the song "Guardian Angel" by Alphaville is located?
_


Consequently, assuming the above list contains all your songs, the result could be this (showing all songs from Alphaville):

<pre class="brush: plain">
Song Title                       Artist            Genre		    Album	

Forever Young                    Alphaville        Pop
Sounds like a melody             Alphaville        Pop		

</pre>

.. or this (showing all rock songs):

<pre class="brush: plain">
Song Title                       Artist            Genre		    Album	

Going Home                       Runrig            Rock	
Rhythm of my heart               Rod Stewart       Rock             Story so far			
</pre>

So to sum it up: storing information in a database is a ***good design approach***, because the same information can be viewed in many different ways (and used for different purposes as well) . You can adjust the view anytime to better fit your current needs, thus you'll always see the desired results.

And even this is only a part of the picture. Databases can do other useful things too, like _counting the entries,  calculating averages and totals, sorting the results_ etc etc. They can make your application really powerful.

# Database and the Music Catalog

Let's see how the general database structure we described at the beginning of this chapter fits our Music Catalog!


As you already know, the database is the entire information archive. It contains only one table at the moment, this is enough to store all info about our songs. The table holds many rows or records, each representing an _individual song_. 
The columns or fields of the table are the properties of a song: _title, artist, genre and location_.

# What about Models?

In AppFlower, Models are very similar to database tables. However, they are ***not*** the same. In nutshell, ***a Model is a way to handle the database table***.

AppFlower communicates with the underlying database using Models, and performs all database related operations with their help. Among other things, models are used to _put, retrieve and modify_ data. Anyway, in the world of AppFlower, you really don't have to care about this. You could learn more about models, but you don't have to. 

Using Studio, you can work with Models _as if they were_ tables. You should think of them as objects that hold the blueprint of the table as well as all the tools you need to work with the table and the data inside. The rest is up to the AppFlower Engine. For this reason, we'll use the term ***model*** instead of ***table*** from now on, to keep things as simple as possible.


Now that you have a basic understanding of databases and their benefits, and you see how Models fit into this picture, it's time to see it all in action! In the next chapter we'll build our Music model, the basis of our Music Catalog application! 
