## Instalando o ngnix

#### Primeiramente certifique que os diretórios estão atualizados:

```
apt update
```

#### Começando a implementar o NGINX

```
apt install nginx
```

#### Iniciando e verificando se o serviço está funcionando:

```
service nginx start
service nginx status
```


#### Instalando o php-fpm (o apropriado para funcionar junto ao nginx)
> Instalando também o php-mysql para permitir uma interação com o mysql

```
apt install php-fpm php-mysql
```

#### No diretório do nginx:

```
cd /etc/nginx/sites-available/
```

#### Edite o arquivo default:

```
nano default
```
> No arquivo default descomentar as configurações do php:



