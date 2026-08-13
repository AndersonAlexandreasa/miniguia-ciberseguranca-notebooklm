# 🛡️ Resumo — Mini Guia de Cibersegurança

## 1. Introdução

A **cibersegurança** é o conjunto de práticas, tecnologias e processos utilizados para proteger computadores, redes, sistemas, aplicações e informações contra acessos não autorizados, ataques, falhas e outras ameaças digitais.

Para compreender cibersegurança, é importante começar pelos fundamentos de **redes de computadores**, pois grande parte das ameaças e mecanismos de proteção ocorre durante a comunicação entre dispositivos.

---

## 2. Fundamentos de Redes

Uma rede de computadores permite que dispositivos troquem informações.

Os principais elementos envolvidos incluem:

- Computadores;
- Servidores;
- Roteadores;
- Switches;
- Access points;
- Interfaces de rede;
- Endereços IP;
- Endereços MAC;
- Protocolos de comunicação.

### Endereço IP

O endereço IP identifica um dispositivo dentro de uma rede.

Exemplo:

```text
192.168.1.10
```

Em redes IPv4, o endereço é formado por quatro grupos de números separados por pontos.

### Endereço MAC

O endereço MAC identifica uma interface de rede no nível de enlace.

Exemplo:

```text
00:11:22:33:44:55
```

---

# 3. Modelo TCP/IP

O modelo TCP/IP organiza a comunicação de rede em diferentes camadas.

Uma representação simplificada é:

```text
Aplicação
    ↓
Transporte
    ↓
Internet
    ↓
Acesso à Rede
```

Cada camada possui responsabilidades específicas.

### Camada de Aplicação

É onde funcionam protocolos utilizados diretamente pelas aplicações.

Exemplos:

- HTTP;
- HTTPS;
- DNS;
- SSH;
- FTP.

### Camada de Transporte

É responsável pela comunicação entre processos.

Os principais protocolos são:

- TCP;
- UDP.

### Camada Internet

É responsável principalmente pelo endereçamento e encaminhamento de pacotes IP.

### Camada de Acesso à Rede

Relaciona-se à transmissão dos dados através da tecnologia de rede utilizada, como Ethernet e Wi-Fi.

---

# 4. TCP

O **TCP (Transmission Control Protocol)** é um protocolo orientado à conexão.

Ele oferece mecanismos para:

- Entrega confiável;
- Ordenação dos dados;
- Controle de fluxo;
- Controle de congestionamento;
- Retransmissão de segmentos.

## Three-Way Handshake

Antes de transmitir dados através de uma conexão TCP, normalmente ocorre o estabelecimento da conexão.

A sequência básica é:

```text
Cliente                    Servidor

   SYN  -------------------->

        <-------------------- SYN-ACK

   ACK  -------------------->
```

Depois disso, a comunicação pode prosseguir.

No Wireshark, essa sequência pode ser observada através das flags TCP.

---

# 5. UDP

O **UDP (User Datagram Protocol)** é um protocolo de transporte mais simples que o TCP.

Ele não estabelece uma conexão da mesma maneira que o TCP e não oferece as mesmas garantias de entrega e ordenação.

Pode ser utilizado em aplicações nas quais baixa latência e simplicidade são importantes.

Exemplos de aplicações que podem utilizar UDP incluem determinados tipos de:

- DNS;
- Streaming;
- Comunicação em tempo real;
- Jogos online.

---

# 6. DNS

O **DNS (Domain Name System)** permite associar nomes de domínio a informações utilizadas na comunicação de rede, especialmente endereços IP.

Por exemplo:

```text
www.exemplo.com
       ↓
   endereço IP
```

Sem o DNS, os usuários precisariam memorizar endereços IP para acessar serviços.

Uma consulta DNS normalmente envolve:

```text
Cliente
   ↓
Consulta DNS
   ↓
Servidor DNS
   ↓
Resposta
   ↓
Endereço IP
```

No Wireshark, consultas e respostas DNS podem ser identificadas através do protocolo DNS.

---

# 7. HTTP

O **HTTP (Hypertext Transfer Protocol)** é utilizado na comunicação entre clientes e servidores Web.

Uma requisição HTTP pode conter:

- Método;
- URL;
- Cabeçalhos;
- Informações adicionais.

Exemplo simplificado:

```text
Cliente
   │
   │ HTTP Request
   ▼
Servidor
   │
   │ HTTP Response
   ▼
Cliente
```

Alguns métodos HTTP comuns:

- GET;
- POST;
- PUT;
- DELETE.

Alguns códigos de resposta:

| Código | Significado |
|---:|---|
| 200 | Sucesso |
| 301 | Redirecionamento |
| 400 | Requisição inválida |
| 401 | Não autorizado |
| 403 | Acesso proibido |
| 404 | Recurso não encontrado |
| 500 | Erro interno do servidor |

---

# 8. HTTPS e TLS

O **HTTPS** utiliza HTTP protegido por **TLS (Transport Layer Security)**.

A utilização de TLS ajuda a proteger a comunicação contra interceptação e alteração indevida dos dados.

Uma diferença importante é:

```text
HTTP
Dados transmitidos sem a proteção criptográfica fornecida pelo TLS

HTTPS
HTTP + TLS
```

Por isso, HTTPS é utilizado para proteger muitas comunicações realizadas na Web.

---

# 9. Wireshark

O **Wireshark** é uma ferramenta utilizada para capturar e analisar tráfego de rede.

Ele permite estudar:

- Pacotes;
- Protocolos;
- Endereços IP;
- Portas;
- Flags TCP;
- Consultas DNS;
- Comunicação HTTP;
- TLS;
- Retransmissões;
- Erros de comunicação.

## Informações importantes para observar

Durante uma análise, é possível verificar:

```text
IP de origem
IP de destino
Protocolo
Porta de origem
Porta de destino
Informações do pacote
```

O Wireshark é especialmente útil para aprender como os protocolos funcionam na prática.

---

# 10. Filtros do Wireshark

Os filtros de exibição facilitam a análise de determinados protocolos ou tipos de tráfego.

Exemplos:

```text
tcp
```

Mostra tráfego TCP.

```text
udp
```

Mostra tráfego UDP.

```text
dns
```

Mostra tráfego DNS.

```text
http
```

Mostra tráfego HTTP.

```text
icmp
```

Mostra tráfego ICMP.

Também podem ser utilizados filtros envolvendo endereços IP e portas.

Exemplo:

```text
ip.addr == 192.168.1.10
```

Esse filtro permite concentrar a análise no endereço especificado.

---

# 11. Cibersegurança

A cibersegurança busca proteger três propriedades fundamentais da informação:

## Confidencialidade

Somente pessoas ou sistemas autorizados devem ter acesso às informações.

## Integridade

As informações devem permanecer corretas e não sofrer alterações indevidas.

## Disponibilidade

Sistemas e informações devem estar disponíveis quando necessários.

Esses três princípios formam a conhecida:

**Tríade CIA**

```text
Confidencialidade
       +
Integridade
       +
Disponibilidade
```

---

# 12. Principais ameaças

Entre as ameaças encontradas em cibersegurança estão:

### Malware

Software desenvolvido para realizar ações maliciosas.

Exemplos:

- Vírus;
- Worm;
- Trojan;
- Ransomware;
- Spyware.

### Phishing

Técnica de engenharia social utilizada para enganar pessoas e tentar obter informações, credenciais ou outros dados.

### Ransomware

Tipo de malware que pode impedir o acesso aos dados, frequentemente utilizando criptografia, e exigir pagamento para tentar recuperar o acesso.

### DDoS

Ataque distribuído de negação de serviço que procura tornar um serviço indisponível através de grande quantidade de tráfego ou requisições.

### Man-in-the-Middle

Situação em que um atacante consegue se posicionar entre duas partes da comunicação para tentar interceptar ou manipular os dados.

---

# 13. Vulnerabilidades

Uma **vulnerabilidade** é uma fraqueza que pode permitir que um sistema seja comprometido.

As vulnerabilidades podem estar relacionadas a:

- Software desatualizado;
- Configurações inadequadas;
- Senhas fracas;
- Falhas de programação;
- Serviços desnecessários;
- Falta de controles de segurança.

A identificação e correção de vulnerabilidades fazem parte de uma estratégia de segurança.

---

# 14. Firewall

O **firewall** controla o tráfego de rede com base em regras.

Ele pode controlar, por exemplo:

- Endereços IP;
- Portas;
- Protocolos;
- Origem;
- Destino;
- Direção do tráfego.

Seu objetivo é permitir ou bloquear determinados tipos de comunicação de acordo com uma política de segurança.

---

# 15. IDS e IPS

### IDS

**Intrusion Detection System**

Sistema de detecção de intrusão.

Seu objetivo é identificar atividades suspeitas ou possíveis ataques.

### IPS

**Intrusion Prevention System**

Sistema de prevenção de intrusão.

Além de detectar determinadas atividades, pode atuar para bloquear ou impedir comportamentos considerados maliciosos.

---

# 16. Processo básico de análise de rede

Uma investigação simples pode seguir esta sequência:

```text
1. Identificar o problema
        ↓
2. Capturar o tráfego
        ↓
3. Filtrar os pacotes
        ↓
4. Identificar protocolos
        ↓
5. Analisar IPs e portas
        ↓
6. Observar a comunicação
        ↓
7. Procurar erros ou anomalias
        ↓
8. Formular uma hipótese
        ↓
9. Testar a hipótese
        ↓
10. Documentar o resultado
```

Esse processo ajuda a desenvolver uma mentalidade de investigação.

---

# 17. Laboratório de aprendizagem

Um laboratório de cibersegurança permite estudar técnicas e ferramentas em um ambiente controlado.

Uma estrutura de aprendizado pode utilizar:

```text
┌───────────────────┐
│    Kali Linux     │
│ Ferramentas       │
│ de análise        │
└─────────┬─────────┘
          │
          │ Rede isolada
          │
┌─────────▼─────────┐
│ Máquina de        │
│ laboratório       │
└───────────────────┘
```

O objetivo é permitir experimentação sem afetar sistemas de terceiros.

---

# 18. O que observar em uma captura

Ao analisar uma captura no Wireshark, um iniciante deve procurar:

### Identificação

- Quem enviou?
- Quem recebeu?
- Qual protocolo está sendo utilizado?

### Transporte

- TCP ou UDP?
- Qual porta de origem?
- Qual porta de destino?

### Comunicação

- A conexão foi estabelecida?
- Existem respostas?
- Existem retransmissões?
- Existem erros?

### Aplicação

- Existe DNS?
- Existe HTTP?
- Existe TLS?
- Qual serviço está sendo utilizado?

---

# 19. Relação entre os conhecimentos

Os assuntos estudados estão diretamente relacionados:

```text
REDES
  │
  ▼
TCP/IP
  │
  ▼
PROTOCOLOS
  │
  ├── TCP
  ├── UDP
  ├── DNS
  ├── HTTP
  └── HTTPS
  │
  ▼
TRÁFEGO DE REDE
  │
  ▼
WIRESHARK
  │
  ▼
ANÁLISE
  │
  ▼
CIBERSEGURANÇA
```

Aprender cibersegurança começa pela compreensão de como os sistemas realmente se comunicam.

---

# 20. Competências desenvolvidas

Ao concluir este mini guia, o estudante deverá ser capaz de:

- Compreender os fundamentos de redes;
- Diferenciar TCP e UDP;
- Entender o funcionamento básico do TCP/IP;
- Identificar IPs e portas;
- Entender o Three-Way Handshake;
- Compreender o funcionamento básico do DNS;
- Entender requisições e respostas HTTP;
- Diferenciar HTTP e HTTPS;
- Utilizar filtros básicos do Wireshark;
- Analisar pacotes de rede;
- Reconhecer conceitos básicos de cibersegurança;
- Identificar ameaças comuns;
- Compreender a Tríade CIA;
- Trabalhar com laboratórios de segurança de forma responsável.

---

# 21. Conclusão

Redes de computadores são a base para compreender grande parte dos problemas e mecanismos de segurança digital.

Ao estudar **TCP/IP**, **DNS**, **HTTP**, **HTTPS** e **Wireshark**, o estudante começa a enxergar a comunicação de rede de forma prática.

A partir dessa base, conceitos de cibersegurança como **vulnerabilidades, malware, phishing, firewall, IDS, IPS e análise de tráfego** tornam-se mais fáceis de compreender.

O objetivo deste projeto não é apenas memorizar conceitos, mas desenvolver a capacidade de:

**observar → investigar → compreender → testar → analisar → proteger.**

Todo conhecimento prático de segurança deve ser aplicado somente em **ambientes próprios, controlados ou explicitamente autorizados**.

---

## 📚 Arquivos relacionados

- `README.md`
- `fonte-01-redes.md`
- `fonte-02-wireshark.md`
- `fonte-03-tcp-ip.md`
- `fonte-04-http-dns.md`
- `fonte-05-ciberseguranca.md`
- `glossario.md`
- `prompts-reutilizaveis.md`
- `resumo.md`
