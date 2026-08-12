# 📡 Fonte 01 — Fundamentos de Redes de Computadores

## 1. Identificação da Fonte

**Tema:** Fundamentos de Redes de Computadores

**Categoria:** Material técnico / referência educacional

**Objetivo no projeto:**  
Utilizar esta fonte como base para compreender os conceitos fundamentais necessários para o estudo de Cibersegurança e análise de tráfego de rede.

**Fonte principal recomendada:**  
Cisco Networking Academy — Introdução às Redes

**Link:**  
https://www.netacad.com/courses/networking-basics

---

# 2. Por que esta fonte foi selecionada?

Os fundamentos de redes são essenciais para o estudo de Cibersegurança.

Antes de analisar vulnerabilidades, tráfego de rede ou incidentes de segurança, é necessário compreender como os dispositivos se comunicam e como os dados são transportados entre diferentes pontos da rede.

Esta fonte foi selecionada porque aborda conceitos fundamentais relacionados a:

- redes de computadores;
- dispositivos de rede;
- endereçamento;
- protocolos;
- comunicação entre dispositivos;
- modelos de comunicação;
- conceitos básicos de infraestrutura de redes.

Esses conhecimentos serão utilizados posteriormente durante os laboratórios com **Wireshark**, Kali Linux e máquinas virtuais.

---

# 3. Conceito de Rede de Computadores

Uma rede de computadores é um conjunto de dispositivos capazes de se comunicar e compartilhar informações e recursos.

Os dispositivos podem incluir:

- computadores;
- servidores;
- smartphones;
- impressoras;
- roteadores;
- switches;
- dispositivos IoT.

A comunicação ocorre utilizando protocolos e regras que permitem que os dispositivos entendam como os dados devem ser enviados, recebidos e interpretados.

---

# 4. Principais Componentes de uma Rede

## 4.1 Dispositivos finais

São dispositivos que participam diretamente da comunicação.

Exemplos:

- computador;
- notebook;
- servidor;
- smartphone;
- impressora;
- câmera IP.

Esses dispositivos também podem ser chamados de **hosts** ou dispositivos finais.

---

## 4.2 Switch

O switch conecta dispositivos dentro de uma rede local.

Ele trabalha principalmente na camada de enlace do modelo OSI e utiliza endereços MAC para encaminhar quadros dentro da rede local.

Exemplo:

```text
Computador A
     |
     |
   Switch
   /    \
  /      \
PC B     PC C
```

---

## 4.3 Roteador

O roteador é utilizado para encaminhar pacotes entre redes diferentes.

Exemplo:

```text
Rede local
192.168.1.0/24
      |
      |
   Roteador
      |
      |
   Internet
```

O roteador utiliza informações de endereçamento IP e tabelas de roteamento para determinar para onde os pacotes devem ser encaminhados.

---

# 5. Tipos de Rede

## LAN

**LAN — Local Area Network**

É uma rede que cobre uma área relativamente limitada.

Exemplo:

- residência;
- escritório;
- laboratório;
- escola.

---

## WAN

**WAN — Wide Area Network**

É uma rede que pode interligar redes geograficamente distantes.

A Internet é um exemplo de uma grande infraestrutura composta por redes interconectadas.

---

## WLAN

**WLAN — Wireless Local Area Network**

É uma rede local que utiliza comunicação sem fio.

Um exemplo comum é uma rede Wi-Fi residencial.

---

# 6. Endereço IP

O endereço IP é utilizado para identificar logicamente uma interface ou dispositivo em uma rede IP.

Um exemplo de endereço IPv4 é:

```text
192.168.1.10
```

Um endereço IPv4 possui 32 bits e normalmente é representado por quatro números decimais separados por pontos.

Exemplo:

```text
192 . 168 . 1 . 10
```

---

# 7. Endereço MAC

O endereço MAC identifica uma interface de rede no contexto da comunicação da camada de enlace.

Um endereço MAC possui normalmente 48 bits e costuma ser representado em hexadecimal.

Exemplo:

```text
00:11:22:33:44:55
```

Durante a análise de pacotes no Wireshark, é possível observar endereços MAC em protocolos e quadros apropriados.

---

# 8. IPv4 e Máscara de Rede

O IPv4 utiliza endereços de 32 bits.

Exemplo:

```text
192.168.101.40
```

Uma máscara de rede pode ser:

```text
255.255.255.0
```

Também pode ser representada utilizando notação CIDR:

```text
192.168.101.40/24
```

O `/24` indica que os primeiros 24 bits correspondem ao prefixo da rede.

---

# 9. Protocolos de Rede

Um protocolo é um conjunto de regras utilizado para permitir a comunicação entre dispositivos.

Alguns protocolos importantes para o estudo de redes e Cibersegurança são:

| Protocolo | Função |
|---|---|
| ARP | Associação entre IPv4 e MAC em redes locais |
| IP | Endereçamento e encaminhamento de pacotes |
| ICMP | Mensagens de controle e diagnóstico |
| TCP | Transporte orientado à conexão |
| UDP | Transporte sem conexão |
| DNS | Resolução de nomes |
| HTTP | Comunicação web |
| HTTPS | Comunicação web protegida por TLS |

---

# 10. Modelo OSI

O modelo OSI organiza as funções de comunicação de rede em sete camadas.

| Camada | Nome | Exemplo |
|---:|---|---|
| 7 | Aplicação | HTTP, DNS |
| 6 | Apresentação | Formatação/representação |
| 5 | Sessão | Gerenciamento de sessões |
| 4 | Transporte | TCP, UDP |
| 3 | Rede | IP |
| 2 | Enlace | Ethernet, MAC |
| 1 | Física | Sinais e transmissão de bits |

O modelo OSI é especialmente útil para organizar mentalmente os diferentes componentes envolvidos em uma comunicação de rede.

---

# 11. Modelo TCP/IP

O modelo TCP/IP é utilizado como referência para a arquitetura das redes Internet.

Uma representação simplificada é:

```text
┌─────────────────────────────┐
│         Aplicação           │
├─────────────────────────────┤
│         Transporte          │
├─────────────────────────────┤
│           Internet          │
├─────────────────────────────┤
│       Acesso à Rede         │
└─────────────────────────────┘
```

Alguns exemplos:

```text
Aplicação
   ↓
HTTP / HTTPS / DNS

Transporte
   ↓
TCP / UDP

Internet
   ↓
IP / ICMP

Acesso à Rede
   ↓
Ethernet / Wi-Fi
```

---

# 12. TCP e UDP

## TCP

O TCP é um protocolo de transporte orientado à conexão.

Entre suas características estão:

- estabelecimento de conexão;
- confirmação de recebimento;
- controle de fluxo;
- retransmissão;
- entrega ordenada dos dados.

Uma conexão TCP começa normalmente com o **Three-Way Handshake**.

```text
Cliente                 Servidor

   SYN  ────────────────>

        <──────────── SYN-ACK

   ACK  ────────────────>
```

---

## UDP

O UDP não estabelece uma conexão da mesma maneira que o TCP.

Ele possui menor overhead e não fornece, por si só, mecanismos equivalentes aos do TCP para garantir entrega e ordenação.

É utilizado por diversos tipos de aplicações que podem se beneficiar de uma comunicação mais simples e de menor overhead.

---

# 13. Portas de Comunicação

As portas permitem identificar serviços e processos associados à comunicação de transporte.

Exemplos comuns:

| Porta | Protocolo/Serviço |
|---:|---|
| 22 | SSH |
| 53 | DNS |
| 80 | HTTP |
| 443 | HTTPS |

A porta, entretanto, deve ser interpretada em conjunto com o protocolo e o contexto da comunicação.

Durante a análise de tráfego, o Wireshark permite visualizar portas de origem e destino.

---

# 14. DNS

O DNS, **Domain Name System**, permite realizar a resolução de nomes.

Por exemplo:

```text
www.exemplo.com
       ↓
    Consulta DNS
       ↓
Endereço IP correspondente
```

Esse processo permite que usuários e aplicações utilizem nomes em vez de precisarem conhecer diretamente os endereços IP dos serviços.

No Wireshark, podemos utilizar o filtro:

```text
dns
```

para facilitar a visualização de pacotes relacionados ao DNS.

---

# 15. HTTP e HTTPS

O HTTP é um protocolo utilizado para comunicação entre clientes e servidores web.

Uma comunicação simplificada pode ser representada como:

```text
Cliente
   |
   | HTTP Request
   ↓
Servidor
   |
   | HTTP Response
   ↓
Cliente
```

O HTTPS utiliza TLS para proteger a comunicação.

Isso é importante para a análise de tráfego porque, embora seja possível observar informações de conexão e metadados de determinados fluxos, o conteúdo da aplicação protegido por TLS não fica normalmente disponível em texto aberto como em uma comunicação HTTP sem criptografia.

---

# 16. Relação com o Wireshark

Os conceitos apresentados nesta fonte serão utilizados diretamente durante os laboratórios.

Ao capturar tráfego no Wireshark, será possível relacionar a teoria com os pacotes observados.

Por exemplo:

```text
Conceito aprendido
       ↓
Protocolo
       ↓
Pacote capturado
       ↓
Análise no Wireshark
       ↓
Interpretação
```

### Informações que podem ser analisadas

- IP de origem;
- IP de destino;
- MAC de origem;
- MAC de destino;
- protocolo;
- porta de origem;
- porta de destino;
- flags TCP;
- tamanho do pacote;
- sequência de comunicação;
- consultas DNS;
- requisições HTTP.

---

# 17. Filtros iniciais do Wireshark

Alguns filtros úteis para o laboratório:

### Mostrar tráfego IP

```text
ip
```

### Mostrar TCP

```text
tcp
```

### Mostrar UDP

```text
udp
```

### Mostrar DNS

```text
dns
```

### Mostrar HTTP

```text
http
```

### Mostrar ICMP

```text
icmp
```

### Identificar pacotes TCP SYN

```text
tcp.flags.syn == 1
```

Esses filtros serão utilizados posteriormente nas atividades práticas do projeto.

---

# 18. Relação com Cibersegurança

O conhecimento de redes é uma das bases para compreender Cibersegurança.

Um profissional de segurança precisa entender como:

```text
Dispositivo
    ↓
Rede
    ↓
Protocolo
    ↓
Comunicação
    ↓
Tráfego
    ↓
Análise
    ↓
Detecção de eventos
```

Sem compreender os protocolos e o comportamento normal da rede, torna-se mais difícil identificar comportamentos anômalos.

Por esse motivo, fundamentos de redes serão utilizados como base para estudos posteriores de:

- análise de tráfego;
- monitoramento;
- detecção de anomalias;
- segurança de redes;
- análise de incidentes;
- testes de segurança em ambientes autorizados.

---

# 19. Perguntas para o NotebookLM

As seguintes perguntas serão utilizadas no caderno temático.

### Pergunta 01

> O que é uma rede de computadores e quais são seus principais componentes?

### Pergunta 02

> Explique a diferença entre endereço IP e endereço MAC.

### Pergunta 03

> Qual é a função de um switch e de um roteador?

### Pergunta 04

> Compare o modelo OSI e o modelo TCP/IP.

### Pergunta 05

> Explique as principais diferenças entre TCP e UDP.

### Pergunta 06

> Explique o funcionamento básico do DNS.

### Pergunta 07

> Explique o conceito de portas TCP e UDP.

### Pergunta 08

> Como identificar os principais protocolos de rede em uma captura do Wireshark?

### Pergunta 09

> Explique o Three-Way Handshake do TCP e mostre como identificá-lo no Wireshark.

### Pergunta 10

> Quais conceitos desta fonte são mais importantes para um iniciante em Cibersegurança?

---

# 20. Prompt de Estudo

Será utilizado o seguinte prompt no NotebookLM:

```text
Com base exclusivamente nas fontes disponibilizadas neste
notebook, explique os fundamentos de redes de computadores
para um estudante iniciante em Cibersegurança.

Organize a resposta nos seguintes tópicos:

1. Conceito de rede;
2. Dispositivos de rede;
3. Endereço IP;
4. Endereço MAC;
5. Modelo OSI;
6. Modelo TCP/IP;
7. TCP;
8. UDP;
9. DNS;
10. HTTP e HTTPS;
11. Portas;
12. Relação desses conceitos com o Wireshark.

Para cada tópico:
- apresente uma definição;
- explique sua finalidade;
- forneça um exemplo;
- indique como o conceito pode aparecer em uma captura de rede.

Não invente informações que não estejam nas fontes.
Ao final, indique quais fontes foram utilizadas.
```

---

# 21. Pontos para Validação

As informações apresentadas nesta fonte deverão ser confrontadas com outras fontes do projeto.

Especial atenção será dada aos seguintes conceitos:

- funcionamento do TCP;
- diferenças entre TCP e UDP;
- endereçamento IPv4;
- funcionamento do DNS;
- funcionamento das portas;
- camadas do modelo OSI;
- relação entre OSI e TCP/IP;
- interpretação de pacotes no Wireshark.

A validação cruzada é importante para evitar que uma explicação simplificada seja interpretada como uma definição técnica completa.

---

# 22. Resumo da Fonte

Os principais conhecimentos obtidos nesta etapa são:

1. Redes permitem a comunicação entre dispositivos.
2. Diferentes dispositivos possuem funções específicas.
3. Endereços IP são utilizados no endereçamento de redes IP.
4. Endereços MAC são utilizados no contexto da camada de enlace.
5. Protocolos definem regras para a comunicação.
6. O modelo OSI divide as funções de rede em sete camadas.
7. O modelo TCP/IP organiza a arquitetura utilizada nas redes Internet.
8. TCP e UDP possuem características diferentes.
9. DNS permite a resolução de nomes.
10. Portas ajudam a identificar serviços e processos na comunicação.
11. Wireshark permite observar e analisar tráfego de rede.
12. Esses conhecimentos são fundamentais para o estudo de Cibersegurança.

---

# 23. Referência

**Cisco Networking Academy — Networking Basics**

Disponível em:

https://www.netacad.com/courses/networking-basics

**Data de consulta:** 12/08/2026

---

## 📌 Observação

Este arquivo faz parte do projeto:

**Miniguia de Cibersegurança com NotebookLM**

As informações serão complementadas e validadas com as demais fontes selecionadas para o projeto.
