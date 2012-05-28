# Creating Backups

We believe, it is always useful to backup your valuable data on a regular basis. This is important mainly for safety reasons.: should any part of 
your system get corrupted, this allows you to revert to a previous state quickly and efficiently. 

In case of AppFlower applications, basically you'll have to backup two things: your ***application files*** (source code) and the ***data*** it 
manages. Fortunately, this is quite easy to accomplish and can be done in multiple ways.

In this chapter, we'll explain how to do these things. However, it should be noted that the examples below assume that you're working with our 
_virtual machine_. If this is not the case, probably your _web root and project directories_ are located elsewhere and consequently, you'll 
have to change some paths. You can always look up the correct paths in Studio Beta -> Settings widget.


## Backing Up Data: The MySQL Way

It is very easy to create a backup for MySQL. This method is recommended if the production server and your development environment <u>both operate with MySQL</u> and you have no plans to migrate to another RDBMS anytime soon.

So let's get started!

***To backup the DB structure only***, simply click Studio Beta -> Project -> Export Project -> DB -> Structure. An SQL dump named ***yourproject.sql*** will be created in a few seconds and a download dialog appears.

***To backup the structure and the data***, select Studio Beta -> Project -> Export Project -> DB -> Structure + data (for mysql). This will also create a DB dump, but this time with records included.

## Restoring MySQL Data

You may restore your database contents any time, using a previously saved backup and the mysql client utility.:

First of all, copy the SQL dump to your environment. In case of the virtual machine, you'll have to use an SCP tool to transfer the file,  for example the _scp_ shell utility under Linux / Unix or something like <a href="http://www.winscp.net" >WinSCP</a> under Windows. Once you've done this, run the following command:

<pre>
mysql -u yourdbuser -p yourdatabasename < /path/to/your/backup.sql
</pre>

The "yourdbuser" and "yourdatabasename" parts should be obviously replaced with real values. If you're running our VM, both should be ***root***. Otherwise you should use the database settings in Studio, which you can find on the second tab of Studio Beta -> Settings panel.



## Backing up Data: The Cross-Database Way

It is also possible to backup your data in a _database-independent_ way. This method is suggestible if you have to use <u>different database 
systems</u> in your development environment and the production server, or if you wish to migrate to another database engine.

To export your database data via this method, enter your project directory using the shell..

<pre>
cd /var/www/yourproject
</pre> 

.. then execute the command:

<pre>
./symfony propel:data-dump project_20110912
</pre> 

NOTICE: : Please note that the file's name ***ends with a number***, which represents the current date. You can, of course name this anyhow, but 
it is usually helpful to use a naming convention, so you can save many different, yet easily identifiable backups to the same place.

This operation will create the file /var/www/yourproject/data/fixtures/project_20110912.yml, which holds the 
contents of your database in a format supported by all database engines compatible with AppFlower.

Should you want to restore this data later, you can do so by running:

<pre>
./symfony propel:data-load data/fixtures/project_20110912.yml
</pre> 

***If you don't want to backup your project files***, you should copy the backup you've just created to the web directory of your project for immediate download:

<pre>
cp /var/www/yourproject/data/fixtures/project_20110912.yml /var/www/yourproject/web/backup.yml
</pre> 

..then open ***http://yourhost/backup.yml*** in browser to save the file.

## Backing up Project files

This is even easier than backing up DB contents. Simply choose Sutio Beta -> Project -> Export Project -> Sources. In a few moments, a download dialog appears allowing you fetch a compressed file, ***yourproject.tar.gz***. This file contains all your project files as well as AppFlower sources and all required components.

If you have used the ***database-independent*** method described above, then your database backup was also added to the above file. You can find it in ***data/fixtures*** directory.

NOTICE: : The aforementioned package uses Tar / Gzip compression, which is handled by virtually all Unix / Linux systems. Under Windows, you may 
open such a file using third-party software, such as <a href="http://www.totalcmd.com" >Total Commander</a>.

Well, that's it. You have just created your first backup package, thumbs up! -:).