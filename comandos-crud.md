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
```