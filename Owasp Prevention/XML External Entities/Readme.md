## XXE prevention

<a href="https://owasp.org/Top10/A05_2021-Security_Misconfiguration/">Owasp XML external entity</a>

* Quando possível use formatos mais simples, como o JSON
* Atualize todos os processadores XML e suas livrarias (SOAP)
* Disativar a validação de XML external entities e o DTD processing em todo o XML -- <a href="https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html">OWASP Cheat Sheet 'XXE Prevention'</a>
* "White list" positiva para inputs; Validando, filtrando e sanitizando
* Utilizar validação de arquivos XML ou XSL por XSD validation ou similares
* Use ferramentas estáticas para detectar o XEE (SAST)
