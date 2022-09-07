## Certificado SSL

```
cd /etc/nginx/sites-enabled/

nano default

> Dentro do default:

server_name <coloque o domínio>;    > Sem as chaves (<>)

```
#### Instalando o certbot:

```
apt install certbot python3-certbot-nginx

certbot --nginx -d <domínio>
```

> O certbot opera em python
> <br>O certbot automatiza a instalação do certificado e o renova
> <br>Os procedimentos resultarão em uma alteração para o funcionamento no arquivo default

<br><br>

Obs:

1.  Caso vc tente acessar o link após as configurações serem feitas, não irá dar certo, porque vc estará tentando acessar externamente o que já é interno.
2.  Isso é normal de acontecer
3.  Só funcionará em um ambiente com um ip dedicado
