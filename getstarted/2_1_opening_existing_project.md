# How to open a Project?
In the Studio Beta menu, click Projects -> Load project.

<div class="image_medium" style="float:right;"><a href="/uploads/book/projects/07_load_project.png" rel="prettyPhoto" title=""><img alt="Load Project" src="/uploads/book/projects/07_load_project.png" hspace="5" vspace="5"></a></div> 

This will open a directory browser. Simply navigate to your project directory (somewhere under web root) and click Load.

NOTICE: : There are ***no files to select here***, you only have to select the directory whose name is the same as the name of your project.



# Recent Projects
<div class="image_medium" style="float:right;"><a href="/uploads/book/projects/08_recent_projects.png" rel="prettyPhoto" title=""><img alt="Recent Projects" src="/uploads/book/projects/08_recent_projects.png" hspace="5" vspace="5"></a></div> 

Once you have already worked on a project, Studio will remember it for a while. You can open it without any browsing using Project -> Recent projects in ***Studio Beta*** menu. Just select its name from the list, Studio will load it instantly.



# Project Settings


Once a project has been loaded, you may change or review its settings anytime, by clicking Studio Beta -> Settings.
The dialogue has two tabs that display all those details you defined when you've created the project.

## Project

You can find some quite important general information here:

Project Name: is the name of the project. This can be anything you like.

Url: is the URL to load if you want to use your application in a browser.

Path to Project: is the ***file system path***. That's where you can find the source code on the disk. Should you ever want to 
_backup your project_, or use system utilities to modify it, this is where you have to go.

## Database

The settings of the database connection used by your application can be found here.

Database: is the name of the MySQL (or whatever) database.

Host: is the IP address or domain name of the host where the database server is running. The special value _"localhost"_ 
means the current computer and should do fine in most cases.

Port: is the port number where clients can connect to the database service, running on the host defined above. Normally it's empty, which means the 
default port is used.

NOTICE: : Unless you have a very good reason, ***you shouldn't change this***!

Username: is the username of the database user.

Password: is the password of the database user.

NOTICE: : Please keep in mind, that changing the authentication details above ***does not create*** a new user, ***nor does it change***
the settings of an existing one. These are merely for the records of Studio. To perform these operations, you have to use a database client!