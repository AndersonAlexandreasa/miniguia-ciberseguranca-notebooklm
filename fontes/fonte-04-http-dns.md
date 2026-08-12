# Fonte 04 — HTTP e DNS

## HTTP e DNS: como funciona o acesso a um serviço web

Quando um usuário digita um endereço como `https://www.exemplo.com` no navegador, várias etapas acontecem antes que a página seja apresentada.

De forma simplificada:

```text
Usuário
   ↓
Navegador
   ↓
DNS
   ↓
Endereço IP
   ↓
TCP/IP ou transporte utilizado
   ↓
HTTP/HTTPS
   ↓
Servidor Web
   ↓
Resposta
   ↓
Navegador
```

O **DNS** ajuda a descobrir o endereço IP associado ao nome do domínio, enquanto o **HTTP** define a comunicação entre cliente e servidor web.

---

## 1. O que é HTTP?

**HTTP — Hypertext Transfer Protocol** é um protocolo da camada de aplicação utilizado para comunicação entre clientes e servidores.

Um navegador funciona normalmente como cliente, enviando uma requisição para um servidor. O servidor processa a requisição e devolve uma resposta.

```text
Cliente                         Servidor

   HTTP Request ──────────────────►

   ◄──────────────── HTTP Response
```

O HTTP utiliza o modelo **cliente-servidor** e é um protocolo **stateless**, ou seja, o protocolo HTTP, por si só, não mantém o estado de uma requisição para outra. Recursos como cookies podem ser utilizados para manter informações de sessão.

---

## 2. Requisição HTTP

Uma requisição HTTP contém informações que permitem ao servidor compreender o que o cliente deseja.

Exemplo simplificado:

```text
GET /index.html HTTP/1.1
Host: exemplo.com
Accept: text/html
```

Os principais componentes incluem:

- método HTTP;
- caminho do recurso;
- versão do protocolo;
- cabeçalhos;
- eventualmente um corpo.

O RFC 9110 define a semântica moderna do HTTP, incluindo métodos, cabeçalhos, códigos de status e mensagens de requisição e resposta.

---

## 3. Principais métodos HTTP

Alguns dos métodos mais importantes são:

| Método | Função geral |
|---|---|
| GET | Solicitar um recurso |
| POST | Enviar dados para processamento |
| PUT | Criar ou substituir uma representação |
| PATCH | Modificar parcialmente um recurso |
| DELETE | Solicitar a remoção de um recurso |
| HEAD | Solicitar informações semelhantes às de uma resposta GET, sem o conteúdo da representação |

Exemplo:

```text
GET /produtos
```

pode ser utilizado para solicitar uma lista de produtos.

Já:

```text
POST /usuarios
```

pode representar o envio de dados para criação de um usuário em uma aplicação.

O significado preciso desses métodos é definido pela especificação HTTP.

---

## 4. Resposta HTTP

Depois de receber uma requisição, o servidor retorna uma resposta.

Exemplo:

```text
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1250
```

Uma resposta normalmente possui:

- versão HTTP;
- código de status;
- cabeçalhos;
- corpo, quando aplicável.

A estrutura de resposta e os códigos de status fazem parte da semântica definida pelo HTTP.

---

## 5. Códigos de status HTTP

Os códigos HTTP são divididos em cinco grupos principais:

```text
1xx → Informações
2xx → Sucesso
3xx → Redirecionamento
4xx → Erro do cliente
5xx → Erro do servidor
```

Alguns exemplos importantes:

| Código | Significado |
|---:|---|
| 200 | OK |
| 201 | Created |
| 301 | Moved Permanently |
| 302 | Found |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |
| 502 | Bad Gateway |
| 503 | Service Unavailable |

Esses códigos são importantes durante a análise de aplicações web e também podem ser observados no Wireshark em tráfego HTTP não criptografado.

---

# 6. HTTP e HTTPS

É importante diferenciar HTTP de HTTPS.

### HTTP

```text
Cliente
   ↓
HTTP
   ↓
TCP/IP
   ↓
Servidor
```

### HTTPS

```text
Cliente
   ↓
HTTP
   ↓
TLS
   ↓
TCP/IP
   ↓
Servidor
```

O HTTPS utiliza TLS para proteger a comunicação HTTP.

Em uma captura de rede, isso significa que, em condições normais, o conteúdo da aplicação não aparece como HTTP em texto aberto simplesmente porque a conexão utiliza a porta 443.

O HTTP moderno possui especificações separadas para semântica, HTTP/1.1, HTTP/2 e HTTP/3.

---

# 7. O que é DNS?

**DNS — Domain Name System** é o sistema utilizado para associar nomes de domínio a informações de rede, incluindo endereços IP.

Os seres humanos preferem trabalhar com nomes como:

```text
www.exemplo.com
```

enquanto a comunicação IP utiliza endereços como:

```text
192.0.2.10
```

O DNS funciona como um sistema distribuído de resolução de nomes.

De forma simplificada:

```text
Nome
 ↓
DNS
 ↓
Endereço IP
```

O navegador pode então utilizar o endereço obtido para estabelecer a comunicação com o servidor.

---

# 8. Como funciona uma consulta DNS

Suponha que o usuário digite:

```text
www.exemplo.com
```

O computador precisa descobrir qual endereço IP está associado ao nome.

Um fluxo simplificado é:

```text
Navegador
   ↓
Resolvedor DNS
   ↓
Servidores DNS
   ↓
Resposta
   ↓
Endereço IP
```

Depois que o endereço é obtido, o navegador pode iniciar a comunicação com o servidor correspondente.

É importante entender que **DNS e HTTP são protocolos diferentes**.

O DNS resolve informações de nomes. O HTTP é utilizado posteriormente para a comunicação da aplicação web.

---

# 9. Registros DNS

O DNS possui diferentes tipos de registros.

Alguns dos mais conhecidos são:

| Registro | Função |
|---|---|
| A | Endereço IPv4 |
| AAAA | Endereço IPv6 |
| CNAME | Alias para outro nome |
| MX | Servidores responsáveis por e-mail |
| NS | Servidores autoritativos de uma zona |
| TXT | Informações textuais associadas ao domínio |

Exemplo conceitual:

```text
exemplo.com
      │
      ├── A → 192.0.2.10
      │
      └── AAAA → 2001:db8::10
```

---

# 10. DNS e cache

Para evitar consultas desnecessárias, respostas DNS podem ser armazenadas temporariamente em cache.

O tempo pelo qual uma informação pode permanecer válida é associado ao **TTL — Time To Live**.

Exemplo:

```text
Domínio:
exemplo.com

IP:
192.0.2.10

TTL:
3600 segundos
```

Enquanto a informação estiver válida no cache, uma nova consulta completa pode não ser necessária.

Isso melhora o desempenho e reduz a quantidade de consultas DNS.

---

# 11. DNS e portas

O DNS tradicional utiliza principalmente a porta:

```text
UDP 53
```

Também pode utilizar:

```text
TCP 53
```

dependendo da situação.

Em ambientes modernos também existem mecanismos de DNS que protegem as consultas utilizando criptografia, como:

- DNS over TLS — DoT;
- DNS over HTTPS — DoH;
- DNS over QUIC — DoQ.

Essas tecnologias podem reduzir a exposição das consultas DNS tradicionais, mas também modificam a forma como o tráfego aparece durante uma análise de rede.

---

# 12. Fluxo completo: DNS + HTTP

Uma forma simples de visualizar o acesso a um site é:

```text
1. Usuário digita o domínio
          ↓
2. Cliente verifica informações locais/cache
          ↓
3. Cliente realiza consulta DNS
          ↓
4. DNS retorna endereço IP
          ↓
5. Cliente inicia comunicação com o servidor
          ↓
6. Cliente envia requisição HTTP/HTTPS
          ↓
7. Servidor processa a requisição
          ↓
8. Servidor envia resposta
          ↓
9. Navegador recebe os dados
          ↓
10. Navegador monta a página
```

A documentação da MDN descreve esse fluxo geral: resolução DNS, comunicação usando TCP/IP e envio de uma requisição HTTP para obtenção dos recursos da página.

---

# 13. Exemplo prático com Wireshark

O conhecimento de HTTP e DNS é especialmente importante para o uso do Wireshark.

Durante uma captura, utilize:

```text
dns
```

para visualizar tráfego DNS.

Para tráfego HTTP:

```text
http
```

Para visualizar conexões TCP:

```text
tcp
```

Para investigar uma porta específica:

```text
tcp.port == 80
```

ou:

```text
tcp.port == 443
```

Para investigar DNS em uma captura:

```text
udp.port == 53
```

---

# 14. Exercício de laboratório — DNS

Em uma máquina Kali Linux autorizada, execute:

```bash
nslookup example.com
```

ou:

```bash
dig example.com
```

Observe:

- nome consultado;
- servidor DNS utilizado;
- endereço IPv4;
- endereço IPv6, quando disponível;
- tempo da consulta;
- informações retornadas.

Depois abra o Wireshark e utilize:

```text
dns
```

Procure a consulta correspondente.

O objetivo é relacionar:

```text
Comando
   ↓
Consulta DNS
   ↓
Servidor DNS
   ↓
Resposta
   ↓
Endereço IP
```

---

# 15. Exercício de laboratório — HTTP

Em um ambiente de laboratório controlado que disponibilize um serviço HTTP, gere uma requisição.

Por exemplo:

```bash
curl http://192.168.101.40/
```

No Wireshark, utilize:

```text
http
```

Analise:

- IP de origem;
- IP de destino;
- porta de origem;
- porta de destino;
- método HTTP;
- URI;
- código de resposta;
- cabeçalhos.

A sequência pode ser observada conceitualmente como:

```text
Kali
192.168.101.10
      │
      │ GET /
      ▼
Servidor HTTP
192.168.101.40:80
      │
      │ 200 OK
      ▼
Kali
```

---

# 16. Relação entre DNS, TCP/IP e HTTP

Os três conceitos estudados neste projeto podem ser relacionados:

```text
                 APLICAÇÃO
                    │
          ┌─────────┴─────────┐
          │                   │
         DNS                 HTTP
          │                   │
          └─────────┬─────────┘
                    ↓
                 TCP/UDP
                    ↓
                    IP
                    ↓
              Ethernet/Wi-Fi
```

O DNS ajuda o cliente a descobrir informações necessárias para localizar um serviço.

O TCP ou UDP fornece transporte, dependendo do protocolo e da implementação utilizada.

O IP fornece endereçamento e encaminhamento.

O HTTP define a comunicação entre cliente e servidor web.

---

# 17. HTTP, DNS e cibersegurança

Esses protocolos também são importantes para a análise de segurança.

Um analista pode investigar:

### DNS

- consultas incomuns;
- domínios suspeitos;
- grande quantidade de consultas;
- padrões de comunicação anormais;
- servidores DNS inesperados.

### HTTP

- métodos HTTP utilizados;
- códigos de erro;
- URLs acessadas;
- cabeçalhos;
- comportamento anormal das requisições;
- comunicação com servidores suspeitos.

### TCP/IP

- endereços de origem e destino;
- portas;
- conexões;
- retransmissões;
- padrões de tráfego.

O DNS é particularmente relevante em segurança porque os nomes de domínio constituem uma parte importante da infraestrutura utilizada pelas aplicações e também podem aparecer em diferentes tipos de atividades maliciosas.

---

# 18. O que observar no Wireshark

Para um iniciante, recomenda-se seguir esta sequência:

```text
1. Identificar o IP de origem
             ↓
2. Identificar o IP de destino
             ↓
3. Identificar o protocolo
             ↓
4. Identificar a porta
             ↓
5. Identificar a requisição
             ↓
6. Identificar a resposta
             ↓
7. Observar o comportamento da comunicação
```

Exemplo:

```text
192.168.101.10:52344
        │
        │ TCP
        ▼
192.168.101.40:80
        │
        │ HTTP GET
        ▼
     200 OK
```

Esse tipo de análise transforma os conceitos teóricos de TCP/IP em informações observáveis em uma captura real.

---

# 19. Relação com as fontes anteriores

Esta fonte complementa diretamente as fontes anteriores do projeto.

```text
Fonte 01
Redes
   ↓
Fonte 02
Wireshark
   ↓
Fonte 03
TCP/IP
   ↓
Fonte 04
HTTP + DNS
```

A sequência permite compreender:

```text
REDE
 ↓
PROTOCOLOS
 ↓
TCP/IP
 ↓
DNS
 ↓
HTTP
 ↓
CAPTURA DE PACOTES
 ↓
ANÁLISE DE TRÁFEGO
 ↓
CIBERSEGURANÇA
```

---

# 20. Pontos principais para revisão

### HTTP

- É um protocolo de camada de aplicação;
- utiliza o modelo cliente-servidor;
- trabalha com requisições e respostas;
- possui métodos como GET e POST;
- utiliza códigos de status;
- é stateless por natureza;
- pode ser utilizado sobre conexões protegidas por TLS.

### DNS

- É um sistema distribuído de nomes;
- permite obter informações associadas a nomes de domínio;
- possui diferentes tipos de registros;
- utiliza cache;
- pode utilizar UDP ou TCP;
- possui versões e mecanismos modernos que protegem as consultas por criptografia.

### Wireshark

- Permite observar consultas DNS;
- permite analisar HTTP em ambientes apropriados;
- permite identificar IPs;
- permite identificar portas;
- permite observar conexões TCP;
- permite relacionar diferentes camadas da comunicação.

---

# 21. Fontes recomendadas

**MDN Web Docs — Overview of HTTP**  
Material introdutório sobre HTTP, cliente-servidor, requisições, respostas, mensagens e fluxo HTTP.

[MDN — Overview of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview?utm_source=chatgpt.com)

**MDN Web Docs — How the Web Works**  
Explica, em nível introdutório, a relação entre DNS, HTTP, TCP/IP e o carregamento de uma página web.

[MDN — How the Web Works](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works?utm_source=chatgpt.com)

**RFC 9110 — HTTP Semantics**  
Especificação oficial da semântica HTTP.

[RFC 9110 — HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110.html?utm_source=chatgpt.com)

---

# Relação com o projeto

Esta fonte é importante para o **Miniguia de Cibersegurança no NotebookLM** porque conecta os conceitos de redes e TCP/IP com aplicações reais.

O estudante passa a compreender que, ao acessar um site, não existe apenas uma comunicação HTTP isolada. Existe uma sequência de processos envolvendo resolução de nomes, endereçamento, transporte e aplicação.

A compreensão dessa sequência é fundamental para interpretar uma captura no Wireshark e posteriormente avançar para temas como **análise de tráfego, monitoramento de rede, investigação de incidentes e detecção de comportamentos suspeitos**.
