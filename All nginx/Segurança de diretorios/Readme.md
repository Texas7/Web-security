## Segurança de diretórios

* Passo 1:

```
apt install openssl      > É provável que o Ubuntu ja tenha vindo com o openssl, mas, atualize-o se possivel

```

* Passo 2:

```
openssl passwd <definir senha> 
```
> Será gerado um hash que será sua senha 
> <br>Armazene o código pois ele será usado no próximo momento

* Passo 3:

```
cd /etc/nginx/

nano <nome do arquivo irá armazenar o usuário e senha>

> No arquivo gerado pelo nano:

Definir_Usuário:código gerado pelo openssl
```

* Passo 4:

```
cd /etc/nginx/sites-enabled/

nano default



location /diretório_que_deseja_proteger {
    auth_basic "Login";                    > Campo para exibir uma msg
    auth_basic_user_file /etc/nginx/arquivo_nano_criado_para_armazenar_o_usuário_e_senha;
}
```

