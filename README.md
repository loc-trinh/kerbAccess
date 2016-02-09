# kerbAccess
MIT kerberos access with simmons-dev. Requires Django 1.7.

### .htaccess
```
AddHandler wsgi-script .py
Options +ExecCGI

RewriteEngine On
RewriteBase /PATH

RewriteRule ^(static.*)$ - [L]

RewriteCond %{REQUEST_URI} ^/PATH/$
RewriteRule ^$ APP_NAME/wsgi.py [L]

RewriteCond %{REQUEST_URI} !/PATH/APP_NAME/wsgi.py
RewriteRule ^(.*)$ APP_NAME/wsgi.py/$1 [L]
```

### APP_NAME/settings.py
```
STATIC_URL = '/APP_NAME/static'
```

### APP_NAME/wsgi.py
```
import sys
sys.path.append(os.path.dirname(os.path.dirname(__file__)))
```



