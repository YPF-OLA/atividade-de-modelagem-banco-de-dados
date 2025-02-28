# Comandos para operações CRUD no Banco de Dados

## Resumo

- C -> **C**reate    -> **INSERT**: INSERIR dados/registros na tela

- R -> **R**ead      -> **SELECT**: consultar/ler dados/registrados na tabela

- U -> **U**pdate    -> **UPDATE**: atualizar dados/registros na tebela

- D -> **D**elete -> **DELETE**: excluir dados/registros na tabela


---

## INSERT (Fabricantes)

```sql
INSERT INTO fabricantes (nome) VALUES('Asus');
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome) VALUES('Apple');

INSERT INTO fabricantes (nome) VALUES('LG'), ('Samsung'), ('Brastemp');
```

## SELECT (Fabricantes)

```sql
SELECT * FROM fabricantes;
```

---

## INSERT (Produtos)

```sql
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
VALUES(
    'Notbook',
    'Util para trabalho...',
    2450.78,
    200,
    2   -- id do fabricante Dell
);

INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
VALUES(
    'Televisão',
    'Muito grande para assistir series e filmes e etc... com sua família',
    5490.48,
    28,
    5  -- id do fabricante Samsung
);

INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
VALUES(
   'Geladeira',
   'Congela tudo',
   4900.87,
   38,
   6 -- Brastemp
), 
(
    'iPhone 18 Pro Max Ferradão',
    'Smartphone Apple cheio das frescura da Apple',
    13987.76,
    24,
    3 -- Apple
),
(
    'iPad Mini',
    'Tablet bom Pra caramba',
    3200.98,
    23,
    3 -- Apple
);


```


```sql
INSERT INTO fabricantes (nome) VALUES('Positivo');
INSERT INTO fabricantes (nome) VALUES('Microsoft');

```

```sql
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
VALUES(
    'Xbox Series S',
    'Velocidade e desempenho de última geração.',
    1997,
    5,
    8   
),
(
    'Notebook Motion',
    'Intel Dual Core 4GB de RAM, 128GB SSD e Tela 14,1 polegadas.',
    1213.65,
    8,
    7    
);
```

## SELECT (Produtos)

```sql
-- Lendo TODAS as colunas de TODOS os registros
SELECT * FROM produtos;

-- Lendo somente nome e preço de todos registros
SELECT nome, preco FROM produtos;
SELECT nome, preco FROM produtos;

-- Mostrando nome, preço e quantidade SOMENTE dos produtos que custam abaixo de 5000
SELECT nome, preco, quantidade FROM produtos
WHERE preco < 5000;

-- Mini-exercício: mostra o nome e descrição somente dos produtos da Apple
SELECT nome, descricao FROM produtos
WHERE fabricante_id = 3;
```

### Operador Lógicos: E, OU e NÃO

#### E (AND)

```sql
SELECT nome, preco FROM produtos
WHERE preco >= 2000 AND preco <= 6000;
```

#### OU (OR)

```sql
-- Exibir nome, descricao dos produtos da Aplle e da Samsung
SELECT nome, descricao FROM produtos
WHERE fabricante_id = 3 OR fabricante_id = 5;

-- Versão usando a função SQL IN()
SELECT nome, descricao FROM produtos
WHERE fabricante_id IN(3, 5);
```

#### NÃO (NOT)

```sql
-- Nome, descrição e preço de todos os produtos EXCETO da POSTIVO
SELECT nome, descricao, preco FROM produtos
WHERE NOT fabricante_id = 7;

-- Versão usando operador relacional de "diferente/diferença" 
SELECT nome, descricao, preco FROM produtos
WHERE NOT fabricante_id != 7;
```

---

## UPDATE (Fabricantes)

**PERIGO !**

**SEMPRE USE** A cláusula `WHERE` em seu comando `UPDATE` especificando uma ou mais condições para a atualização.

```sql
-- Trocando o nome do fabricante 
UPDATE fabricantes SET nome = 'Asus do Brasil';
WHERE id = 1;

-- Alterar a quantidade para 10 dos queustam abaixo de 2000 exceto da Microsoft.

UPDATE produtos SET quantidade = 10
WHERE preco < 2000 AND fabricante_id != 8;
```

---

## UPDATE (Fabricantes)

**PERIGO !**

**SEMPRE USE** A cláusula `WHERE` em seu comando `UPDATE` especificando uma ou mais condições para a atualização.


```sql
DELETE FROM fabricantes WHERE id = 4;
DELETE FROM fabricantes WHERE id = 1;

DELETE FROM produtos WHERE id = 4;

-- DELETE FROM fabricantes WHERE id = 3;
```

## SELECT: outras formas de uso
#### Classificação/Ordenação
```sql
-- DESC: ordena em ordem decrescente
-- ASC: ordena em ordem crescente (padrão)
SELECT nome, preco FROM produtos ORDER BY nome;
SELECT nome, preco FROM produtos ORDER BY preco;
SELECT nome, preco FROM produtos ORDER BY preco DESC;

SELECT nome, preco, quantidade FROM produtos
WHERE fabricante_id = 5 ORDER BY quantidade;
```
## Operações e funções de agregação

```sql
-- Função de SOMA (SUM)
SELECT SUM(preco) FROM produtos;

-- alias/apelido pra colunas
SELECT SUM(preco) AS Total FROM produtos;
SELECT SUM(preco) AS "Total dos Preços dos Produtos" FROM produtos; 
SELECT nome AS Produto, preco as Preço FROM produtos;
SELECT nome Produto, preco Preço FROM produtos; -- omitindo o AS

-- Funções de formatação/configuração: FORMAT e REPLACE
SELECT FORMAT(SUM(preco), 2) AS Total FROM produtos;
SELECT REPLACE(FORMAT(SUM(preco), 2), ",", ".") AS Total FROM produtos;

-- Função de média: AVG (Average) 
-- Função de arredondamento: ROUND
SELECT AVG(preco) AS "Média dos Preços" FROM produtos;
SELECT ROUND(AVG(preco), 2) AS "Média dos Preços" FROM produtos;

-- Função de contagem: COUNT
SELECT COUNT(id) AS "Qtd de Produtos" FROM produtos;
SELECT COUNT(DISTINCT fabricante_id) AS "Qtd de Fabricantes com Produtos" FROM produtos;

-- Operações matemáticas
SELECT nome, preco, quantidade, (preco * quantidade) as Total
FROM produtos;

--- Segmentação/Agrupamento de resultados
SELECT fabricante_id, SUM(preco) AS Total FROM produtos
GROUP BY fabricante_id;
```

## Consultas (Queries) em duas ou mais tabelas relacionadas (JUNÇÃO/JOIN)

### Exibir o nome do produto e o nome do fabricante do produto

```sql
-- SELECT nomeDaTabela1.nomeDaColuna, nomeDaTabela2.nomeDaColuna, 
SELECT produtos.nome AS Produto, fabricantes.nome AS Fabricante

-- JOIN permite JUNTAR as tabelas no momento do SELECT
FROM produtos JOIN fabricantes

-- ON tabela1.chave_estrangeira = tabela2.chave_primaria
ON produtos.fabricante_id = fabricantes.id;
```

## Nome do produto, preço do produto, nome do fabricante ordenados pelo nome do produto e pelo preço

```sql
SELECT 
    produtos.nome AS Produto,
    produtos.preco AS Preço,
    fabricantes.nome AS Fabricante
FROM produtos INNER JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id
ORDER BY Produto ASC, Preço DESC;
```


## Fabricante, Soma dos Preços, Quantidade de Produtos POR Fabricante

```sql
SELECT
    fabricantes.nome AS Fabricante,
    SUM(produtos.preco) AS Total,
    COUNT(produtos.fabricante_id) AS "Qtd de Produtos"
FROM produtos RIGHT JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id
GROUP BY Fabricante
ORDER BY Total;  
```  