## Broken authentication prevention

<a href="https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/">Owasp broken authentication</a>

* Quando possível, implemente multi-factor authentication .
* Não colocar usuários e senhas padrão para admins, desative isso.
* Implemente checks para indentificar senhas simples; <a href="https://github.com/danielmiessler/SecLists/blob/master/Passwords/Common-Credentials/10-million-password-list-top-10000.txt">weak-passwords</a>
* Tamanho de senhas e políticas: <a href="https://pages.nist.gov/800-63-3/sp800-63b.html">Nist 800-63</a>
* Evitar mensagens específicas que promovam ataques de enumeração (ex: quando apenas o usuário ou a senha nao existir, retorne "Usuário ou senha incorretos") - (ex: Quando utilizar uma recuperação de senhas, mensagem retornada "Caso o usuário exista, um e-mail será enviado")
* Diminuir a tentativas de login (block de ip, tentantivas em geral, timeout)
* Utilize logs para registrar as informações de tentativas
* Gerencia os sessions IDs, não devem estar presentes na url
* Quando o cliente deslogar, remova(invalide) o cookie de indentificação dele e remova o cookie de indentificação do cliente no servidor
* Timeout de sessão
