# Análise de distribuição de itens - Apriori

Trabalho realizado para a disciplina de Inteligência Artificial

Departamento de Ciência da Computação - Universidade de Brasília

Este repositório explora o uso do método apriori para a resolução do problema de alocação do estoque de itens de supermercado, de modo a otimizar a distribuição de produtos que sejam comprados em conjunto com frequência.

## Dataset

O dataset utilizado é o [groceries dataset](https://www.kaggle.com/heeraldedhia/groceries-dataset) proveniente do Kaggle que consiste em um csv preparado para o estudo de regras de associação com itens de supermercado.

O arquivo é composto por 38765 linhas com as compras registradas de clientes em um supermercado, cada linha possui 3 colunas: o id do cliente, nome do produto e data da aquisição. Existem 3898 IDs únicos de clientes e 167 produtos adquiridos entre 01/01/2014 e 31/10/2015.

## Apriori

O algoritmo Apriori calcula a probabilidade de um cliente comprar o produto P2 se já adquiriu o produto P1. Ele faz isso computando o suporte, a confiança e o "lift" para diferentes combinações de produtos.

O suporte de um produto (ou de um conjunto de produtos) é tido como a probabilidade dos usuários comprarem o produto P, definido por:

![equation](https://latex.codecogs.com/png.latex?\huge&space;Suporte(P)&space;=&space;\frac{Numero\\:de\\:clientes\\:&space;que\\:&space;compraram\\:&space;P}{Numero\\:&space;total\\:&space;de\\:&space;clientes})

A confiança é o cálculo de quantos clientes compraram o produto P2 dentre os que compraram o produto P1, definido por:

![equation](https://latex.codecogs.com/png.latex?\huge&space;Confianca(P1\rightarrow&space;P2)&space;=&space;\frac{Clientes\\:&space;que\\:&space;compraram\\:&space;P1\\:&space;e\\:&space;P2}{Clientes\\:&space;que\\:&space;compraram\\:&space;P1})

O lift é a proporção entre confiança e suporte. Um lift alto sugere que há alguma relação entre os dois produtos e a maioria dos clientes que compraram o produto P1 provavelmente comprarão o produto P2.

![equation](https://latex.codecogs.com/png.latex?\huge&space;Lift(P1\rightarrow&space;P2)&space;=&space;\frac{Confianca(P1\rightarrow&space;P2)&space;}{Suporte(P1)})

O valor do lift para um determinado item em relação a outros pode ser utilizado para recomendar produtos que, no geral, são comprados em conjunto.

## Instalação

Instalação do python
```
sudo apt-get update
sudo apt-get install python3.6
```

Criação de um "virtual environment" chamado "venv" e o ativa:
```
python3 -m venv venv
source venv/bin/activate
```

Instalação dos pacotes necessários
```
python3 -m pip install -r requirements.txt
```