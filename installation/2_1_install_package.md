# Installing using AppFlower Bundled Package

The AppFlower bundled package is a archive containing all the AppFlower playground project including Studio.

# Step 1: AppFlower Requirements
In order to use AppFlower, your development environment has to meet certain requirements.  To find out whether your system is ready for AppFlower , please see <a 
href="/doc/1_2/learn_requirements">Hosting and Requirements</a> chapter!</a>

# Step 2: Download and Install the AppFlower Bundle
If you haven't already downloaded the appFlower bundle you can find the latest from the <a href="/cms/download">download page</a>. Download this to your web-server.

***2.1 Decompress the bundle package***
<pre>
tar –xvzf filename.tar.gz /your_web_root_path/myproject
cd /your_web_root_path/myproject
</pre>

***2.2 Check Environment:*** you can run the batch/check_configuration.php file to test if your php environment is correctly configured before you continue.

<pre>
 php batch/check_configuration.php
</pre>

# Step 3: Configuring AppFlower
***3.1 Database Settings:*** Adjust the database settings. Basically, you'll have to update two system files with the name of your MySQL database and the username and password to access it:

myproject/config/databases.yml Locate the lines below and change them appropriately:

<pre>
all:
  propel:
      ...
      dsn:        mysql:dbname=yourdb;host=localhost
      username:   someuser
      password:   somepass
      ...
</pre>

myproject/config/propel.ini This one is longer, change only the following lines:

<pre>
...
propel.database.url = mysql:dbname=yourdb;host=localhost
...
propel.database.user = someuser
propel.database.password = somepass
</pre>

NOTICE: : Don't forget to make sure that the "yourdb" database actually exists. You should also double check if "someuser" exists and his password is indeed "somepass". Besides the usual rights, this user ***must*** also have ***CREATE and DROP*** credentials!

***3.2. Setting Project Permissions***
<pre>
 ./symfony project:permission
 ./symfony afs:fix-perms
</pre>

***3.3. Building Database*** handler classes and insert the database structure.
<pre>
 ./symfony propel:build-model
 ./symfony propel:insert-sql
</pre>

***3.4. Build the cache*** for AppFlower's XML validator, for best performance:
<pre>
 ./symfony appflower:validator-cache frontend cache yes
</pre>

***3.5. Virtual Host*** Finally, you need to setup a virtual host so you can access the project in browser. If you're familiar with Apache configuration, simply add the following host and update your hosts file with the _myproject.local_ entry. Should you need more information, detailed instructions can be found in <a href="http://www.appflower.com/cms/learn_vhost">Configuring Apache Virtual Hosts</a> chapter.

<script type="syntaxhighlighter" class="brush:bash">
<![CDATA[
<VirtualHost *:80>
  ServerName myproject.local
  DocumentRoot /your_web_root_path/myproject/web

  <Directory "/your_web_root_path/myproject/web">
    AllowOverride All
  </Directory>
</VirtualHost>
]]>
</script>


# Step 4: Open your new Project
That’s it! If done correctly, you should see a nice user interface, with a simple “Hello world” message displayed when opening ***http://myproject.local/*** in your browser.


<strong><u><a href="/doc/1_2/learn_install_finalstep">CONTINUE TO LAST PART OF INSTALLATION &gt;</a></u></strong> 
