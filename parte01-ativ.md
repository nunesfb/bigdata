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

### 3. Atividades individuais

## Atividade individual 1 — Diagnóstico inicial de repertório

### Quando aplicar

No início da aula, antes da exposição principal.

### Objetivo

Identificar o conhecimento prévio dos estudantes sobre Big Data, tipos de dados e uso de dados em negócios digitais.

### Tempo sugerido

10 minutos.

### Como aplicar

Entregue aos estudantes uma folha, formulário ou quadro digital com perguntas curtas. Eles respondem individualmente, sem consulta.

### Enunciado sugerido

Responda brevemente às questões abaixo:

1. O que você entende por Big Data?
2. Cite um exemplo de dado estruturado.
3. Cite um exemplo de dado semiestruturado.
4. Cite um exemplo de dado não estruturado.
5. Em sua visão, por que uma empresa digital precisa de dados além de relatórios tradicionais?

### Onde essa atividade se encaixa

Ela funciona como abertura da aula, pois ajuda o professor a identificar:

* percepções intuitivas dos alunos;
* confusões conceituais iniciais;
* repertório técnico da turma;
* pontos que exigirão maior ênfase na exposição.

### O que observar na correção

* se o aluno reduz Big Data a apenas volume;
* se distingue corretamente os tipos de dados;
* se percebe a relação entre dados, decisão e IA.

---

## Atividade individual 2 — Classificação de exemplos de dados

### Quando aplicar

Após a explicação sobre tipos de dados.

### Objetivo

Fixar a diferença entre dados estruturados, semiestruturados e não estruturados.

### Tempo sugerido

10 minutos.

### Como aplicar

Apresente uma lista de exemplos e peça que cada estudante classifique individualmente cada item.

### Itens sugeridos

Classifique cada exemplo como **estruturado**, **semiestruturado** ou **não estruturado**:

* tabela de pedidos;
* arquivo CSV de vendas;
* documento JSON de catálogo;
* imagem de produto;
* texto de avaliação de cliente;
* log de navegação;
* planilha de estoque;
* áudio de atendimento;
* XML de integração;
* tabela de pagamentos.

### Onde essa atividade se encaixa

Ela funciona logo após a explicação conceitual, antes que a aula avance para arquitetura e workloads. É importante porque fortalece a linguagem comum da turma.

### Variação possível

Depois da resposta individual, o professor pode corrigir coletivamente e pedir que os estudantes justifiquem um ou dois casos mais ambíguos, como log de navegação e JSON.

---

## Atividade individual 3 — Leitura rápida de workload

### Quando aplicar

Após a explicação de OLTP, OLAP e workloads de ciência de dados.

### Objetivo

Fazer o estudante reconhecer diferenças entre operação, análise e modelagem.

### Tempo sugerido

10 a 15 minutos.

### Enunciado sugerido

Associe cada situação abaixo ao tipo de workload predominante: **OLTP**, **OLAP** ou **ciência de dados**.

1. Registrar um novo pedido no sistema.
2. Calcular receita mensal por região.
3. Treinar um modelo de previsão de churn.
4. Atualizar status de pagamento.
5. Identificar categorias com maior crescimento trimestral.
6. Gerar variáveis para um modelo de recomendação.

### Onde essa atividade se encaixa

Essa atividade entra como verificação imediata de entendimento, logo após a parte conceitual sobre workloads.

### O que ela desenvolve

* leitura de contexto;
* associação entre problema e tipo de sistema;
* base para decisões arquiteturais futuras.

---

### 4. Atividades em grupo

## Atividade em grupo 1 — Leitura orientada do cenário-base

### Quando aplicar

Depois da introdução teórica sobre Big Data e após apresentar o caso do marketplace.

### Objetivo

Levar os grupos a reconhecer as fontes de dados, os processos de negócio e os sinais de complexidade do cenário.

### Tempo sugerido

15 a 20 minutos.

### Como aplicar

Divida a turma em grupos de 4 a 6 estudantes. Entregue o cenário-base e peça que os grupos destaquem trechos que indiquem:

* fontes de dados;
* áreas do negócio envolvidas;
* sinais de crescimento;
* possíveis usos analíticos;
* possíveis usos de IA.

### Produto esperado

Um quadro simples com duas colunas:

| Elemento identificado | Evidência no cenário |
| --------------------- | -------------------- |
| Fonte de dados        |                      |
| Problema relatado     |                      |
| Necessidade analítica |                      |
| Oportunidade de IA    |                      |

### Onde essa atividade se encaixa

Ela deve acontecer antes do mapeamento analítico mais detalhado. Sua função é garantir que os grupos compreendam o caso antes de propor soluções ou classificações.

### Papel do professor durante a atividade

Circular entre os grupos e verificar se eles perceberam que o cenário não envolve apenas banco relacional, mas também catálogo variável, logs, avaliações, comportamento e aplicações de IA.

---

## Atividade em grupo 2 — Mapeamento das fontes de dados do negócio

### Quando aplicar

Depois da leitura orientada do cenário e após a discussão sobre tipos de dados.

### Objetivo

Construir uma visão inicial do ecossistema de dados do caso.

### Tempo sugerido

20 a 25 minutos.

### Como aplicar

Cada grupo deve mapear as principais fontes de dados do marketplace e classificá-las.

### Instrução para os grupos

Preencham um quadro com as seguintes colunas:

| Fonte de dados | Exemplo no cenário | Tipo de dado | Uso principal | Frequência de geração |
| -------------- | ------------------ | ------------ | ------------- | --------------------- |
| Pedidos        |                    |              |               |                       |
| Catálogo       |                    |              |               |                       |
| Navegação      |                    |              |               |                       |
| Avaliações     |                    |              |               |                       |
| Atendimento    |                    |              |               |                       |
| Marketing      |                    |              |               |                       |

### Onde essa atividade se encaixa

Esse é o momento em que os estudantes aplicam o conteúdo sobre tipos de dados a um contexto concreto.

### Aprendizagens envolvidas

* classificação de dados;
* leitura sistêmica do negócio;
* relação entre fonte, formato e uso;
* preparação para discussão de arquitetura.

### Dica de condução

Peça que os grupos não apenas nomeiem a fonte, mas também expliquem **por que aquele dado é importante** e **para quem ele gera valor**.

---

## Atividade em grupo 3 — Identificação de gargalos de uma arquitetura centralizada

### Quando aplicar

Após a discussão sobre BI tradicional, ecossistemas modernos e diferenças entre workloads.

### Objetivo

Fazer os estudantes perceberem por que uma arquitetura tradicional centralizada pode se tornar insuficiente.

### Tempo sugerido

20 a 25 minutos.

### Como aplicar

Peça que os grupos assumam que o marketplace usa um único banco relacional central para quase tudo. Em seguida, devem listar problemas possíveis.

### Perguntas-guia

1. O que pode acontecer se o mesmo banco atender operação e análise pesada?
2. Quais problemas surgem com o crescimento de logs e eventos?
3. Como dados semiestruturados e não estruturados afetam essa arquitetura?
4. Quais impactos isso teria em relatórios, operação e IA?

### Produto esperado

Uma tabela como esta:

| Gargalo identificado         | Causa provável               | Impacto no negócio     | Impacto em dados/IA          |
| ---------------------------- | ---------------------------- | ---------------------- | ---------------------------- |
| Lentidão em consultas        | competição entre OLTP e OLAP | atraso operacional     | atraso analítico             |
| Dificuldade de integrar JSON | modelo rígido                | perda de flexibilidade | limitação para novos casos   |
| Crescimento de logs          | volume elevado               | aumento de custo       | dificuldade de processamento |

### Onde essa atividade se encaixa

Ela é ideal após o bloco conceitual sobre workloads e antes da síntese sobre engenharia de dados.

### O que ela prepara

Prepara o terreno para as próximas aulas sobre armazenamento em escala, processamento distribuído e arquiteturas analíticas.

---

## Atividade em grupo 4 — Quadro analítico do caso

### Quando aplicar

Na parte final do desenvolvimento da aula, depois que todos os conceitos centrais já foram apresentados.

### Objetivo

Consolidar a compreensão do cenário em uma visão integrada.

### Tempo sugerido

25 a 35 minutos.

### Como aplicar

Cada grupo deve construir um quadro com quatro eixos principais:

1. tipos de dados presentes no cenário;
2. pontos de crescimento de volume;
3. necessidades de velocidade e escalabilidade;
4. perguntas de negócio e de IA a serem respondidas.

### Modelo de quadro

| Dimensão                                    | Resposta do grupo |
| ------------------------------------------- | ----------------- |
| Tipos de dados presentes no cenário         |                   |
| Pontos de crescimento de volume             |                   |
| Necessidades de velocidade e escalabilidade |                   |
| Perguntas de negócio                        |                   |
| Perguntas de IA                             |                   |

### Onde essa atividade se encaixa

Essa é a principal atividade de consolidação da aula. Ela deve ocorrer depois das atividades menores e antes do desafio final.

### Papel do professor

Nesta etapa, o professor pode exigir maior qualidade de justificativa. Não basta listar elementos: o grupo deve explicar por que cada item importa no contexto do negócio.

---

### 5. Atividades de socialização e discussão

## Socialização curta entre grupos

### Quando aplicar

Depois do quadro analítico do caso.

### Objetivo

Permitir comparação de leituras e ampliar repertório.

### Tempo sugerido

10 a 15 minutos.

### Como aplicar

Cada grupo apresenta em até 2 minutos:

* uma fonte de dado crítica;
* um gargalo central da arquitetura atual;
* uma pergunta de IA relevante para o cenário.

### Onde essa atividade se encaixa

Entre a produção em grupo e o desafio final. Ela ajuda a preparar o fechamento da aula porque expõe visões diferentes do mesmo caso.

### O que observar

* clareza de argumentação;
* consistência do raciocínio;
* relação entre dados, negócio e IA.

---

### 6. Desafio final para fechar a aula

## Desafio integrador — Mapa inicial do ecossistema de dados do marketplace

### Quando aplicar

No fechamento da aula, como atividade-síntese.

### Objetivo

Integrar todos os conceitos trabalhados no encontro em um único artefato.

### Tempo sugerido

20 a 30 minutos.

### Formato

Em grupo.

### Enunciado do desafio

Com base em tudo o que foi discutido na aula, elaborem um **mapa inicial do ecossistema de dados** do marketplace. O grupo deve representar:

* as principais fontes de dados;
* os tipos de dados envolvidos;
* os pontos de maior crescimento de volume;
* as necessidades de velocidade e escalabilidade;
* os gargalos da arquitetura centralizada atual;
* pelo menos 3 perguntas de negócio e 2 perguntas de IA que esse ecossistema deveria suportar.

### Formato da entrega

O mapa pode ser produzido em:

* papel A3;
* slide único;
* quadro branco colaborativo;
* documento visual simples.

### Estrutura mínima da entrega

O grupo deve conter no mapa:

1. **fontes de dados**;
2. **classificação dos dados**;
3. **problemas atuais**;
4. **usos analíticos**;
5. **usos para IA**.

### Critérios de avaliação do desafio

| Critério               | O que observar                                    |
| ---------------------- | ------------------------------------------------- |
| Compreensão do cenário | se o grupo leu corretamente o caso                |
| Aplicação conceitual   | se classificou adequadamente dados e workloads    |
| Visão sistêmica        | se articulou fontes, problemas e usos             |
| Clareza visual         | se o mapa é compreensível e organizado            |
| Justificativa          | se o grupo explica por que cada ponto é relevante |

### Onde esse desafio se encaixa

Ele fecha a aula porque obriga os estudantes a articular todo o conteúdo:

* evolução de BI para ecossistemas modernos;
* 5 Vs;
* tipos de dados;
* workloads;
* papel da engenharia de dados.

### Como o professor pode conduzir o fechamento

Após os grupos finalizarem, selecione 2 ou 3 mapas para apresentação rápida e encerre retomando perguntas como:

* qual foi a principal fonte de complexidade do caso?
* em que ponto a arquitetura tradicional começou a falhar?
* que tipo de necessidade do negócio já aponta para a próxima aula, sobre armazenamento em escala?

---

### 7. Sugestão de sequência completa de aplicação em aula

| Etapa | Atividade                                             | Formato    | Tempo       |
| ----- | ----------------------------------------------------- | ---------- | ----------- |
| 1     | diagnóstico inicial de repertório                     | individual | 10 min      |
| 2     | classificação de tipos de dados                       | individual | 10 min      |
| 3     | leitura rápida de workloads                           | individual | 10 min      |
| 4     | leitura orientada do cenário                          | grupo      | 15 min      |
| 5     | mapeamento das fontes de dados                        | grupo      | 20 min      |
| 6     | identificação de gargalos da arquitetura centralizada | grupo      | 20 min      |
| 7     | quadro analítico do caso                              | grupo      | 30 min      |
| 8     | socialização curta                                    | grupo      | 10 min      |
| 9     | desafio integrador final                              | grupo      | 20 a 30 min |

---

### 8. Observações didáticas finais

#### Quando priorizar atividades individuais

As atividades individuais funcionam melhor:

* no início da aula;
* logo após blocos conceituais;
* quando o objetivo é verificar compreensão imediata;
* quando se quer evitar que alguns estudantes dependam do grupo para responder.

#### Quando priorizar atividades em grupo

As atividades em grupo funcionam melhor:

* quando o problema exige interpretação de cenário;
* quando há múltiplas respostas possíveis;
* quando a tarefa envolve análise, síntese e argumentação;
* quando se deseja desenvolver visão sistêmica e tomada de decisão coletiva.

#### Quando aplicar o desafio final

O desafio final deve ser aplicado apenas depois que a turma já tiver passado por:

* conceitos básicos;
* leitura do cenário;
* classificação dos dados;
* discussão sobre gargalos;
* reflexão sobre uso analítico e IA.

Isso evita que a atividade vire apenas um exercício de adivinhação e garante que ela funcione como síntese real da aprendizagem.

---

### 9. Resultado esperado ao final da aula

Ao concluir esse conjunto de atividades, espera-se que os estudantes sejam capazes de:

* reconhecer que Big Data é um problema de escala, diversidade, velocidade e uso;
* ler um cenário de negócio sob a ótica de dados;
* diferenciar tipos de dados e workloads;
* identificar limitações de arquiteturas centralizadas;
* construir um mapa inicial de ecossistema de dados;
* preparar a base conceitual para a próxima aula da disciplina.
