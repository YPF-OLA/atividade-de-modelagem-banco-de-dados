## Exercício 04 Trabalhando com CRUD

```sql
INSERT INTO generos(nome) VALUES('Drama'),
('Terror'),
('Suspense'),
('Documentário');
```

```sql
INSERT INTO filmes(titulo, lancamento, genero_id) 
VALUES(
    'Ferdinand',
    '2017-12-15',
    1
),
(
    'Transformers One',
    '2024-07-26',
    2
),
(
    'Ainda Estou Aqui',
    '2024-11-07',
    3
),
(
    'Cuando acecha la maldad',
    '2024-02-01',
    4
),
(
    'Reptile',
    '2023-07-29',
    5
),
(
    'Xuxa',
    '2023-07-13',
    6
);
```

```sql
INSERT INTO filmes(duracao, sinopse, bilheteria, orcamento, filme_id) 
VALUES(
    108,
    'Ferdinand é um touro gigante, mas com um coração gentil e pacífico. ',
    296000000.00,
    111000000.00,
    1
),
(
    104,
    'A animação explora as origens da rivalidade entre Optimus Prime e Megatron, apresentando-os como amigos próximos que, eventualmente, se tornam adversários.',
    129400000.00,
    147000000.00,
    2
),
(
    ,
    '',
    ,
    ,
    3
),
(
    ,
    '',
    ,
    ,
    4
),
(
    '',
    '',
    '',
    '',
    ''
),
(
    '',
    '',
    '',
    '',
    ''
);
```

