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
INSERT INTO detalhes(duracao, sinopse, bilheteria, orcamento, filme_id) 
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
    137,
    'Ambientado no Brasil de 1971, o filme acompanha Eunice Paiva, mãe de cinco filhos, que se vê forçada a se reinventar como ativista após o desaparecimento de seu marido, Rubens Paiva, sequestrado pela Polícia Militar e desaparecido sob sua custódia.',
    27300000.00,
    1500000.00,
    3
),
(
    99,
    'Em uma cidade remota, dois irmãos encontram um homem possuído por um demônio, prestes a liberar o mal que carrega dentro dele. Ao tentarem detê-lo, acabam acelerando o processo, desencadeando algo ainda mais aterrorizante, especialmente quando esse mal ameaça se espalhar para áreas mais povoadas.',
    10000000.00,
    18300000.00,
    4
),
(
    120,
    'bom muito bom de mais',
    15200320.00,
    12000321.00,
    5
),
(
    250,
    'um filme bom de trabalhar com esses comandos.',
    132265000.00,
    150000.00,
    6
);
```



