# Fonte 02 — Wireshark

## Wireshark: análise e captura de tráfego de rede

O **Wireshark** é um analisador de protocolos de rede utilizado para capturar, visualizar e analisar pacotes que trafegam por uma interface de rede. Ele é amplamente utilizado em atividades de administração de redes, troubleshooting, análise de protocolos e estudos de cibersegurança.

Para este projeto, o Wireshark será utilizado como fonte de conhecimento para compreender como os dados são transportados em uma rede e como um analista pode identificar informações como endereços IP, portas, protocolos, consultas DNS, conexões TCP e requisições HTTP em ambientes de laboratório.

### 1. O que é possível analisar

Durante uma captura, o Wireshark permite observar diferentes camadas e protocolos da comunicação, incluindo:

- Endereço IP de origem e destino;
- Endereços MAC;
- Protocolos TCP e UDP;
- Portas de comunicação;
- Consultas e respostas DNS;
- Handshake TCP;
- Comunicação HTTP;
- Comunicação TLS;
- Retransmissões TCP;
- Erros e comportamentos anormais de rede;
- Conversações entre hosts;
- Estatísticas dos protocolos capturados.

A documentação oficial do Wireshark apresenta recursos para análise de protocolos, conversações, endpoints e estatísticas de tráfego.

### 2. Captura de pacotes

A captura começa selecionando uma interface de rede ativa, como Ethernet ou Wi-Fi, e iniciando a captura.

Durante o processo, o Wireshark registra os pacotes observados pela interface selecionada. O arquivo de captura pode posteriormente ser salvo para análise, permitindo repetir a investigação sem precisar capturar novamente o tráfego.

Para estudos de cibersegurança, recomenda-se utilizar redes próprias ou ambientes de laboratório autorizados.

### 3. Filtros de análise

Um dos recursos mais importantes do Wireshark são os filtros.

Existem dois conceitos que precisam ser diferenciados:

**Capture Filter**

É utilizado durante a captura para limitar os pacotes que serão registrados.

Exemplo:

```text
tcp port 80
```

**Display Filter**

É utilizado depois que os pacotes foram capturados para selecionar quais deles serão exibidos na tela.

Exemplos:

```text
ip
```

```text
dns
```

```text
http
```

```text
tcp
```

```text
icmp
```

```text
ip.addr == 192.168.1.10
```

```text
tcp.analysis.retransmission
```

A documentação do Wireshark destaca que filtros de captura e filtros de exibição possuem sintaxes e finalidades diferentes.

### 4. Identificação de IPs

Para estudar a comunicação entre máquinas, o analista pode utilizar:

```text
ip
```

Depois de selecionar um pacote, os campos de origem e destino podem ser observados na camada IPv4 ou IPv6.

Também é possível utilizar:

```text
ip.src
```

para analisar endereços de origem e:

```text
ip.dst
```

para analisar endereços de destino.

Para investigar um host específico:

```text
ip.addr == 192.168.101.40
```

O endereço deve ser substituído pelo IP utilizado no laboratório.

### 5. Análise de TCP

O protocolo TCP utiliza um processo conhecido como **three-way handshake** para estabelecer uma conexão.

A sequência normalmente observada é:

```text
SYN
   ↓
SYN, ACK
   ↓
ACK
```

No Wireshark, o filtro:

```text
tcp
```

permite visualizar o tráfego TCP.

Também é possível pesquisar retransmissões utilizando:

```text
tcp.analysis.retransmission
```

Esse tipo de análise pode auxiliar na investigação de problemas de conectividade e desempenho.

### 6. Análise de DNS

O DNS é utilizado para resolver nomes de domínio em endereços IP.

Para visualizar consultas DNS:

```text
dns
```

Durante uma análise, pode-se observar:

```text
Cliente → Servidor DNS
```

e posteriormente:

```text
Servidor DNS → Cliente
```

Isso permite estudar o relacionamento entre nomes de domínio e endereços IP.

### 7. Análise de HTTP

Em um laboratório controlado que utilize HTTP, o filtro:

```text
http
```

pode ser utilizado para localizar requisições e respostas HTTP.

É possível analisar informações como:

- método HTTP;
- host;
- URI;
- código de resposta;
- versão HTTP;
- cabeçalhos;
- conteúdo transmitido, quando disponível.

O Wireshark possui recursos específicos para estatísticas e análise de requisições HTTP.

**Importante:** HTTP e HTTPS não devem ser tratados da mesma maneira. Em HTTPS, o conteúdo da aplicação normalmente está protegido por TLS, portanto não se deve esperar visualizar o conteúdo HTTP em texto aberto apenas filtrando a porta 443.

### 8. Follow TCP Stream

O recurso **Follow TCP Stream** permite visualizar os dados pertencentes a uma determinada comunicação TCP.

O procedimento básico é:

1. Selecionar um pacote TCP;
2. Clicar com o botão direito;
3. Selecionar **Follow → TCP Stream**;
4. Observar a comunicação associada à conexão.

A documentação do Wireshark descreve esse recurso como uma forma de acompanhar o fluxo de uma conexão e aplicar automaticamente um filtro correspondente ao fluxo selecionado.

### 9. Estatísticas

O Wireshark também disponibiliza ferramentas estatísticas para compreender o tráfego capturado.

Entre os recursos estão:

- Protocol Hierarchy;
- Conversations;
- Endpoints;
- estatísticas IPv4;
- estatísticas IPv6;
- estatísticas HTTP;
- gráficos e informações relacionadas ao TCP.

Esses recursos podem ajudar o analista a identificar quais protocolos estão presentes e quais hosts estão participando da comunicação.

### 10. Aplicação no estudo de cibersegurança

O Wireshark é especialmente útil para desenvolver a capacidade de observar uma comunicação de rede em nível de pacotes.

Em um laboratório autorizado, o estudante pode praticar:

```text
Capturar pacotes
      ↓
Identificar protocolos
      ↓
Identificar IPs
      ↓
Identificar portas
      ↓
Analisar DNS
      ↓
Analisar TCP
      ↓
Analisar HTTP
      ↓
Identificar anomalias
```

Esse processo ajuda a desenvolver conhecimentos importantes para áreas como:

- análise de redes;
- Blue Team;
- SOC;
- Network Security;
- resposta a incidentes;
- troubleshooting;
- análise de tráfego;
- detecção de comportamentos suspeitos.

### 11. Laboratório sugerido

Para fins educacionais, recomenda-se realizar os experimentos em uma rede virtual própria, como um laboratório utilizando **Kali Linux e Metasploitable 2**.

Exemplo de laboratório:

```text
Kali Linux
192.168.101.10
      │
      │ Rede virtual
      │
      ▼
Metasploitable 2
192.168.101.40
```

No Kali Linux, o Wireshark pode ser utilizado para observar o tráfego gerado durante atividades controladas.

Exemplos de exercícios:

1. Identificar o endereço IP da máquina;
2. Capturar tráfego ICMP;
3. Identificar um ping;
4. Observar o handshake TCP;
5. Identificar portas TCP;
6. Capturar consultas DNS;
7. Analisar tráfego HTTP em laboratório;
8. Identificar retransmissões;
9. Utilizar **Follow TCP Stream**;
10. Consultar estatísticas da captura.

### 12. Boas práticas

A captura de tráfego pode revelar informações potencialmente sensíveis. Por isso, as atividades devem ser realizadas somente em redes, máquinas e ambientes para os quais exista autorização.

Para o projeto, recomenda-se utilizar:

- máquinas virtuais;
- redes isoladas;
- tráfego gerado pelo próprio estudante;
- arquivos `.pcap` ou `.pcapng` de treinamento;
- sistemas deliberadamente vulneráveis destinados a laboratório.

### Fonte oficial

A principal referência utilizada neste tópico é a documentação oficial do Wireshark:

[Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html/index.html?utm_source=chatgpt.com)

[Wireshark Documentation](https://www.wireshark.org/docs/?utm_source=chatgpt.com)

### Relação com o projeto

Esta fonte contribui para o **Miniguia de Cibersegurança no NotebookLM** ao fornecer fundamentos práticos para análise de tráfego de rede.

O conhecimento desta ferramenta permite ao estudante relacionar conceitos teóricos de redes — como IP, TCP, UDP, DNS e HTTP — com pacotes reais observados durante uma captura.
