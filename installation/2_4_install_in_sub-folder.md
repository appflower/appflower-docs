# Install AppFlower in a domain's subdirectory structure
Suppose we have a project installed in _/var/www_ called _requisitions_ and we want to access the project by _http://example.appflower.com/***requisitions***_

The directory structure would be '/var/www/requisitions'. In this directory, we have the usual directories from Symfony applications, like 'apps', 'lib', 'web', and so forth. You need to setup the virtual host (like in the example below) and edit the './web/.htaccess' file.

## Virtual host configuration example

<pre>
Listen IP:PORT
NameVirtualHost IP:PORT

<VirtualHost IP:PORT>
 ServerName IP:PORT
 DocumentRoot /var/www/
 DirectoryIndex index.php
 Alias /requisitions/sf "/var/www/symfony-1.4/data/web/sf"
 Alias /requisitions/ /var/www/requisitions/web/
 Alias /appFlowerPlugin/ /var/www/requisitions/web/appFlowerPlugin/
 Alias /images/ /var/www/requisitions/web/images/

 <Directory "/var/www/">
   AllowOverride All
   Allow from All
 </Directory>
</VirtualHost>
</pre>

## ./web/.htaccess file example

<pre>
Options +FollowSymLinks +ExecCGI

<IfModule mod_rewrite.c>
 RewriteEngine On
 RewriteBase /requisitions/
 RewriteRule ^$ index.html [QSA]
 RewriteRule ^([^.]+)$ $1.html [QSA]
 RewriteCond %{REQUEST_FILENAME} !-f
 RewriteRule ^(.*)$ index.php [QSA,L]
</IfModule>
</pre>