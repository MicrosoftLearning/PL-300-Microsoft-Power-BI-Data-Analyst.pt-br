---
lab:
  "\_\_ title": (Optional) Optimize model performance in Power BI
  "\_\_ module": Optimize model performance in Power BI
---

# Otimizar o desempenho do modelo

## Revisar um design de modelo DirectQuery

> **Observação**: esta demonstração usa um arquivo diferente do Power BI Desktop.

1. Abra o arquivo D:\PL300\Demo\Resources\AW Sales Analysis.pbix.

1. Se for solicitado a se conectar à fonte de dados, clique em Conectar.

1. No canto inferior direito, aponte que o modelo de dados compreende tabelas DirectQuery.

1. Salve o arquivo do Power BI Desktop na pasta D:\PL300\Demo\MySolution.

1. No modo de exibição Modelo, introduza o design do modelo, que inclui duas tabelas relacionadas.

1. No modo de exibição Relatório, interaja com o relatório selecionando diferentes itens na segmentação de dados Ano Fiscal.

1. Analise detalhadamente qualquer coluna do mês para revelar os detalhes do pedido.

1. Retorne à página Resumo de Vendas.

## Examinar desempenho de consulta lenta

1. Na guia Exibir faixa de opções, mostre o painel Analisador de Desempenho.

1. Atualize os elementos visuais e expanda a segmentação de dados e o visual Vendas por Mês.

1. Saliente que eles usaram o modo DirectQuery (os dados foram solicitados da fonte de dados).

## Configurar tabelas de armazenamento duplas

1. No modo de exibição Modelo, selecione a tabela Data e selecione o modo de armazenamento como Dual.

1. Quando os dados tiverem sido importados, alterne para o modo Relatório e, no painel Analisador de Desempenho, atualize os elementos visuais.

1. Saliente que a tabela Date agora é consultada a partir do cache do modelo.

## Criar agregações

1. Abra a janela do Editor do Power Query e, no painel Consultas, duplique a consulta Vendas do Revendedor.

1. Renomeie a nova consulta como Revendedor de Vendas Agg.

1. Aplique um grupo por transformação, da seguinte maneira:

    - Agrupar por OrderDate.

    - Nova coluna: Sales, que é a soma da coluna SalesAmount.

1. Feche e aplique as consultas.

1. No modo de exibição Modelo, defina o modo de armazenamento da tabela Agg de vendas do revendedor como Importar.

1. Crie uma relação a partir da coluna Data da tabela Data para a coluna OrderDate da tabela Agg de vendas do revendedor — certifique-se de que a cardinalidade da coluna esteja definida como um-para-muitos, com a tabela Date em um lado.

1. Gerencie agregações na tabela Agg de vendas do revendedor:

    - OrderDate: agrupe pela coluna OrderDate da tabela Reseller Sales.

    - Vendas: Somar a coluna SalesAmount da tabela Vendas do revendedor.

1. Saliente que a tabela de agregação agora está oculta.

1. Alterne para o modo de exibição Relatório e no painel Analisador de Desempenho e atualize os elementos visuais.

1. Saliente que a tabela Vendas por Mês agora é consultada a partir do cache do modelo.

1. Faça drill through a partir de qualquer mês e aponte que os detalhes na tabela são solicitados como DirectQuery da fonte de dados.

1. Salve o arquivo do Power BI Desktop.

1. Feche o Power BI Desktop.

> **Observação**: você não usará essa solução do Power BI Desktop novamente.
