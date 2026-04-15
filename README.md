# Introdução ao Big Data, Armazenamento e Processamento de Dados em Escala, Tecnologias para Ciência de Dados e Bancos de Dados NoSQL para Ciência de Dados

## 1. Identificação da disciplina

**Disciplina:** Introdução ao Big Data; Armazenamento e Processamento de Dados em Escala; Tecnologias para Ciência de Dados; Bancos de Dados NoSQL para Ciência de Dados  
**Curso:** Especialização em Ciência de Dados e Inteligência Artificial  
**Carga horária:** 40 horas  

---

## 2. Ementa

Fundamentos de Big Data e suas implicações para ciência de dados e inteligência artificial. Armazenamento de dados em escala. Arquiteturas de dados para analytics e IA. Formatos de dados e estratégias de particionamento. Armazenamento orientado à análise com Hadoop HDFS, Hive, Parquet e Delta Lake. Processamento distribuído de dados. ETL/ELT e pipelines de dados. Ecossistema tecnológico para ciência de dados. Modelos de bancos de dados NoSQL. Conceitos e aplicações de bancos de documentos, chave-valor, colunares e grafos. Estruturas distribuídas, replicação, particionamento e sharding. Consistência, disponibilidade e escalabilidade. Critérios para escolha entre tecnologias SQL e NoSQL em projetos de dados. Aplicação de tecnologias de armazenamento e processamento em escala em cenários de análise de dados, machine learning e sistemas inteligentes.

---

## 3. Objetivo geral

Compreender os fundamentos, arquiteturas, tecnologias e práticas de armazenamento e processamento de dados em escala, articulando conceitos de Big Data, ecossistemas de dados para ciência de dados e IA e bancos NoSQL, com foco em análise crítica, modelagem e aplicação prática em problemas reais.

---

## 4. Objetivos específicos

Ao final da disciplina, espera-se que o estudante seja capaz de:

- compreender os fundamentos e os principais desafios associados a Big Data;
- diferenciar abordagens de armazenamento relacional, distribuído e NoSQL;
- analisar formatos de dados e estratégias de organização voltadas a desempenho e escalabilidade;
- compreender os princípios do processamento distribuído de dados;
- utilizar ferramentas e ambientes básicos para manipulação e processamento de dados em escala;
- estruturar pipelines de dados para fins analíticos e para aplicações em IA;
- identificar o papel de tecnologias como data lakes, engines distribuídas, mensageria e bancos NoSQL no ecossistema de dados;
- comparar modelos NoSQL e selecionar soluções de acordo com requisitos de acesso, consistência e escalabilidade;
- modelar dados para bancos de documentos e outros paradigmas NoSQL em cenários de ciência de dados;
- propor arquiteturas de dados coerentes com necessidades analíticas, operacionais e de inteligência artificial.

---

## 5. Competências desenvolvidas

- visão sistêmica sobre ecossistemas de dados;
- capacidade de leitura arquitetural de soluções de dados;
- raciocínio sobre escalabilidade, desempenho e custo;
- modelagem de dados orientada a caso de uso;
- articulação entre base conceitual e implementação prática;
- tomada de decisão tecnológica com justificativa técnica.

---

## 6. Metodologia

A disciplina será desenvolvida com abordagem teórico-prática, combinando:

- exposição dialogada dos fundamentos conceituais;
- demonstrações guiadas de ferramentas e fluxos de trabalho;
- laboratórios práticos com dados semiestruturados e analíticos;
- estudos de caso orientados a problemas de negócio;
- atividades em grupo para análise, modelagem e decisão arquitetural;
- exercícios de aplicação e desafios de diagnóstico;
- mini projeto integrador ao longo da disciplina.

A condução didática seguirá uma lógica em espiral: os conceitos são introduzidos, experimentados em laboratório, aplicados em um caso de uso e retomados com maior profundidade ao longo dos encontros.

---

## 7. Estratégia didática

A disciplina será organizada em torno de um **caso integrador**, preferencialmente um cenário de marketplace/e-commerce, para permitir a articulação entre:

- dados transacionais de pedidos;
- catálogos semiestruturados;
- logs de navegação e eventos;
- perfis de usuários;
- consultas analíticas;
- preparação de dados para modelos de IA;
- cenários de baixa latência e serving.

Esse caso servirá como fio condutor para relacionar teoria, laboratório e tomada de decisão tecnológica.

---

## 8. Recursos e tecnologias sugeridos

### Stack principal para aprofundamento prático

- Python
- Jupyter Notebook
- SQL
- PySpark
- Parquet
- Delta Lake
- DuckDB ou engine SQL leve
- MongoDB

### Stack complementar para demonstração e comparação

- Hadoop HDFS
- Hive
- Redis
- Kafka
- Cassandra
- Neo4j

Essa escolha permite aprofundar o uso prático de um conjunto enxuto de ferramentas, preservando ao mesmo tempo visão arquitetural ampla do ecossistema.

---

## 9. Avaliação

- **100%** laboratórios práticos e mini projeto final em grupo.

### Critérios de avaliação

- compreensão conceitual;
- capacidade de aplicar conceitos a cenários reais;
- qualidade da modelagem de dados;
- coerência técnica na escolha de tecnologias;
- clareza na argumentação arquitetural;
- funcionalidade e consistência das soluções práticas.

---

## 10. Sequência didática da disciplina

### Tema: Introdução ao Big Data e o problema de dados em escala

**Objetivos do encontro**

- alinhar conceitos fundamentais;
- compreender por que Big Data é estratégico para ciência de dados e IA;
- apresentar o caso integrador da disciplina.

**Conteúdos**

- evolução de BI tradicional para ecossistemas de dados em escala;
- os 5 Vs do Big Data;
- tipos de dados: estruturados, semiestruturados e não estruturados;
- diferenças entre OLTP, OLAP e workloads de ciência de dados;
- papel da engenharia de dados no ciclo de analytics e IA.

**Atividades**

- leitura do cenário-base do marketplace;
- mapeamento de fontes de dados do negócio;
- identificação de gargalos de uma arquitetura tradicional centralizada.

**Exercício prático**

Em grupos, os estudantes elaboram um quadro com:

- tipos de dados presentes no cenário;
- pontos de crescimento de volume;
- necessidades de velocidade e escalabilidade;
- perguntas de negócio e de IA a serem respondidas.

**Entrega do encontro**

- mapa inicial do ecossistema de dados do caso.

---

### Tema: Armazenamento de dados em escala

**Objetivos do encontro**

- compreender como decisões de armazenamento afetam custo, desempenho e análise;
- introduzir formatos de dados e arquiteturas de armazenamento modernas.

**Conteúdos**

- arquivos versus bancos de dados;
- HDFS e object storage;
- formatos CSV, JSON, Avro, ORC e Parquet;
- compressão, particionamento e schema evolution;
- data lake, data warehouse e lakehouse;
- armazenamento orientado à análise com Hadoop HDFS, Hive, Parquet e Delta Lake.

**Atividades**

- comparação do mesmo conjunto de dados em diferentes formatos;
- análise de impacto em tamanho, leitura e consulta;
- organização de dados por partições adequadas ao caso.

**Exercício prático**

Laboratório guiado com:

- gravação do dataset em CSV, JSON e Parquet;
- consulta e organização de dados em estrutura analítica inspirada em Hive;
- comparação entre tabelas em Parquet e Delta Lake;
- escolha da melhor estratégia de armazenamento para pedidos, catálogo e logs.

**Entrega do encontro**

- matriz de decisão entre formatos e estratégias de armazenamento.

---

### Tema: Fundamentos do processamento distribuído e introdução ao Spark

**Objetivos do encontro**

- compreender a lógica do processamento distribuído;
- iniciar a exploração prática de uma engine distribuída.

**Conteúdos**

- limites do processamento local;
- noções de MapReduce;
- partições, paralelismo e shuffle;
- DAG e lazy evaluation;
- visão geral do Spark.

**Atividades**

- leitura de dados em ambiente distribuído;
- transformações básicas e ações;
- filtros, agregações e joins.

**Exercício prático**

Laboratório em PySpark para responder perguntas como:

- categorias com maior volume de vendas;
- ticket médio por região;
- clientes com maior recorrência;
- análise básica de navegação e abandono.

**Entrega do encontro**

- primeiro pipeline analítico distribuído.

---

### Tema: ETL/ELT, qualidade de dados e performance

**Objetivos do encontro**

- articular processamento em escala com confiabilidade analítica;
- compreender a importância de desenho de pipeline e qualidade de dados.

**Conteúdos**

- ETL versus ELT;
- arquitetura em camadas: bronze, silver e gold;
- qualidade de dados em pipelines;
- deduplicação, tipagem, tratamento de nulos e integridade;
- problemas de desempenho: skew, joins mal planejados e partições ruins.

**Atividades**

- construção de pipeline em camadas;
- limpeza e padronização dos dados;
- geração de tabela analítica consolidada.

**Exercício prático**

Desafio de diagnóstico em grupo com correção de:

- pipeline lento;
- colunas com schema inconsistente;
- joins com explosão de cardinalidade;
- particionamento inadequado.

**Entrega do encontro**

- pipeline batch otimizado e documentado.

---

### Tema: Tecnologias para ciência de dados e arquiteturas de dados

**Objetivos do encontro**

- consolidar a visão do ecossistema tecnológico;
- relacionar componentes arquiteturais às demandas de analytics e IA.

**Conteúdos**

- engines de processamento;
- catálogos e governança de dados;
- orquestração;
- mensageria e eventos;
- observabilidade;
- integração com notebooks, analytics e machine learning;
- papel de Hadoop HDFS, Hive, Parquet e Delta Lake no ecossistema analítico.

**Atividades**

- workshop de desenho arquitetural;
- definição de soluções para diferentes contextos organizacionais.

**Exercício prático**

Em grupos, os estudantes propõem arquiteturas para cenários como:

- empresa de pequeno porte;
- organização regulada;
- produto digital de alto volume;
- necessidade de processamento quase em tempo real.

**Entrega do encontro**

- arquitetura de referência justificada tecnicamente.

---

### Tema: Fundamentos de NoSQL e decisão arquitetural

**Objetivos do encontro**

- compreender a emergência dos bancos NoSQL;
- diferenciar modelos e relacioná-los a casos de uso.

**Conteúdos**

- contexto de surgimento do NoSQL;
- CAP e trade-offs entre consistência, disponibilidade e tolerância a partição;
- consistência forte e eventual;
- tipos de bancos NoSQL: documento, chave-valor, coluna larga e grafo;
- estruturas distribuídas, replicação, particionamento e sharding;
- critérios para escolha entre SQL e NoSQL em projetos de dados.

**Atividades**

- análise de necessidades do caso integrador;
- classificação de cargas e padrões de acesso.

**Exercício prático**

Os grupos recebem diferentes problemas do cenário e devem decidir:

- qual modelo NoSQL usar;
- por que ele é mais adequado;
- quais trade-offs estão envolvidos.

**Entrega do encontro**

- mapa de adequação de tecnologias NoSQL por caso de uso.

---

### Tema: Banco de documentos na prática — MongoDB

**Objetivos do encontro**

- trabalhar modelagem orientada a acesso;
- aplicar consultas e agregações em dados semiestruturados.

**Conteúdos**

- documentos e coleções;
- embedding versus referencing;
- índices;
- aggregation pipeline;
- distribuição de dados e sharding em MongoDB;
- boas práticas de modelagem em bancos documentais.

**Atividades**

- modelagem de catálogo de produtos, avaliações e perfis;
- consultas por atributos variáveis;
- criação de índices e análises agregadas.

**Exercício prático**

Laboratório guiado com:

- carga de dados em MongoDB;
- consultas por filtros dinâmicos;
- agregações por categoria, perfil e comportamento;
- refatoração de uma modelagem inadequada.

**Entrega do encontro**

- coleção modelada e consultada segundo requisitos do caso.

---

### Tema: Outros modelos NoSQL e aplicações em ciência de dados

**Objetivos do encontro**

- ampliar repertório de soluções NoSQL;
- relacionar NoSQL a baixa latência, recomendação e análise de relacionamento.

**Conteúdos**

- Redis para cache, sessões e serving rápido;
- Cassandra para escrita massiva, particionamento e alta disponibilidade;
- grafos para relacionamento, recomendação e fraude;
- comparação entre modelos e limitações;
- critérios comparativos entre SQL e NoSQL conforme padrão de acesso, consistência, custo e escalabilidade.

**Atividades**

- exploração orientada de diferentes paradigmas;
- análise comparativa por caso de uso.

**Exercício prático**

Atividades em estações:

- estação 1: uso de Redis para cache e lookup rápido;
- estação 2: desenho de modelagem por consulta em coluna larga;
- estação 3: consulta simples sobre relacionamentos em grafo.

**Entrega do encontro**

- quadro comparativo de aplicações NoSQL para ciência de dados.

---

### Tema: Integração de tecnologias para ciência de dados e IA

**Objetivos do encontro**

- conectar armazenamento, processamento e serving;
- mostrar como dados em escala apoiam modelos e aplicações inteligentes.

**Conteúdos**

- batch versus streaming;
- feature engineering em escala;
- preparação de dados para treinamento;
- camadas de serving online e offline;
- papel de NoSQL em aplicações de IA.

**Atividades**

- construção de fluxo integrado de dados;
- preparação de visões de consumo analítico e operacional.

**Exercício prático**

Mini projeto orientado em grupo com etapas como:

- ingestão de dados;
- armazenamento em formato colunar;
- transformação em Spark;
- persistência analítica;
- persistência operacional ou documental;
- geração de artefato útil para analytics ou IA.

**Entrega do encontro**

- solução integrada parcial do caso.

---

### Tema: Consolidação, apresentação e fechamento

**Objetivos do encontro**

- sintetizar o percurso formativo;
- consolidar a capacidade de análise, escolha tecnológica e aplicação.

**Conteúdos**

- revisão dos conceitos estruturantes;
- anti-padrões em armazenamento e processamento de dados;
- critérios para escolha tecnológica;
- síntese: quando usar o quê.

**Atividades**

- apresentação dos mini projetos;
- peer review entre grupos;
- fechamento conceitual pelo professor.

**Exercício avaliativo**

Cada grupo apresenta:

- o problema atacado;
- a arquitetura proposta;
- as tecnologias escolhidas;
- os trade-offs envolvidos;
- a relação da solução com analytics e IA.

**Entrega do encontro**

- apresentação final do projeto integrador.

---

## 11. Atividades práticas 

### Microlabs em todas as aulas

Atividades curtas e objetivas para consolidar conceitos operacionais, como:

- leitura e inspeção de dados;
- conversão entre formatos;
- particionamento;
- consultas e agregações;
- ajustes de performance;
- criação de índices;
- modelagem documental;
- uso de cache.

### Desafios de diagnóstico

Situações-problema em que os estudantes analisam e corrigem falhas, como:

- pipelines lentos;
- schemas inconsistentes;
- duplicidades;
- modelagem inadequada;
- uso indevido de tecnologias.

### Estudos de caso

Aplicação contínua do caso integrador em diferentes camadas do ecossistema de dados.

### Quizzes conceituais curtos

Aplicados ao fim de blocos temáticos, cobrindo tópicos como:

- CAP;
- formatos de dados;
- ETL/ELT;
- data lake/lakehouse;
- modelos NoSQL.

### Design review em grupo

Momentos de apresentação e crítica técnica de arquiteturas propostas pelos estudantes.

### Mini projeto final

Projeto integrador em grupo, articulando armazenamento, processamento, modelagem e justificativa arquitetural.


