---
demo:
  title: 'Limpar, transformar e carregar dados no Power BI'
  module: 'Clean, transform, and load data in Power BI'
---

# Limpar, transformar e carregar dados no Power BI

## Aplicar transformações de consulta

1. Primeiro, aplique transformações à consulta Product.

1. Remova as colunas RetailPrice, Photo e Sales.

1. Altere o tipo de dados da coluna Channels para Número Inteiro.

1. Renomear as seguintes colunas:

    - ProductSKU para SKU

    - ProductName para Product

    - ProductCategory para Category

    - ItemGroup para Item Group

    - KitType para Kit Type

1. Em segundo lugar, aplique transformações à consulta Sales.

1. Remova todas as colunas, exceto:

    - OrderDate

    - ProductID

    - Quantidade

    - UnitPrice

1. Altere o tipo de dados da coluna UnitPrice para Número Decimal Fixo.

1. Renomeie a coluna UnitPrice para Preço Unitário.

1. Selecione as colunas Quantity e Unit Price e adicione uma nova coluna com base em sua multiplicação.

1. Renomeie a nova coluna como Sales.

## Integrar consultas

1. Crie uma nova consulta usando o conector do Excel, conectando-se ao arquivo D:\PL300\Demo\Data\ProductCost.xlsx.

1. Remova a coluna Product.

1. Altere o tipo de dados da coluna ProductCost para Número decimal fixo.

1. Selecione a consulta Product e mescle com a consulta ProductCost, relacionando as colunas SKU.

1. Na janela Níveis de Privacidade, defina o nível de privacidade de D:\ como Organizacional.

1. Expanda a coluna ProductCost para incluir a coluna ProductCost (da consulta ProductCost).

1. Renomeie a nova coluna como Cost.

## Desabilitar e carregar consultas no modelo de dados

1. No painel Consultas, desabilite a consulta ProductCost.

1. Na guia da faixa de opções Página Inicial, clique no ícone Fechar e Aplicar.

1. No Power BI Desktop, aponte as duas tabelas no painel Dados.

1. Salve o arquivo do Power BI Desktop.

1. Deixe o arquivo do Power BI Desktop aberto para a próxima demonstração.
