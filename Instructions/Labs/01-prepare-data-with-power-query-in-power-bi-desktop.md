---
lab:
  title: Obter Dados no Power BI Desktop
  module: Get Data in Power BI
---

# Obter Dados no Power BI Desktop

## **História do laboratório**

Este laboratório foi projetado para apresentá-lo ao aplicativo Power BI Desktop e como se conectar a dados e como usar técnicas de pré-visualização de dados para entender as características e a qualidade dos dados de fonte. Os objetivos de aprendizagem são:

- Abrir o Power BI Desktop
- Conectar-se a diferentes fontes de dados
- Pré-visualizar dados de fonte com o Power Query
- Usar recursos de criação de perfil de dados no Power Query

**Este laboratório levará aproximadamente 30 minutos.**

## **Introdução ao Power BI Desktop**

Nesta tarefa, você começa abrindo um arquivo inicial do Power BI (.pbix). O arquivo inicial não contém dados, mas foi especialmente configurado para ajudar você a concluir o laboratório. As seguintes configurações em nível de relatório foram desabilitadas no arquivo inicial:

- Carregamento de Dados > Importar relacionamentos de fontes de dados no primeiro carregamento
- Carregamento de Dados > Detectar automaticamente novos relacionamentos depois que os dados são carregados

*Observação: embora ter essas duas opções habilitadas possa ser útil ao desenvolver um modelo de dados, você as desabilitou anteriormente para oferecer suporte à experiência de laboratório. Ao criar relacionamentos no laboratório **Carregar Dados Transformados no Power BI Desktop**, você aprenderá por que está adicionando cada um deles.*

1. Abra o Power BI Desktop.

    ![Ícone do Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Dica: por padrão, a caixa de diálogo Introdução é aberta na frente do Power BI Desktop. Você pode optar por entrar e, em seguida, fechar o pop-up.*

1. Para abrir o arquivo inicial do Power BI Desktop, selecione **Arquivo > Abrir Relatório > Procurar Relatórios**.

1. Na janela **Abrir**, navegue até a pasta **D:\PL300\Labs\01-prepare-data-with-power-query-in-power-bi-desktop\Starter**.

1. Selecione o arquivo **Análise de Vendas**.

1. Salve uma cópia do arquivo com **Salvar como** na pasta **D:\PL300\MySolution**.


## **Obter dados do SQL Server**

Esta tarefa ensina como se conectar a um banco de dados do SQL Server e importar tabelas, que criam consultas no Power Query.

1. Na guia de faixa de opções **Página Inicial**, no grupo **Dados**, selecione **SQL Server**.

     ![Ícone Obter Dados do SQL Server](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

1. Na janela **Banco de Dados SQL Server**, na caixa **Servidor**, insira **localhost** e, em seguida, selecione **OK**.

    *Observação: neste laboratório, você se conectará ao banco de dados do SQL Server usando **localhost** porque as fontes de dados de gateway não podem resolver **localhost**. Essa não é uma prática recomendada ao criar suas próprias soluções.*

1. Se forem solicitadas credenciais, na janela **Banco de Dados do SQL Server**, selecione **Usar minhas credenciais atuais** e, em seguida **Conectar**.

1. Na janela **Navegador**, à esquerda, expanda o banco de dados **AdventureWorksDW2020**.

    *Observação: o banco de dados **AdventureWorksDW2020** é baseado no banco de dados de exemplo **AdventureWorksDW2017**. Ele foi modificado para apoiar os objetivos de aprendizagem dos laboratórios do curso.*

1. Selecione, mas não marque a tabela **DimEmployee**

     ![Banco de dados AdventureWorksDW2020 com DimEmployee indicado](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

1. No painel direito, observe uma pré-visualização dos dados da tabela. Os dados da pré-visualização permitem que você veja as colunas e uma amostra de linhas.

1. Para criar consultas, marque a caixa de seleção ao lado das seis seguintes tabelas:

    - DimEmployee
    - DimEmployeeSalesTerritory
    - DimProduct
    - DimReseller
    - DimSalesTerritory
    - FactResellerSales

1. Conclua esta tarefa selecionando **Transformar Dados**, que abrirá o Editor do Power Query.
    
    1. *Este laboratório se destina apenas a conectar e criar o perfil dos dados, mas não a **transformar dados**.*


## **Pré-Visualizar Dados no Editor do Power Query**

Esta tarefa apresenta o Editor do Power Query e permite a você rever e criar o perfil dos dados. Isso ajuda a determinar como limpar e transformar os dados posteriormente.

1. Na janela **Editor do Power Query**, à esquerda, observe o painel **Consultas**. O painel **Consultas** contém uma consulta para cada tabela selecionada.

     ![Lista de consultas carregadas](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

1. Selecione a primeira consulta **DimEmployee**.

    *A tabela **DimEmployee** no banco de dados do SQL Server armazena uma linha para cada funcionário. Um subconjunto das linhas dessa tabela representa os vendedores, que serão relevantes para o modelo que você desenvolverá.*

1. No canto inferior esquerdo, na barra de status, algumas estatísticas da tabela são concedidas: a tabela tem 33 colunas e 296 linhas.

     ![Contagem de 33 colunas, 296 linhas](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

1. No painel de visualização de dados, role horizontalmente para examinar todas as colunas. Observe que as últimas cinco colunas contêm links de **Tabela** ou **Valor**.

    *Essas cinco colunas representam relações com outras tabelas no banco de dados. Eles podem ser usados para unir mesas. Você ingressará em tabelas no laboratório **Carregar Dados Transformados no Power BI Desktop**.*

1. Para avaliar a qualidade da coluna, na guia **Exibição** da faixa de opções, dentro do grupo **Visualização de Dados**, marque **Qualidade da Coluna**. O recurso da qualidade da coluna permite que você determine facilmente o percentual de valores válidos, com erro ou vazios.

     ![Seleção de Qualidade da Coluna na faixa de opções](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

1. Observe que a coluna **Posição** tem 94% de linhas vazias (nulas).

     ![Qualidade da coluna mostrando 94% de linhas vazias](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

1. Para avaliar a distribuição da coluna, na guia **Exibição** da faixa de opções, dentro do grupo **Visualização de Dados**, marque **Distribuição da Coluna**.

1. Examine a coluna **Posição** novamente e observe que há quatro valores distintos e um valor exclusivo.

1. Examine a distribuição de coluna para a coluna **EmployeeKey** - há 296 valores distintos e 296 valores exclusivos.

    *Quando as contagens distintas e exclusivas são as mesmas, isso significa que a coluna contém valores exclusivos. Ao modelar, é importante que algumas tabelas de modelo tenham colunas exclusivas. Essas colunas exclusivas podem ser usadas para criar relacionamentos um-para-muitos, o que você fará no laboratório **Dados de Modelo no Power BI Desktop**.*

     ![Distribuição de colunas mostrando 296 valores distintos e 296 exclusivos](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

1. No painel **Consultas**, selecione a consulta **DimEmployeeSalesTerritory**.

    *A tabela **DimEmployeeSalesTerritory** armazena uma linha para cada funcionário e as regiões do território de vendas que eles gerenciam. A tabela suporta relacionar muitas regiões a um único funcionário. Alguns funcionários gerenciam uma, duas ou possivelmente mais regiões. Ao modelar esses dados, você precisará definir uma relação muitos-para-muitos.*

1. No painel **Consultas**, selecione a consulta **DimProduct**. A tabela **DimProduct** contém uma linha por produto vendido pela empresa.

1. Role horizontalmente para revelar as últimas colunas. Observe a coluna **DimProductSubcategory**.

    *Ao adicionar transformações a essa consulta no laboratório **Carregar Dados Transformados no Power BI Desktop**, você usará a coluna **DimProductSubcategory** para unir tabelas.*

1. No painel **Consultas**, selecione a consulta **DimReseller**.

    *A tabela **DimReseller** contém uma linha por revendedor. Os revendedores vendem, distribuem ou agregam valor aos produtos da Adventure Works.*

1. Para exibir valores da coluna, na guia **Exibição** da faixa de opções, dentro do grupo **Visualização de Dados**, marque **Perfil da Coluna**.

1. Selecione o cabeçalho da coluna **BusinessType** e observe o novo painel abaixo do painel de pré-visualização de dados.

1. Examine as estatísticas da coluna e a distribuição de valor no painel de pré-visualização de dados.

    *Observe o problema de qualidade dos dados: há dois rótulos para warehouse (**Warehouse** e **Ware House**, com a grafia incorreta).*

     ![Distribuição de valor para a coluna BusinessType](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

1. Passe o mouse sobre a barra **Ware House** e observe que há cinco linhas com esse valor.

    *Você aplicará uma transformação para rotular novamente essas cinco linhas no laboratório **Carregar Dados Transformados no Power BI Desktop**.*

1. No painel **Consultas**, selecione a consulta **DimSalesTerritory**.  

    *A tabela **DimSalesTerritory** contém uma linha por região de vendas, incluindo **Corporate HQ** (sede). As regiões são atribuídas a um país e os países são atribuídos a grupos. No laboratório **Dados de Modelo no Power BI Desktop**, você criará uma hierarquia para dar suporte à análise em nível de região, país ou grupo.*

1. No painel **Consultas**, selecione a consulta **FactResellerSales**.

    *A tabela **FactResellerSales** contém uma linha por linha de pedido de venda. Um pedido de venda contém um ou mais itens de linha.*

1. Examine a qualidade da coluna **TotalProductCost** e observe que 8% das linhas estão vazias.

    *Os valores ausentes da coluna **TotalProductCost** é um problema de qualidade de dados. Para resolver o problema no laboratório **Carregar Dados Transformados no Power BI Desktop**, você aplicará transformações para preencher os valores ausentes usando o custo padrão do produto, que está armazenado na tabela relacionada **DimProduct**.*


## **Obter dados de um arquivo CSV**

Nesta tarefa, você criará uma nova consulta com base em arquivos CSV.

1. Para adicionar uma nova consulta, na janela do **Editor do Power Query**, na guia de faixa de opções **Página Inicial**, no grupo **Nova Consulta**, escolha a seta para baixo **Nova Fonte** e selecione **Texto/CSV**.

1. Na janela **Abrir**, procure a pasta **D:\PL300\Resources** e selecione o arquivo **ResellerSalesTargets.csv**. Selecione **Abrir**.

1. Na janela **ResellerSalesTargets.csv**, examine os dados da pré-visualização. Selecione **OK**.

1. No painel **Consultas**, observe a adição da consulta **ResellerSalesTargets**.

    *O arquivo CSV **ResellerSalesTargets** contém uma linha por vendedor, por ano. Cada linha registra 12 metas de vendas mensais (expressas em milhares). O ano comercial da empresa Adventure Works começa em 1º de julho.*

1. Observe que nenhuma coluna contém valores vazios.  Quando não há uma meta de vendas mensal, um caractere de hífen é armazenado em seu lugar.

1. Examine os ícones de cada cabeçalho de coluna à esquerda do nome da coluna. Os ícones representam o tipo de dados da coluna. **123** é número inteiro e **ABC** é texto.

     ![Imagem 74](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

1. Use as etapas para criar uma consulta baseada no arquivo **D:\PL300\Resources\ColorFormats.csv**.

    *O arquivo CSV **ColorFormats** contém uma linha por cor do produto. Cada linha registra os códigos HEX para formatar as cores do plano de fundo e da fonte.*

*Agora você deve ter duas novas consultas, **ResellerSalesTargets** e **ColorFormats**.*

 ![Lista de consultas](Linked_image_Files/01-all-queries-loaded.png)


### **Conclusão**

Nesta tarefa, você concluirá o laboratório.

1. Na guia **Exibir** da faixa de opções, dentro do grupo **Pré-Visualizar Dados**, desmarque as três opções de pré-visualização de dados que foram ativadas anteriormente neste laboratório:

    - Qualidade da coluna
    - Distribuição de colunas
    - Perfil da coluna

     ![Imagem 76](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image40.png)

1. **Salve** o arquivo do Power BI Desktop. Quando for solicitado a aplicar as alterações pendentes, selecione **Aplicar Mais Tarde**.

    *Dica: a aplicação das consultas carregará seus dados no modelo de dados. Você não está pronto para fazer isso, pois há muitas transformações que devem ser aplicadas primeiro.*
