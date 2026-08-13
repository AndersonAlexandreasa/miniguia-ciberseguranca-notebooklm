# 🤖 Prompts Reutilizáveis — Mini Guia de Cibersegurança

Coleção de prompts desenvolvidos para utilizar no **NotebookLM** e em outras ferramentas de Inteligência Artificial durante os estudos de redes e cibersegurança.

Os prompts foram organizados para estimular **aprendizagem ativa, análise crítica, revisão e prática**.

---

## 1. 📚 Explicar um conceito

```text
Explique o conceito de [TEMA] para uma pessoa que está começando a estudar cibersegurança.

Use linguagem simples, exemplos práticos e uma analogia do cotidiano.

Depois da explicação:
1. apresente os conceitos mais importantes;
2. explique por que esse conceito é importante;
3. mostre onde ele é utilizado;
4. apresente um exemplo prático;
5. faça 3 perguntas para verificar meu entendimento.
```

**Exemplo:**

```text
Explique o que é TCP para um iniciante em cibersegurança.
```

---

## 2. 🧠 Aprendizagem ativa

```text
Quero aprender [TEMA] por meio de aprendizagem ativa.

Não entregue apenas uma explicação pronta.

Primeiro, faça uma pergunta para descobrir o que eu já sei.
Depois:
1. apresente uma pequena explicação;
2. faça uma pergunta;
3. espere minha resposta;
4. corrija meu entendimento;
5. aumente gradualmente a dificuldade.

Ao final, faça um resumo do que aprendi.
```

---

## 3. 🔍 Analisar uma captura do Wireshark

```text
Analise esta captura de tráfego de rede considerando que sou iniciante em Wireshark.

Explique:
1. IP de origem;
2. IP de destino;
3. protocolo utilizado;
4. portas de origem e destino;
5. tamanho do pacote;
6. flags TCP, quando existirem;
7. possíveis requisições DNS;
8. possíveis requisições HTTP;
9. possíveis erros ou anomalias;
10. o que esse pacote representa na comunicação.

Explique cada item de maneira didática.
```

---

## 4. 🌐 Analisar o TCP/IP

```text
Explique a comunicação abaixo utilizando o modelo TCP/IP:

[DESCREVA A COMUNICAÇÃO]

Identifique:
1. camada de aplicação;
2. camada de transporte;
3. camada de Internet;
4. camada de acesso à rede;
5. protocolos utilizados;
6. endereços IP;
7. portas;
8. sequência de comunicação.

Apresente o resultado em uma sequência passo a passo.
```

---

## 5. 🤝 Entender o Three-Way Handshake

```text
Explique o TCP Three-Way Handshake de forma simples.

Mostre a sequência:

SYN
↓
SYN-ACK
↓
ACK

Para cada etapa explique:
- quem envia;
- quem recebe;
- qual é a finalidade;
- quais informações são transportadas;
- como identificar essa etapa no Wireshark.
```

---

## 6. 🌎 Entender DNS

```text
Explique como funciona uma consulta DNS quando um usuário acessa:

[DOMÍNIO]

Mostre o processo desde a digitação do domínio até a obtenção do endereço IP.

Explique:
1. cliente;
2. resolvedor DNS;
3. servidor DNS;
4. consulta;
5. resposta;
6. endereço IP;
7. porta utilizada;
8. protocolo utilizado.

Depois explique como identificar essa comunicação no Wireshark.
```

---

## 7. 🌐 Entender HTTP

```text
Explique uma comunicação HTTP entre cliente e servidor.

Mostre um exemplo contendo:
- requisição;
- método HTTP;
- URL;
- headers;
- resposta;
- código de status;
- conteúdo retornado.

Depois explique como identificar cada elemento em uma captura do Wireshark.
```

---

## 8. 🔐 Comparar HTTP e HTTPS

```text
Compare HTTP e HTTPS para um iniciante.

Crie uma comparação considerando:

- finalidade;
- porta padrão;
- criptografia;
- segurança;
- TLS;
- exposição dos dados;
- utilização prática;
- identificação no Wireshark.

Finalize explicando por que HTTPS é preferível ao HTTP para comunicações que precisam de proteção.
```

---

## 9. 🛡️ Identificar ameaças

```text
Analise o seguinte cenário de segurança:

[CENÁRIO]

Identifique:
1. possível ameaça;
2. vulnerabilidade envolvida;
3. ativo afetado;
4. impacto;
5. indicadores que poderiam ser observados;
6. medidas preventivas;
7. medidas de detecção;
8. medidas de resposta.

Não ensine técnicas ofensivas contra sistemas reais. Mantenha a análise voltada para ambientes autorizados e defensivos.
```

---

## 10. 🧪 Criar laboratório prático

```text
Crie um laboratório de cibersegurança para iniciantes utilizando:

- Kali Linux;
- Wireshark;
- uma máquina virtual de laboratório;
- uma rede isolada.

Objetivo:

[OBJETIVO]

Forneça:
1. pré-requisitos;
2. configuração da rede;
3. preparação das máquinas;
4. atividade prática;
5. comandos necessários;
6. filtros do Wireshark;
7. resultado esperado;
8. perguntas para análise;
9. possíveis erros;
10. como verificar se o laboratório funcionou.

Utilize somente ambientes próprios ou autorizados.
```

---

## 11. 🧩 Resolver um problema

```text
Estou estudando cibersegurança e encontrei este problema:

[DESCREVA O PROBLEMA]

Não entregue imediatamente a solução.

Primeiro:
1. explique o que pode estar acontecendo;
2. apresente possíveis causas;
3. peça que eu faça uma verificação;
4. analise o resultado;
5. indique o próximo teste;
6. somente depois apresente a solução.

Quero aprender a diagnosticar o problema, e não apenas copiar uma resposta.
```

---

## 12. 📝 Criar perguntas de revisão

```text
Com base nas fontes fornecidas, crie 15 perguntas sobre:

[TEMA]

Distribua as perguntas em:
- 5 fáceis;
- 5 intermediárias;
- 5 avançadas.

Não apresente as respostas inicialmente.

Depois que eu responder, corrija cada questão e explique meus erros.
```

---

## 13. 🎯 Simulado

```text
Crie um simulado de cibersegurança para iniciantes baseado exclusivamente nas fontes fornecidas.

Crie:
- 10 questões de múltipla escolha;
- 5 questões verdadeiro ou falso;
- 5 questões discursivas.

Não mostre o gabarito inicialmente.

Após minhas respostas:
1. corrija;
2. informe minha pontuação;
3. explique os erros;
4. indique quais assuntos preciso revisar.
```

---

## 14. 📖 Resumir uma fonte

```text
Resuma a fonte [NOME DA FONTE].

Organize o resultado em:

1. objetivo da fonte;
2. conceitos principais;
3. termos importantes;
4. exemplos;
5. pontos que precisam de atenção;
6. conhecimentos que devo memorizar;
7. perguntas para revisão.

Não invente informações que não estejam presentes na fonte.
```

---

## 15. 🔗 Relacionar várias fontes

```text
Compare as fontes:

- fonte-01-redes.md
- fonte-02-wireshark.md
- fonte-03-tcp-ip.md
- fonte-04-http-dns.md
- fonte-05-ciberseguranca.md

Identifique:
1. conceitos compartilhados;
2. conceitos complementares;
3. relação entre redes e cibersegurança;
4. relação entre TCP/IP e Wireshark;
5. relação entre HTTP/DNS e análise de tráfego;
6. conhecimentos que formam uma sequência lógica de aprendizado.

Apresente uma visão geral do conhecimento construído pelas fontes.
```

---

## 16. 🧭 Criar trilha de estudos

```text
Com base nas fontes disponíveis, crie uma trilha de estudos para um iniciante em cibersegurança.

Organize na seguinte ordem:

1. fundamentos de redes;
2. TCP/IP;
3. análise de pacotes;
4. Wireshark;
5. DNS;
6. HTTP/HTTPS;
7. conceitos de cibersegurança.

Para cada etapa informe:
- o que estudar;
- por que estudar;
- exercício recomendado;
- conhecimento necessário para avançar.
```

---

## 17. 💡 Explicar com analogias

```text
Explique [TEMA] utilizando uma analogia do cotidiano.

Depois da analogia:
1. explique o conceito técnico correto;
2. mostre onde a analogia funciona;
3. mostre onde ela deixa de ser precisa;
4. apresente um exemplo real de utilização.

O objetivo é facilitar a compreensão sem distorcer o conceito técnico.
```

---

## 18. 🔎 Investigar um termo desconhecido

```text
Encontrei o termo:

[TERMO]

Explique:
1. definição;
2. origem ou significado da sigla;
3. finalidade;
4. como funciona;
5. exemplo;
6. relação com redes;
7. relação com cibersegurança;
8. como identificar esse conceito no Wireshark, quando aplicável.

Utilize linguagem adequada para iniciante.
```

---

## 19. 🧠 Técnica Feynman

```text
Quero estudar [TEMA] utilizando a Técnica Feynman.

Siga estas etapas:

1. explique o conceito de maneira simples;
2. peça para eu explicar o conceito com minhas próprias palavras;
3. identifique erros ou lacunas na minha explicação;
4. explique novamente somente os pontos problemáticos;
5. peça uma nova explicação minha;
6. finalize com um resumo de uma página.

Não aceite respostas vagas.
```

---

## 20. 🚀 Projeto final

```text
Crie um projeto prático de conclusão para um iniciante em cibersegurança utilizando os conhecimentos das fontes disponíveis.

O projeto deve envolver:

- redes;
- TCP/IP;
- Wireshark;
- DNS;
- HTTP/HTTPS;
- análise de tráfego;
- conceitos básicos de segurança.

Defina:
1. objetivo;
2. ambiente;
3. requisitos;
4. etapas;
5. atividades;
6. evidências que devem ser coletadas;
7. perguntas de análise;
8. resultado esperado;
9. critérios para considerar o projeto concluído.

O projeto deve ser realizado exclusivamente em ambiente próprio ou autorizado.
```

---

# 🎓 Prompt Mestre

Este prompt pode ser reutilizado como **prompt principal de estudo**:

```text
Atue como meu tutor de fundamentos de redes e cibersegurança.

Sou iniciante e quero aprender por meio de aprendizagem ativa.

Utilize prioritariamente as fontes fornecidas neste projeto.

Ao explicar qualquer assunto:

1. comece pelo conceito básico;
2. utilize linguagem simples;
3. apresente exemplos práticos;
4. relacione o conceito com redes e cibersegurança;
5. mostre como o conceito pode ser observado em um laboratório;
6. quando aplicável, explique como identificá-lo no Wireshark;
7. destaque termos técnicos importantes;
8. faça perguntas para verificar meu entendimento;
9. não entregue imediatamente a resposta de exercícios;
10. corrija minhas respostas explicando meus erros;
11. diferencie claramente fatos presentes nas fontes de explicações adicionais;
12. não invente informações que não estejam nas fontes.

Sempre incentive raciocínio, investigação e compreensão em vez de simples memorização.

Quando uma atividade envolver segurança ofensiva, mantenha-a restrita a laboratórios, máquinas virtuais e sistemas para os quais exista autorização.
```

---

# 📌 Como reutilizar os prompts

Para usar qualquer prompt, substitua os campos entre colchetes.

Exemplo:

```text
[TEMA]
```

pode ser substituído por:

```text
TCP Three-Way Handshake
```

ou:

```text
Consulta DNS
```

ou:

```text
Análise de pacotes HTTP no Wireshark
```

A coleção pode ser ampliada conforme novos conteúdos forem adicionados ao projeto.
