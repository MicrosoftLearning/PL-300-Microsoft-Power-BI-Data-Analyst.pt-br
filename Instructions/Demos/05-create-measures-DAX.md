---
demo:
  course: 'PL-300, DP-605'
  title: Criar medidas usando DAX no Power BI
  module: Create measures using DAX in Power BI
---
# Criar medidas usando DAX no Power BI

> **Dica**: Todos os cálculos podem ser copiados do arquivo D:\Allfiles\Demo\Resources\Snippets-Demo-05.txt.

## Criar uma tabela calculada

1. Crie uma tabela calculada usando a seguinte expressão:

```dax
Date = CALENDARAUTO()
```

1. Alterne para a exibição Data e revise a tabela, que compreende uma única coluna de data.

Criar colunas calculadas

1. Adicionar uma coluna calculada à tabela Data:

```dax
Year = "CY" & YEAR('Date'[Date])
```

1. Adicionar uma coluna adicional calculada à tabela Data:

```dax
Month = FORMAT('Date'[Date], "YYYY-MM")
```

1. Na exibição Model, crie uma relação arrastando a coluna Data da tabela Data para a coluna OrderDate da tabela Sales.

1. Ocultar a coluna OrderDate da tabela Sales.

1. Na tabela Data, crie a hierarquia Calendário, com os níveis Year e Month.

1. Na visualização Report, marque a tabela Data como uma tabela de datas usando a coluna Data.

1. No visual da matriz, remova a hierarquia Products e substitua-a pela hierarquia Calendar.

1. Adicione uma coluna calculada à tabela Sales:

```dax
Cost = 'Sales'[Quantity] * RELATED('Product'[Cost])
```

1. Formate a coluna Cost para duas casas decimais.

## Criar uma medida rápida

1. Adicione uma medida rápida à tabela Sales, subtraindo a coluna Cost da coluna Profit.

1. Renomeie a medida como Profit.

1. Explique que a medida não armazena dados no modelo.

Criar medidas regulares

1. Adicionar uma medida à tabela Sales:

```dax
Profit Margin = DIVIDE([Profit], SUM('Sales'[Sales]))
```

1. Formate a coluna Profit Margin como uma porcentagem.

1. Adicionar outra medida à tabela Sales:

```dax
Sales YTD = TOTALYTD(SUM('Sales'[Sales]), 'Date'[Date])
```

1. Formate a coluna Sales YTD com duas casas decimais.

## Validar os cálculos com o visual da matriz

1. Adicione os campos Cost, Profit, Profit Margin, and Sales YTD ao visual da matriz.

1. Salve o arquivo do Power BI Desktop.

1. Deixe o arquivo do Power BI Desktop aberto para uma demonstração posterior.
