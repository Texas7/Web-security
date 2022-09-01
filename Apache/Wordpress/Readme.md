#### Segurança no WordPress:

1. Mantenha seu WordPress e plugins atualizados.
2. Tome cuidado com temas e plugins falsos ou duvidosos.
3. Utilize apenas plugins conhecidos e com boas qualificações.
4. Nunca use o usuário padrão “admin”.
5. Use senhas fortes, com mais de 6 dígitos, letras maiúsculos, minúsculas, caracteres especiais e números.
6. Desabilite a opção “qualquer pessoa pode registrar-se”.
7. Apague os arquivos readme.html e install.php.
8. Use autenticação de dois fatores.
9. Instale um bom WAF (Web Application Firewall).
10. Esconda a versão de seu WordPress, use o seguinte método:

##### No arquivo header.php remova a seguinte linha
```
<meta name=”generator” content=”WordPress <?php bloginfo(‘version’); ?>” />
Ou adicione esse código em seu arquivo functions.php
<?php remove_action(‘wp_head’, ‘wp_generator’); ?>
Proteja o arquivo “wp-config.php” através do .htaccess.
Altere o diretório padrão de acesso administrador “wp-admin”.
```
11. Evite deixar arquivos importantes expostos.
12. Coloque diretórios e arquivos mais sensíveis no robots.txt, para evitar Web crawling (spidering).
13. Limite o número de tentativas de login, evitando ataques brute-force.
15. Se possível use uma hospedagem dedicada ou escolha uma compartilhada de confiança.
16. Sempre que você tiver certeza que seu site está seguro e seus arquivos íntegros, faça backup.
