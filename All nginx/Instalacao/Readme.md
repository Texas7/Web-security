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

![unknown](https://user-images.githubusercontent.com/104938729/188776411-c25ce9fa-129e-474e-a887-21ea41213c4e.png)
> 1. Ja está descomentado na imagem<br>
> 2. Verificar se a versão do php-fpm do arquivo default é a mesma instalada no ambiente, caso seja diferente, alterar no arquivo<br>
> 3. Reinicie o serviço após as intruções

```
service nginx restart
```
#### Verificando se o php está funcionando devidamente:
```
cd /var/www/html/        > Raiz do site

nano index.php           > Criando um arquivo para teste

>No index.php:

<?php
    phpinfo();
?>
```
#### Volte na pasta default e coloque o index.php na lista:

![unknown2](https://user-images.githubusercontent.com/104938729/188777671-eca5d7c7-32d0-4484-b378-bf42a4087f13.png)

> Reinicie o serviço nginx

#### Instalando o banco de dados:

```
apt install mariadb-server mariadb-client

systemctl status mysql       > Verificando o serviço
```

#### Fazendo as configurações básicas e seguras do banco:

* Passo 1:

```
mysql_secure_installation
```

* Passo 2:

```
apt install phpmyadmin
```
> Instalando o phpmyadmin para fazer o gerenciamento do banco

* Passo 3:

![unknown3](https://user-images.githubusercontent.com/104938729/188778474-97668023-b17d-459f-b6a2-097659e67632.png)

> Caso não seja nenhum dos dois a cima, aperte tab e de um OK

![unknow4](https://user-images.githubusercontent.com/104938729/188778675-82998c33-e268-48e1-a1e9-232ec3563c93.png)

* Passo 5:

![unknown5](https://user-images.githubusercontent.com/104938729/188778815-b6b7ee31-e58e-4a1a-b053-2365098c3a5e.png)

> Defina a senha de configuração do mysql_secure

* Passo 6:

```
ln -s /usr/share/phpmyadmin/ /var/www/html/<Defina um nome que seja seguro!!!>
```
> Criando um atalho do phpmyadmin para acesso

* Passo 7:

```
mysql -u root -p

create user 'Nome_seguro'@'localhost' identified by 'senha';

grant all privileges on *.* to 'Nome_definido'@'localhost' with grant option;

flush privileges;

exit
```
> Definindo um usuário para logar na pagina do phpmyadmin


