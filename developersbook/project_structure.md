# Project Directory Structure

The structure is similar to Symfony's, but with a few minor extensions.

## Basic Directory Structure

The basic and most often used parts of the directory structure are found inside modules, lib, and config. The most notable difference between Symfony and AppFlower are the XML files placed under each module's config folder. These XML files are the actual rendering settings, which we will go into later.

<pre>
apps/
  frontend/
    modules/
      [module_name]/
        actions/
            actions.class.php
                config/
                    edit.xml
                    list.xml
                    show.xml
config/
lib/
plugins/
    appFlowerPlugin/
</pre>

***[module_name]/actions/***	Generally contains a single class file named actions.class.php, in which you can store all the actions of the module. You can also write different actions of a module in separate files.

***[module_name]/config/***	Contains all AppFlower rendering templates for the actions of the modules stored in XML format. Config can also contain custom configuration files with local parameters for the module.

<b<config/***	Holds the general configuration of the project.

***lib/***	Dedicated to foreign classes or libraries. Here, you can add the code that needs to be shared among your applications. The model/ subdirectory stores the object model of the project (described in Chapter 8).

***plugins***	Contains the added plugins, but also actual appFlower engine which extends Symfony. Notice that usually you would not need to modify code inside the appFlower engine.


## Full Directory Structure
<pre>
apps/
  frontend/
  backend/
batch/
cache/
config/
data/
  sql/
doc/
lib/
  model/
log/
plugins/
test/
  unit/
  functional/
web/
  css/
  images/
  js/
  uploads/
</pre>

***apps/***	Contains one directory for each application of the project (typically, frontend and backend for the front and back office).

***cache/***	Contains the cached version of the configuration, and (if you activate it) the cache version of the actions and templates of the project. The cache mechanism (detailed in Chapter 12) uses these files to speed up the answer to web requests. Each application will have a subdirectory here, containing preprocessed PHP and HTML files.

***config/***	Holds the general configuration of the project.
***data/***	Here, you can store the data files of the project, like a database schema, a SQL file that creates tables, or even a SQLite database file.

***doc/***	A default place to store project documentation

***lib/***	Dedicated to foreign classes or libraries. Here, you can add the code that needs to be shared among your applications. The model/ subdirectory stores the object model of the project (described in Chapter 8).

***log/***	Stores the applicable log files generated directly by symfony. It can also contain web server log files, database log files, or log files from any part of the project. Symfony creates one log file per application and per environment (log files are discussed in Chapter 16).

***plugins/***	Stores the plug-ins installed in the application (plug-ins are discussed in Chapter 17).

***test/***	Contains unit and functional tests written in PHP and compatible with the symfony testing framework (discussed in Chapter 15). During the project setup, symfony automatically adds some stubs with a few basic tests.

***web/***	The root for the web server. The only files accessible from the Internet are the ones located in this directory.


## Application Tree Structure
The tree structure of all application directories is the same:

<pre>
apps/
  [application name]/
    config/
    i18n/
    lib/
    modules/
    templates/
      layout.php
</pre>


***config/***	Holds a hefty set of YAML configuration files. This is where most of the application configuration is, apart from the default parameters that can be found in the framework itself. Note that the default parameters can still be overridden here if needed. You'll learn more about application configuration in the Chapter 5.

***i18n/***	Contains files used for the internationalization of the application--mostly interface translation files (Chapter 13 deals with internationalization). You can bypass this directory if you choose to use a database for internationalization.

***lib/***	Contains classes and libraries that are specific to the application.

***modules/***	Stores all the modules that contain the features of the application.

***templates/***	Lists the global templates of the application--the ones that are shared by all modules. By default, it contains a layout.php file, which is the main layout in which the module templates are inserted.
