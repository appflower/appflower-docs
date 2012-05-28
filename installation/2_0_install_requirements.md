# AppFlower Requirements

<p class="warning">Please note that the requirements listed below are important only if you're ***not using our virtual machine***. In the VM, everything is already configured correctly is ready to use.

Should you want to deploy your application onto a production server or relocate it to your own development environment, you have to make
sure that the following components are installed and configured correctly:

<ul>
<li>PHP with 5.3.x or later</li>
<li>Web Server running </li>
<li>A supported RDMBS Database</li>
<li>Symfony Framework (v1.4) if installed manually</li>
</ul>



## PHP 5.3.x+

The <a href="http://www.php.net" target="_bank">PHP5</a> language is required, since the AppFlower Engine was created using this technology.

There are no AppFlower specific PHP settings or INI configuration, however, you must make sure that he following modules
are available for ***both*** PHP CLI and web versions:

<pre>
curl
json
libxml
memcache
mysql
mysqli
odbc
PDO
pdo_mysql
PDO_ODBC
SPL
xml
xmlrpc
</pre>

## Check your PHP Environment
As PHP configurations can vary a lot from one OS to another, or even between different Linux distributions, you need to check that your PHP configuration meets the symfony minimum requirements. First, ensure that you have PHP 5.3.x at a minimum installed by using the phpinfo() built-in function or by running php -v on the command line. Be aware that on some configurations, you might have two different PHP versions installed: one for the command line, and another for the web.

Then, download the symfony configuration checker script at the following URL:
<a href="http://sf-to.org/1.4/check.php">http://sf-to.org/1.4/check.php</a>. Save the script somewhere under your current web root directory.

Launch the configuration checker script from the command line:
<pre>
$ php check_configuration.php
</pre>

If there is a problem with your PHP configuration, the output of the command will give you hints on what to fix and how to fix it. You should also execute the checker from a browser and fix the issues it might discover. That's because PHP can have a distinct php.ini configuration file for these two environments, with different settings.

NOTE: Don't forget to remove the file from your web root directory afterwards.

## Apache 2.x

<a href="http://httpd.apache.org/" target="_bank">Apache</a> is the web server of choice for AppFlower applications, and this is the one AppFlower was tested with.

A default Apache configuration should almost do, basically, you just have to make mod_rewrite module enabled. You also have to be able to create Apache ***Virtual 
Hosts***.

Of course, there are a bunch of Apache settings you could tweak, but those are for optimizations only (to improve performance), so you don't need them to make AppFlower work.
A detailed tutorial on <a href="/doc/1_1/cookbook_apacheoptimization" >Apache Optimization</a> can be found in the AppFlower Cookbook. 

If you prefer to try a different web server, that should be possible as long as it can provide an alternative to Apache's _mod_rewrite_ functions as well as its <span 
class="code_snippet">VirtualHost directives. These are the minimum requirements, however, since AppFlower _was tested only with Apache_, using another web server might rise other issues too.


## A supported RDBMS solution

AppFlower requires a database engine to store its system data and also because it creates database-driven applications by default.

It handles databases through PHP's ***PDO*** architecture and the ***Propel*** ORM layer. This means, any database system is supported as long as it can be managed through PDO and there is a Propel driver 
for it.

At the time of writing, the following database engines meet the above criteria:

MySQL
PostgreSQL
SQLite
MSSQL
Oracle

AppFlower is configured to use <a href="http://www.mysql.com" target="_bank">MySQL</a> by default. Although it's not a requirement, it is recommended to use _MySQL 5.0+_ for best performance.

NOTE: Please note that AppFlower performs all database operations ***exclusively through PDO***, so old database bindings (i.e.: the ones with procedural APIs) won't work!

NOTE: If you prefer to use a database engine other than MySQL, don't forget to review the PHP modules listed above! You'll have to
***install the PDO modules*** required to handle your database of choice, since the default configuration was meant to be used with MySQL only!

## Symfony 1.4

AppFlower's foundation is the <a href="http://www.symfony-project.org" >Symfony PHP framework</a>. It is bundled with all AppFlower distributions, so you don't have to install it manually. 
However, please keep in mind that ***AppFlower works with Symfony version 1.4 only*** at the moment, so you shouldn't update or change the included package in any way, unless you know what you're doing.
