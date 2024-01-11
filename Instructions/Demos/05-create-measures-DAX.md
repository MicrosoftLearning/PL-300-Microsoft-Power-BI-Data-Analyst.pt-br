---
lab:
  "\_\_ title": Create measures using DAX in Power BI
  "\_\_ module": Create measures using DAX in Power BI
---
# Criar medidas usando DAX no Power BI

> **Dica**: Todos os cálculos podem ser copiados do arquivo D:\PL300\Demo\Resources\Snippets-Demo-05.txt

## Criar uma tabela calculada

1. Crie uma tabela calculada usando a seguinte expressão:

```dax
Date = CALENDARAUTO()
```

1. Alterne para o modo de exibição Dados e revise a tabela, que compreende uma única coluna de data.

Criar colunas calculadas

1. Adicionar uma coluna calculada à tabela Dates

```dax
Year = "CY" & YEAR('Date'[Date])
```

1. Adicionar uma coluna calculada à tabela Dates

```dax
Month = FORMAT('Date'[Date], "YYYY-MM")
```

1. No modo de exibição Modelo, crie uma relação arrastando a coluna Data da tabela Data para a coluna Data da tabela Vendas.

1. Ocultar a coluna OrderDate da tabela Sales.

1. Na tabela Data, crie a hierarquia Calendário, com os níveis Ano e Mês.

1. Marque a tabela Data de Conclusão como uma tabela de data usando a coluna Data de Conclusão.

1. No visual da matriz, remova a hierarquia Produtos e substitua-a pela hierarquia Calendário.

1. Adicione uma coluna calculada à tabela Salesperson.

```dax
Cost = 'Sales'[Quantity] * RELATED('Product'[Cost])
```

1. Definir o formato para duas casas decimais

## Criar uma medida rápida

1. Adicione uma medida rápida à tabela Vendas, subtraindo a coluna Custo da coluna Lucro.

1. Renomear a medida como Profit Margin

1. Explique que a medida não armazena dados no modelo.

Criar medidas regulares

1. Adicionar uma medida à tabela selecionada.

```dax
Profit Margin = DIVIDE([Profit], SUM('Sales'[Sales]))
```

1. Formate a coluna Margem de lucro como uma porcentagem.

1. Adicione outra medida à tabela Sales:

```dax
Sales YTD = TOTALYTD(SUM('Sales'[Sales]), 'Date'[Date])
```

1. Formate a coluna YTD de vendas com duas casas decimais.

## Validar os cálculos com o visual matricial

1. Adicione os campos Custo, Lucro, Margem de lucro e YTD de vendas ao visual da matriz.

1. Salve o arquivo do Power BI Desktop.

1. Deixe o arquivo do Power BI Desktop aberto para uma demonstração posterior.
