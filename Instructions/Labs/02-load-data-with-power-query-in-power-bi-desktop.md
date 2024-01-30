---
lab:
  course: 'PL-300, DP-605'
  title: Carregar Dados Transformados no Power BI Desktop
  module: 'Clean, Transform, and Load Data in Power BI'
---

# Carregar Dados Transformados no Power BI Desktop

## **História do laboratório**

Neste laboratório, você usará técnicas de limpeza e transformação de dados para começar a moldar seu modelo de dados. Em seguida, você aplicará as consultas para carregar cada uma delas como uma tabela no modelo de dados.

Neste laboratório, você aprenderá a:

- Aplicar várias transformações
- Carregar consultas no modelo de dados

**Este laboratório levará aproximadamente 45 minutos.**

## **Introdução**

Nesta tarefa, você vai configurar o ambiente para o laboratório.

*Importante: se você concluiu o laboratório anterior na mesma VM, pule para a próxima tarefa.*

1. Abra o Power BI Desktop.

    *Dica: por padrão, a caixa de diálogo Introdução é aberta na frente do Power BI Desktop. Você pode optar por entrar e, em seguida, fechar o pop-up.*

    ![Ícone do Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. Para abrir o arquivo inicial do Power BI Desktop, selecione **Arquivo > Abrir Relatório > Procurar Relatórios**.

1. Na janela **Abrir**, navegue até a pasta **D:\Allfiles\Labs\02-load-data-with-power-query-in-power-bi-desktop\Starter** e abra o arquivo **Análise de Vendas**.

1. Feche todas as janelas informativas que possam ser abertas.

1. Observe a mensagem de aviso abaixo da faixa de opções.

    *Essa mensagem alerta para o fato de que as consultas não foram aplicadas para carregar como tabelas de modelo. Você aplicará as consultas posteriormente neste laboratório.*

    Para ignorar a mensagem de aviso, à direita da mensagem de aviso, selecione **X**.

1. Para criar uma cópia do arquivo, vá para **Arquivo > Salvar como** e salve na pasta **D:\Allfiles\MySolution**.

1. Caso precise aplicar as alterações, selecione **Aplicar Mais Tarde**.

## **Configurar a consulta Vendedor**

Nesta tarefa, você vai usar o Editor do Power Query para configurar a consulta **Vendedor**.

*Importante: quando você for instruído a renomear as colunas, será importante que as renomeie exatamente conforme descrito.*

1. Para abrir a janela do **Editor do Power Query**, na guia de faixa de opções **Página Inicial**, no grupo **Consultas**, selecione o ícone **Transformar Dados**.

     ![Transformar Dados na faixa de opções Página Inicial](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image10.png)

1. Na janela do **Editor do Power Query**, no painel **Consultas**, selecione a consulta **DimEmployee**.

     ![Figura 1](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image11.png)

1. Para renomear a consulta, no painel **Configurações de Consulta** (localizado à direita), na caixa **Nome**, substitua o texto por **Vendedor** e clique em **ENTER**. Em seguida, verifique se o nome foi atualizado no painel **Consultas**.

    *O nome da consulta determina o nome da tabela do modelo. Recomenda-se definir nomes concisos e fáceis de usar.*

1. Para localizar uma coluna específica, na guia de faixa de opções **Página Inicial**, no grupo **Gerenciar Colunas**, escolha a seta para baixo **Escolher Colunas** e selecione **Ir para Coluna**.

    *Ir para Coluna é um recurso útil com muitas colunas. Caso contrário, você pode rolar horizontalmente encontrar colunas.*

     ![Gerenciar colunas > Escolher colunas > Ir para coluna](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image13.png)

1. Na janela **Ir para Coluna**, para ordenar a lista pelo nome da coluna, selecione o botão de classificação **AZ**, depois selecione **Nome** e **SalesPersonFlag**. Clique em **OK.**

     ![Ir para opções de classificação de coluna](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image14.png)

1. Localize a coluna **SalesPersonFlag** e, em seguida, filtre a coluna para selecionar apenas Vendedores (ou seja, **TRUE**) e clique em **OK**.

1. No painel **Configurações de Consulta**, na lista **Etapas Aplicadas**, observe a adição da etapa **Linhas Filtradas**.

    *Cada transformação criada resulta em outra lógica de etapa. É possível editar ou excluir etapas. Também é possível selecionar uma etapa para visualizar os resultados da consulta nesse estágio da transformação da consulta.*

     ![Etapas aplicadas](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image17.png)

1. Para remover colunas, na guia de faixa de opções **Página Inicial**, no grupo **Gerenciar Colunas**, selecione o ícone **Escolher Colunas**.

1. Na janela **Escolher Colunas**, para desmarcar todas as colunas, desmarque o item **(Selecionar Todas as Colunas)**.

1. Para incluir colunas, marque as seis seguintes colunas:

    - EmployeeKey
    - EmployeeNationalIDAlternateKey
    - Nome
    - LastName
    - Título
    - EmailAddress

1. Na lista **Etapas Aplicadas**, observe a adição de outra etapa de consulta.

     ![Etapa de outras colunas removidas](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image21.png)

1. Para criar uma coluna de nome único, primeiro selecione o cabeçalho da coluna **FirstName**. Ao selecionar a tecla **CTRL**, selecione a coluna **LastName**.

     ![Seleção múltipla de duas colunas para criar uma única coluna](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image22.png)

1. Clique com o botão direito do mouse em um dos cabeçalhos da coluna selecionados e, no menu de contexto, escolha **Mesclar Colunas**.

    *Muitas transformações comuns podem ser aplicadas clicando com o botão direito do mouse no cabeçalho da coluna e escolhendo-as no menu de contexto. No entanto, observe que há mais transformações disponíveis nesta faixa de opções.*

1. Na janela **Mesclar Colunas**, na lista suspensa **Separador**, selecione **Espaço**.

1. Na caixa **Nome da Nova Coluna**, substitua o texto por **Salesperson**.

1. Para renomear a coluna **EmployeeNationalIDAlternateKey**, clique duas vezes no cabeçalho da coluna **EmployeeNationalIDAlternateKey** e substitua o texto por **EmployeeID** e pressione **Enter**.

1. Use as etapas anteriores para renomear a coluna **EmailAddress** como **UPN**.

    *UPN é um acrônimo de Nome Principal do Usuário.*

1. No canto inferior esquerdo, na barra de status, confirme se a consulta tem cinco colunas e 18 linhas.

## **Configurar a consulta SalespersonRegion**

Nesta tarefa, você vai configurar a consulta **SalespersonRegion**.

1. No painel **Consultas**, selecione a consulta **DimEmployeeSalesTerritory**.

1. No painel **Configurações de Consulta**, renomeie a consulta como **SalespersonRegion**.

1. Para remover as duas últimas colunas, primeiro, selecione o cabeçalho da coluna **DimEmployee**.

1. Selecionando a tecla **CTRL**, selecione o cabeçalho da coluna **DimSalesTerritory**.

1. Clique com o botão direito do mouse em um dos cabeçalhos da coluna selecionados e, no menu de contexto, selecione **Remover Colunas**.

1. Na barra de status, confirme se a consulta tem duas colunas e 39 linhas.

## **Configurar a consulta de Produto**

Nesta tarefa, você vai configurar a consulta **Product**.

*Importante: quando instruções detalhadas já tiverem sido fornecidas, as etapas do laboratório fornecerão instruções mais concisas. Se precisar das instruções detalhadas, consulte as etapas das tarefas anteriores.*

1. Selecione a consulta **DimProduct** e renomeie a consulta como **Produto**.

1. Localize a coluna **FinishedGoodsFlag** e filtre-a para recuperar os produtos que são mercadorias concluídas (ou seja, TRUE).

1. Remova todas as colunas, **exceto** as seguintes:

    - ProductKey
    - EnglishProductName
    - StandardCost
    - Cor
    - DimProductSubcategory

1. Observe que a coluna **DimProductSubcategory** representa uma tabela relacionada (ela contém links **Valor**).

1. No cabeçalho da coluna **DimProductSubcategory**, à direita do nome da coluna, selecione o botão Expandir.

    ![Ícone de expansão de coluna](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image31.png)

1. Consulte a lista completa de colunas e selecione a caixa **Selecionar Todas as Colunas** para desmarcar todas as colunas.
2. Selecione **EnglishProductSubcategoryName** e **DimProductCategory** e desmarque a caixa de seleção **Usar Nome da Coluna Original como Prefixo** antes de selecionar **OK**.

    *Ao selecionar essas duas colunas, uma transformação será aplicada para a junção à tabela **DimProductSubcategory** e a inclusão dessas colunas. A coluna **DimProductCategory** é, na verdade, outra tabela relacionada na fonte de dados.*

    *Os nomes das colunas de consulta devem ser sempre exclusivos. Se deixada marcada, essa caixa de seleção prefixaria cada coluna com o nome da coluna expandida (neste caso, **DimProductSubcategory**). Como é sabido que os nomes de coluna selecionados não colidem com nomes de coluna na consulta **Produto**, a opção é desmarcada.*

1. Observe que a transformação resultou na adição de duas colunas e que a coluna **DimProductSubcategory** foi removida.

1. Expanda a coluna **DimProductCategory** e introduza apenas a coluna **EnglishProductCategoryName**.

1. Renomeie as quatro seguintes colunas:

    - **EnglishProductName** como **Product**
    - **StandardCost** como **Standard Cost** (inclua um espaço)
    - **EnglishProductSubcategoryName** como **Subcategory**
    - **EnglishProductCategoryName** como **Category**

1. Na barra de status, confirme se a consulta tem seis colunas e 397 linhas.

## **Configurar a consulta Revendedor**

Nesta tarefa, você vai configurar a consulta **Revendedor**.

1. Selecione a consulta **DimReseller** e renomeie como **Revendedor**.

1. Remova todas as colunas, **exceto** as seguintes:

    - ResellerKey
    - BusinessType
    - ResellerName
    - DimGeography

1. Expanda a coluna **DimGeography**, para incluir **apenas** as três seguintes colunas:

    - City
    - StateProvinceName
    - EnglishCountryRegionName

1. No cabeçalho da coluna **Tipo de Negócio**, selecione a seta para baixo e, em seguida, examine os valores de coluna distintos e observe os valores **Warehouse** e **Ware House**.

1. Clique com o botão direito do mouse no cabeçalho da coluna **Business Type** e selecione **Substituir Valores**.

1. Na janela **Substituir Valores**, configure os seguintes valores:

    - Na caixa **Valor a ser Localizado**, insira **Ware House**
    - Na caixa **Substituir por**, insira **Warehouse**

     ![Caixa de diálogo Substituir valores](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image40.png)

1. Renomeie as quatro seguintes colunas:

    - **BusinessType** como **Business Type** (inclua um espaço)
    - **ResellerName** como **Reseller**
    - **StateProvinceName** como **State-Province**
    - **EnglishCountryRegionName** como **Country-Region**

1. Na barra de status, confirme se a consulta tem seis colunas e 701 linhas.

## **Configurar a consulta Região**

Nesta tarefa, você vai configurar a consulta **Region**.

1. Selecione a consulta **DimSalesTerritory** e renomeie a consulta como **Região**.

1. Aplique um filtro à coluna **SalesTerritoryAlternateKey** para remover o valor 0 (zero).

    *Isso removerá uma linha.*

1. Remova todas as colunas, **exceto** as seguintes:

    - SalesTerritoryKey
    - SalesTerritoryRegion
    - SalesTerritoryCountry
    - SalesTerritoryGroup

1. Renomeie as três seguintes colunas:

    - **SalesTerritoryRegion** como **Region**
    - **SalesTerritoryCountry** como **Country**
    - **SalesTerritoryGroup** como **Group**

1. Na barra de status, confirme se a consulta tem quatro colunas e 10 linhas.

## **Configurar a consulta Vendas**

Nesta tarefa, você vai configurar a consulta **Vendas**.

1. Selecione a consulta **FactResellerSales** e renomeie-a como **Vendas**.

1. Remova todas as colunas, **exceto** as seguintes:

    - SalesOrderNumber
    - OrderDate
    - ProductKey
    - ResellerKey
    - EmployeeKey
    - SalesTerritoryKey
    - OrderQuantity
    - UnitPrice
    - TotalProductCost
    - SalesAmount
    - DimProduct

        *Observação: você deve se lembrar que, no laboratório **Preparar Dados no Power BI Desktop**, uma pequena porcentagem das linhas **FactResellerSales** tinha valores T**TotalProductCost** ausentes. A coluna **DimProduct** foi incluída para recuperar a coluna de custo padrão do produto para ajudar a corrigir os valores ausentes.*

1. Expanda a coluna **DimProduct**, desmarque todas as colunas e inclua apenas a coluna **StandardCost**.

1. Para criar uma coluna personalizada, na guia de faixa de opções **Adicionar Coluna**, no grupo **Geral**, selecione **Coluna Personalizada**.

     ![Imagem 5664](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image47.png)

1. Na janela **Coluna Personalizada**, na caixa **Nome da Nova Coluna**, substitua o texto por **Cost**.

1. Na caixa **Fórmula de Coluna Personalizada**, insira a seguinte expressão (após o símbolo de igualdade):
    - *Você pode copiar a expressão do arquivo **D:\Allfiles\Labs\02-load-data-with-power-query-in-power-bi-desktop\Assets\Snippets.txt**.*
    - *Essa expressõa testa se o valor **TotalProductCost** está ausente. Nesse caso, ele produz um valor multiplicando o valor de **OrderQuantity** pelo valor **StandardCost**;caso contrário, ele usa o valor de **TotalProductCost** existente.*


    `
    if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost]
    `

1. Remova as duas seguintes colunas:

    - TotalProductCost
    - StandardCost

1. Renomeie as três seguintes colunas:

    - **OrderQuantity** como **Quantity**
    - **UnitPrice** como **Unit Price** (inclua um espaço)
    - **SalesAmount** como **Sales**

1. Para modificar o tipo de dados da coluna, no cabeçalho da coluna **Quantity**, à esquerda do nome da coluna, selecione o ícone **1,2** e escolha **Número Inteiro**.

    *A configuração correta do tipo de dados é importante. Quando a coluna contiver um valor numérico, também será importante escolher o tipo correto se você esperar fazer cálculos matemáticos.*

     ![Imagem 5667](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image50.png)

1. Modifique os tipos de dados das três colunas a seguir para **Número Decimal Fixo**.

    *O tipo de dados de número decimal fixo permite 19 dígitos e permite maior precisão para evitar erros de arredondamento. É importante usar o tipo de número decimal fixo para valores financeiros ou taxas (como taxas de câmbio).*

    - Preço Unitário
    - Vendas
    - Custo

1. Na barra de status, confirme se a consulta tem 10 colunas e mais de 999 linhas.

    *Um máximo de 1.000 linhas será carregado como os dados de visualização para cada consulta.*

## **Configurar a consulta Metas**

Nesta tarefa, você vai configurar a consulta **Targets**.

1. Selecione a consulta **ResellerSalesTargets** e renomeie como **Metas**.

1. Para transformar as colunas de 12 meses (**M01**-**M12**) em linhas, primeiro, faça uma seleção múltipla dos cabeçalhos das colunas **Ano** e **EmployeeID**.

1. Clique com o botão direito do mouse em um dos cabeçalhos da coluna selecionados e, no menu de contexto, selecione **Transformar Outras Colunas em Linhas**.

1. Observe que os nomes das colunas agora são exibidos na coluna **Attribute** e os valores são exibidos na coluna **Value**.

1. Aplique um filtro à coluna **Value** para remover os valores de hífen (-).

    *Talvez você se lembre de que o caractere de hífen foi usado no arquivo CSV de origem para representar zero (0).*

1. Renomeie as duas seguintes colunas:

    - **Atributo** para **MonthNumber** (não há espaço)
    - **Value** como **Target**

1. Para preparar os valores da coluna **MonthNumber**, clique com o botão direito do mouse no cabeçalho da coluna **MonthNumber** e selecione **Substituir Valores**.

    *Agora você aplicará transformações para produzir uma coluna de data. A data será derivada das colunas **Ano** e **MonthNumber**. Você criará a coluna usando o recurso **Colunas de Exemplos**.*

1. Na janela **Substituir Valores**, na caixa **Valor a Ser Localizado**, insira **M** e deixe **Substituir por** vazio.

1. Modifique o tipo de dados da coluna **MonthNumber** para **Número Inteiro**.

1. Na guia de faixa de opções **Adicionar Coluna**, no grupo **Geral**, selecione o ícone de **Coluna com Base em Exemplos**.

    ![Imagem 5675](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image59.png)

1. Observe que a primeira linha se refere ao ano **2017** e ao mês número **7**.

1. Na coluna **Coluna 1**, na primeira célula da grade, insira **7/1/2017** e pressione **Enter**.

    *A máquina virtual usa configurações regionais dos EUA, portanto, essa data é, na verdade, 1º de julho de 2017. Outras configurações regionais podem exigir um **0** antes da data.*

1. Observe que as células da grade são atualizadas com os valores previstos.

    *O recurso previu com precisão que você está combinando valores das colunas **Ano** e **MonthNumber**.*

1. Observe também a fórmula apresentada acima da grade da consulta.

     ![Imagem 5679](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image60.png)

1. Para renomear a nova coluna, clique duas vezes no cabeçalho da coluna **Mesclado** e renomeie a coluna como **TargetMonth**.

1. Remova as seguintes colunas:

    - Ano
    - MonthNumber

1. Modifique os seguintes tipos de dados de coluna:

    - **Target** como um número decimal fixo
    - **TargetMonth** como uma data

1. Para multiplicar os valores de **Target** por 1.000, selecione o cabeçalho da coluna **Target** e, na guia de faixa de opções **Transformar**, no grupo **Coluna de Número**, selecione **Padrão** e **Multiplicar**.

    *Talvez você se lembre que os valores de destino foram armazenados como milhares.*

     ![Imagem 5682](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image63.png)

1. Na janela **Multiplicar**, na caixa **Valor**, insira **1000** e selecione **OK**.

1. Na barra de status, confirme se a consulta tem três colunas e 809 linhas.

## **Configurar a consulta ColorFormats**

Nesta tarefa, você vai configurar a consulta **ColorFormats**.

1. Selecione a consulta **ColorFormats** e observe que a primeira linha contém os nomes das colunas.

1. Na guia de faixa de opções **Página Inicial**, no grupo **Transformar**, selecione **Usar a Primeira Linha como Cabeçalho**.

     ![Imagem 5688](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image68.png)

1. Na barra de status, confirme se a consulta tem três colunas e 10 linhas.

## **Atualizar a consulta do Produto**

Nesta tarefa, você atualizará a consulta **Product** mesclando a consulta **ColorFormats**.

1. Selecione a consulta **Product**.

1. Para mesclar a consulta **ColorFormats**, na guia de faixa de opções **Página Inicial**, selecione a seta **Combinar** para baixo e, em seguida, selecione **Mesclar Consultas**.

    *A mesclagem de consultas permite a integração de dados, neste caso, de fontes de dados diferentes (do SQL Server e de um arquivo CSV).*

     ![Imagem 5654](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image71.png)

1. Na janela **Mesclar**, na grade da consulta **Product**, selecione o cabeçalho da coluna **Color**.

     ![Imagem 5655](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image72.png)

1. Abaixo da grade da consulta **Product**, na lista suspensa, selecione a consulta **ColorFormats**.

     ![Figura 21](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image73.png)

1. Na grade da consulta **ColorFormats**, selecione o cabeçalho da coluna **Color**.

1. Quando a janela **Níveis de Privacidade** é aberta, para cada uma das duas fontes de dados, na lista suspensa correspondente, selecione **Organizacional** e **Salvar**.

    *Os níveis de privacidade podem ser configurados para a fonte de dados para determinar se os dados podem ser compartilhados entre fontes. Definir cada fonte de dados como **Organizacional** permite que eles compartilhem dados, se necessário. As fontes de dados privadas nunca podem ser compartilhadas com outras fontes de dados. Isso não significa que os dados privados não possam ser compartilhados; mas sim que o mecanismo do Power Query não pode compartilhar dados entre as fontes.*

     ![Imagem 5691](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image74.png)

1. Na janela **Mesclar**, use o **Tipo de Ingresso** padrão mantendo a seleção de Externa Esquerda e selecione **OK**.

1. Expanda a coluna **ColorFormats** para incluir as duas seguintes colunas:

    - Background Color Format
    - Font Color Format

1. Na barra de status, confirme se a consulta agora tem oito colunas e 397 linhas.

## **Atualizar a consulta ColorFormats**

Nesta tarefa, você atualizará a consulta **ColorFormats** para desabilitar a carga dela.

1. Selecione a consulta **ColorFormats**.

1. No painel **Configurações de Consulta**, selecione o link **Todas as Propriedades**.

     ![Imagem 322](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image80.png)

1. Na janela **Propriedades da Consulta**, desmarque a caixa de seleção **Habilitar Carregamento para o Relatório**.

    *Desabilitar a carga significa que ela não será carregada como uma tabela para o modelo de dados. Isso é feito porque a consulta foi mesclada com a consulta de **Produto**, que está habilitada para carregar no modelo de dados.*

     ![Imagem 323](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image81.png)

### **Conclusão**

Nesta tarefa, você concluirá o laboratório.

1. Confirme se você tem oito consultas, corretamente nomeadas da seguinte maneira:

    - Salesperson
    - SalespersonRegion
    - Product
    - Reseller
    - Region
    - Vendas
    - Destinos
    - ColorFormats (não será carregada no modelo de dados)

1. Para carregar o modelo de dados, no modo de exibição Backstage **Arquivo**, selecione **Fechar &amp; Aplicar**.

    *Todas as consultas habilitadas para carga agora são carregadas no modelo de dados.*

     ![Imagem 326](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image83.png)

1. No painel **Dados** (localizado à direita), observe as sete tabelas carregadas no modelo de dados.

     ![Figura 3](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image84.png)

1. Salve o arquivo do Power BI Desktop.

*Você vai configurar as tabelas do modelo de dados e as relações no laboratório **Modelar Dados no Power BI Desktop**.*
