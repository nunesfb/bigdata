## Laboratório prático com ferramentas online, SQL e gabarito

### 1. Visão geral da proposta

Este conjunto de atividades foi pensado para a aula **Introdução ao Big Data e o problema de dados em escala**, com foco em práticas que possam ser realizadas **sem programação tradicional**, usando principalmente:

* consultas SQL;
* leitura de dados tabulares e semiestruturados;
* identificação de workloads;
* análise de qualidade de dados;
* reflexão arquitetural inicial.

A proposta é especialmente adequada para uma primeira aula prática da disciplina porque permite que os estudantes:

* tenham contato com dados reais ou simulados;
* usem ferramentas simples e acessíveis no navegador;
* exercitem análise com SQL;
* conectem teoria e prática sem exigir ainda Python, Spark ou código mais avançado.

---

### 2. Ferramentas sugeridas

## 2.1. Ferramenta para SQL relacional

Pode ser usado qualquer ambiente online de banco relacional com suporte a SQL. A ideia é que os alunos consigam:

* criar tabelas;
* inserir dados;
* executar `SELECT`, `JOIN`, `GROUP BY`, `UPDATE`;
* observar a diferença entre consultas operacionais e analíticas.

## 2.2. Ferramenta para leitura de CSV e JSON via SQL

Pode ser usado um ambiente SQL no navegador que permita ler arquivos CSV e JSON, para que os estudantes percebam a diferença entre:

* dados estruturados;
* dados semiestruturados;
* formas distintas de organização e consulta.

---

### 3. Organização didática das atividades

A sequência recomendada é:

1. microlab sobre OLTP e OLAP com banco relacional;
2. microlab sobre tipos de dados com CSV e JSON;
3. microlab sobre qualidade de dados;
4. microlab sobre perguntas de negócio com SQL;
5. atividade em grupo sobre adequação entre tipo de dado e tecnologia;
6. desafio final integrador com gabarito comentado.

Essa ordem é pedagogicamente útil porque parte da execução de consultas simples, passa pela leitura dos dados e termina em reflexão sobre arquitetura.

---

# 4. Microlab 1 — OLTP x OLAP na prática

### Objetivo

Mostrar, com SQL, a diferença entre:

* consulta operacional;
* atualização transacional;
* consulta analítica agregada.

### Momento ideal da aula

Após a explicação de:

* OLTP;
* OLAP;
* workloads de ciência de dados.

### Duração sugerida

20 a 25 minutos.

### Formato

Individual ou em dupla.

---

## 4.1. Script base para os alunos

```sql
CREATE TABLE clientes (
    cliente_id INT PRIMARY KEY,
    nome VARCHAR(100),
    cidade VARCHAR(100)
);

CREATE TABLE produtos (
    produto_id INT PRIMARY KEY,
    nome VARCHAR(100),
    categoria VARCHAR(50),
    preco NUMERIC(10,2)
);

CREATE TABLE pedidos (
    pedido_id INT PRIMARY KEY,
    cliente_id INT,
    data_pedido DATE,
    status VARCHAR(30),
    valor_total NUMERIC(10,2),
    FOREIGN KEY (cliente_id) REFERENCES clientes(cliente_id)
);

CREATE TABLE itens_pedido (
    pedido_id INT,
    produto_id INT,
    quantidade INT,
    preco_unitario NUMERIC(10,2),
    FOREIGN KEY (pedido_id) REFERENCES pedidos(pedido_id),
    FOREIGN KEY (produto_id) REFERENCES produtos(produto_id)
);

INSERT INTO clientes VALUES
(1, 'Ana', 'São Paulo'),
(2, 'Bruno', 'Campinas'),
(3, 'Carla', 'Rio de Janeiro');

INSERT INTO produtos VALUES
(101, 'Mouse', 'Eletronicos', 80.00),
(102, 'Teclado', 'Eletronicos', 150.00),
(103, 'Camiseta', 'Moda', 60.00);

INSERT INTO pedidos VALUES
(1001, 1, '2026-04-01', 'pago', 230.00),
(1002, 2, '2026-04-02', 'enviado', 60.00),
(1003, 1, '2026-04-03', 'aguardando_pagamento', 80.00);

INSERT INTO itens_pedido VALUES
(1001, 101, 1, 80.00),
(1001, 102, 1, 150.00),
(1002, 103, 1, 60.00),
(1003, 101, 1, 80.00);
```

---

## 4.2. Enunciado para os alunos

Utilizando a base acima, resolva as tarefas a seguir:

1. consulte o status do pedido `1002`;
2. atualize o status do pedido `1003` para `pago`;
3. calcule o faturamento por categoria;
4. calcule o ticket médio por cliente;
5. classifique cada uma das tarefas anteriores como **OLTP** ou **OLAP**.

Ao final, responda:

**Por que as tarefas analíticas não devem disputar os mesmos recursos do banco transacional principal em um ambiente de produção?**

---

## 4.3. Gabarito

### Questão 1

```sql
SELECT status
FROM pedidos
WHERE pedido_id = 1002;
```

**Resposta esperada:** `enviado`

**Classificação:** OLTP

**Justificativa:** consulta pontual, rápida e operacional.

### Questão 2

```sql
UPDATE pedidos
SET status = 'pago'
WHERE pedido_id = 1003;
```

Consulta para verificar o resultado:

```sql
SELECT pedido_id, status
FROM pedidos
WHERE pedido_id = 1003;
```

**Resposta esperada:** pedido `1003` com status `pago`.

**Classificação:** OLTP

**Justificativa:** atualização de transação operacional.

### Questão 3

```sql
SELECT
    p.categoria,
    SUM(i.quantidade * i.preco_unitario) AS faturamento
FROM itens_pedido i
JOIN produtos p ON i.produto_id = p.produto_id
GROUP BY p.categoria
ORDER BY faturamento DESC;
```

**Resposta esperada:**

* Eletronicos = 310.00
* Moda = 60.00

**Classificação:** OLAP

**Justificativa:** consulta agregada para análise.

### Questão 4

```sql
SELECT
    cliente_id,
    AVG(valor_total) AS ticket_medio
FROM pedidos
GROUP BY cliente_id
ORDER BY cliente_id;
```

**Resposta esperada:**

* cliente 1 = 155.00
* cliente 2 = 60.00

**Classificação:** OLAP

**Justificativa:** agregação histórica por cliente.

### Questão 5 — resposta conceitual esperada

As tarefas analíticas fazem mais leitura, agregação e processamento sobre maior volume de registros. Se forem executadas no mesmo ambiente que registra pedidos e pagamentos, podem competir por CPU, memória, disco e locks, prejudicando a operação do negócio.

---

# 5. Microlab 2 — Tipos de dados com CSV e JSON

### Objetivo

Mostrar, de forma prática, a diferença entre:

* dado estruturado;
* dado semiestruturado;
* uso de SQL sobre fontes distintas.

### Momento ideal da aula

Após a explicação sobre:

* tipos de dados;
* variedade;
* ecossistema de dados em escala.

### Duração sugerida

20 a 30 minutos.

### Formato

Individual ou em dupla.

---

## 5.1. Arquivos para os alunos

### Arquivo `pedidos.csv`

```csv
pedido_id,cliente_id,data_pedido,valor_total,status
1001,1,2026-04-01,230.00,pago
1002,2,2026-04-02,60.00,enviado
1003,1,2026-04-03,80.00,aguardando_pagamento
```

### Arquivo `catalogo.json`

```json
[
  {
    "produto_id": 101,
    "nome": "Mouse",
    "categoria": "Eletronicos",
    "atributos": {
      "cor": "preto",
      "conexao": "usb"
    }
  },
  {
    "produto_id": 102,
    "nome": "Teclado",
    "categoria": "Eletronicos",
    "atributos": {
      "cor": "branco",
      "layout": "abnt2"
    }
  },
  {
    "produto_id": 103,
    "nome": "Camiseta",
    "categoria": "Moda",
    "atributos": {
      "cor": "azul",
      "tamanho": "M"
    }
  }
]
```

---

## 5.2. Enunciado para os alunos

Com base nos arquivos fornecidos, realize as tarefas abaixo:

1. leia o arquivo `pedidos.csv` e conte quantos pedidos existem;
2. leia o arquivo `catalogo.json` e liste `nome` e `categoria` dos produtos;
3. classifique cada arquivo como **estruturado** ou **semiestruturado**;
4. responda: qual formato é mais natural para um catálogo com atributos variáveis?
5. explique por que esses dois tipos de dado não precisam, necessariamente, ser armazenados da mesma forma.

---

## 5.3. Exemplos de comandos esperados

### Leitura de CSV

```sql
SELECT *
FROM read_csv_auto('pedidos.csv');
```

### Contagem de pedidos

```sql
SELECT COUNT(*) AS total_pedidos
FROM read_csv_auto('pedidos.csv');
```

### Leitura de JSON

```sql
SELECT *
FROM read_json_auto('catalogo.json');
```

### Nome e categoria

```sql
SELECT nome, categoria
FROM read_json_auto('catalogo.json');
```

---

## 5.4. Gabarito

### Questão 1

```sql
SELECT COUNT(*) AS total_pedidos
FROM read_csv_auto('pedidos.csv');
```

**Resposta esperada:** `3`

### Questão 2

```sql
SELECT nome, categoria
FROM read_json_auto('catalogo.json');
```

**Resposta esperada:**

* Mouse | Eletronicos
* Teclado | Eletronicos
* Camiseta | Moda

### Questão 3

**Classificação esperada:**

* `pedidos.csv` = estruturado
* `catalogo.json` = semiestruturado

### Questão 4

**Resposta esperada:** JSON ou modelo documental é mais natural para catálogo com atributos variáveis, porque diferentes produtos podem ter campos diferentes sem exigir um esquema relacional rígido.

### Questão 5

**Resposta conceitual esperada:**

Dados tabulares e estáveis, como pedidos, costumam se ajustar bem a modelos relacionais. Já dados com atributos variáveis, como catálogo, podem ser melhor representados em JSON ou banco documental. Isso reduz rigidez estrutural e facilita evolução do schema.

---

# 6. Microlab 3 — Qualidade de dados com SQL

### Objetivo

Mostrar que problemas de qualidade de dados afetam:

* relatórios;
* análises;
* modelos de IA;
* confiança nos dados.

### Momento ideal da aula

Após a discussão sobre:

* veracidade;
* papel da engenharia de dados;
* importância da consistência dos dados.

### Duração sugerida

15 a 20 minutos.

### Formato

Individual com correção coletiva.

---

## 6.1. Script base para os alunos

```sql
CREATE TABLE clientes_raw (
    cliente_id INT,
    nome VARCHAR(100),
    email VARCHAR(100),
    cidade VARCHAR(100)
);

INSERT INTO clientes_raw VALUES
(1, 'Ana Silva', 'ana@email.com', 'São Paulo'),
(2, 'Bruno Lima', 'bruno@email.com', 'Campinas'),
(3, 'Ana Silva', 'ana@email.com', 'Sao Paulo'),
(4, 'Carla Souza', NULL, 'Rio de Janeiro');
```

---

## 6.2. Enunciado para os alunos

Analise a tabela `clientes_raw` e resolva as tarefas abaixo:

1. identifique possíveis duplicidades por e-mail;
2. conte quantos registros têm e-mail nulo;
3. explique como esse tipo de problema pode afetar dashboards;
4. explique como esse tipo de problema pode afetar modelos preditivos;
5. proponha uma regra simples de limpeza para essa base.

---

## 6.3. Gabarito

### Questão 1

```sql
SELECT
    email,
    COUNT(*) AS total_registros
FROM clientes_raw
GROUP BY email
HAVING COUNT(*) > 1;
```

**Resposta esperada:**

* `ana@email.com` aparece 2 vezes.

### Questão 2

```sql
SELECT COUNT(*) AS emails_nulos
FROM clientes_raw
WHERE email IS NULL;
```

**Resposta esperada:** `1`

### Questão 3

**Resposta esperada:**

Duplicidades podem inflar métricas de clientes, afetar contagem de base ativa e distorcer indicadores de cadastro, recorrência e retenção.

### Questão 4

**Resposta esperada:**

Modelos preditivos podem aprender padrões errados, contar o mesmo cliente mais de uma vez ou perder registros importantes se chaves críticas estiverem ausentes ou inconsistentes.

### Questão 5

**Exemplo de resposta adequada:**

* deduplicar por e-mail;
* padronizar cidade;
* tratar nulos em e-mail segundo regra de negócio;
* criar uma chave de cliente confiável para integração.

---

# 7. Microlab 4 — Perguntas de negócio respondidas com SQL

### Objetivo

Mostrar o conceito de **valor** dos dados por meio de perguntas analíticas simples.

### Momento ideal da aula

Na parte final do desenvolvimento da aula, antes do desafio integrador.

### Duração sugerida

20 minutos.

### Formato

Em dupla.

---

## 7.1. Enunciado para os alunos

Usando a base relacional do marketplace, responda com SQL:

1. qual categoria vendeu mais?
2. qual cliente comprou mais de uma vez?
3. qual é o ticket médio dos pedidos?
4. quantos pedidos ainda não foram concluídos?
5. classifique cada pergunta como:

   * operacional;
   * gerencial;
   * potencial insumo para IA.

---

## 7.2. Gabarito

### Questão 1

```sql
SELECT
    p.categoria,
    SUM(i.quantidade * i.preco_unitario) AS receita
FROM itens_pedido i
JOIN produtos p ON i.produto_id = p.produto_id
GROUP BY p.categoria
ORDER BY receita DESC;
```

**Resposta esperada:**

* Eletronicos = 310.00
* Moda = 60.00

**Classificação:** gerencial

### Questão 2

```sql
SELECT
    cliente_id,
    COUNT(*) AS total_pedidos
FROM pedidos
GROUP BY cliente_id
HAVING COUNT(*) > 1;
```

**Resposta esperada:**

* cliente 1 = 2 pedidos

**Classificação:** gerencial e potencial insumo para IA

### Questão 3

```sql
SELECT AVG(valor_total) AS ticket_medio
FROM pedidos;
```

**Resposta esperada:** aproximadamente `123.33`

**Classificação:** gerencial

### Questão 4

```sql
SELECT COUNT(*) AS pedidos_nao_concluidos
FROM pedidos
WHERE status NOT IN ('pago', 'enviado');
```

**Resposta esperada antes do update do microlab 1:** `1`

**Resposta esperada depois do update do microlab 1:** `0`

**Classificação:** operacional ou gerencial de monitoramento, dependendo da discussão do professor.

### Questão 5 — resposta esperada

* categoria que vendeu mais = gerencial;
* cliente com recorrência = gerencial e pode servir a IA;
* ticket médio = gerencial;
* pedidos não concluídos = operacional/monitoramento.

---

# 8. Atividade em grupo — Qual tecnologia ou organização inicial parece fazer mais sentido?

### Objetivo

Levar os grupos a traduzirem os dados vistos nas atividades em raciocínio arquitetural inicial.

### Momento ideal da aula

Após os microlabs, como ponte entre prática e síntese.

### Duração sugerida

20 a 25 minutos.

### Formato

Em grupo.

---

## 8.1. Enunciado para os grupos

Com base nos dados e exercícios realizados, preencham o quadro abaixo:

| Dado       | Exemplo                         | Tipo de dado | Forma de uso principal | Ajuste inicial mais natural |
| ---------- | ------------------------------- | ------------ | ---------------------- | --------------------------- |
| Pedidos    | transações de compra            |              |                        |                             |
| Catálogo   | atributos variáveis de produtos |              |                        |                             |
| Avaliações | texto livre                     |              |                        |                             |
| Navegação  | eventos e cliques               |              |                        |                             |

Depois, respondam:

1. se tudo isso fosse armazenado em um único banco relacional central, onde começariam os gargalos?
2. quais dados parecem mais adequados para uso operacional?
3. quais dados parecem mais adequados para uso analítico?
4. quais dados poderiam servir de base para aplicações de IA?

---

## 8.2. Gabarito orientador

### Preenchimento esperado

| Dado       | Exemplo                         | Tipo de dado    | Forma de uso principal                       | Ajuste inicial mais natural                      |
| ---------- | ------------------------------- | --------------- | -------------------------------------------- | ------------------------------------------------ |
| Pedidos    | transações de compra            | estruturado     | operacional e analítico                      | banco relacional                                 |
| Catálogo   | atributos variáveis de produtos | semiestruturado | consulta de produto, analytics, recomendação | JSON ou banco documental                         |
| Avaliações | texto livre                     | não estruturado | análise textual, percepção do cliente, IA    | armazenamento de arquivos/documentos + metadados |
| Navegação  | eventos e cliques               | semiestruturado | análise comportamental, funil, recomendação  | camada analítica/eventos                         |

### Respostas conceituais esperadas

**1. Onde começariam os gargalos?**

* concorrência entre OLTP e OLAP;
* dificuldade de armazenar dados flexíveis e variados;
* crescimento de volume em eventos;
* degradação de desempenho;
* limitação para analytics e IA.

**2. Dados mais adequados para uso operacional:**

* pedidos;
* pagamentos;
* estoque.

**3. Dados mais adequados para uso analítico:**

* histórico de pedidos;
* navegação;
* agregações de vendas;
* campanhas.

**4. Dados que podem servir de base para IA:**

* histórico de compra;
* navegação;
* avaliações textuais;
* catálogo de produtos.

---

# 9. Desafio final integrador

### Objetivo

Fechar a aula com uma atividade de síntese, conectando:

* SQL;
* tipos de dados;
* workloads;
* arquitetura inicial;
* perguntas de negócio e IA.

### Momento ideal da aula

Fechamento da aula.

### Duração sugerida

20 a 30 minutos.

### Formato

Em grupo.

---

## 9.1. Enunciado para os grupos

Cada grupo deve construir um quadro final contendo:

1. uma consulta SQL para responder uma pergunta de negócio;
2. a classificação dessa consulta como OLTP ou OLAP;
3. o tipo de dado principal envolvido;
4. uma observação arquitetural sobre onde esse dado faria mais sentido;
5. uma pergunta adicional de IA que poderia ser respondida a partir desse ecossistema.

O grupo deve escolher pelo menos **três perguntas** dentre as abaixo:

* quais categorias mais faturaram?
* quais clientes têm maior recorrência?
* quantos pedidos ficaram pendentes?
* como representar um catálogo com atributos variáveis?
* onde os logs de navegação deveriam entrar no ecossistema de dados?

### Formato da entrega

| Pergunta | SQL ou resposta técnica | OLTP/OLAP | Tipo de dado | Observação arquitetural | Possível uso em IA |
| -------- | ----------------------- | --------- | ------------ | ----------------------- | ------------------ |

---

## 9.2. Gabarito orientador

### Exemplo 1

| Pergunta                         | SQL ou resposta técnica                                        | OLTP/OLAP | Tipo de dado | Observação arquitetural    | Possível uso em IA                |
| -------------------------------- | -------------------------------------------------------------- | --------- | ------------ | -------------------------- | --------------------------------- |
| Quais categorias mais faturaram? | `SELECT p.categoria, SUM(i.quantidade * i.preco_unitario) ...` | OLAP      | estruturado  | melhor em camada analítica | previsão de demanda por categoria |

### Exemplo 2

| Pergunta                              | SQL ou resposta técnica                               | OLTP/OLAP | Tipo de dado | Observação arquitetural              | Possível uso em IA               |
| ------------------------------------- | ----------------------------------------------------- | --------- | ------------ | ------------------------------------ | -------------------------------- |
| Quais clientes têm maior recorrência? | `SELECT cliente_id, COUNT(*) ... HAVING COUNT(*) > 1` | OLAP      | estruturado  | histórico analítico separado do OLTP | churn, segmentação, recomendação |

### Exemplo 3

| Pergunta                           | SQL ou resposta técnica                                  | OLTP/OLAP             | Tipo de dado | Observação arquitetural                                | Possível uso em IA                    |
| ---------------------------------- | -------------------------------------------------------- | --------------------- | ------------ | ------------------------------------------------------ | ------------------------------------- |
| Quantos pedidos ficaram pendentes? | `SELECT COUNT(*) FROM pedidos WHERE status NOT IN (...)` | OLTP ou monitoramento | estruturado  | pode estar no operacional, com visões de monitoramento | risco operacional, previsão de atraso |

### Exemplo 4

| Pergunta                                              | SQL ou resposta técnica        | OLTP/OLAP                 | Tipo de dado    | Observação arquitetural                    | Possível uso em IA                |
| ----------------------------------------------------- | ------------------------------ | ------------------------- | --------------- | ------------------------------------------ | --------------------------------- |
| Como representar um catálogo com atributos variáveis? | usar JSON ou modelo documental | não se aplica diretamente | semiestruturado | melhor evitar rigidez relacional excessiva | recomendação baseada em atributos |

### Exemplo 5

| Pergunta                                   | SQL ou resposta técnica        | OLTP/OLAP                    | Tipo de dado    | Observação arquitetural                     | Possível uso em IA                                   |
| ------------------------------------------ | ------------------------------ | ---------------------------- | --------------- | ------------------------------------------- | ---------------------------------------------------- |
| Onde os logs de navegação deveriam entrar? | em camada de eventos/analítica | OLAP ou exploração analítica | semiestruturado | melhor fora do banco transacional principal | recomendação, jornada do usuário, propensão à compra |

---

# 10. Rubrica simplificada para correção

## 10.1. Critérios para os microlabs

| Critério                   | Excelente                                   | Adequado                      | Insuficiente                         |
| -------------------------- | ------------------------------------------- | ----------------------------- | ------------------------------------ |
| Execução do SQL            | executa corretamente e sem erros relevantes | executa com pequenos ajustes  | não consegue executar ou interpretar |
| Interpretação do resultado | interpreta corretamente os dados            | interpreta parcialmente       | interpreta de forma incorreta        |
| Classificação conceitual   | distingue bem OLTP, OLAP e tipo de dado     | distingue com pequenas falhas | apresenta confusão conceitual        |
| Justificativa              | argumenta com clareza                       | argumenta de forma básica     | não justifica adequadamente          |

## 10.2. Critérios para o desafio final

| Critério                       | Excelente                              | Bom                                     | Básico                          | Insuficiente         |
| ------------------------------ | -------------------------------------- | --------------------------------------- | ------------------------------- | -------------------- |
| Uso do SQL                     | consultas corretas e coerentes         | consultas adequadas com pequenas falhas | consultas incompletas           | consultas incorretas |
| Relação entre teoria e prática | integra muito bem conceito e execução  | integra bem a maior parte dos elementos | integração parcial              | pouca integração     |
| Raciocínio arquitetural        | identifica bem onde surgem os gargalos | identifica os gargalos principais       | identifica de forma superficial | não identifica       |
| Clareza da entrega             | quadro claro e organizado              | compreensível com pequenas falhas       | pouco organizado                | confuso              |

---

# 11. Fechamento sugerido para o professor

Ao final dessas atividades, o professor pode retomar a aula com uma síntese como esta:

> Nas atividades de hoje, vimos que Big Data não é apenas uma questão de quantidade de dados. O problema aparece quando diferentes tipos de dado, diferentes workloads e diferentes necessidades de negócio passam a conviver no mesmo ecossistema. O uso de SQL e de ferramentas simples já mostrou que operação, análise e preparação para IA não têm exatamente o mesmo comportamento e, por isso, não devem ser tratados sempre da mesma forma.

Essa fala ajuda a consolidar o aprendizado e prepara a transição para as próximas aulas sobre armazenamento em escala, formatos analíticos, processamento distribuído e tecnologias NoSQL.
