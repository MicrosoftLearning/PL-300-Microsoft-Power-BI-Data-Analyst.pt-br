---
lab:
  "\_\_ title": 'Clean, transform, and load data in Power BI'
  "\_\_ module": 'Clean, transform, and load data in Power BI'
---
# Limpar, transformar e carregar dados no Power BI

## Aplicar transformações

1. Primeiro, aplique transformações à consulta Produto.

1. Remova as colunas RetailPrice, Photo e Sales.

1. Altere o tipo de dados da coluna Canais para Número Inteiro.

1. Renomear as seguintes colunas:

    - ProductSKU para SKU

    - NomeProduto Produto Um

    - ProductCategory[CategoryId]

    - ItemGroup para Grupo de Itens

    - KitType para Tipo de Kit

1. Em segundo lugar, aplique transformações à consulta Sales.

1. Remova todas as colunas, exceto ,  e .

    - OrderDate

    - ProductID

    - Quantidade

    - UnitPrice

1. Altere o tipo de dados da coluna PreçoUnitário para Número Decimal Fixo.

1. Renomeie a coluna PreçoUnitário para Preço Unitário.

1. Selecione várias das colunas Quantidade e Preço Unitário e adicione uma nova coluna com base em sua multiplicação.

1. Renomeie a nova coluna como Escala.

## Integrar consultas

1. Crie uma nova consulta usando o conector do Excel, conectando-se ao arquivo D:\PL300\Demo\Data\ProductCost.xlsx.

1. Remova a coluna Status do Produto.

1. Altere o tipo de dados da coluna ProductCost para Número decimal fixo.

1. Selecione a consulta Produto e mescle com a consulta ProductCost, relacionando as colunas SKU.

1. Na janela Níveis de Privacidade, defina o nível de privacidade de D:\ como Organizacional.

1. Expanda a coluna ProductCost para incluir a coluna ProductCost (da consulta ProductCost).

1. Renomeie a nova coluna como Escala.

## Desabilitar e carregar consultas no modelo de dados

1. No painel Consultas, desabilite a consulta ProductCost.

1. Na guia da faixa de opções Página Inicial, clique no ícone Fechar & Aplicar.

1. No Power BI Desktop, aponte as duas tabelas no painel Dados.

1. Salve o arquivo do Power BI Desktop.

1. Deixe o arquivo do Power BI Desktop aberto para a próxima demonstração.
