# The Console
Studio has a Console tool which allows you to execute various useful commands and see their output. It is almost the same as a ***shell window*** in Linux / Unix systems or the ***command prompt*** under Windows. It is primarily used to run Symfony or AppFlower specific tasks and to execute system utilities.

The Console is mostly oriented towards power users, but can become handy when debugging, doing cleanup or other related maintenance tasks. It is also very useful during development, since it allows you perform a couple important "low-level" tasks directly from Studio.

<div class="image_medium" style="float:right;"><a href="/uploads/book/console/studio_consle.png" rel="prettyPhoto" title=""><img alt="Console" src="/uploads/book/console/studio_consle.png" hspace="5" vspace="5"></a></div>

To open Studio Console, select Tools -> Console. A window shows up and you should see something like the image on the right.

You can type the commands into the input box at the top, and the output will be shown in the black area below, once you pressed enter.

<p class="note" >Did you know that the output area displays some important information automatically when you load up Console? It prints things like the ***name and version of your OS***, your ***kernel version*** etc. These may come in handy when you have to contact our support!

You can see a list of the most frequently used commands next to the input box, but these are just examples.: With Studio Console, you may execute just about any command available under your OS!

<p class="note" >Please note that while the Console is a very useful tool, it is ***not a Shell replacement!*** It is provided for convenience only, and has ***certain limitations***. For instance, it ***does not*** support those commands requiring user interruption, like "top" or "php" (in interactive mode), you cannot open multiple Console instances etc. When you need full power, use a real shell prompt!

If you already know everything about the *Nix Shell (or the equivalent tool of your OS) and Symfony CLI tasks, you can stop reading this. Just hop on the beam, and start to work -:)

Those, being not familiar with the above terms should read on, however. Below you can find a short introduction to the most common commands. This is just a small guide to get you started, it doesn't have all the details. To learn more about a given command, you should consult its help. Don't know how to do that? No worries, we'll show you when you get there, just keep on reading -:) 

# Useful system commands

Here comes a list of almost all those programs listed beside the input area. Let's have a look at each of them:

<p class="note" >If you need more information about a command, you should run the following:

<pre>
 man command_name
</pre>

This will print a detailed help text, full usage instructions and everything you'll ever need to know about the given utility. 

In case of ***man*** program is not available under your OS, you can find the same information (and much more) at <a href="http://unixhelp.ed.ac.uk/CGI/man-cgi" >http://unixhelp.ed.ac.uk/CGI/man-cgi</a>. 



This guide assumes that you're using a Linux system, some kind of Unix or our virtual machine (which is a FreeBSD by the way). If this is the case, the guide below should be fine. However, it is possible that some commands listed here are missing or work in a slightly different way under your OS. This is due to differences between the various Unix / Linux versions out there. If you have difficulties, please consult the documentation of your OS.

Those readers using Windows can find a short introduction to the most useful Windows commands at <a href="http://www.bleepingcomputer.com/tutorials/tutorial76.html" >http://www.bleepingcomputer.com/tutorials/tutorial76.html.</a>

And now, let's see those commands! -:)

# Directory contents
Lists the contents of a directory. The following will always produce nice output
<pre>
 ls -la /your/directory
</pre>

# Current Directory
Will tell you the current working directory. This is the one Studio is currently using.
<pre>
 pwd
</pre>

# Git Commands
It calls the GIT version control system client application. You can use this to keep your AppFlower Engine or Studio source code up-to-date. This is a complex application, so:

 
To learn the basics, log into GitHub and check out the quick help at
<a href="http://www.github.com" >http://www.github.com</a>

To learn more about the features and advanced usage, read the documentation at 
<a href="http://git-scm.com/documentation" >http://git-scm.com/documentation</a>

<pre>
 git
</pre>

# Display File Contents
Can show you the contents of any (text) file. 
<pre>
 cat /path/to/myfile 
</pre>

For files having a lot of content this command is better:
<pre>
 cat /path/to/myfile | less
</pre>

# Creating a Folder
To create a folder in your project, you can issue the mkdir command.
<pre>
 mkdir /my/new/dir
</pre>

# Deleting Entries
Removes one or more files or directories.  Supports * wildcard.
<pre>
 rm /dir/myfile
 rm /dir/*.txt
</pre>

If you need to remove a directory with all its contents, use:
<pre>
 rm -rf /mydir
</pre>

# Copying Files
Copies one or more files (NOT directories!).  Wildcard * is supported.

<pre>
 cp /dir/file /dir2
 cp /dir/*.mp3 /dir2
</pre>

# Moving and Renaming Files
Moves or renames one or more entries. It works the same way as ***cp***, but deletes the source. Unlike ***cp***, however, it can move or rename directories too!

# Creating empty Files
To create an empty file use:

<pre>
 touch /dir/mynewfile
</pre>

# File Permissions
Changes the access rights of one or more files or directories. Supports * wildcard.

<pre>
 chmod 0666 /dir/myfile
 chmod 0777 /dir/*.txt
</pre>

If you need to set the same rights for all files in a directory and its subdirectories, use:

<pre>
 chmod -R 0777 /my/dir
</pre>

# Disk Space Information
Shows how much free disk space you have
<pre>
 free
</pre>

or:

<pre>
 df -lh
</pre>

The latter displays all mounted file systems with some info on how much disk space they use and other important details.

# Finding Files

Finds one or more files in a given file system using a pattern. It is recursive and supports * wildcard.

<pre>
 find /usr -name mydoc.doc
</pre>

To look up files anywhere on your computer, use:

<pre>
 find / -name my.file
 find / -name *.doc
</pre>

# clear
Clears the console screen

# php

Starts the PHP CLI. In Console,  it must be used to execute scripts only (***no interactive mode!***).

<pre>
 php /my/script.php
</pre>

# Useful Symfony and AppFlower tasks

The console also allows you to run any Symfony task, including AppFlower and Studio specific ones. You can find the most important tasks listed below. Again, this is just a short summary.
For detailed usage instructions you should see the task help, which you can invoke like this:

<pre>
 sf help cc
 sf help afs:fix-perms
 sf help appflower:validator-cache
</pre>

<p class="note" >If you are unfamiliar with Symfony framework or Symfony CLI, ***DO NOT run these!*** Please read the documentation first at
 <a href="http://www.symfony-project.org/doc/1_4/" >http://www.symfony-project.org/doc/1_4/</a>


# Symfony Tasks - sf
Run an standard Symfony task by perpending the sf prefix to the task name.

<pre>
 sf cc
 sf propel:build-all
</pre>

# AppFlower Studio Tasks - afs
The afs prefix can be used to invoke Studio related tasks.

# afs fix-perms
Fixes access rights of applications built with Studio. It's ***not*** the same as Symfony's fix-perms task. Normally, you have to run this only when your application has issues with file permissions.

<pre>
 afs fix-perms
</pre>

# afs insert-diff-sql
This checks if Studio database structure is correct and fixes it if it's broken. Again, you have to run this only in case of trouble with your Studio DB. 

<pre>
 afs insert-diff-sql
</pre>

# afs generate-widget
It will generate one or more widgets based on a given Model. This can be used to quickly build prototypes of widgets to fine-tune in Studio afterwards. The task has several options, you should check out its help. The following command creates the edit, show and list widgets using Model ***MyModel*** and will place them in a new module called ***mymodule***

<pre>
 afs generate-widget -m MyModel -l mymodule
</pre>

The command below will build only a list widget:

<pre>
 afs generate-widget -m MyModel -l mymodule -k list
</pre>

# afs generate-widget-all
This is the bulk version of the previous task. It will generate the desired type of widgets for each currently existing Model. It won't overwrite existing widgets by default, but you can force this behavior using the ***--refresh*** option.

<pre>
 afs generate-widget-all
</pre>

The next command will build Edit widgets only and will overwrite existing ones:

<pre>
 afs generate-widget-all  -k edit --refresh
</pre>

# afs init
Task task is a wrapper for several initialization tasks that has to be executed to setup a deployed project and make it operational and is provided for convenience. You should run this with care though, since it rebuilds DB as well!

<pre>
 afs init
</pre>

# AppFlower Tasks - appflower
The appflower prefix can be used to execute AppFlower Engine related tasks. The following ones are sometimes useful in development phase.

# appflower validator-cache
This task has a dual purpose: It validates all your widget and layout XMLs against the AppFlower Schema and it builds a kind of cache too, to prevent the engine from validating files at runtime, thus increasing performance. If a widget is cached, it will be validated again only when you change its XML code or when the cache is cleared for some reason.

To validate all widgets and layouts, run this:

<pre>
 appflower validator-cache frontend full yes
</pre>

To quickly build the cache (assuming all XMLs are valid), run:

<pre>
 appflower validator-cache frontend cache
</pre>

The task has several other useful features as well. For instance, it can validate a single file (e.g.: a newly added widget), can generate a validation log, and it can run in "incremental" mode too (stops on each error) etc. Please consult the task help for more details.

# appflower list-files
This task ***must*** be executed if you've added new external ***JS files*** to your application. This allows the engine to load and use those files.

<pre>
 appflower list-files js 
</pre>	

It is mostly used to build a Javascript file list for the engine, but can be used to list any kind of files.

<pre>
 appflower list-files png /location/myfile.list
</pre>

# appflower update-widget-selector

This one adds one or more widgets to the widget selector. These widgets will available for every Layout. It can be used to quickly add all your widgets or to add a newly created widget etc.

<pre>
 appflower update-widget-selector
</pre>

By default, it is running in interactive mode, so it prompts the user with various questions whenever it's necessary. If you want it to run silently, use:

<pre>
 appflower update-widget-selector no yes
</pre>

This will add widgets using default Symfony names and conventions.

# appflower portal-state-cc

It is useful when you need to reset the settings of a Layout. It will restore default settings (columns and arrangement).

<pre>
 appflower portal-state-cc pages/dashboard
</pre>