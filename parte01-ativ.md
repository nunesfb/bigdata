## Atividades práticas

### 1. Organização geral das atividades na aula

As atividades práticas desta aula devem ser distribuídas ao longo do encontro para que cumpram três funções pedagógicas complementares:

* **ativar repertório prévio** e conectar os estudantes ao problema;
* **transformar conceitos abstratos em leitura concreta de cenário**;
* **consolidar a aprendizagem** por meio de análise, argumentação e produção de um artefato final.

A lógica recomendada é a seguinte:

1. primeiro, uma atividade curta e individual para ativação conceitual;
2. depois, uma atividade guiada em grupo para leitura do caso;
3. em seguida, uma atividade analítica em grupo para mapear dados, gargalos e necessidades;
4. por fim, um desafio integrador para fechamento da aula.

Essa sequência ajuda a sair da compreensão inicial do tema e chegar à aplicação prática em um caso de negócio.

---

### 2. Momento ideal para aplicar cada atividade

| Momento da aula                                          | Objetivo pedagógico                       | Tipo de atividade            | Duração sugerida |
| -------------------------------------------------------- | ----------------------------------------- | ---------------------------- | ---------------- |
| Início da aula                                           | ativar conhecimento prévio                | individual                   | 10 a 15 min      |
| Após a exposição inicial sobre Big Data e BI tradicional | conectar conceito ao caso                 | individual ou dupla          | 10 min           |
| Após apresentar os 5 Vs, tipos de dados e workloads      | analisar o cenário de forma aplicada      | grupo                        | 20 a 30 min      |
| Após discutir engenharia de dados                        | organizar raciocínio arquitetural inicial | grupo                        | 25 a 35 min      |
| Fechamento da aula                                       | síntese, integração e argumentação        | grupo com apresentação curta | 20 a 30 min      |

---

## Enunciados prontos para aplicar em sala e rubrica de correção

### 1. Orientação geral ao professor

Este material foi elaborado para uso direto em sala de aula, como complemento ao bloco de atividades práticas da aula **Introdução ao Big Data e o problema de dados em escala**. O objetivo aqui é oferecer textos que possam ser lidos, projetados ou entregues aos estudantes sem necessidade de adaptação extensa, além de uma rubrica que permita avaliar a participação e a produção dos alunos com maior consistência.

A proposta está organizada em três partes:

1. **enunciados das atividades individuais**;
2. **enunciados das atividades em grupo**;
3. **rubrica de correção e avaliação formativa**.

O professor pode utilizar todas as atividades na mesma aula ou selecionar apenas algumas, conforme o tempo disponível e o perfil da turma.

---

### 2. Enunciados prontos — atividades individuais

## Atividade individual 1 — Diagnóstico inicial de repertório

### Enunciado para os alunos

Leia as perguntas abaixo e responda de forma breve e objetiva, com suas próprias palavras. Não é necessário consultar material neste momento.

1. O que você entende por Big Data?
2. Cite um exemplo de dado estruturado.
3. Cite um exemplo de dado semiestruturado.
4. Cite um exemplo de dado não estruturado.
5. Por que uma empresa digital pode precisar de mais do que relatórios tradicionais para tomar decisões?

### Orientação de aplicação

* tempo sugerido: 10 minutos;
* aplicação: individual;
* objetivo: levantar repertório prévio e identificar concepções iniciais.

### Resultado esperado

Espera-se que o estudante demonstre compreensão inicial sobre o tema, ainda que incompleta. O foco dessa atividade não é exigir domínio técnico pleno, mas revelar o ponto de partida da turma.

---

## Atividade individual 2 — Classificação de tipos de dados

### Enunciado para os alunos

Classifique cada item abaixo como **dado estruturado**, **dado semiestruturado** ou **dado não estruturado**.

1. tabela de pedidos de um e-commerce;
2. arquivo CSV com vendas mensais;
3. documento JSON de catálogo de produtos;
4. imagem de produto;
5. avaliação textual deixada por um cliente;
6. log de navegação de uma aplicação;
7. planilha de estoque;
8. áudio de atendimento ao cliente;
9. XML de integração entre sistemas;
10. tabela de pagamentos.

Depois de classificar, escolha **dois exemplos** e justifique sua resposta em uma frase para cada um.

### Orientação de aplicação

* tempo sugerido: 10 minutos;
* aplicação: individual;
* objetivo: consolidar a distinção entre tipos de dados.

### Resultado esperado

O estudante deve conseguir reconhecer que nem todo dado se organiza em tabela e que diferentes formatos exigem diferentes formas de armazenamento e tratamento.

---

## Atividade individual 3 — Identificação de workloads

### Enunciado para os alunos

Associe cada situação abaixo ao tipo de workload predominante: **OLTP**, **OLAP** ou **ciência de dados**.

1. registrar um novo pedido no sistema;
2. calcular a receita mensal por região;
3. treinar um modelo para prever churn;
4. atualizar o status de pagamento de um pedido;
5. analisar as categorias com maior crescimento no trimestre;
6. gerar variáveis para um modelo de recomendação;
7. consultar rapidamente o status de uma compra;
8. comparar o desempenho de vendas entre dois anos.

Ao final, responda à pergunta:

**Por que um mesmo sistema não é, necessariamente, ideal para atender igualmente bem os três tipos de workload?**

### Orientação de aplicação

* tempo sugerido: 10 a 15 minutos;
* aplicação: individual;
* objetivo: distinguir operação, análise e modelagem.

### Resultado esperado

Espera-se que o aluno compreenda que workloads diferentes exigem arquiteturas, estruturas e prioridades diferentes.

---

### 3. Enunciados prontos — atividades em grupo

## Atividade em grupo 1 — Leitura orientada do cenário-base

### Enunciado para os grupos

Leiam atentamente o cenário do marketplace apresentado pelo professor. Em seguida, identifiquem no texto os elementos abaixo:

1. principais fontes de dados do negócio;
2. sinais de crescimento ou complexidade;
3. necessidades analíticas já presentes no cenário;
4. oportunidades de aplicação de IA;
5. problemas ou limitações relatados na arquitetura atual.

Registrem as respostas em um quadro como o modelo abaixo:

| Elemento identificado | Evidência encontrada no cenário |
| --------------------- | ------------------------------- |
| Fonte de dados        |                                 |
| Sinal de crescimento  |                                 |
| Necessidade analítica |                                 |
| Oportunidade de IA    |                                 |
| Problema atual        |                                 |

### Orientação de aplicação

* tempo sugerido: 15 a 20 minutos;
* aplicação: grupos de 4 a 6 estudantes;
* objetivo: garantir leitura qualificada do caso antes da análise mais profunda.

### Resultado esperado

Os grupos devem demonstrar capacidade de localizar no cenário os elementos que justificam o estudo de Big Data como problema arquitetural e analítico.

---

## Atividade em grupo 2 — Mapeamento das fontes de dados do negócio

### Enunciado para os grupos

Com base no cenário do marketplace, construam um quadro de mapeamento das principais fontes de dados do negócio. Para cada fonte, indiquem:

1. o exemplo correspondente no cenário;
2. o tipo de dado predominante;
3. o uso principal desse dado;
4. a frequência com que ele é gerado ou atualizado.

Utilizem o modelo abaixo:

| Fonte de dados | Exemplo no cenário | Tipo de dado | Uso principal | Frequência de geração |
| -------------- | ------------------ | ------------ | ------------- | --------------------- |
| Pedidos        |                    |              |               |                       |
| Catálogo       |                    |              |               |                       |
| Navegação      |                    |              |               |                       |
| Avaliações     |                    |              |               |                       |
| Atendimento    |                    |              |               |                       |
| Marketing      |                    |              |               |                       |

Ao final, respondam:

**Qual dessas fontes tende a gerar maior complexidade para armazenamento e processamento? Justifiquem.**

### Orientação de aplicação

* tempo sugerido: 20 a 25 minutos;
* aplicação: em grupo;
* objetivo: relacionar tipos de dados a usos e dinâmica de geração.

### Resultado esperado

O grupo deve demonstrar leitura sistêmica do negócio e compreensão de que fontes diferentes geram exigências diferentes para a arquitetura de dados.

---

## Atividade em grupo 3 — Identificação de gargalos da arquitetura centralizada

### Enunciado para os grupos

Considerem que o marketplace utiliza um único banco relacional central para armazenar e atender, ao mesmo tempo:

* operações de pedidos e pagamentos;
* consultas gerenciais e relatórios;
* integração de novos dados do catálogo;
* armazenamento de logs e eventos de navegação;
* extrações para análises avançadas e modelos de IA.

A partir disso, respondam:

1. quais gargalos podem surgir nessa arquitetura?
2. quais impactos esses gargalos podem causar na operação do negócio?
3. quais impactos esses gargalos podem causar em análises e iniciativas de IA?

Organizem as respostas no quadro abaixo:

| Gargalo identificado | Causa provável | Impacto no negócio | Impacto em analytics/IA |
| -------------------- | -------------- | ------------------ | ----------------------- |
|                      |                |                    |                         |

### Orientação de aplicação

* tempo sugerido: 20 a 25 minutos;
* aplicação: em grupo;
* objetivo: perceber os limites de uma arquitetura centralizada diante do crescimento de volume, variedade e uso.

### Resultado esperado

Os grupos devem ser capazes de argumentar que o problema não é apenas de armazenamento, mas também de concorrência de workload, rigidez estrutural e limitação para novas aplicações analíticas.

---

## Atividade em grupo 4 — Quadro analítico do caso

### Enunciado para os grupos

Com base em tudo o que foi discutido até aqui, elaborem um quadro analítico do caso do marketplace. O grupo deve preencher os seguintes itens:

1. tipos de dados presentes no cenário;
2. pontos de crescimento de volume;
3. necessidades de velocidade e escalabilidade;
4. perguntas de negócio que os dados deveriam responder;
5. perguntas de IA que o ecossistema de dados deveria suportar.

Utilizem o modelo abaixo:

| Dimensão                                    | Resposta do grupo |
| ------------------------------------------- | ----------------- |
| Tipos de dados presentes no cenário         |                   |
| Pontos de crescimento de volume             |                   |
| Necessidades de velocidade e escalabilidade |                   |
| Perguntas de negócio                        |                   |
| Perguntas de IA                             |                   |

Ao final, escolham **um item** do quadro e preparem uma justificativa oral de até 1 minuto explicando por que ele é especialmente relevante para o caso.

### Orientação de aplicação

* tempo sugerido: 25 a 35 minutos;
* aplicação: em grupo;
* objetivo: consolidar os conceitos da aula em uma leitura integrada do cenário.

### Resultado esperado

O grupo deve demonstrar capacidade de síntese, seleção de evidências relevantes e articulação entre conteúdo conceitual e caso de negócio.

---

### 4. Desafio final de fechamento

## Desafio integrador — Mapa inicial do ecossistema de dados do marketplace

### Enunciado para os grupos

Agora que vocês já analisaram o cenário sob diferentes perspectivas, produzam um **mapa inicial do ecossistema de dados do marketplace**.

O mapa deve representar, de forma visual e organizada:

1. as principais fontes de dados do negócio;
2. os tipos de dados envolvidos;
3. os pontos de maior crescimento de volume;
4. as necessidades de velocidade e escalabilidade;
5. os gargalos da arquitetura atual;
6. pelo menos **3 perguntas de negócio** que esse ecossistema deve responder;
7. pelo menos **2 perguntas de IA** que esse ecossistema deve viabilizar.

### Formato permitido

A entrega pode ser feita em:

* cartaz em papel;
* slide único;
* quadro branco colaborativo;
* mapa visual digital simples.

### Orientação adicional aos grupos

O objetivo do desafio não é desenhar uma arquitetura final ou tecnicamente completa, mas construir uma **visão inicial e coerente** do problema de dados do caso.

### Tempo sugerido

20 a 30 minutos.

### Apresentação

Cada grupo terá até **3 minutos** para apresentar seu mapa final.

### Resultado esperado

Espera-se que os grupos fechem a aula com uma visão organizada do ecossistema de dados do cenário, articulando fonte, tipo, problema, uso analítico e potencial para IA.

---

### 5. Rubrica de correção — atividades individuais

## Rubrica geral para atividades individuais

| Critério                  | Nível 3 — adequado e consistente                     | Nível 2 — parcialmente adequado                      | Nível 1 — insuficiente                      |
| ------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ------------------------------------------- |
| Compreensão conceitual    | responde com clareza e usa corretamente os conceitos | responde com alguma compreensão, mas com imprecisões | apresenta confusões conceituais importantes |
| Identificação de exemplos | classifica corretamente e justifica com lógica       | classifica parte corretamente, mas com dúvidas       | classifica de modo inconsistente            |
| Capacidade de aplicação   | relaciona conceito a situações de negócio            | faz relação básica, ainda superficial                | não consegue aplicar o conceito ao contexto |
| Clareza da resposta       | resposta objetiva e compreensível                    | resposta compreensível, mas incompleta               | resposta vaga ou confusa                    |

### Uso prático da rubrica

O professor pode usar essa rubrica de forma qualitativa ou atribuir pontuação, por exemplo:

* nível 3 = 2 pontos;
* nível 2 = 1 ponto;
* nível 1 = 0 ponto.

---

### 6. Rubrica de correção — atividades em grupo

## Rubrica geral para atividades em grupo

| Critério                | Nível 4 — excelente                                              | Nível 3 — bom                                     | Nível 2 — básico                            | Nível 1 — insuficiente                    |
| ----------------------- | ---------------------------------------------------------------- | ------------------------------------------------- | ------------------------------------------- | ----------------------------------------- |
| Leitura do cenário      | identifica com precisão fontes, problemas e oportunidades        | identifica a maior parte dos elementos relevantes | identifica apenas parte dos elementos       | leitura superficial ou equivocada         |
| Aplicação dos conceitos | aplica corretamente tipos de dados, workloads e noções de escala | aplica os conceitos principais com poucas falhas  | aplica os conceitos de forma parcial        | não consegue relacionar conceitos ao caso |
| Argumentação            | justifica decisões e interpretações com coerência                | apresenta justificativas adequadas                | apresenta justificativas frágeis            | não justifica ou justifica mal            |
| Visão sistêmica         | articula negócio, dados, gargalos e IA                           | relaciona bem a maior parte dos elementos         | faz relações limitadas                      | apresenta elementos desconectados         |
| Organização da entrega  | entrega clara, estruturada e comunicável                         | entrega organizada com pequenas falhas            | entrega compreensível, mas pouco organizada | entrega confusa ou incompleta             |
| Participação do grupo   | todos contribuem e a apresentação é equilibrada                  | participação majoritariamente compartilhada       | participação concentrada em poucos          | baixa colaboração                         |

### Sugestão de pontuação

O professor pode atribuir de 1 a 4 pontos por critério e, ao final, converter para nota ou conceito.

---

### 7. Rubrica específica para o desafio final

## Rubrica — mapa inicial do ecossistema de dados

| Critério                              | Excelente                                                              | Bom                                      | Básico                                          | Insuficiente                        |
| ------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------- | ----------------------------------------------- | ----------------------------------- |
| Identificação das fontes de dados     | mapeia fontes relevantes com precisão e completude                     | mapeia as principais fontes corretamente | mapeia apenas parte das fontes                  | omite fontes centrais               |
| Classificação dos tipos de dados      | classifica corretamente e demonstra entendimento claro                 | classifica corretamente a maior parte    | apresenta algumas classificações imprecisas     | classifica de forma equivocada      |
| Identificação de gargalos             | reconhece gargalos técnicos e de negócio com clareza                   | identifica os gargalos principais        | identifica poucos gargalos ou de forma genérica | não reconhece os problemas centrais |
| Relação com perguntas de negócio e IA | formula perguntas relevantes e bem alinhadas ao caso                   | formula perguntas adequadas              | formula perguntas pouco específicas             | perguntas desconectadas do cenário  |
| Integração conceitual                 | articula bem Big Data, workloads, tipos de dados e engenharia de dados | integra bem a maior parte dos conceitos  | integra conceitos de forma parcial              | não consegue integrar os conceitos  |
| Qualidade visual e comunicativa       | mapa claro, organizado e fácil de interpretar                          | mapa organizado com pequenos problemas   | mapa compreensível, mas pouco claro             | mapa confuso ou incompleto          |

### Perguntas de apoio para o professor durante a avaliação

* O grupo enxergou que o problema vai além de “ter muitos dados”?
* O grupo percebeu a diferença entre operação, análise e IA?
* O grupo relacionou corretamente tipo de dado e complexidade arquitetural?
* O grupo conseguiu justificar por que certos dados ou gargalos são estratégicos?

---

### 8. Modelo de feedback rápido para o professor usar em sala

## Feedback para atividades individuais

### Quando a resposta estiver boa

* “Boa resposta: você distinguiu corretamente volume de valor.”
* “A classificação ficou consistente e a justificativa mostrou entendimento.”
* “Você percebeu bem a diferença entre operação e análise.”

### Quando a resposta estiver parcial

* “Sua resposta aponta na direção correta, mas ainda reduz Big Data apenas a quantidade de dados.”
* “A classificação está quase certa, mas faltou considerar a flexibilidade do formato.”
* “Você identificou o workload, mas não explicou por que ele exige um tipo de sistema específico.”

### Quando a resposta estiver fraca

* “É importante rever a diferença entre estruturado, semiestruturado e não estruturado.”
* “Sua resposta mistura análise com operação. Tente focar no objetivo principal do sistema.”
* “Faltou ligar o conceito ao cenário de negócio.”

## Feedback para atividades em grupo

### Quando a produção estiver forte

* “O grupo articulou bem fonte, uso e gargalo.”
* “A leitura do cenário foi precisa e conectada ao conteúdo da aula.”
* “As perguntas de IA estão bem alinhadas ao caso.”

### Quando a produção estiver mediana

* “O mapeamento está correto, mas ainda falta justificar melhor as escolhas.”
* “Vocês identificaram os elementos centrais, porém precisam explicitar melhor os impactos para a arquitetura.”
* “A visão está boa, mas as perguntas de negócio ainda estão genéricas.”

### Quando a produção estiver frágil

* “O grupo listou elementos do cenário, mas ainda não os conectou entre si.”
* “Faltou diferenciar melhor o que é fonte de dado, tipo de dado e uso do dado.”
* “É importante revisar por que a arquitetura centralizada gera gargalos diferentes para operação e análise.”

---

### 9. Encerramento pedagógico sugerido

Ao final da aula, o professor pode retomar os resultados das atividades com uma síntese como esta:

> Ao longo da aula, vocês identificaram que o problema de Big Data não está apenas na quantidade de dados, mas na combinação entre crescimento de volume, diversidade de formatos, exigência de velocidade, confiabilidade e necessidade de gerar valor. Também perceberam que diferentes workloads exigem tratamentos distintos e que a engenharia de dados tem papel central para transformar dados dispersos em base útil para analytics e IA.

Essa fala ajuda a fechar o percurso didático da aula e preparar a transição para o próximo encontro sobre armazenamento de dados em escala.


---

# Mapa inicial do ecossistema de dados do marketplace

## 1. Principais fontes de dados do negócio

- Pedidos
- Pagamentos
- Estoque
- Catálogo de produtos
- Navegação / cliques / eventos
- Avaliações de clientes
- Atendimento ao cliente
- Marketing / campanhas

## 2. Tipos de dados envolvidos

| Fonte | Tipo de dado |
|---|---|
| Pedidos | Estruturado |
| Pagamentos | Estruturado |
| Estoque | Estruturado |
| Catálogo em JSON | Semiestruturado |
| Navegação / logs / eventos | Semiestruturado |
| Avaliações textuais | Não estruturado |
| Atendimento (áudio/chat/e-mail) | Não estruturado |
| Marketing | Estruturado e semiestruturado |

## 3. Pontos de maior crescimento de volume

- Eventos de navegação, porque são gerados continuamente e em grande volume
- Catálogo, porque cresce com mais produtos e atributos variáveis
- Avaliações, conforme a base de clientes aumenta
- Atendimento, principalmente se houver áudio, chat e histórico acumulado

## 4. Necessidades de velocidade e escalabilidade

- Pedidos e pagamentos precisam de resposta rápida e alta confiabilidade
- Estoque precisa de atualização frequente
- Navegação exige coleta contínua e processamento em alto volume
- Dashboards precisam de consultas rápidas para análise gerencial
- Recomendação e fraude pedem processamento analítico e, em alguns casos, quase em tempo real
- IA precisa de dados integrados, limpos e históricos maiores para treinar modelos

## 5. Gargalos da arquitetura centralizada atual

- Um único banco relacional atende tudo ao mesmo tempo
- Há concorrência entre OLTP e OLAP
- O banco recebe dados de naturezas muito diferentes
- Logs e eventos de alto volume pressionam a mesma infraestrutura
- Extrações para analytics e IA consomem recursos do banco operacional
- Resultado: lentidão, dificuldade de escalar e risco de impacto na operação

## 6. Pelo menos 3 perguntas de negócio que o ecossistema deve responder

- Quais produtos vendem mais e em quais períodos?
- Quais clientes têm maior chance de comprar novamente?
- Quais campanhas de marketing trazem mais conversão?
- Quais categorias precisam de reposição de estoque mais rápida?
- Onde os usuários abandonam a jornada de compra?

## 7. Pelo menos 2 perguntas de IA que o ecossistema deve viabilizar

- Quais produtos recomendar para cada usuário?
- Quais transações têm maior probabilidade de fraude?
- Qual é o sentimento das avaliações dos clientes?
- Quais clientes podem ser segmentados em perfis de comportamento?

## Exemplo de mapa em formato de texto

```text
FONTES DE DADOS
├── Pedidos (estruturado)
├── Pagamentos (estruturado)
├── Estoque (estruturado)
├── Catálogo JSON (semiestruturado)
├── Navegação / cliques / logs (semiestruturado)
├── Avaliações textuais (não estruturado)
├── Atendimento: chat/áudio/e-mail (não estruturado)
└── Marketing / campanhas (estruturado e semi)

USOS DO NEGÓCIO
├── Operação diária
├── Dashboards gerenciais
├── Segmentação de clientes
├── Recomendação
└── Detecção de fraude

PONTOS DE MAIOR CRESCIMENTO
├── Navegação / eventos
├── Catálogo
├── Avaliações
└── Atendimento

GARGALOS ATUAIS
├── Banco relacional único central
├── OLTP e OLAP competindo
├── Alto volume de eventos
├── Dados variados no mesmo sistema
└── Extrações pesadas para analytics/IA

NECESSIDADES
├── Mais escalabilidade
├── Separação entre operação e análise
├── Suporte a múltiplos tipos de dados
└── Maior velocidade para consulta e processamento

