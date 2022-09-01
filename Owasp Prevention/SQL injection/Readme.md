## SQL Prevention


<a href="https://owasp.org/Top10/A03_2021-Injection/">Owasp sql</a>

-------------------

* Não concatenar Strings !!!!!!!!
* Utilize uma API segura realizar a sanitização
* Evitar utilizar um interpretador, sanitize primeiramente e depois avalie se irá precisar
* Ou use ferramentas ORMs (Hibernate)
* Sanitize as informações de todos os serviços
* Utilize "Whitelist" positivas para validar os dados do input 
* Se restou alguma querie dinâmica onde não possivel aplicar as soluções, utilize o escape dos caracteres especiais (Em geral é dificil fazer)
* Use o LIMIT nas queries do sql (restrinja os mecanismos de busca do sql, exemplo: campo login)
* Não se contente apenas a essas informações

#### In java:

Utilize o PreparedStatement para separar os parâmetros enviados pelo usuário

```
String sql=Insert into accounts(username, password) values (?,?);   > Parametro do seu banco;

PreparedStatement stmt = connection.prepareStatement(sql);

stmt.setString(1, usuario);        > 'usuario' será o valor que entrará no parâmetro do banco
stmt.setString(2, senha);          > 'senha' será o valor que entrará no parâmetro do banco
stmt.execute();
```

