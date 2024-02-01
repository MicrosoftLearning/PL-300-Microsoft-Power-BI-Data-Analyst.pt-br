---
demo:
  course: PL-300
  title: (Opcional) Otimizar o desempenho do modelo no Power BI
  module: Optimize model performance in Power BI
---

# (Opcional) Otimizar o desempenho do modelo

## Revisar um design de modelo DirectQuery

> **Nota**: esta demonstração usa um arquivo diferente do Power BI Desktop.

1. Abra o arquivo D:\Allfiles\Demo\Resources\AW Sales Analysis.pbix.

1. Se for solicitado a se conectar à fonte de dados, clique em Conectar.

1. No canto inferior direito, indique que o modelo de dados compreende tabelas DirectQuery.

1. Salve o arquivo do Power BI Desktop na pasta D:\Allfiles\Demo\MySolution.

1. Na exibição Model, introduza o design do modelo, que inclui duas tabelas relacionadas.

1. Na exibição Report, interaja com o relatório selecionando diferentes itens na segmentação de dados Fiscal Year.

1. Analise detalhadamente qualquer coluna do mês para revelar os detalhes do pedido.

1. Retorne à página Sales Summary.

## Examinar o desempenho da consulta

1. Na guia Exibir faixa de opções, mostre o painel Analisador de Desempenho.

1. Atualize os elementos visuais e expanda a segmentação de dados e o visual Sales by Month.

1. Saliente que eles usaram o modo DirectQuery (os dados foram solicitados da fonte de dados).

## Configurar tabelas de armazenamento duplo

1. Na exibição Model, selecione a tabela Data e selecione o modo de armazenamento como Dual.

1. Quando os dados tiverem sido importados, alterne para a exibição Report e, no painel Analisador de Desempenho, atualize os elementos visuais.

1. Saliente que a tabela Data agora é consultada a partir do cache do modelo.

## Criar agregações

1. Abra a janela do Editor do Power Query e, no painel Consultas, duplique a consulta Reseller Sales.

1. Renomeie a nova consulta como Reseller Sales Agg.

1. Aplique um grupo por transformação, da seguinte maneira:

    - Agrupar por OrderDate.

    - Nova coluna: Sales, que é a soma da coluna SalesAmount.

1. Feche e aplique as consultas.

1. Na exibição Model, defina o modo de armazenamento da tabela Reseller Sales Agg como Import.

1. Crie uma relação a partir da coluna Data da tabela Data para a coluna OrderDate da tabela Reseller Sales Agg — certifique-se de que a cardinalidade da coluna esteja definida como um-para-muitos, com a tabela Data em um lado.

1. Gerenciar agregações na tabela Reseller Sales Agg:

    - OrderDate: agrupe pela coluna OrderDate da tabela Reseller Sales.

    - Sales: somar a coluna SalesAmount da tabela Reseller Sales.

1. Saliente que a tabela de agregação agora está oculta.

1. Alterne para a exibição Report e no painel Analisador de Desempenho e atualize os elementos visuais.

1. Saliente que a tabela Sales by Month agora é consultada a partir do cache do modelo.

1. Analise detalhadamente a partir de qualquer mês e indique que os detalhes na tabela sejam solicitados como DirectQuery da fonte de dados.

1. Salve o arquivo do Power BI Desktop.

1. Feche o Power BI Desktop.

> **Nota**: você não usará essa solução do Power BI Desktop novamente.
