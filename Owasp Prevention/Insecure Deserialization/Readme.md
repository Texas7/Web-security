## Insecure Deserialization Prevention

<a href="https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/">Owasp Deserialization</a>

* Não aceitar dados serializados de fontes desconhecidas ou usar somente tipos de dados primitivos
* Implementar checks de integridadde como assinaturas digitais para garantir sua fonte
* Isolar e iniciar codigós deserializados em ambientes de baixo privilégio
* Gerar Logs
* Restringir ou monitorar o padrão dos dados
* Monitorar a deserialização
