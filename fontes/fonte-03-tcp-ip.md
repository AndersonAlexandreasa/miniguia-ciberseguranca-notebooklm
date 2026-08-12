# Fonte 03 — TCP/IP

## TCP/IP: fundamentos dos protocolos de comunicação em redes

O **TCP/IP** é o conjunto de protocolos utilizado como base para a comunicação em redes modernas e na Internet. Embora o nome destaque os protocolos TCP e IP, a arquitetura envolve diversos outros protocolos, como UDP, ICMP, ARP e protocolos de aplicação.

O RFC 1180 apresenta o TCP/IP como uma arquitetura composta por diferentes protocolos que trabalham em conjunto para transportar informações entre hosts e redes.

## 1. O que é TCP/IP?

TCP/IP significa:

- **TCP — Transmission Control Protocol**
- **IP — Internet Protocol**

Eles desempenham funções diferentes.

O **IP** é responsável principalmente pelo endereçamento e encaminhamento dos datagramas entre hosts e redes.

O **TCP** atua na camada de transporte, fornecendo comunicação orientada à conexão e mecanismos de confiabilidade para aplicações que necessitam de entrega ordenada dos dados.

De forma simplificada:

```text
Aplicação
    ↓
TCP ou UDP
    ↓
IP
    ↓
Ethernet / Wi-Fi
    ↓
Meio físico
```

## 2. Camadas do modelo TCP/IP

A arquitetura TCP/IP pode ser estudada utilizando quatro camadas principais:

```text
┌─────────────────────────────┐
│ Aplicação                   │
│ HTTP, DNS, SSH, FTP, etc.   │
├─────────────────────────────┤
│ Transporte                  │
│ TCP, UDP                    │
├─────────────────────────────┤
│ Internet                    │
│ IP, ICMP                    │
├─────────────────────────────┤
│ Acesso à rede               │
│ Ethernet, Wi-Fi, ARP, etc.  │
└─────────────────────────────┘
```

A arquitetura da Internet utiliza uma organização em camadas. O RFC 1122 descreve as camadas de aplicação, Internet e enlace, enquanto protocolos de transporte como TCP e UDP ficam entre a aplicação e o IP.

### 2.1 Camada de aplicação

É a camada na qual funcionam os protocolos utilizados diretamente pelas aplicações.

Exemplos:

- HTTP;
- HTTPS;
- DNS;
- SSH;
- FTP;
- SMTP.

Quando um usuário acessa um site, por exemplo, o navegador utiliza protocolos da camada de aplicação para solicitar e receber informações.

### 2.2 Camada de transporte

Os principais protocolos são:

- **TCP**
- **UDP**

O TCP oferece mecanismos de comunicação confiável e ordenada.

O UDP possui uma abordagem mais simples, sem estabelecer uma conexão TCP antes do envio dos datagramas.

O RFC 1180 apresenta TCP e UDP como protocolos situados acima do IP na arquitetura TCP/IP.

### 2.3 Camada Internet

O principal protocolo dessa camada é o **IP**.

Sua função inclui permitir que os datagramas sejam endereçados e encaminhados entre diferentes redes.

O IP é um serviço de datagramas sem garantia de entrega fim a fim. A confiabilidade, quando necessária, é fornecida por protocolos superiores, como o TCP.

### 2.4 Camada de acesso à rede

Essa camada está relacionada à transmissão dos dados pela rede local e pelo meio utilizado.

Exemplos:

- Ethernet;
- Wi-Fi;
- ARP.

O RFC 1180 utiliza Ethernet como exemplo de tecnologia de rede sobre a qual os protocolos superiores podem operar.

## 3. Endereçamento IP

O endereço IP identifica uma interface dentro de uma rede IP.

Exemplo de endereço IPv4:

```text
192.168.101.40
```

Uma rede pode ser representada utilizando CIDR:

```text
192.168.101.0/24
```

Nesse exemplo, `/24` indica que os primeiros 24 bits correspondem ao prefixo da rede.

Em um laboratório virtual, por exemplo:

```text
Kali Linux
192.168.101.10/24

       │
       │ Rede virtual
       │
       ▼

Metasploitable 2
192.168.101.40/24
```

Isso permite que as duas máquinas estejam na mesma rede IP e possam trocar tráfego diretamente, dependendo da configuração da rede virtual.

## 4. TCP

O **Transmission Control Protocol (TCP)** é um protocolo de transporte orientado à conexão.

A especificação atual do TCP está consolidada no **RFC 9293**, que substituiu a especificação original do RFC 793 e reúne diversas atualizações posteriores.

O TCP oferece, entre outras características:

- comunicação orientada à conexão;
- transmissão bidirecional;
- entrega ordenada de bytes;
- números de sequência;
- confirmações;
- retransmissão;
- controle de fluxo;
- utilização de portas para identificar serviços.



## 5. Three-way handshake

Antes de transmitir dados em uma conexão TCP, normalmente ocorre o estabelecimento da conexão.

A sequência básica é:

```text
Cliente                         Servidor

   SYN ───────────────────────────►

       ◄──────────────────── SYN, ACK

   ACK ───────────────────────────►

       Conexão estabelecida
```

Os três segmentos principais são:

1. **SYN**
2. **SYN + ACK**
3. **ACK**

Esse processo permite que os dois lados estabeleçam os parâmetros necessários para a comunicação TCP. O RFC 9293 descreve o funcionamento da conexão e da máquina de estados do TCP.

## 6. Portas TCP e UDP

Os números de porta permitem identificar serviços e diferentes fluxos de comunicação.

Exemplos comuns:

| Serviço | Porta comum | Protocolo |
|---|---:|---|
| HTTP | 80 | TCP |
| HTTPS | 443 | TCP |
| SSH | 22 | TCP |
| DNS | 53 | UDP/TCP |
| FTP | 21 | TCP |

A porta não identifica uma máquina. Ela identifica um serviço ou fluxo associado a um host.

Por exemplo:

```text
192.168.101.40:80
```

pode representar um serviço HTTP na máquina `192.168.101.40`.

O TCP utiliza números de porta para identificar serviços de aplicação e multiplexar diferentes fluxos entre hosts.

## 7. UDP

O **User Datagram Protocol (UDP)** é um protocolo de transporte mais simples que o TCP.

Diferentemente do TCP, o UDP não estabelece uma conexão TCP antes de transmitir os datagramas.

Isso pode ser útil quando baixa sobrecarga e rapidez são mais importantes do que mecanismos de confiabilidade fornecidos pelo TCP.

Exemplos de aplicações que podem utilizar UDP incluem determinados tipos de:

- DNS;
- streaming;
- VoIP;
- jogos online;
- serviços de descoberta.

O RFC 1180 apresenta UDP como um dos principais protocolos associados ao conjunto TCP/IP.

## 8. ICMP

O **Internet Control Message Protocol (ICMP)** é utilizado para mensagens de controle e diagnóstico relacionadas ao IP.

Um dos exemplos mais conhecidos é o comando:

```text
ping
```

O ping normalmente utiliza mensagens ICMP para verificar a comunicação entre hosts.

No Wireshark, pode-se utilizar:

```text
icmp
```

como filtro de exibição para visualizar esse tráfego.

O RFC 1122 descreve ICMP como parte integrante da arquitetura IP, incluindo funções relacionadas a notificações de erro e controle.

## 9. ARP

Em redes IPv4 locais, o **ARP — Address Resolution Protocol** é utilizado para relacionar endereços IPv4 a endereços de camada de enlace, como endereços MAC em redes Ethernet.

Um exemplo simplificado:

```text
IP conhecido:
192.168.101.40

        ↓ ARP

MAC correspondente:
XX:XX:XX:XX:XX:XX
```

Em uma captura do Wireshark, pode-se utilizar:

```text
arp
```

para visualizar mensagens ARP.

O tutorial TCP/IP do RFC 1180 apresenta ARP e sua utilização na resolução entre endereços IP e endereços de rede local.

## 10. Encapsulamento

Quando uma aplicação envia dados, cada camada adiciona informações necessárias para que o dado seja transportado.

Exemplo:

```text
Dados da aplicação
       ↓
[ Cabeçalho TCP ][ Dados ]
       ↓
[ Cabeçalho IP ][ TCP ][ Dados ]
       ↓
[ Ethernet ][ IP ][ TCP ][ Dados ]
```

No destino, ocorre o processo inverso, chamado de **desencapsulamento**.

```text
Ethernet
   ↓
IP
   ↓
TCP
   ↓
Aplicação
```

Esse conceito é fundamental para compreender uma captura de pacotes no Wireshark.

## 11. TCP/IP no Wireshark

O conhecimento de TCP/IP é essencial para interpretar uma captura no Wireshark.

Ao selecionar um pacote, normalmente é possível visualizar uma estrutura semelhante a:

```text
Frame
 └── Ethernet
      └── Internet Protocol Version 4
           └── Transmission Control Protocol
                └── Application Protocol
```

Por exemplo, uma comunicação HTTP pode apresentar:

```text
Ethernet
   ↓
IPv4
   ↓
TCP
   ↓
HTTP
```

Isso permite relacionar a teoria das redes com uma comunicação real.

## 12. Exercício prático

Em um laboratório autorizado com Kali Linux, abra o Wireshark e selecione uma interface de rede ativa.

Inicie a captura e gere tráfego utilizando, por exemplo:

```text
ping 192.168.101.40
```

Depois utilize o filtro:

```text
icmp
```

Observe:

- IP de origem;
- IP de destino;
- tipo da mensagem ICMP;
- tamanho do pacote;
- tempo entre os pacotes.

Em seguida, para investigar TCP, utilize:

```text
tcp
```

Procure uma conexão e identifique:

```text
SYN
SYN, ACK
ACK
```

Também é possível utilizar filtros como:

```text
tcp.port == 80
```

ou:

```text
tcp.port == 443
```

para investigar conexões TCP destinadas a determinadas portas.

## 13. TCP/IP e cibersegurança

O conhecimento de TCP/IP é uma das bases para a formação em cibersegurança.

Um analista precisa compreender:

```text
IP
 ↓
Porta
 ↓
Protocolo
 ↓
Serviço
 ↓
Comunicação
```

Isso permite interpretar situações como:

- conexões inesperadas;
- portas abertas;
- retransmissões;
- tráfego anormal;
- comunicação entre hosts;
- consultas DNS;
- conexões com servidores;
- problemas de conectividade.

Ferramentas como Wireshark, Nmap e outros recursos de análise de rede dependem de uma boa compreensão dos protocolos TCP/IP.

## 14. Relação com o laboratório Kali + Metasploitable

No laboratório utilizado para estudos de cibersegurança:

```text
┌──────────────────┐
│    Kali Linux    │
│ 192.168.101.10   │
└────────┬─────────┘
         │
         │ TCP/IP
         │
┌────────▼─────────┐
│  Metasploitable  │
│ 192.168.101.40   │
└──────────────────┘
```

O estudante pode utilizar o Wireshark para observar o tráfego gerado entre as máquinas.

O objetivo não é apenas executar comandos, mas entender **o que acontece na rede quando um comando é executado**.

Por exemplo:

```text
Comando
   ↓
Aplicação
   ↓
TCP/UDP
   ↓
IP
   ↓
Ethernet
   ↓
Rede
```

## 15. Pontos principais para revisão

### TCP

- Orientado à conexão;
- utiliza portas;
- utiliza números de sequência;
- utiliza confirmações;
- permite retransmissão;
- entrega os dados em ordem;
- possui controle de fluxo.

### IP

- fornece endereçamento;
- permite encaminhamento entre redes;
- trabalha com datagramas;
- não fornece, por si só, garantia de entrega fim a fim.

### UDP

- protocolo de transporte;
- não estabelece uma conexão TCP;
- possui menor complexidade;
- utiliza portas.

### ICMP

- utilizado para mensagens de controle e diagnóstico;
- é associado à camada Internet;
- pode ser observado com ferramentas como `ping`.

### ARP

- utilizado em redes IPv4 locais;
- relaciona endereços IP e endereços de enlace, como MAC em Ethernet.

## 16. Fontes oficiais

**RFC 1180 — A TCP/IP Tutorial**  
Tutorial introdutório sobre TCP/IP, Ethernet, ARP, IP e UDP.

[RFC 1180 — A TCP/IP Tutorial](https://www.rfc-editor.org/rfc/rfc1180.html?utm_source=chatgpt.com)

**RFC 9293 — Transmission Control Protocol (TCP)**  
Especificação atual do TCP como Internet Standard.

[RFC 9293 — Transmission Control Protocol](https://www.rfc-editor.org/rfc/rfc9293.html?utm_source=chatgpt.com)

**RFC 791 — Internet Protocol**  
Especificação clássica do IPv4.

[RFC 791 — Internet Protocol](https://www.rfc-editor.org/rfc/rfc791.html?utm_source=chatgpt.com)

**RFC 1122 — Requirements for Internet Hosts**  
Documento que descreve requisitos e organização das camadas da arquitetura Internet.

[RFC 1122 — Requirements for Internet Hosts](https://www.rfc-editor.org/rfc/rfc1122.html?utm_source=chatgpt.com)

## Relação com o projeto

Esta fonte fornece a base conceitual para compreender como os protocolos de rede funcionam.

No **Miniguia de Cibersegurança no NotebookLM**, o conteúdo de TCP/IP pode ser relacionado diretamente à fonte sobre **Wireshark**, permitindo passar do conceito teórico para a análise prática de pacotes.

A sequência de aprendizagem recomendada é:

```text
TCP/IP
  ↓
Endereçamento IP
  ↓
TCP / UDP
  ↓
Portas
  ↓
DNS / HTTP / ICMP
  ↓
Wireshark
  ↓
Análise de pacotes
  ↓
Análise de segurança
```
