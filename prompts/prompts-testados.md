# 🧪 Prompts Testados — Mini Guia de Cibersegurança

Este arquivo registra prompts utilizados durante o desenvolvimento e estudo do projeto **Mini Guia de Cibersegurança com NotebookLM**.

O objetivo é documentar quais abordagens foram utilizadas, para que serviram e quais resultados podem ser esperados.

---

## 1. 📚 Explicação para iniciantes

### Prompt

```text
Explique o conceito de [TEMA] para uma pessoa que está começando a estudar cibersegurança.

Utilize linguagem simples, exemplos práticos e analogias.

Depois:
1. explique o conceito;
2. apresente os principais pontos;
3. mostre um exemplo;
4. explique sua importância;
5. faça 3 perguntas para verificar meu entendimento.

Baseie a resposta nas fontes fornecidas.
```

### Objetivo

Utilizado para transformar conceitos técnicos em explicações adequadas para iniciantes.

### Resultado esperado

Uma explicação organizada, com exemplos e perguntas para reforçar a aprendizagem.

---

# 2. 🦈 Análise de tráfego no Wireshark

### Prompt

```text
Analise esta captura de rede como um instrutor de redes.

Sou iniciante em Wireshark.

Identifique:
- IP de origem;
- IP de destino;
- protocolo;
- porta de origem;
- porta de destino;
- flags TCP;
- possíveis consultas DNS;
- possíveis requisições HTTP;
- possíveis respostas;
- erros ou comportamentos incomuns.

Explique o significado de cada informação encontrada.
```

### Objetivo

Aprender a interpretar uma captura de pacotes.

### Resultado esperado

Identificação dos principais elementos de uma comunicação de rede.

---

# 3. 🤝 TCP Three-Way Handshake

### Prompt

```text
Explique o TCP Three-Way Handshake utilizando uma sequência simples:

SYN
SYN-ACK
ACK

Para cada pacote explique:
- quem envia;
- quem recebe;
- finalidade;
- significado da flag;
- como localizar o pacote no Wireshark.

Depois faça uma pergunta para verificar meu entendimento.
```

### Objetivo

Relacionar o conceito teórico do TCP com uma captura real.

### Resultado esperado

Compreensão do estabelecimento de uma conexão TCP.

---

# 4. 🌎 Análise de DNS

### Prompt

```text
Explique o processo de resolução DNS quando um usuário digita um endereço de site no navegador.

Mostre:
1. cliente;
2. consulta DNS;
3. servidor DNS;
4. resposta;
5. endereço IP;
6. comunicação posterior.

Depois explique como identificar essa comunicação no Wireshark.
```

### Objetivo

Entender como nomes de domínio são utilizados na comunicação de rede.

### Resultado esperado

Compreensão da relação entre domínio, DNS e endereço IP.

---

# 5. 🌐 Análise de HTTP

### Prompt

```text
Explique uma comunicação HTTP entre cliente e servidor.

Mostre:
- requisição;
- método;
- URL;
- headers;
- resposta;
- código de status.

Depois explique como localizar esses elementos em uma captura do Wireshark.
```

### Objetivo

Compreender o funcionamento básico do protocolo HTTP.

### Resultado esperado

Identificação de requisições e respostas HTTP.

---

# 6. 🔐 HTTP x HTTPS

### Prompt

```text
Compare HTTP e HTTPS.

Explique:
- finalidade;
- porta padrão;
- criptografia;
- TLS;
- segurança;
- exposição dos dados;
- utilização prática;
- identificação no Wireshark.

Finalize com uma explicação simples para um iniciante.
```

### Objetivo

Entender a importância da proteção criptográfica nas comunicações Web.

### Resultado esperado

Compreensão da diferença entre HTTP e HTTPS.

---

# 7. 🧠 Aprendizagem ativa

### Prompt

```text
Quero estudar [TEMA] por aprendizagem ativa.

Não me dê a resposta completa inicialmente.

Faça uma pergunta para descobrir o que eu já sei.

Depois:
1. apresente uma pequena explicação;
2. faça uma nova pergunta;
3. aguarde minha resposta;
4. corrija meu raciocínio;
5. explique meus erros;
6. aumente gradualmente a dificuldade.

No final, faça um resumo do que aprendi.
```

### Objetivo

Evitar aprendizado puramente passivo.

### Resultado esperado

Maior participação do estudante durante o processo de aprendizagem.

---

# 8. 🧩 Diagnóstico de problemas

### Prompt

```text
Estou realizando um laboratório de redes e encontrei este problema:

[DESCREVA O PROBLEMA]

Não entregue a solução imediatamente.

Ajude-me a investigar seguindo uma sequência:

1. identificar o sintoma;
2. levantar possíveis causas;
3. escolher um teste;
4. analisar o resultado;
5. formular uma nova hipótese;
6. testar novamente;
7. apresentar a solução.

Quero aprender o processo de diagnóstico.
```

### Objetivo

Desenvolver capacidade de troubleshooting.

### Resultado esperado

Aprender a investigar problemas em vez de apenas copiar comandos.

---

# 9. 🧪 Laboratório prático

### Prompt

```text
Crie um exercício prático de cibersegurança para iniciante utilizando um laboratório isolado.

Ferramentas disponíveis:
- Kali Linux;
- Wireshark;
- máquina virtual de laboratório.

Tema:
[TEMA]

Forneça:
1. objetivo;
2. preparação;
3. configuração;
4. atividade;
5. comandos;
6. filtros do Wireshark;
7. resultado esperado;
8. perguntas;
9. erros comuns;
10. solução dos erros.

O exercício deve ser realizado somente em sistemas próprios ou autorizados.
```

### Objetivo

Transformar conhecimento teórico em prática.

### Resultado esperado

Um exercício reproduzível em laboratório controlado.

---

# 10. 📝 Criar questões

### Prompt

```text
Crie 10 perguntas sobre [TEMA] com base nas fontes fornecidas.

Distribua em:
- 3 fáceis;
- 4 intermediárias;
- 3 avançadas.

Não apresente as respostas.

Depois que eu responder, corrija cada questão e explique meus erros.
```

### Objetivo

Testar conhecimento.

### Resultado esperado

Identificação de pontos fortes e assuntos que precisam de revisão.

---

# 11. 🎯 Simulado

### Prompt

```text
Crie um simulado sobre fundamentos de redes e cibersegurança.

Utilize somente as fontes fornecidas.

Crie:
- 10 questões de múltipla escolha;
- 5 questões verdadeiro ou falso;
- 5 questões discursivas.

Não mostre o gabarito.

Depois que eu responder:
1. corrija;
2. calcule minha pontuação;
3. explique os erros;
4. indique quais assuntos devo revisar.
```

### Objetivo

Avaliar o conhecimento adquirido.

### Resultado esperado

Uma avaliação estruturada do aprendizado.

---

# 12. 📖 Resumo de fonte

### Prompt

```text
Resuma a fonte [NOME].

Organize em:

1. objetivo;
2. conceitos principais;
3. termos técnicos;
4. exemplos;
5. pontos importantes;
6. conceitos que precisam ser memorizados;
7. perguntas para revisão.

Não invente informações que não estejam presentes na fonte.
```

### Objetivo

Facilitar a revisão dos materiais.

### Resultado esperado

Um resumo organizado e baseado no conteúdo fornecido.

---

# 13. 🔗 Comparação entre fontes

### Prompt

```text
Compare as seguintes fontes:

fonte-01-redes.md
fonte-02-wireshark.md
fonte-03-tcp-ip.md
fonte-04-http-dns.md
fonte-05-ciberseguranca.md

Identifique:
- conceitos em comum;
- conceitos complementares;
- diferenças;
- relações entre os assuntos;
- sequência lógica de aprendizado.

Mostre como os conhecimentos das fontes se conectam.
```

### Objetivo

Perceber a relação entre os diferentes conteúdos do projeto.

### Resultado esperado

Uma visão integrada do conhecimento estudado.

---

# 14. 🧠 Técnica Feynman

### Prompt

```text
Utilize a Técnica Feynman para me ensinar [TEMA].

Primeiro explique o conceito de forma simples.

Depois peça para eu explicar o assunto com minhas próprias palavras.

Analise minha explicação e identifique:
- erros;
- conceitos incompletos;
- confusões;
- informações desnecessárias.

Depois explique novamente os pontos problemáticos e peça uma nova explicação.
```

### Objetivo

Verificar se o estudante realmente compreendeu o assunto.

### Resultado esperado

Identificação de lacunas de conhecimento.

---

# 15. 💡 Explicação por analogia

### Prompt

```text
Explique [TEMA] utilizando uma analogia do cotidiano.

Depois:
1. explique o conceito técnico;
2. compare a analogia com o funcionamento real;
3. indique onde a analogia é útil;
4. indique onde ela pode gerar confusão;
5. apresente um exemplo técnico.

Mantenha precisão técnica.
```

### Objetivo

Facilitar a compreensão de conceitos abstratos.

### Resultado esperado

Maior facilidade para visualizar conceitos técnicos.

---

# 16. 🛡️ Análise de ameaça

### Prompt

```text
Analise o seguinte cenário:

[CENÁRIO]

Identifique:
1. ameaça;
2. vulnerabilidade;
3. ativo afetado;
4. possível impacto;
5. indicadores;
6. medidas preventivas;
7. medidas de detecção;
8. medidas de resposta.

Mantenha a análise voltada para defesa e ambientes autorizados.
```

### Objetivo

Desenvolver pensamento voltado à segurança defensiva.

### Resultado esperado

Uma análise estruturada de risco e proteção.

---

# 17. 🧭 Plano de estudo

### Prompt

```text
Crie uma sequência de estudos para um iniciante utilizando as fontes deste projeto.

Organize os assuntos em uma ordem lógica:

1. redes;
2. TCP/IP;
3. Wireshark;
4. TCP;
5. UDP;
6. DNS;
7. HTTP;
8. HTTPS;
9. cibersegurança.

Para cada etapa informe:
- o que estudar;
- objetivo;
- exercício;
- conhecimento necessário para avançar.
```

### Objetivo

Organizar o aprendizado progressivamente.

### Resultado esperado

Uma trilha de estudos estruturada.

---

# 18. 🤖 Prompt para usar a IA como tutor

### Prompt

```text
Atue como meu tutor de fundamentos de redes e cibersegurança.

Sou iniciante.

Utilize as fontes fornecidas como principal referência.

Não quero apenas respostas prontas.

Quando eu fizer uma pergunta:
1. explique o conceito;
2. utilize linguagem simples;
3. apresente exemplos;
4. faça relação com o laboratório;
5. faça perguntas para verificar meu entendimento;
6. corrija meus erros;
7. indique o que devo estudar em seguida.

Sempre diferencie informações presentes nas fontes de explicações adicionais.

Quando houver atividades práticas de segurança, considere somente ambientes próprios, isolados ou autorizados.
```

### Objetivo

Transformar a IA em uma ferramenta contínua de aprendizagem.

### Resultado esperado

Estudo interativo e progressivo.

---

# 19. ⭐ Prompt mais útil

Entre os prompts testados, um dos mais importantes para este projeto é o prompt de **aprendizagem ativa**.

Ele muda a forma de utilização da IA:

```text
Não quero somente a resposta.

Quero entender como chegar à resposta.
```

Essa abordagem ajuda a desenvolver:

- Raciocínio lógico;
- Capacidade de investigação;
- Pensamento crítico;
- Capacidade de diagnóstico;
- Autonomia no aprendizado.

---

# 20. 📊 Avaliação dos prompts

| Prompt | Objetivo | Utilidade |
|---|---|---|
| Explicação para iniciantes | Compreender conceitos | ⭐⭐⭐⭐⭐ |
| Wireshark | Analisar pacotes | ⭐⭐⭐⭐⭐ |
| TCP Handshake | Entender TCP | ⭐⭐⭐⭐⭐ |
| DNS | Entender resolução de nomes | ⭐⭐⭐⭐⭐ |
| HTTP | Entender Web | ⭐⭐⭐⭐⭐ |
| HTTP x HTTPS | Comparar protocolos | ⭐⭐⭐⭐ |
| Aprendizagem ativa | Aprender interativamente | ⭐⭐⭐⭐⭐ |
| Diagnóstico | Resolver problemas | ⭐⭐⭐⭐⭐ |
| Laboratório | Praticar | ⭐⭐⭐⭐⭐ |
| Questões | Revisar | ⭐⭐⭐⭐ |
| Simulado | Avaliar | ⭐⭐⭐⭐ |
| Resumo | Revisar fontes | ⭐⭐⭐⭐ |
| Comparação de fontes | Integrar conhecimentos | ⭐⭐⭐⭐⭐ |
| Técnica Feynman | Verificar compreensão | ⭐⭐⭐⭐⭐ |
| Analogia | Facilitar compreensão | ⭐⭐⭐⭐ |
| Análise de ameaça | Pensamento defensivo | ⭐⭐⭐⭐⭐ |
| Plano de estudo | Organizar aprendizado | ⭐⭐⭐⭐⭐ |

---

# 21. 📌 Conclusão

Os prompts testados demonstram que a Inteligência Artificial pode ser utilizada de diferentes maneiras durante o aprendizado de cibersegurança.

Ela pode atuar como:

**Professor → Tutor → Avaliador → Investigador → Gerador de exercícios → Assistente de laboratório**

Porém, a melhor utilização não é simplesmente solicitar respostas.

É utilizar a IA para desenvolver a capacidade de **pensar, questionar, investigar e verificar**.

> **O objetivo não é usar a IA para pensar no lugar do estudante, mas usar a IA para ajudar o estudante a pensar melhor.**
