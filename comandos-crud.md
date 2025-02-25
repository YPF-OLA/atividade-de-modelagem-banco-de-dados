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
INSERT INTO fabricantes (nome) VALUES('Microsof');

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