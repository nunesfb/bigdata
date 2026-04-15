## Conteúdo

### 1. Evolução de BI tradicional para ecossistemas de dados em escala

A compreensão de Big Data começa pela análise da evolução das arquiteturas de informação nas organizações. Durante muito tempo, o modelo dominante foi o de **Business Intelligence (BI) tradicional**, centrado em sistemas transacionais, processos periódicos de extração e consolidação de dados e geração de relatórios gerenciais. Nesse modelo, os dados costumam ser majoritariamente estruturados, provenientes de sistemas corporativos como ERP, CRM, financeiro, estoque e vendas. A ênfase recai sobre o monitoramento do desempenho do negócio por meio de indicadores, painéis e relatórios históricos.

Nesse contexto, a arquitetura tradicional tende a seguir um fluxo relativamente estável: os dados são gerados nos sistemas operacionais, extraídos por processos ETL, carregados em um data warehouse e consumidos por ferramentas analíticas. Essa abordagem foi, e continua sendo, extremamente relevante para apoiar decisões gerenciais, controle operacional e análise retrospectiva do desempenho organizacional.

Entretanto, a transformação digital ampliou radicalmente a natureza do problema de dados. As organizações passaram a lidar com:

* múltiplas fontes de dados internas e externas;
* geração contínua de eventos em aplicações web e mobile;
* interações em redes sociais;
* logs de sistemas;
* sensores e dispositivos conectados;
* documentos, imagens, textos, vídeos e áudios;
* demandas por decisões cada vez mais rápidas;
* uso de dados para personalização, automação, recomendação e inteligência artificial.

Esse cenário exige uma mudança de paradigma. Em vez de uma arquitetura estritamente centralizada e orientada a relatórios, emerge um **ecossistema de dados em escala**, caracterizado por maior diversidade de tecnologias, maior elasticidade de armazenamento e processamento e maior integração entre camadas operacionais, analíticas e inteligentes.

#### 1.1. Características do BI tradicional

* foco predominante em relatórios e indicadores;
* dados estruturados e relativamente estáveis;
* integração em ciclos periódicos;
* armazenamento centralizado;
* consultas voltadas para análise histórica;
* baixa flexibilidade para novos formatos de dados;
* menor aderência a casos de uso de machine learning e analytics avançado.

#### Exemplo prático de BI tradicional

Uma rede varejista registra vendas em um banco relacional e, ao final do dia, executa um processo ETL que consolida os dados em um data warehouse. No dia seguinte, gestores acessam um dashboard com:

* faturamento por loja;
* produtos mais vendidos;
* ticket médio;
* comparação com o mês anterior.

Esse modelo funciona bem quando:

* os dados são majoritariamente tabulares;
* o volume é controlável;
* as análises são históricas;
* não existe necessidade de resposta imediata.

#### Exemplo SQL típico em BI tradicional

```sql
SELECT
    loja_id,
    DATE_TRUNC('month', data_pedido) AS mes,
    SUM(valor_total) AS faturamento,
    AVG(valor_total) AS ticket_medio,
    COUNT(*) AS total_pedidos
FROM pedidos
GROUP BY loja_id, DATE_TRUNC('month', data_pedido)
ORDER BY mes, faturamento DESC;
```

Essa consulta representa bem um uso analítico clássico: consolidação histórica e agregação sobre dados estruturados.

#### 1.2. Características dos ecossistemas de dados em escala

* múltiplas fontes de dados heterogêneas;
* coexistência de dados estruturados, semiestruturados e não estruturados;
* processamento em batch e, em alguns casos, em tempo real ou quase real;
* uso combinado para operação, análise e IA;
* necessidade de escalabilidade horizontal;
* uso de armazenamento distribuído e formatos otimizados para análise;
* integração entre engenharia de dados, analytics e machine learning.

#### Exemplo prático de ecossistema de dados em escala

Em um marketplace, a empresa não trabalha apenas com a tabela de pedidos. Ela precisa integrar:

* pedidos e pagamentos em banco relacional;
* catálogo de produtos em JSON;
* eventos de navegação do site;
* avaliações textuais dos usuários;
* imagens de produtos;
* campanhas de marketing;
* dados usados para recomendação e detecção de fraude.

Nesse cenário, o dado deixa de servir apenas para relatório. Ele passa a alimentar:

* dashboards;
* treinamento de modelos de recomendação;
* segmentação de clientes;
* monitoramento operacional;
* sistemas de personalização.

#### Exemplo de evento semiestruturado em JSON

```json
{
  "event_id": "evt_90871",
  "timestamp": "2026-04-15T10:22:14Z",
  "user_id": 1827,
  "session_id": "sess_44A9",
  "event_type": "add_to_cart",
  "product": {
    "product_id": 9981,
    "category": "eletronicos",
    "price": 1299.90
  },
  "device": {
    "type": "mobile",
    "os": "Android"
  }
}
```

Esse tipo de dado não se encaixa com a mesma naturalidade em uma modelagem relacional rígida, especialmente quando o esquema evolui com frequência.

#### 1.3. Implicações dessa evolução

A transição de BI tradicional para ecossistemas de dados em escala não significa abandono do BI, mas sua ampliação. O BI continua relevante, porém passa a ser apenas uma parte de uma paisagem mais ampla. O desafio deixa de ser apenas “gerar relatório” e passa a incluir:

* ingerir grandes volumes de dados;
* armazenar dados de naturezas distintas;
* processar dados com eficiência;
* disponibilizar dados confiáveis para análise e IA;
* responder a demandas de negócio com rapidez e robustez;
* sustentar crescimento sem colapso de desempenho ou custo.

#### Exemplo de limitação arquitetural

Imagine um único banco relacional central recebendo:

* transações de compra em tempo real;
* consultas analíticas pesadas;
* extrações para machine learning;
* dados de navegação sendo inseridos continuamente.

Problemas comuns:

* lentidão nas operações transacionais;
* concorrência entre leitura analítica e escrita operacional;
* crescimento de custo vertical;
* dificuldade de incorporar JSON, logs e imagens;
* pipelines frágeis e lentos.

---

### 2. Os 5 Vs do Big Data

Big Data não deve ser entendido apenas como sinônimo de “muitos dados”. O conceito envolve um conjunto de características que tornam o problema de dados mais complexo do ponto de vista tecnológico, analítico e organizacional. Uma formulação didática clássica é dada pelos **5 Vs**: **Volume, Velocidade, Variedade, Veracidade e Valor**.

#### 2.1. Volume

O volume refere-se à quantidade de dados produzidos, armazenados e processados. Em ambientes digitais, esse crescimento pode ser exponencial, impulsionado por transações, eventos, interações de usuários, registros de sistemas, integrações entre plataformas e histórico acumulado.

O volume torna-se um problema quando os mecanismos tradicionais de armazenamento e processamento passam a apresentar limitações de:

* capacidade;
* desempenho;
* custo;
* tempo de resposta;
* manutenção.

Exemplos de crescimento de volume incluem:

* milhões de pedidos em plataformas digitais;
* catálogos extensos de produtos;
* históricos de acesso e navegação;
* registros contínuos de sensores;
* acúmulo de dados históricos para treinamento de modelos.

#### Exemplo prático de volume

Uma plataforma de e-commerce registra:

* 200 mil pedidos por dia;
* 8 milhões de eventos de clique por dia;
* 50 mil novas avaliações textuais por semana;
* 3 anos de histórico para modelos preditivos.

Mesmo que cada registro isolado seja pequeno, o conjunto acumulado rapidamente passa da escala tratável por processos locais simples.

#### Exemplo SQL para medir crescimento de volume

```sql
SELECT
    DATE(data_evento) AS dia,
    COUNT(*) AS total_eventos
FROM eventos_navegacao
GROUP BY DATE(data_evento)
ORDER BY dia;
```

Esse tipo de consulta ajuda a enxergar o crescimento do volume ao longo do tempo.

#### 2.2. Velocidade

A velocidade refere-se tanto à rapidez com que os dados são gerados quanto à rapidez com que precisam ser processados e consumidos. Em muitos cenários, não basta apenas armazenar grandes volumes; é necessário reagir em prazos curtos para que a informação tenha utilidade prática.

A velocidade está associada a situações como:

* captura contínua de eventos;
* atualização frequente de indicadores;
* resposta operacional com baixa latência;
* alimentação rápida de sistemas analíticos;
* uso em aplicações inteligentes e mecanismos de decisão automática.

A relevância da velocidade aumenta em ambientes que demandam:

* monitoramento quase em tempo real;
* detecção de fraude;
* recomendação online;
* ajuste dinâmico de campanhas;
* observação contínua de comportamento do usuário.

#### Exemplo prático de velocidade

Um sistema antifraude precisa avaliar uma compra em segundos. Se o dado chegar tarde ou o processamento for lento, a decisão perde valor operacional.

Outro exemplo: uma recomendação de produto exibida minutos depois da navegação do usuário pode ser muito menos útil do que uma recomendação exibida durante a sessão.

#### Exemplo de consulta operacional de baixa latência

```sql
SELECT status_pagamento, valor_total
FROM pedidos
WHERE pedido_id = 8745123;
```

Essa consulta é pontual, rápida e típica de ambientes que exigem resposta imediata.

#### 2.3. Variedade

A variedade diz respeito à diversidade de formatos, estruturas e origens dos dados. Diferentemente de contextos mais tradicionais, em que predominavam tabelas relacionais bem definidas, os ecossistemas modernos lidam com uma combinação ampla de estruturas.

Entre os formatos e tipos mais comuns estão:

* tabelas transacionais;
* arquivos CSV;
* documentos JSON;
* logs de aplicações;
* mensagens de eventos;
* textos livres;
* imagens;
* áudios;
* vídeos;
* grafos de relacionamento.

A variedade aumenta a complexidade porque exige:

* modelagens distintas;
* diferentes estratégias de armazenamento;
* múltiplos mecanismos de leitura e transformação;
* flexibilidade para evolução de esquema;
* maior cuidado na integração entre fontes.

#### Exemplo prático de variedade

No mesmo negócio podem coexistir:

* uma tabela relacional de pedidos;
* um arquivo JSON com características de produtos;
* avaliações em texto;
* imagens de catálogo;
* logs técnicos de servidores;
* relações entre usuários e produtos clicados.

#### Exemplo de estrutura relacional e documental

Tabela relacional simplificada:

```sql
CREATE TABLE pedidos (
    pedido_id BIGINT PRIMARY KEY,
    cliente_id BIGINT,
    data_pedido TIMESTAMP,
    valor_total NUMERIC(12,2),
    status VARCHAR(30)
);
```

Documento de catálogo em MongoDB:

```javascript
{
  _id: 9981,
  nome: "Smartphone X",
  categoria: "eletronicos",
  preco: 1299.90,
  atributos: {
    memoria: "128GB",
    cor: "preto",
    tela: "6.4"
  },
  avaliacoes_media: 4.6
}
```

O exemplo mostra que nem todos os dados são naturalmente modelados com a mesma abordagem.

#### 2.4. Veracidade

A veracidade trata da confiabilidade, da consistência e da qualidade dos dados. Em ambientes de escala, problemas de qualidade tendem a se multiplicar, seja por integração entre múltiplas fontes, seja por inconsistências operacionais, registros duplicados, campos ausentes, erros de preenchimento ou divergências semânticas.

A veracidade afeta diretamente:

* a confiança nas análises;
* a robustez de modelos preditivos;
* a interpretação de indicadores;
* a eficácia de decisões automatizadas;
* a credibilidade das áreas de dados.

Aspectos típicos de veracidade incluem:

* duplicidade de registros;
* campos nulos;
* categorias mal preenchidas;
* eventos incompletos;
* divergência entre sistemas;
* inconsistência temporal;
* falta de padronização.

#### Exemplo prático de problema de veracidade

Considere uma base de clientes em que o mesmo usuário aparece três vezes com nomes levemente diferentes. Em um dashboard isso pode inflar a base de clientes. Em um modelo de churn, isso pode distorcer frequência de compra e histórico do usuário.

#### Exemplo SQL para detectar possíveis duplicidades

```sql
SELECT
    email,
    COUNT(*) AS total_registros
FROM clientes
GROUP BY email
HAVING COUNT(*) > 1;
```

#### Exemplo SQL para medir nulos em uma coluna crítica

```sql
SELECT
    COUNT(*) AS total_linhas,
    SUM(CASE WHEN categoria IS NULL THEN 1 ELSE 0 END) AS categorias_nulas
FROM produtos;
```

#### 2.5. Valor

O valor é a dimensão que conecta dados à geração de resultados concretos para a organização. Dados só têm relevância estratégica quando podem ser transformados em informação útil, conhecimento acionável, melhoria operacional ou vantagem competitiva.

O valor pode se manifestar em diferentes formas:

* geração de insights de negócio;
* suporte à decisão;
* automação de processos;
* personalização de produtos e serviços;
* previsão de demanda;
* identificação de risco;
* melhoria de eficiência;
* desenvolvimento de aplicações de IA.

A existência de volume, velocidade e variedade não garante valor. O valor depende da capacidade organizacional e tecnológica de transformar dados em uso efetivo.

#### Exemplo prático de valor

Dois cenários distintos:

* empresa A armazena bilhões de eventos, mas não consegue usá-los em nenhuma decisão concreta;
* empresa B usa dados de navegação e compras para recomendar produtos, reduzir abandono de carrinho e aumentar conversão.

A segunda extrai valor. A primeira apenas acumula dados.

#### Exemplo analítico simples para geração de valor

```sql
SELECT
    categoria,
    COUNT(*) AS total_pedidos,
    SUM(valor_total) AS receita
FROM pedidos
GROUP BY categoria
ORDER BY receita DESC;
```

Essa análise pode apoiar decisão comercial, estoque e planejamento.

---

### 3. Tipos de dados: estruturados, semiestruturados e não estruturados

A compreensão dos tipos de dados é central para a definição de arquitetura, modelagem, armazenamento e processamento. Em contextos de Big Data, a diversidade estrutural dos dados é uma das principais razões pelas quais soluções tradicionais isoladas se tornam insuficientes.

#### 3.1. Dados estruturados

São dados organizados em esquemas rígidos e previsíveis, normalmente representados em tabelas com linhas e colunas. Possuem tipos bem definidos, integridade mais facilmente controlável e grande aderência a bancos relacionais e consultas SQL.

Exemplos comuns:

* pedidos;
* clientes;
* pagamentos;
* estoque;
* faturamento;
* cadastros formais;
* transações bancárias;
* registros contábeis.

Principais características:

* esquema definido previamente;
* facilidade de consulta e agregação;
* maior padronização;
* boa aderência a análise tabular e relatórios;
* forte uso em sistemas OLTP e OLAP.

#### Exemplo de estrutura relacional

```sql
CREATE TABLE clientes (
    cliente_id BIGINT PRIMARY KEY,
    nome VARCHAR(200),
    email VARCHAR(200),
    data_cadastro DATE,
    cidade VARCHAR(100),
    estado CHAR(2)
);
```

Esse tipo de estrutura é ideal quando os atributos são estáveis e bem definidos.

#### 3.2. Dados semiestruturados

São dados que possuem algum grau de organização, mas não necessariamente um esquema rígido e uniforme. Frequentemente usam estruturas de pares chave-valor, documentos hierárquicos ou registros cujos campos podem variar entre ocorrências.

Exemplos comuns:

* JSON de APIs;
* catálogos de produtos com atributos variáveis;
* logs estruturados;
* eventos de navegação;
* documentos XML;
* mensagens de integrações.

Principais características:

* estrutura flexível;
* campos variáveis entre registros;
* facilidade para representar heterogeneidade;
* necessidade de tratamento específico para análise;
* boa aderência a bancos documentais e pipelines de ingestão.

#### Exemplo de documento JSON

```json
{
  "produto_id": 501,
  "nome": "Tênis esportivo",
  "categoria": "calcados",
  "atributos": {
    "cor": "azul",
    "tamanho": 42,
    "material": "sintetico"
  }
}
```

Um produto de outra categoria pode possuir atributos completamente diferentes, o que torna o modelo documental conveniente.

#### Exemplo de inserção em MongoDB

```javascript
db.produtos.insertOne({
  produto_id: 501,
  nome: "Tênis esportivo",
  categoria: "calcados",
  atributos: {
    cor: "azul",
    tamanho: 42,
    material: "sintetico"
  }
})
```

#### 3.3. Dados não estruturados

São dados que não se organizam de forma natural em tabelas ou esquemas convencionais. Em geral, exigem técnicas específicas de armazenamento, indexação, extração de atributos e análise.

Exemplos comuns:

* textos livres;
* avaliações escritas por usuários;
* imagens;
* vídeos;
* áudios;
* documentos digitalizados;
* e-mails;
* conversas em atendimento.

Principais características:

* ausência de estrutura tabular nativa;
* necessidade de pré-processamento;
* maior complexidade para análise;
* forte relevância para IA, NLP e visão computacional;
* potencial elevado de geração de insight, desde que bem tratado.

#### Exemplo prático de dado não estruturado

Uma avaliação de produto escrita livremente:

> "O celular tem ótima bateria, mas a câmera noturna deixou a desejar."

Esse dado não cabe diretamente em métricas tabulares sem algum processamento adicional, como análise de sentimento, extração de tópicos ou classificação.

#### Exemplo simples de tabela para metadados de arquivos

```sql
CREATE TABLE midias_produto (
    media_id BIGINT PRIMARY KEY,
    produto_id BIGINT,
    tipo_arquivo VARCHAR(20),
    caminho_arquivo TEXT,
    data_upload TIMESTAMP
);
```

Note que, muitas vezes, o banco guarda os **metadados** do arquivo, enquanto o conteúdo bruto fica em armazenamento de objetos ou sistema de arquivos distribuído.

#### 3.4. Relação entre os tipos de dados

Em ambientes reais, os três tipos frequentemente coexistem. Um mesmo caso de negócio pode envolver:

* dados estruturados para registrar transações;
* dados semiestruturados para representar atributos dinâmicos;
* dados não estruturados para capturar contexto, comportamento e percepção do usuário.

Essa coexistência exige arquiteturas mais flexíveis e reforça a necessidade de escolhas tecnológicas orientadas ao tipo de dado e ao padrão de uso.

#### Exemplo integrador

No marketplace:

* pedidos = estruturados;
* catálogo = semiestruturado;
* avaliações e imagens = não estruturados.

Cada tipo pode exigir estratégia distinta de persistência, indexação e processamento.

---

### 4. Diferenças entre OLTP, OLAP e workloads de ciência de dados

Uma das distinções mais importantes em ecossistemas de dados é a diferença entre tipos de workload, isto é, entre padrões de uso e processamento. Essa distinção ajuda a compreender por que uma única tecnologia raramente atende de forma ótima todas as necessidades de uma organização.

#### 4.1. OLTP — Online Transaction Processing

OLTP refere-se aos sistemas voltados para operações do dia a dia. Seu objetivo principal é registrar e manter transações de negócio com rapidez, consistência e confiabilidade.

Exemplos típicos:

* registrar um pedido;
* processar um pagamento;
* atualizar o estoque;
* cadastrar um cliente;
* alterar o status de uma entrega.

Características principais:

* muitas operações curtas e frequentes;
* grande volume de leitura e escrita transacional;
* baixa latência;
* alta consistência;
* forte normalização dos dados;
* foco na integridade operacional.

O desempenho em OLTP depende da capacidade de responder rapidamente a operações pontuais e simultâneas, sem comprometer a consistência do sistema.

#### Exemplo SQL de OLTP

```sql
BEGIN;

INSERT INTO pedidos (pedido_id, cliente_id, data_pedido, valor_total, status)
VALUES (1009001, 321, CURRENT_TIMESTAMP, 249.90, 'aguardando_pagamento');

UPDATE estoque
SET quantidade = quantidade - 1
WHERE produto_id = 8801;

COMMIT;
```

Esse é um exemplo típico de transação operacional: curta, precisa e sensível à consistência.

#### 4.2. OLAP — Online Analytical Processing

OLAP refere-se a workloads voltados para análise. O foco está em consultas mais pesadas, agregações, cruzamentos dimensionais e exploração histórica dos dados para suporte à decisão.

Exemplos típicos:

* vendas por região e período;
* ticket médio por categoria;
* análise de sazonalidade;
* desempenho por canal de aquisição;
* comparação entre períodos.

Características principais:

* consultas complexas;
* leitura intensiva;
* agregações e joins frequentes;
* visão histórica e analítica;
* organização voltada para exploração de dados;
* menor ênfase em escrita transacional contínua.

Sistemas OLAP são desenhados para responder perguntas sobre o negócio, não para registrar operações em tempo real.

#### Exemplo SQL de OLAP

```sql
SELECT
    d.ano,
    d.mes,
    c.regiao,
    p.categoria,
    SUM(f.valor_total) AS receita,
    COUNT(*) AS total_pedidos
FROM fato_vendas f
JOIN dim_data d ON f.data_id = d.data_id
JOIN dim_cliente c ON f.cliente_id = c.cliente_id
JOIN dim_produto p ON f.produto_id = p.produto_id
GROUP BY d.ano, d.mes, c.regiao, p.categoria
ORDER BY d.ano, d.mes, receita DESC;
```

Essa consulta representa um padrão típico de análise multidimensional.

#### 4.3. Workloads de ciência de dados

Workloads de ciência de dados envolvem exploração, experimentação, preparação de dados, construção de atributos, treinamento de modelos, avaliação de resultados e, em alguns casos, inferência em produção.

Exemplos típicos:

* previsão de churn;
* recomendação de produtos;
* classificação de risco;
* previsão de demanda;
* detecção de fraude;
* segmentação de clientes.

Características principais:

* combinação de múltiplas fontes;
* uso intensivo de dados históricos;
* necessidade de transformações complexas;
* dados frequentemente em grande escala;
* experimentação iterativa;
* dependência de qualidade e rastreabilidade;
* integração entre estatística, computação e domínio do negócio.

Esses workloads diferem de OLTP e OLAP porque frequentemente exigem maior flexibilidade, uso de grandes volumes, múltiplos formatos e processamento exploratório.

#### Exemplo prático de preparação de dados para ciência de dados

Objetivo: prever probabilidade de recompra de clientes.

Possíveis variáveis:

* número de compras nos últimos 90 dias;
* ticket médio;
* tempo desde a última compra;
* número de categorias consumidas;
* total de sessões no site;
* taxa de abandono de carrinho.

#### Exemplo SQL para geração de atributos

```sql
SELECT
    cliente_id,
    COUNT(*) AS total_pedidos_90d,
    AVG(valor_total) AS ticket_medio_90d,
    MAX(data_pedido) AS ultima_compra,
    COUNT(DISTINCT categoria) AS total_categorias_90d
FROM pedidos
WHERE data_pedido >= CURRENT_DATE - INTERVAL '90 days'
GROUP BY cliente_id;
```

Esse tipo de consulta já não é apenas operacional ou puramente gerencial: ele apoia construção de dataset para modelagem.

#### Exemplo comparativo resumido

| Tipo de workload | Foco principal                   | Exemplo                        | Requisito dominante                        |
| ---------------- | -------------------------------- | ------------------------------ | ------------------------------------------ |
| OLTP             | operação do negócio              | registrar pedido               | baixa latência e consistência              |
| OLAP             | análise gerencial                | analisar vendas por período    | leitura e agregação eficientes             |
| Ciência de dados | previsão, descoberta e modelagem | recomendação, fraude, previsão | flexibilidade, escala e preparação robusta |

#### 4.4. Implicação arquitetural

A distinção entre OLTP, OLAP e workloads de ciência de dados mostra que os dados não são consumidos sempre da mesma maneira. Isso implica que:

* bancos transacionais não devem ser sobrecarregados com análises pesadas;
* ambientes analíticos precisam ser organizados para consulta eficiente;
* workloads de IA requerem bases integradas, limpas e historicamente consistentes;
* a arquitetura de dados precisa ser pensada em função dos usos.

#### Exemplo de erro comum

Executar consultas analíticas com múltiplos joins e agregações diretamente no banco que sustenta checkout e pagamento pode degradar a operação do negócio.

---

### 5. Papel da engenharia de dados no ciclo de analytics e IA

A engenharia de dados ocupa posição central nos ecossistemas modernos porque é a área responsável por transformar dados dispersos, heterogêneos e brutos em ativos confiáveis e utilizáveis para análise, automação e inteligência artificial.

#### 5.1. Engenharia de dados como função estruturante

Em termos gerais, a engenharia de dados atua na construção e manutenção da infraestrutura lógica e operacional que permite:

* coletar dados;
* integrar fontes diversas;
* armazenar dados adequadamente;
* transformar e padronizar registros;
* garantir qualidade;
* disponibilizar dados para consumo;
* sustentar pipelines escaláveis e reprodutíveis.

Ela não se limita ao aspecto técnico de mover dados de um ponto a outro. Seu papel envolve decisões arquiteturais que afetam desempenho, custo, governança, confiabilidade e capacidade analítica.

#### Exemplo prático

Sem uma camada de engenharia de dados, um cientista de dados pode precisar:

* extrair manualmente arquivos de múltiplos sistemas;
* corrigir inconsistências de schema a cada semana;
* reconciliar chaves de clientes duplicadas;
* criar bases temporárias sem rastreabilidade.

Com engenharia de dados bem estabelecida, essas etapas passam a ocorrer em pipelines padronizados e auditáveis.

#### 5.2. Etapas do ciclo de dados para analytics e IA

No ciclo de analytics e IA, a engenharia de dados participa de diversas etapas, como:

##### a) Ingestão

Coleta de dados oriundos de diferentes fontes, como sistemas transacionais, APIs, logs, arquivos, eventos e bases externas.

##### Exemplo

Receber pedidos de um banco relacional, catálogo de uma API e eventos de clique de uma fila de mensagens.

##### b) Armazenamento

Definição de onde e como os dados serão armazenados, considerando formato, custo, escalabilidade, consulta e evolução futura.

##### Exemplo

Salvar dados brutos em armazenamento de objetos e transformar dados analíticos em Parquet particionado por data.

##### c) Transformação

Limpeza, padronização, enriquecimento, deduplicação, tipagem, junção de fontes e preparação dos dados para consumo.

##### Exemplo SQL de transformação

```sql
SELECT
    CAST(cliente_id AS BIGINT) AS cliente_id,
    LOWER(TRIM(email)) AS email_padronizado,
    COALESCE(cidade, 'nao_informada') AS cidade,
    data_cadastro
FROM staging_clientes;
```

##### d) Organização analítica

Estruturação dos dados em camadas, tabelas analíticas, datasets confiáveis ou visões específicas para diferentes usos.

##### Exemplo

Criar uma tabela analítica com vendas diárias por categoria e região para alimentar dashboards.

##### e) Disponibilização

Entrega dos dados para consumo por analistas, cientistas de dados, sistemas de visualização, aplicações e modelos.

##### Exemplo

Expor uma tabela gold para BI e um dataset de features para treino de modelo.

##### f) Monitoramento e confiabilidade

Acompanhamento da qualidade dos dados, da execução dos pipelines, de falhas, atrasos, inconsistências e impactos operacionais.

##### Exemplo

Alertar quando o volume diário de pedidos cair abruptamente ou quando um campo crítico vier nulo acima do limite aceitável.

#### 5.3. Relação com analytics

Para analytics, a engenharia de dados garante que indicadores, painéis e análises sejam construídos sobre dados consistentes, atualizados e compreensíveis. Sem essa base, os resultados analíticos podem ser lentos, incorretos ou não reprodutíveis.

#### Exemplo

Um dashboard de receita diária só é confiável se houver:

* integração correta entre pedidos e pagamentos;
* tratamento de cancelamentos;
* padronização de datas;
* atualização consistente.

#### 5.4. Relação com inteligência artificial

Para IA, a engenharia de dados é ainda mais crítica. Modelos dependem de dados históricos confiáveis, bem preparados e representativos. Problemas de qualidade, ausência de integração, atraso de atualização ou inconsistência semântica afetam diretamente:

* desempenho dos modelos;
* generalização;
* interpretação dos resultados;
* robustez operacional;
* confiança no uso da IA.

Além disso, aplicações inteligentes frequentemente exigem fluxos contínuos de atualização, integração entre dados online e offline e capacidade de servir informações com baixa latência.

#### Exemplo prático

Um modelo de recomendação precisa combinar:

* histórico de compra;
* eventos de clique;
* atributos de produto;
* disponibilidade de estoque.

Se esses dados estiverem desalinhados temporalmente ou mal integrados, a recomendação perde qualidade.

#### 5.5. Engenharia de dados como ponte entre negócio e tecnologia

A engenharia de dados também cumpre um papel de tradução entre necessidades do negócio e soluções tecnológicas. Ela ajuda a responder questões como:

* quais dados são relevantes para determinada decisão;
* onde estão os gargalos do fluxo atual;
* que arquitetura suporta o crescimento esperado;
* como equilibrar custo e desempenho;
* que formato e organização favorecem análise futura;
* como garantir que dados operacionais virem ativos analíticos.

#### Exemplo de decisão arquitetural

Problema: consultas analíticas estão lentas no banco transacional.

Possível decisão de engenharia:

* manter OLTP para operação;
* extrair dados para camada analítica;
* organizar dados em formato colunar;
* permitir consultas pesadas fora do ambiente operacional.

#### 5.6. Síntese conceitual

No contexto de Big Data, a engenharia de dados deixa de ser apenas suporte técnico e passa a ser parte estratégica da organização. Ela viabiliza o uso efetivo dos dados em ambientes complexos, sustentando desde relatórios tradicionais até pipelines analíticos avançados e aplicações de IA.

---

### 6. Síntese integradora do tema

O problema de dados em escala surge quando o crescimento do negócio, a multiplicidade de fontes, a velocidade de geração de eventos e a diversidade de usos tornam insuficientes as abordagens centralizadas e tradicionais. Nesse cenário, Big Data deve ser entendido como uma combinação de desafios de volume, velocidade, variedade, veracidade e valor.

A compreensão dos tipos de dados e dos diferentes workloads é indispensável para a leitura correta das demandas de negócio e para o desenho de arquiteturas coerentes. Enquanto sistemas OLTP priorizam operação e consistência, ambientes OLAP favorecem análise histórica e workloads de ciência de dados exigem flexibilidade, integração e escala para suportar processos de descoberta e inteligência artificial.

Nesse contexto, a engenharia de dados assume papel estruturante, organizando o fluxo que transforma dados dispersos em base confiável para analytics e IA. O tema introdutório da disciplina, portanto, estabelece os fundamentos conceituais para as discussões posteriores sobre armazenamento em escala, processamento distribuído, pipelines de dados, arquiteturas analíticas e tecnologias NoSQL.

#### Exemplo final integrador

Em um marketplace em crescimento:

* o banco OLTP registra pedidos, pagamentos e atualizações de estoque;
* uma camada analítica consolida histórico para dashboards e indicadores;
* eventos de navegação e catálogo semiestruturado alimentam modelos de recomendação;
* avaliações textuais e imagens ampliam o uso de IA;
* pipelines de engenharia de dados garantem integração, qualidade e disponibilidade.

A visão integrada do tema mostra que Big Data não é apenas uma questão de tamanho. É uma questão de arquitetura, uso, processamento e geração de valor.

#### Perguntas de reflexão para fechar o conteúdo

1. Em que momento uma arquitetura tradicional deixa de ser suficiente para um negócio digital?
2. Por que o crescimento do volume, sozinho, não explica todo o problema de Big Data?
3. Quais tipos de dados do marketplace exigiriam soluções diferentes de armazenamento?
4. Por que OLTP, OLAP e ciência de dados não devem disputar os mesmos recursos da mesma forma?
5. Como a engenharia de dados sustenta analytics e IA de forma confiável?
