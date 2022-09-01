## Broken Access Control prevention

<a href="https://owasp.org/Top10/A01_2021-Broken_Access_Control/">Owasp Broken Access Control</a>

* Com excessão de recursos que devem estar publicos, recuse todos os outros por padrão
* Implemente mecanismos de defesa únicos e os reutilize
* Todos os controles de acesso devem ser modelados para que você saiba quem criou, quem removeu (criar um auditoria);
Criar controles separadamente se necessário, onde cada perfil pode realizar certas tarefas e naqueles objetos  
* Cada aplicação tem seus próprios limites de requerimentos 
<br> (ex: eu posso descobrir se uma pessoa tem uma conta em um banco?
<br> Existem bancos no Brasil em que se você digitar o CPF de uma pessoa, você fica sabendo na hora se a pessoa tem uma conta lá ou não. 
Por padrão, esses bancos deixam essa função desativada e pedem para que se a pessoa tiver interesse de ser encontrada nos bancos, que ative essa função.)
* Desativar listagem de diretórios
* Controle os acessos (Gere Logs, principalmente em falhas repetidas)
* Limite o número de requisições á sua API sem prejudicar os usuários
* Tokens devem ser invalidados no servidor após um logout !!!
