# Notifications and Debugging
AppFlower Studio comes with a series of built-in tools to make development easier.  

Its ***debug widget*** helps you track down code errors, while the ***audit log feature*** let's you easily find user mistakes and also makes your application more secure. Besides these, Studio also has cool notification system which keeps the user informed about important events and prints informative messages whenever necessary. 

We're going to have a look at all these features in the this chapter. 


# The Audit Log
<div class="image_medium" style="float:right;"><a href="/uploads/book/notifications/studio_notifications.png" rel="prettyPhoto" title=""><img alt="Studio Notifications" src="/uploads/book/notifications/studio_notifications.png" hspace="5" vspace="5"></a></div> 
Most actions doable in Studio will generate some audit data to be saved. These include but are not limited to _pushing important buttons, saving changes, creating, updating or deleting components_ etc. Whenever such an event occurs, Studio performs the requested operation and then saves info about it silently, in the background. 

1. To open the ***Audit Log*** click Debug- > Audit Log to fire up the widget! 

As you can see, it contains detailed information about various events. Each event is printed on a separate line, having the following structure:

<pre class="code">
date User {Studio component}	IP address	Event details.
</pre>

Let's examine each of these parts now:
date the date and time of when the event occured
User the related user's username
Component the Studio component that generated the event
IP address the IP address of the user
Details the details of the event.

This information may come in handy when have to look up a user-made error or just need information about user activity. But these are only 2 possible scenarios, there are many use-cases. The audit log displays all events ordered by date (latest first) and it is scrollable of course.


# Debugging your Application
To raise the debugging level of your application, to debug errors. You can open web/index.php with the code browser and change the value ('frontend', 'prod', false) to ('frontend', 'dev', true). The opposite way around, if you want to lower debugging level for production.

in web/index.php 
<pre>
$configuration = ProjectConfiguration::getApplicationConfiguration('frontend', 'prod', false);
</pre>

and change to 

<pre>
$configuration = ProjectConfiguration::getApplicationConfiguration('frontend', 'dev', true);
</pre>

## The Debug Widget

WARNING: Please note that this feature only works if your log files reside in the project's "log" directory. This is the case with our virtual machine, but in custom environments you'll have to adjust Apache and PHP configuration to make use of this widget.

<div class="image_medium" style="float:right;"><a href="/uploads/book/notifications/studio_debug.png" rel="prettyPhoto" title=""><img alt="Debug Messages" src="/uploads/book/notifications/studio_debug.png" hspace="5" vspace="5"></a></div> 

The ***Debug Widget*** is a useful place to have a look when you need to track down bugs while developing, as it let's you see the details about what's going on under the hood, and displays the errors that has been triggered by the application.

1. To open the widget, click Debug -> Debug

This widget displays 3 important log files in the tabs, each containing plenty of details about important events. Just like the Audit log, these also store various events, each on a separate line. These are:

web.log is the ***Apache HTTP server access log*** (NOT the error log!). It contains Apache events, like requests of certain resources (images, HTML pages, JS files etc), and other useful information (like startup and shutdown info).
error.log is the ***Apache HTTP server error log***. The error.log shows failed requests as well as all PHP errors and warnings. Should you encounter a code error during development, _this is the first place to look_! The last one stores all kind of Symfony events, so besides Symfony errors, traces of successful operations can also be found here. This is also a good candidate for error hunting!
frontend_dev.log is the ***Symfony development environment*** log file.

In the two Apache logs, the data is stored in the following structure

<pre class="code">
 IP	log level 	[date and time]	Log message
</pre>

IP the IP address of the client (browser)
log level is the severity of the event. It allows events to be categorized, since there are many different kinds. An event may represent a major or minor error, a warning, info etc.
date is the date of occurence
Message is the log message. This one usually starts with a reference to the affected resource (i.e: a path to some file).

The Symfony log file is a bit different

<pre class="code">
 date	symfony	[level]	{Syfmony component}	Log message
</pre>

date	the the date and time of the event
Component the Symfony components that generated the event
level the event severity
Message is the event details.

All these logs show only recent entries by default. However, they are pageable, so you can browse the whole log file too quickly and easily, even if it's huge (multiple GBs). To do that, simply use the paging controls at the bottom of the debug window. More information about these files can be found on the web sites of <a href="http://httpd.apache.org/docs/2.2/logs.html">Apache</a> and <a href="http://www.symfony-project.org/gentle-introduction/1_4/en/16-Application-Management-Tools#chapter_16_sub_symfony_logs">Symfony</a> projects.

NOTICE: : For those using their own development environment: Did you know that these files are available in your OS too? You open and browse them using your favorite text editor as well (only plain text editor, not MS Word!). The exact location and naming varies from system to system. But you can always run a file search to find them easily!  Some hint for searching: *_access.log, *_error.log and frontend_dev.log.


# Notifications
Like I said, Studio has a cool built-in notification system, which keeps you up-to-date. It displays small, informative panels whenever something happens. The panel appears at the bottom right corner of the screen. Currently, the system reports three kind of events:

<div class="image_medium" style="float:right;"><a href="/uploads/book/notifications/studio_notification_popup.png" rel="prettyPhoto" title=""><img alt="Notifications System in Studio" src="/uploads/book/notifications/studio_notification_popup.png" hspace="5" vspace="5"></a></div> 
Errors are generated when the requested operation fails for some reason, or it could not be performed. In this case the panel is displayed with a bright red background and an exclamation mark in the top left corner:

NOTICE: : These error message are useful not only for detecting development issues, but also configuration problems that prevent Studio from running properly. You should always pay attention to these, and read all error messages carefully!

<div class="image_medium" style="float:right;"><a href="/uploads/book/notifications/studio_warning_message.png" rel="prettyPhoto" title=""><img alt="Warning Notification" src="/uploads/book/notifications/studio_warning_message.png" hspace="5" vspace="5"></a></div> 
Warnings are sent when an operation was only partly successful and there something to keep in mind about it, or when operation could not be performed due to missing info (like user input). These panels are rendered with a yellowish background and a small triangle thingy in the top left corner.

NOTICE: : You should pay attention to warnings as well! They ALWAYS carry important information!

<div class="image_medium" style="float:right;"><a href="/uploads/book/notifications/studio_system_message.png" rel="prettyPhoto" title=""><img alt="Notification Message" src="/uploads/book/notifications/studio_system_message.png" hspace="5" vspace="5"></a></div> 
Info messages are displayed on success, or as confirmation. They are rendered with white background and a (i) icon in the corner.

The notification system displays these message and removes them after 10 seconds. Error reports are exceptions, however, as they are NOT removed automatically. This is to make sure the user can read and understand these messages. You must close them manually (click the X icon) to get rid of them.
