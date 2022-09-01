## .htaccess validation

#### Configurações aplicadas:

#### Não permite que os diretórios sejam listados:
```
Options All -Indexes
```

#### Personaliza as páginas de erros:
```
ErrorDocument 403 <h1>403</h1>
ErrorDocument 404 <h1>404</h1>
ErrorDocument 503 <h1>503</h1>
```

#### Permite acesso a determinados arquivos:
```
<FilesMatch "\.(css|js|html|jpg|jpeg|png|gif)$" >
Allow from all
</FilesMatch>
```

#### OU permite acesso SÓ a determinados arquivos, o restante é bloqueado:
```
Order Allow,Deny
Deny from all
<FilesMatch "\.(css|js|html|jpg|jpeg|png|gif)$" >
Allow from all
</FilesMatch>
```

#### Não permite acesso a determinados arquivos:
```
<FilesMatch "\.(css|js|html|jpg|jpeg|png|gif)$" >
Deny from all
</FilesMatch>
```

#### Não permite o acesso DIRETO via browser porem permite o download:
```
<FilesMatch "\.(mov|mp3|mp4|wav|pdf|txt)$">
ForceType application/octet-stream
Header set Content-Disposition attachment
</FilesMatch>
```

#### Não permitir acesso direto via browser ou carregamento de um arquivo especifico:
```
<files wp-config.php>
order allow,deny
deny from all
</files>
```

#### Anti hotlink ou seja ela não permite carregamento de arquivos do seu web server por requisições de terceiros:
```
RewriteEngine On
RewriteCond %{HTTP_REFERER} !^http(s)?://(www\.)?seusite.com.br [NC]
RewriteRule \.(jpg|jpeg|png|gif)$ - [NC,F,L]
```
