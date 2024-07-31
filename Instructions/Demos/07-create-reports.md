---
demo:
  title: Criar relatórios no Power BI
  module: Create reports in Power BI
---
# Criar relatórios

## Criar um relatório de página única

1. Remova o visual da matriz que foi usado para testar e validar os cálculos do modelo.

1. Renomeie a página do relatório como Sales Summary.

## Adicionar uma segmentação

1. Adicione uma segmentação de dados para a coluna Year da tabela Date e posicione-a no canto superior esquerdo da página do relatório.

1. Use as opções de formatação para configurar a segmentação de dados para seleção única.

## Adicionar vários elementos visuais

1. Adicione um gráfico de linhas e colunas empilhadas à página e configure-o da seguinte maneira:

    - Eixo compartilhado: Date | Month

    - Valores das colunas: Sales | Sales

    - Valores de linha: Sales | Profit Margin

1. Use a segmentação de dados para filtrar a página por CY2019 e, em seguida, CY2020.

1. No gráfico de linhas e colunas empilhadas, indique que não há coluna de vendas para dezembro de 2020.

1. Configure o eixo compartilhado para "mostrar itens sem dados".

1. Ressalte que dezembro de 2020 foi adicionado ao eixo, mas não há coluna de dados.

1. Explique que os dados de vendas de dezembro de 2020 ainda não aconteceram. *Você executará um script em uma demonstração posterior para carregar as vendas de dezembro de 2020.*

1. Adicione um gráfico de funil e configure-o da seguinte maneira:

    - Grupo: Product | Category

    - Valores: Sales | Profit Margin

1. Use as opções de formatação para selecionar uma cor de dados contrastante.

1. Adicione um visual de Perguntas e Respostas e insira a seguinte pergunta: Total de vendas por produto demográfico

1. Salve o arquivo do Power BI Desktop.

1. Deixe o arquivo do Power BI Desktop aberto para uma demonstração posterior.
