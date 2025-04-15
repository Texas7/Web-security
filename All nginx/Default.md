```
server {
    listen 443 ssl;
    server_name xxxxxxxxxxxxx;  # Substitua pelo seu domínio ou IP público

    # Configuração de certificados SSL
    ssl_certificate /etc/letsencrypt/live/xxxxxxxxxxxxx/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/xxxxxxxxxxxxx/privkey.pem; # managed by Certbot

    # Redireciona para a aplicação na porta 8000 # Mude o conforme
    location / {
        proxy_pass http://127.0.0.1:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }

}

# Opcional: Redirecionar HTTP para HTTPS
server {
    if ($host = xxxxxxxxxxxxx) {	# Substitua pelo seu domínio ou IP público
        return 301 https://$host$request_uri;
    } # managed by Certbot


    listen 80;
    server_name xxxxxxxxxxxxx;  # Substitua pelo seu domínio ou IP público
    return 301 https://$host$request_uri;


}
```
