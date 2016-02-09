# kerbAccess
MIT kerberos access with simmons-dev. Requires Django 1.7.

## .htaccess
AddHandler wsgi-script .py
Options +ExecCGI

RewriteEngine On
RewriteBase /PATH

RewriteRule ^(static.*)$ - [L]

RewriteCond %{REQUEST_URI} ^/PATH/$
RewriteRule ^$ APP_NAME/wsgi.py [L]

RewriteCond %{REQUEST_URI} !/PATH/APP_NAME/wsgi.py
RewriteRule ^(.*)$ APP_NAME/wsgi.py/$1 [L]


