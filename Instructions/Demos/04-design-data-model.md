---
demo:
  title: "Criar um modelo de\_dados\_no Power BI"
  module: Design a data model in Power BI
---
# Criar um modelo de dados no Power BI

## Examinar o modelo

1. No painel Dados, expanda todas as tabelas para revelar todos os campos.

1. Na tabela Sales, indique a hierarquia OrderDate, que foi criada automaticamente.

1. Explique que uma tabela Data será criada na próxima demonstração.

1. Na exibição Model, passe o mouse sobre a relação criada automaticamente entre as duas tabelas.

1. Explicar como os filtros se propagarão da tabela Product para a tabela Sales.

## Criar uma hierarquia

1. Crie uma hierarquia com base na coluna Category da tabela Product.

1. Renomeie a hierarquia como Products.

1. Adicione a coluna Product como o segundo nível.

## Obter propriedades do modelo

1. Oculte as duas colunas ProductID.

1. Formate a coluna Quantity para usar o separador de milhares.

1. Selecione as colunas Sales e Unit Price e formate-as para usar duas casas decimais.

## Validar o design do modelo com um visual de matriz

1. Na exibição Report, adicione um visual de matriz à página e dimensione-o para preencher a página inteira.

1. Adicione a hierarquia Products às linhas e adicione os campos Quantity, Sales e Unit Price.

1. Expanda todos os níveis da hierarquia de Products.

1. Ressalte que os valores da Unit Proce são a soma dos preços, o que não está correto.

1. No painel Dados, selecione o campo Unit Price e configure seu resumo para usar Média.

1. Remova a coluna Sum of Unit Proce do visual da matriz e adicione o campo Unit Price novamente.

1. Salve o arquivo do Power BI Desktop.

1. Deixe o arquivo do Power BI Desktop aberto para a próxima demonstração.
