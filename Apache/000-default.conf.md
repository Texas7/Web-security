```
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html
    ServerName xxxxxxxxxxxxxxx

    # Permite o uso de .htaccess apenas no /var/www/html
    <Directory /var/www/html>
        AllowOverride All
        Require all granted
    </Directory>

    # Bloqueia .htaccess e acessos para subdiretórios, como wp-admin
    <Directory /var/www/html/*>
        AllowOverride None
        Require all denied
    </Directory>

    # Redirecionamento permanente para HTTPS
    Redirect permanent / https://xxxxxxxxxxxxxxx/

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

<VirtualHost *:443>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html
    ServerName xxxxxxxxxxxxxxx

    SSLEngine on

    # Caminhos para os certificados SSL (Certbot)
    SSLCertificateFile /etc/letsencrypt/live/xxxxxxxxxxxxxxx/fullchain.pem
    SSLCertificateKeyFile /etc/letsencrypt/live/xxxxxxxxxxxxxxx/privkey.pem
    SSLCertificateChainFile /etc/letsencrypt/live/xxxxxxxxxxxxxxx/chain.pem

    # Permite o uso de .htaccess apenas no /var/www/html
    <Directory /var/www/html>
        AllowOverride All
        Require all granted
    </Directory>

    # Bloqueia .htaccess e acessos para subdiretórios, como wp-admin
    <Directory /var/www/html/*>
        AllowOverride None
        Require all denied
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error-ssl.log
    CustomLog ${APACHE_LOG_DIR}/access-ssl.log combined
</VirtualHost>
```
