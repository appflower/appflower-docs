# WAMP and AppFlower

The easiest way to install a brand new development environment compatible with AppFlower under Windows is definitely WAMP. It's a bundled package 
which includes all the necessary tools, such as a web server (Apache), a database system (MySQL) and PHP5. It's free, comes with an easy to use setup 
wizard and can be installed in just 5 minutes.

In this tutorial we'll show you how to install and configure ApFlower with WAMP. It will take only a few minutes to read this, and even less to 
perform the actual steps. 

# Installing WAMP

Download <a href="http://www.wampserver.com/en/download.php">WAMP server</a> and start the installer. This is a simple setup wizard, 
basically, you can safely click Next everywhere. There are only things to keep in mind:

The ***Destination Location*** should be a directory easily accessible for you, since that's where your web server root will be located. Typing in 
C:\wamp here should be a good choice. We will use this example throughout this guide.

Don't forget to click Create quick launch icon in ***Select Additional Tasks*** step. This will add a small icon 
to the system tray, which you can use to manage WAMP more easily.

In the last step click Install and wait for the wizard to finish.

# Disable APC cache!

If you have <a href="http://php.net/manual/en/book.apc.php">APC</a> cache  installed or your PHP is complied with APC support, ***you should disable it prior to running Studio***! Unfortunately, APC is known to interfere with AppFlower Studio and might raise issues regarding request processing. 

To disable APC, add the following line to your ***php.ini*** configuration file:

_apc.enabled = 0_

# Installing the AppFlower Source

Grab the <a href="http://www.appflower.com/cms/download">Bundled Package</a> on our download page and unzip it into C:
\wamp\www\appflower.

## Configuring the web server

Click the WAMP icon in the taskbar and open Apache -> httpd.conf. This is long configuration file. Locate the 
following line and remove the "#" prefix, then save (but don't close the file yet). This enables mod_rewrite, which allows the creation of nice, user-
friendly URLs.:

<pre >
#LoadModule rewrite_module modules/mod_rewrite.so
</pre>


Go to the end of this file and add the following declaration. This creates a so called virtual host to allow easy access to your AppFlower 
applications:

<pre >
&lt;VirtualHost *:80&gt;
  ServerName studio.local
  DocumentRoot C:/wamp/www/appflower/web

  &lt;Directory "C:/wamp/www/appflower/web"&gt;
    AllowOverride All
  &lt;/Directory&gt;

   Alias /appFlowerPlugin "C:/wamp/www/appflower/plugins/appFlowerPlugin/web"
   &lt;Directory "C:/wamp/www/appflower/plugins/appFlowerPlugin/web"&gt;
     AllowOverride All                                                       
     Allow from All                                                          
   &lt;/Directory&gt;                                                                
                                                                                
    Alias /appFlowerStudioPlugin "C:/wamp/www/appflower/plugins/appFlowerStudioPlugin/web"
    &lt;Directory "C:/wamp/www/appflower/plugins/appFlowerStudioPlugin/web"&gt;
      AllowOverride All                                                       
      Allow from All                                                          
    &lt;/Directory&gt; 
&lt;/VirtualHost&gt;
</pre>

## Configuring the database

It's time to edit Studio's default database configuration. Launch Notepad and open the file C:\wamp\www\appflower\config
\databases.yml and delete the password's value:

<pre >
username:   root
password:   
</pre>

NOTICE: Make sure you DON'T press the TAB key while you're editing this file. Tabulators are illegal in YML, use spaces.

NOTICE: WAMP'S MySQL doesn't have a root password by default. Of course, if you have changed that, use that password instead.

Click the WAMP icon and select MySQL -> MySQL console. A small black window opens, just hit enter when it asks for 
the password. Create the appflower database via the command below, then simply close the window.:

<pre >
create database appflower_studio; (hit enter)
</pre>

## Adjusting your host configuration

Locate the ***hosts*** file on your computer. This should be somewhere inside the Windows directory and under System32 or System64 subdirectory. On 
mine it's located in C:\Windows\System32\drivers\etc. Open this file in Notepad and add the following line to it. 
This will let your system know about a new local domain name, and will allow you to use this instead of an IP address:

<pre >
127.0.0.1       studio.local
</pre>

NOTICE: Please note that you'll probably have to edit this file as Administrator in order to be able to change it.

## Initializing Studio

We have arrived to the last step. Go to your project directory (C:\wamp\www\appflower) and launch command line (cmd). Once you're there, execute the following command. This will initialize your project.:

<pre >
symfony afs:init
</pre>

That should be it. Your final task is to restart the WAMP stack to make sure the changes take effect. Click the WAMP icon and press <span 
class="code_snippet">Restart All Services. In a few moments the icon turns green again, which means the server is running.

NOTICE: Sometimes the icon doesn't get green. If that happens, click WAMP icon then open Apache -> Service -> Test 
port 80. This will tell you if an application is already running on port 80, so Apache can't. In such a case, simply close that app and hit 
Restart All Services again. It is known that some IM programs, like Skype may cause such disturbances. 

Once WAMP has been restarted, point your browser to ***http://studio.local***. The Studio welcome page should appear with a link to launch 
Studio.


