## Anti ddos and buffer-overflow
> nginx.conf


#### Max de conexões:

```
worker_connections 50000;
```

#### Solicitação apenas a cada 2 segundos por IP (30 solicitações por minuto)

```
limit_req_zone $binary_remote_addr zone=one:10m rate=30r/m;
```

#### Apenas 10 conexões por IP:

```
limit_conn_zone $binary_remote_addr zone=addr:10m;
```

#### 10 solicitações por segundo por IP:

```
limit_req_zone $binary_remote_addr zone=mylimit:10m rate=10r/s;
```
### Após ser feita uma requisição no servidor, ele esperará 20s para obter uma resposta:

```
keepalive_timeout 20;
```

#### Corta a conexão mais rápido que o keepalive:

```
send_timeout 10s;
```

#### Tamanho max que pode ser enviado para o servidor:

```
client_max_body_size 2G;
```

#### Evitando buffer overflow:

```
client_body_buffer_size 200K;

client_header_buffer_size 2k;

large_client_header_buffers 3 1k;
```

<br><br><br>

### sites-enabled  (diretório):


#### Quando for feito a requisição do body ou da header, o stie dará 5s por uma resposta:

```
server {

client_body_timeout 5s;
client_header_timeout 5s;
```

<br>

```   
location {

limit_conn addr 10;                 > Max de 10 conexões por 1p.
limit_rate_after 1000k;             > O servidor fornecerá uma leitura de banda de até 1mb para que o site carregue mais rapidamente.
limit_rate 500k;                    > Após carregar o site a largura de banda cairá pela metade.
```
