# Finalizing deployment

Now that you've successfully transferred the project to your production server, you need to perform a few more steps to make it live. This can be done in different ways, depending on what kind of hosting 
solution you have and what tools are available for you there. Basically, there are two scenarios:


## Instructions for VPS, private servers and shared accounts with shell access

Connect to the production server via SSH and go to the project directory. A very basic example of this can be found below, although, you may have to run ssh in a a slightly different way, depending on 
your SSH configuration and the requirements of the target host.

<pre>
ssh yourusername@yourproductionserver.com
...
(type password)
...
cd /your_webroot/yourproject
</pre>

Create a new database user. It is recommended to use the _same settings as in Studio_, since this will ***save you the trouble of changing configuration files***. Create a user with different 
settings only if you really have to.

If you wish to re-use the Studio user, click Studio Beta -> Settings, then switch to the Database tab. A screen appears with the 
database settings you defined when you created your project in Studio. You can use the _database name, username and password_ from here to perform the next steps.

Edit the configuration file config/propel.ini and find these lines:

<pre>
propel.database.url        = mysql:dbname=yourdb;host=localhost
...
propel.database.user       = someuser
propel.database.password   = somepass
...
propel.output.dir          = /your_webroot/yourproject
</pre>


Then open config/databases.yml file and locate the following lines:

<pre>
all:
  propel:
      ...
      dsn:        mysql:dbname=yourdb;host=localhost
      username:   someuser
      password:   somepass
      ...
</pre>

Replace in both files yourdb with the name of your database, and someuser and
somepass with the username and password of the database user you've just created.

Once you're done, save the files and run the following command. This will create the database as well as the table structure and will initialize various parts of the project.:

<pre>
./symfony afs:init --direct
</pre>

 
***A special note for Non-Unix users***

Make sure that web/appFlowerPlugin points to plugins/appFlowerPlugin/web and web/appFlowerStudioPlugin points to plugins/appFlowerStudioPlugin/web. These are symlinks, a facility not available under some OSes, such as Windows. In such a case, you'll have to use the equivalent tool of your OS or create aliases in Apache. 

That should be it. Your project should be now accessible in browser.

## Instructions for people without shell access

Since there are many different hosting services out there, with different account management features and tools, it is hard to define the exact steps you have to follow. This guide assumes that you have 
access to some kind of web based control panel, such as cPanel. If you have no more
than FTP access, please contact the technical support of your hosting company. They'll assist you with the general instructions outlined below.

Open up Studio and click Studio Beta -> Settings, then switch to the Database tab. A screen appears with the database settings you defined when you created your project in Studio. You can use the _database name, username and password_ from here to perform the next step

1. Unpack the compressed project file created by Studio anywhere on your computer.

2. Go to to your control panel and sign in

3. Create a new database with the same name you used in Studio

4. Add a new database user, whose details (username and password) are the same as the ones you have in Studio.

5. Load the database structure using phpMyAdmin or a similar tool available in your control panel. Basically, you'll have to upload and import
the file config/dump.sql, located in the project folder you've just unpacked. In phpMyAdmin, you must select your database, then click <span 
class="code_snippet">Import on the right. A screen should appear where you can browse and upload the included data file.

6. Make sure this database user has proper access rights. You have to assign _SELECT,INSERT,UPDATE and DELETE_ rights to it.

That should be it. Now your project should be accessible using a web browser
