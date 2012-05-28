# Apache Optimization
Small tweaks in your Apache web server can change hugely the speed of your AppFlower Application. We will look at some of the pointers here.


# Enable caching of static files
You can allow caching of your static files. This can be done either in a .htaccess file, or your apache configuration.

<pre>
Header unset ETag
FileETag None

ExpiresActive On

# Caching 1 year
<FilesMatch "\.(jpg|jpeg|png|gif|swf|ico)$">
  Header set Cache-Control "max-age=31536000, public"
  # Header set Expire "access plus 1 year"
  ExpiresDefault A29030400
  Header append Cache-Control "public"
</FilesMatch>
<FilesMatch "\.(js|css)$">
  Header set Cache-Control "max-age=31536000, public"
  # Header set Expire "access plus 1 year"
  ExpiresDefault A29030400
  Header append Cache-Control "public"
</FilesMatch>
</pre>

# Use mod_deflate
This allows you to compress the response (both HTML and AJAX) before delivering it to the browser. All you need to do is enable it in your .htaccess file.

<pre>
AddOutputFilterByType DEFLATE text/html text/css text/xml text/csv application/x-javascript
</pre>

# Reduce disk seeks

The following optimizations aim to minimize the disk searches. A disk search is necessary when fetching a previously unvisited file from the disk. The process takes less than 10 minutes.

# Use APC PHP cache

Enabling the APC PHP extension will cache the parsed PHP files for subsequent requests.

The production APC configuration should have enough memory to hold all PHP files. You can check this out by reviewing the apc.php file. Even after heavy usage of the internet, the 'Cache full count' information should remain at 0.

It's also possible to disable checking for changed PHP files in production.

APC must be configured in a php.ini file; restart Apache to reload the configuration.

<pre>
apc.shm_size = 40
apc.stat = 0
</pre>

# Disable deep checking for .htaccess

Do this if you have only one .htaccess file. The check is not necessary for all subdirectories; simply disable 'AllowOverride' in the subdirectories.

<script type="syntaxhighlighter" class="brush:bash">
<![CDATA[
<Directory "/path/to/web">
        AllowOverride All
</Directory>
<Directory "/path/to/web/*">
        AllowOverride None
</Directory>
]]>
</script>

# Reduce the number of Symfony plugins

Each enabled Symfony plugin is checked when serving a request. Symfony checks the plugin directory for configuration files.

Use truss on FreeBSD or strace on Linux to see the accessed files.

<pre>
truss -f -p APACHE_PID
</pre>


# Example .htaccess config
This is an example .htaccess config file for Apache you could use and an inspiration source.

<script type="syntaxhighlighter" class="brush:bash">
<![CDATA[
# GZIP DEFLATE
AddOutputFilterByType DEFLATE text/html text/css text/csv application/x-javascript

# CACHING
Header unset ETag
FileETag None

# Turn on Expires and set default to 0
ExpiresActive On

# Caching 1 year
<FilesMatch "\.(jpg|jpeg|png|gif|swf|ico)$">
  Header set Cache-Control "max-age=31536000, public"
  # Header set Expire "access plus 1 year"
  ExpiresDefault A29030400
  Header append Cache-Control "public"
</FilesMatch>
<FilesMatch "\.(js|css)$">
  Header set Cache-Control "max-age=31536000, public"
  # Header set Expire "access plus 1 year"
  ExpiresDefault A29030400
  Header append Cache-Control "public"
</FilesMatch>

<IfModule mod_rewrite.c>
  RewriteEngine On

  # If the URL isn't a static file, we serve our front web controller.
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteRule .* index.php [QSA,L]
</IfModule>
]]>
</script>

NOTICE: If you need high performance, you can look into more advanced topics on top like having a reverse-proxies / caching in front of your Apache server like Varnish and Memcache. Files which are shared over and over again, could be shared through a CDN provider. Tweaking the Operating System and hardware of which your Apache server is running on could as well make a big difference. Here it could be relevant to look at where data is stored (memory / disk) since methods are faster for reading, writing, and long term storage.