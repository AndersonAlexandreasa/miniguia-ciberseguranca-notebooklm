# Fonte 05 — Cibersegurança

## Cibersegurança: fundamentos, riscos, proteção e boas práticas

A **cibersegurança** é o conjunto de práticas, processos, tecnologias e controles utilizados para proteger sistemas, redes, aplicações, dispositivos e informações contra ameaças digitais.

Mais do que utilizar ferramentas de segurança, cibersegurança envolve **identificar riscos, proteger recursos, detectar eventos, responder a incidentes e recuperar a operação**.

O **NIST Cybersecurity Framework (CSF) 2.0** fornece uma estrutura para que organizações de diferentes tamanhos e setores compreendam, avaliem, priorizem e comuniquem seus riscos de cibersegurança.

---

## 1. Objetivos da cibersegurança

Um dos conceitos fundamentais da segurança da informação é a **Tríade CIA**:

```text
                 CONFIDENCIALIDADE
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  /          \
        INTEGRIDADE ---------- DISPONIBILIDADE
```

### Confidencialidade

Busca garantir que somente pessoas ou sistemas autorizados tenham acesso às informações.

Exemplos:

- autenticação;
- controle de acesso;
- criptografia;
- gerenciamento de permissões.

### Integridade

Busca garantir que os dados não sejam alterados de forma indevida.

Exemplos:

- hashes;
- assinaturas digitais;
- controles de alteração;
- mecanismos de validação.

### Disponibilidade

Busca garantir que sistemas e informações estejam disponíveis quando necessários.

Exemplos:

- backups;
- redundância;
- monitoramento;
- planos de recuperação;
- proteção contra indisponibilidade.

---

# 2. Segurança não significa apenas impedir ataques

Um sistema seguro precisa trabalhar continuamente com o risco.

Uma visão simplificada é:

```text
Identificar
    ↓
Proteger
    ↓
Detectar
    ↓
Responder
    ↓
Recuperar
    ↓
Melhorar
    ↺
```

O NIST CSF 2.0 utiliza seis funções principais:

- **Govern**
- **Identify**
- **Protect**
- **Detect**
- **Respond**
- **Recover**

A inclusão de **Govern** no CSF 2.0 reforça a importância da governança e do gerenciamento de riscos de cibersegurança.

---

# 3. Governança

A função **Govern** trata de como a organização estabelece, comunica e acompanha sua estratégia de cibersegurança.

Entre os temas relacionados estão:

- políticas de segurança;
- responsabilidades;
- gestão de riscos;
- requisitos legais;
- fornecedores;
- estratégia de segurança;
- avaliação de riscos.

A segurança precisa estar relacionada aos objetivos do negócio.

Por exemplo:

```text
Negócio
   ↓
Ativos importantes
   ↓
Riscos
   ↓
Controles
   ↓
Monitoramento
```

---

# 4. Identificação de ativos

Antes de proteger uma rede, é necessário saber o que existe nela.

Um inventário pode incluir:

- computadores;
- servidores;
- roteadores;
- switches;
- dispositivos móveis;
- máquinas virtuais;
- aplicações;
- bancos de dados;
- contas;
- serviços;
- informações importantes.

Exemplo:

```text
REDE
│
├── Servidor Web
├── Servidor DNS
├── Banco de Dados
├── Estações
├── Roteador
└── Dispositivos IoT
```

Sem conhecer os ativos, torna-se muito mais difícil identificar riscos.

---

# 5. Vulnerabilidade, ameaça e risco

Esses conceitos são diferentes.

### Vulnerabilidade

É uma fraqueza que pode ser explorada.

Exemplo:

```text
Servidor desatualizado
```

### Ameaça

É algo capaz de explorar uma vulnerabilidade ou causar impacto.

Exemplo:

```text
Atacante
```

### Risco

É a possibilidade de uma ameaça explorar uma vulnerabilidade e produzir consequências.

Uma representação simplificada:

```text
Ameaça
   +
Vulnerabilidade
   +
Impacto
   ↓
Risco
```

O risco deve ser analisado considerando fatores como probabilidade, impacto e contexto.

---

# 6. Principais ameaças

Entre as ameaças que podem afetar ambientes digitais estão:

- malware;
- ransomware;
- phishing;
- engenharia social;
- roubo de credenciais;
- exploração de vulnerabilidades;
- ataques de negação de serviço;
- comprometimento de contas;
- vazamento de informações;
- ataques à cadeia de suprimentos.

A existência de uma ameaça não significa automaticamente que um incidente ocorrerá. A análise de risco deve considerar as características específicas do ambiente.

---

# 7. Malware

**Malware** é um termo utilizado para descrever software malicioso.

Alguns exemplos:

- vírus;
- worms;
- trojans;
- ransomware;
- spyware;
- rootkits.

O comportamento pode variar de acordo com o tipo de malware.

Por isso, mecanismos de proteção devem combinar diferentes estratégias, como:

```text
Prevenção
   ↓
Detecção
   ↓
Análise
   ↓
Resposta
```

---

# 8. Phishing e engenharia social

Nem todos os ataques dependem de explorar diretamente uma vulnerabilidade técnica.

Na **engenharia social**, o atacante pode tentar manipular uma pessoa para obter:

- credenciais;
- informações;
- acesso;
- execução de ações;
- instalação de software.

O phishing é um exemplo conhecido.

Um fluxo típico pode ser:

```text
Mensagem falsa
      ↓
Usuário acessa um link
      ↓
Página falsa
      ↓
Usuário fornece credenciais
      ↓
Credenciais comprometidas
```

Por isso, treinamento e conscientização dos usuários são componentes importantes da segurança.

---

# 9. Autenticação

A autenticação responde à pergunta:

> **Quem é você?**

Exemplos de mecanismos:

- senha;
- certificado digital;
- token;
- biometria;
- autenticação multifator.

A autenticação multifator pode combinar diferentes categorias de fatores.

Por exemplo:

```text
Senha
 +
Código temporário
 =
Autenticação multifator
```

É importante diferenciar **autenticação** de **autorização**.

### Autenticação

Confirma a identidade.

### Autorização

Determina o que aquela identidade pode acessar.

```text
Usuário
   ↓
Autenticação
   ↓
Identidade confirmada
   ↓
Autorização
   ↓
Permissões
```

---

# 10. Controle de acesso

O princípio do **menor privilégio** recomenda conceder somente as permissões necessárias para realizar determinada atividade.

Exemplo:

```text
Usuário comum
   ↓
Acesso somente aos recursos necessários
```

Em vez de:

```text
Usuário comum
   ↓
Privilégios administrativos completos
```

O controle de acesso inadequado é uma preocupação importante em aplicações web. Na edição **OWASP Top 10:2025**, "Broken Access Control" aparece como a categoria A01.

---

# 11. Criptografia

A criptografia utiliza técnicas matemáticas para proteger informações.

Ela pode contribuir para:

- confidencialidade;
- integridade;
- autenticação;
- não repúdio, dependendo do mecanismo utilizado.

Exemplo conceitual:

```text
Mensagem original
       ↓
   Criptografia
       ↓
Mensagem protegida
       ↓
   Descriptografia
       ↓
Mensagem original
```

É importante diferenciar:

### Criptografia

Protege informações utilizando algoritmos e chaves.

### Hash

Produz uma representação de tamanho definido a partir de uma entrada, sendo muito utilizado para verificação de integridade e outros mecanismos de segurança.

---

# 12. Segurança de redes

A segurança de redes busca proteger a comunicação e os recursos conectados.

Alguns mecanismos importantes são:

- firewall;
- segmentação de rede;
- VPN;
- IDS;
- IPS;
- monitoramento;
- controle de acesso;
- análise de tráfego.

Uma arquitetura simples pode ser:

```text
Internet
   │
Firewall
   │
   ├──────── DMZ
   │
Rede interna
   │
   ├── Servidores
   ├── Estações
   └── Dispositivos
```

A segmentação pode limitar a propagação de um incidente entre diferentes partes da infraestrutura.

---

# 13. Firewall

Um firewall controla o tráfego de rede de acordo com regras definidas.

Exemplo conceitual:

```text
Internet
   ↓
Firewall
   │
   ├── Porta permitida → SERVIÇO
   │
   └── Porta bloqueada → DESCARTADA
```

As regras podem considerar:

- endereço IP;
- porta;
- protocolo;
- interface;
- origem;
- destino;
- estado da conexão.

---

# 14. IDS e IPS

### IDS — Intrusion Detection System

Um IDS procura identificar atividades potencialmente suspeitas.

```text
Tráfego
   ↓
IDS
   ↓
Análise
   ↓
Alerta
```

### IPS — Intrusion Prevention System

Um IPS pode atuar de forma preventiva, bloqueando ou interrompendo determinados tráfegos de acordo com suas regras e capacidades.

```text
Tráfego
   ↓
IPS
   ↓
Análise
   ↓
Permitido / Bloqueado
```

---

# 15. Segurança de aplicações

Aplicações web possuem riscos específicos.

O **OWASP Top 10:2025** é uma referência de conscientização para os principais riscos de segurança de aplicações web. A versão atual apresenta dez categorias.

As categorias do OWASP Top 10:2025 são:

1. **A01 — Broken Access Control**
2. **A02 — Security Misconfiguration**
3. **A03 — Software Supply Chain Failures**
4. **A04 — Cryptographic Failures**
5. **A05 — Injection**
6. **A06 — Insecure Design**
7. **A07 — Authentication Failures**
8. **A08 — Software or Data Integrity Failures**
9. **A09 — Security Logging & Alerting Failures**
10. **A10 — Mishandling of Exceptional Conditions**



Essas categorias ajudam desenvolvedores e profissionais de segurança a compreender riscos comuns durante o desenvolvimento e a avaliação de aplicações.

---

# 16. Injeção

Uma vulnerabilidade de **injeção** pode ocorrer quando dados não confiáveis são interpretados de maneira inadequada por um sistema.

Exemplos conceituais incluem:

- SQL Injection;
- Command Injection;
- LDAP Injection;
- outras formas de injeção.

Uma forma simplificada de compreender o problema:

```text
Entrada do usuário
       ↓
Aplicação
       ↓
Interpretador
       ↓
Comando/consulta manipulada
```

Aplicações devem validar entradas, utilizar mecanismos seguros de acesso a dados e evitar construir comandos de forma insegura.

A categoria Injection aparece como **A05:2025** no OWASP Top 10:2025.

---

# 17. Configuração segura

Configurações inadequadas podem aumentar a superfície de ataque.

Exemplos:

- senhas padrão;
- serviços desnecessários ativos;
- permissões excessivas;
- mensagens de erro muito detalhadas;
- componentes desatualizados;
- portas desnecessariamente expostas.

Uma boa prática é:

```text
Instalar
   ↓
Configurar
   ↓
Remover serviços desnecessários
   ↓
Aplicar atualizações
   ↓
Testar
   ↓
Monitorar
```

A **Security Misconfiguration** aparece como A02 no OWASP Top 10:2025.

---

# 18. Atualizações e gerenciamento de vulnerabilidades

Softwares podem apresentar vulnerabilidades conhecidas.

Por isso, é importante manter:

- sistema operacional;
- aplicações;
- bibliotecas;
- firmware;
- ferramentas de segurança

atualizados de acordo com uma política adequada.

O processo pode ser:

```text
Identificar ativos
      ↓
Identificar versões
      ↓
Verificar vulnerabilidades
      ↓
Avaliar risco
      ↓
Priorizar correções
      ↓
Atualizar
      ↓
Validar
```

Nem toda vulnerabilidade possui o mesmo impacto. A prioridade deve considerar o contexto e o risco do ativo.

---

# 19. Logs e monitoramento

Os **logs** registram eventos que podem ser utilizados para investigação e monitoramento.

Exemplos:

- login;
- logout;
- falha de autenticação;
- alteração de configuração;
- acesso a arquivos;
- conexões de rede;
- erros de aplicação.

Um sistema de segurança pode utilizar:

```text
Eventos
   ↓
Logs
   ↓
Coleta
   ↓
Correlação
   ↓
Alertas
   ↓
Investigação
```

O OWASP Top 10:2025 inclui **Security Logging & Alerting Failures** como A09, reforçando a importância do registro e alerta de eventos relevantes.

---

# 20. Resposta a incidentes

Um incidente de segurança exige uma resposta organizada.

Um fluxo simplificado:

```text
Detectar
   ↓
Analisar
   ↓
Conter
   ↓
Erradicar
   ↓
Recuperar
   ↓
Aprender
```

### Detectar

Identificar que algo anormal ocorreu.

### Analisar

Determinar o que aconteceu e qual é o impacto.

### Conter

Limitar a propagação ou o impacto.

### Erradicar

Eliminar a causa ou presença do problema.

### Recuperar

Restaurar os serviços de forma segura.

### Aprender

Registrar as lições aprendidas e melhorar os controles.

---

# 21. Backup

Backups são fundamentais para recuperação após incidentes.

Um backup deve ser:

- planejado;
- testado;
- protegido;
- monitorado;
- recuperável.

Um conceito importante é manter cópias que não sejam facilmente comprometidas pelo mesmo incidente que afeta os sistemas principais.

Exemplo:

```text
Sistema principal
       │
       ├──── Backup local
       │
       └──── Backup separado
```

O backup não deve ser considerado seguro simplesmente porque existe. É necessário testar a restauração.

---

# 22. Cibersegurança e Wireshark

O Wireshark pode ser utilizado para estudar o comportamento da rede.

Em um laboratório autorizado:

```text
Rede
 ↓
Captura
 ↓
Wireshark
 ↓
Análise
 ↓
Identificação de comportamento
```

O estudante pode observar:

- IPs;
- portas;
- protocolos;
- DNS;
- TCP;
- HTTP;
- retransmissões;
- conexões entre máquinas.

Isso conecta diretamente esta fonte às fontes anteriores do projeto.

---

# 23. Cibersegurança e TCP/IP

O conhecimento de TCP/IP permite interpretar o tráfego observado.

Por exemplo:

```text
IP
 ↓
192.168.101.40

Porta
 ↓
80

Protocolo
 ↓
TCP

Aplicação
 ↓
HTTP
```

Um analista consegue então relacionar:

```text
Host
 +
Porta
 +
Protocolo
 +
Serviço
 =
Comunicação
```

Essa capacidade é fundamental para análise de redes.

---

# 24. Laboratório seguro

Para estudar cibersegurança de maneira prática, recomenda-se utilizar ambientes controlados.

Exemplo:

```text
┌────────────────────┐
│     Kali Linux     │
│ 192.168.101.10     │
└─────────┬──────────┘
          │
          │ Rede virtual
          │
┌─────────▼──────────┐
│   Metasploitable   │
│ 192.168.101.40     │
└────────────────────┘
```

O ambiente deve estar isolado de sistemas que não fazem parte do laboratório.

O objetivo é permitir que o estudante pratique:

- identificação de ativos;
- análise de portas;
- captura de tráfego;
- análise de protocolos;
- identificação de vulnerabilidades;
- aplicação de controles;
- documentação dos resultados.

---

# 25. Ética e autorização

O conhecimento de cibersegurança deve ser aplicado de forma responsável.

Antes de realizar qualquer teste, é necessário possuir autorização adequada.

Uma regra simples:

```text
Meu sistema?
      ↓
Posso testar.

Laboratório autorizado?
      ↓
Posso testar conforme as regras.

Sistema de terceiros sem autorização?
      ↓
Não realizar testes.
```

Ferramentas de segurança podem ser utilizadas tanto para defesa quanto para atividades ofensivas. O fator determinante é o contexto, a autorização e a finalidade.

---

# 26. Modelo de defesa em camadas

Não existe uma única ferramenta capaz de proteger completamente um ambiente.

Uma estratégia de defesa pode utilizar várias camadas:

```text
                 INTERNET
                    │
                 Firewall
                    │
              IDS / IPS
                    │
              Segmentação
                    │
              Servidores
                    │
        ┌───────────┴───────────┐
      Logs                    Backup
        │                        │
        └──────────┬─────────────┘
                   │
             Monitoramento
```

Essa abordagem é conhecida como **defesa em profundidade**.

A ideia é evitar que a falha de um único controle resulte automaticamente no comprometimento de todo o ambiente.

---

# 27. Checklist básico de segurança

- [ ] Inventariar ativos.
- [ ] Identificar sistemas e serviços.
- [ ] Aplicar atualizações.
- [ ] Utilizar autenticação adequada.
- [ ] Aplicar menor privilégio.
- [ ] Configurar firewall.
- [ ] Segmentar a rede quando apropriado.
- [ ] Proteger informações sensíveis.
- [ ] Monitorar eventos.
- [ ] Manter backups.
- [ ] Testar restauração.
- [ ] Criar procedimentos de resposta a incidentes.
- [ ] Realizar treinamento de usuários.
- [ ] Avaliar vulnerabilidades.
- [ ] Documentar riscos e controles.

---

# 28. Exercício prático para o projeto

No laboratório Kali Linux + Metasploitable, o estudante pode realizar uma atividade integrando as fontes anteriores.

### Etapa 1 — Identificação

Identificar as máquinas existentes no laboratório.

```text
Kali
   ↓
Rede
   ↓
Metasploitable
```

### Etapa 2 — Serviços

Identificar serviços disponíveis no ambiente autorizado.

### Etapa 3 — Wireshark

Capturar o tráfego gerado durante uma atividade controlada.

### Etapa 4 — TCP/IP

Identificar:

- IP de origem;
- IP de destino;
- protocolo;
- porta.

### Etapa 5 — DNS/HTTP

Observar consultas DNS e tráfego HTTP quando disponíveis.

### Etapa 6 — Segurança

Perguntar:

> Qual ativo está sendo acessado?

> Qual serviço está sendo utilizado?

> Existe alguma configuração que poderia aumentar o risco?

> Que controle poderia reduzir esse risco?

### Etapa 7 — Documentação

Registrar:

```text
Ativo
 ↓
Serviço
 ↓
Risco
 ↓
Impacto
 ↓
Controle
 ↓
Resultado
```

---

# 29. Relação com as fontes anteriores

O conteúdo desta fonte funciona como uma integração dos conhecimentos estudados anteriormente:

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
   ↓
Fonte 05
Cibersegurança
```

A evolução do conhecimento pode ser representada assim:

```text
REDES
  ↓
COMUNICAÇÃO
  ↓
PROTOCOLOS
  ↓
TCP/IP
  ↓
HTTP + DNS
  ↓
WIRESHARK
  ↓
ANÁLISE
  ↓
IDENTIFICAÇÃO DE RISCOS
  ↓
PROTEÇÃO
  ↓
DETECÇÃO
  ↓
RESPOSTA
```

---

# 30. Fontes oficiais recomendadas

### NIST Cybersecurity Framework 2.0

O **NIST CSF 2.0** fornece uma estrutura para gerenciamento de riscos de cibersegurança e pode ser utilizada por organizações de diferentes tamanhos, setores e níveis de maturidade.

[NIST Cybersecurity Framework 2.0](https://csrc.nist.gov/pubs/cswp/29/the-nist-cybersecurity-framework-csf-20/final?utm_source=chatgpt.com)

### NIST — Quick-Start Guide 2026

Em março de 2026, o NIST publicou novos guias rápidos relacionados ao CSF 2.0, incluindo orientações sobre integração entre cibersegurança, gerenciamento de riscos corporativos e força de trabalho.

[NIST SP 1308 — CSF 2.0 Quick-Start Guide](https://csrc.nist.gov/pubs/sp/1308/final?utm_source=chatgpt.com)

### OWASP Top 10:2025

O **OWASP Top 10:2025** apresenta as dez categorias de riscos mais importantes para conscientização sobre segurança de aplicações web.

[OWASP Top 10:2025](https://owasp.org/Top10/?utm_source=chatgpt.com)

---

# Relação com o projeto

Esta fonte representa a transição dos conhecimentos de **redes e protocolos** para a área de **cibersegurança**.

O estudante começa entendendo como uma rede funciona, aprende a observar pacotes com o Wireshark, compreende TCP/IP, DNS e HTTP e, posteriormente, passa a analisar esses conhecimentos sob a perspectiva de segurança.

A principal ideia é:

```text
ENTENDER A REDE
       ↓
OBSERVAR A REDE
       ↓
IDENTIFICAR RISCOS
       ↓
PROTEGER
       ↓
DETECTAR
       ↓
RESPONDER
       ↓
RECUPERAR
```

Esse conhecimento forma uma base importante para continuar os estudos em áreas como **segurança de redes, SOC, Blue Team, análise de vulnerabilidades, segurança de aplicações, resposta a incidentes e testes de segurança autorizados**.
