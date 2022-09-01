## Sensitive Data Exposure prevention

<a href="https://owasp.org/Top10/A02_2021-Cryptographic_Failures/">Owasp Sensitive Data</a>

* Classifique os dados em quais são mais sensitivos e os que não são
* Aplicar controles de acordo com a classificação
* Não armazene dados desnecessários
* Encriptar todos os dados sensiveis enquando estiverem armazenados (data-at-rest)
* Utilize protocolos e algoritmos atualizados
* Dados que estão trafegando devem estar protegidos (Ex: HTTPS, TLS ...)
* Desabilitar cache para dados sensíveis
* Armazene as senhas com algorítmos descentes (Ex: Argon2, Scrypt, Bcrypt or PBKDF2)
* Verifique de forma independente a eficiência das configurações
