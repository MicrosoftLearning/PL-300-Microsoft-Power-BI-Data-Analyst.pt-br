---
lab:
  title: Criar um painel do Power BI
  module: Create Dashboards
---


# **Criar um painel de Power BI**

## **História do laboratório**

Neste laboratório, você criará o **painel Monitoramento de** Vendas no serviço do Power BI usando um relatório existente.

Neste laboratório, você aprenderá a:

- Fixar visuais a um dashboard
- Usar P e R para criar blocos de dashboard

**Este exercício levará aproximadamente 20 minutos.**

## **Tarefa 1: Introdução – Conectar-se**

Nesta tarefa, você vai configurar o ambiente para o laboratório entrando no Power BI.

Se você já entrou no Power BI, continue na próxima tarefa.

1. Para abrir o Microsoft Edge, na barra de tarefas, selecione o atalho do programa Microsoft Edge.

     ![Figura 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. Na janela do navegador Microsoft Edge, navegue até **https://app.powerbi.com**.

    Use também o favorito do serviço do Power BI na barra de favoritos do Microsoft Edge.

1. Conclua o processo de entrada com suas credenciais organizacionais (ou aquelas fornecidas a você). Se você receber um aviso do Microsoft Edge para permanecer conectado, selecione **Sim**.

1. Na janela do navegador Microsoft Edge, no serviço do Power BI, no painel **Navegação**, expanda **Meu Workspace**. Mantenha a janela do navegador Microsoft Edge aberta.

     ![Figura 22](Linked_image_Files/07-my-workspace-new.png)

## **Tarefa 2: Introdução – Abrir relatório**

Nesta tarefa, você vai configurar o ambiente para o laboratório abrindo o relatório inicial.

Se estiver dando continuidade ao laboratório anterior (e concluiu esse laboratório com sucesso), não conclua essa tarefa; em vez disso, continue na próxima tarefa.

1. Abra o Power BI Desktop.
    
    *Por padrão, a caixa de diálogo Introdução é aberta na frente do Power BI Desktop. Entre e feche o pop-up.*

    ![* Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. Para abrir o arquivo inicial do Power BI Desktop, na guia de faixa de opções Arquivo, selecione Abrir relatório e Procurar relatórios.

1. Na janela Abrir, procure a pasta D:\DA100\Labs\09-create-power-bi-dashboard\Starter.

1. Feche todas as janelas informativas que possam ser abertas.

1. Observe a mensagem de aviso em amarelo abaixo da faixa de opções. *Essa mensagem alerta para o fato de que as consultas não foram aplicadas para carregar como tabelas de modelo. Você aplicará as consultas posteriormente no laboratório.*
    
    Para ignorar a mensagem de aviso, à direita da mensagem de aviso em amarelo, selecione X.

1. Caso precise aplicar as alterações, selecione **Aplicar Mais Tarde**.

## **Tarefa 3: Introdução – Publicar o relatório**

Nesta tarefa, você vai configurar o ambiente para o laboratório criando um conjunto de dados. *Se você já publicou o conjunto de dados, vá para a próxima tarefa.*

1. Na janela do navegador Microsoft Edge, no serviço do Power BI, no painel Navegação, expanda Meu Workspace.

1. Selecione Carregar e Procurar.

1. Na janela Abrir, procure a pasta D:\DA100\Labs\09-create-power-bi-dashboard\Starter.

1. Selecione o arquivo **Sales Analysis.pbix** e escolha **Abrir**.

Caso precise substituir o conjunto de dados, selecione Substituir.

## **Criar um painel**

Nesta tarefa, você criará o dashboard **Monitoramento de Vendas**. Você fixará um visual por meio do relatório, adicionará um bloco com base em um URI de dados de imagem e usará a P e R para criar um bloco.

1. No serviço do Power BI, abra o relatório **Análise de vendas dos EUA do Power BI**.

1. Na página **Visão geral**, defina a segmentação **Year** como **FY2020**.

    ![Imagem 4](Linked_image_Files/09-create-power-bi-dashboard_image17.png)

1. Defina a segmentação **Região** como **Selecionar Tudo**.

    *Os elementos visuais fixados são definidos com o contexto do filtro no momento do pino. Se o visual subjacente for alterado, você também precisará atualizar o bloco do painel. Para filtros baseados em tempo, é melhor usar uma segmentação de dados relativa (ou, Perguntas e respostas usando uma pergunta baseada em tempo relativo).*

1. Para criar um dashboard e fixar um visual, posicione o cursor sobre o visual **Vendas e Margem de Lucro por Mês** (coluna/linha).

    ![Figura 43](Linked_image_Files/09-create-power-bi-dashboard_image18.png)

1. Na janela Fixar no Dashboard, na caixa Nome do Dashboard, insira Monitoramento de Vendas.

    ![Figura 3](Linked_image_Files/09-create-power-bi-dashboard_image19.png)

1. Abra **Meu Espaço de Trabalho** e abra o **painel Monitoramento de** Vendas.

1. Observe que o dashboard tem um só bloco.

    ![Figura 45](Linked_image_Files/09-create-power-bi-dashboard_image22.png)

1. Para adicionar um bloco com base em uma pergunta, no canto superior esquerdo do dashboard, selecione **Fazer uma Pergunta sobre os Dados**.
    
    Você pode usar o recurso de P e R para fazer uma pergunta e o Power BI responderá a um visual.

    ![Figura 7](Linked_image_Files/09-create-power-bi-dashboard_image23.png)

1. Selecione uma das perguntas sugeridas abaixo da caixa de P e R, nas caixas azuis.

1. Remova todo o texto da caixa de perguntas e respostas e digite o seguinte: **Vendas YTD**

1. Observe a resposta **(Em Branco)**.
    
    *Você deve se lembrar de ter adicionado a medida YTD** de vendas no laboratório Criar cálculos avançados de **DAX no **Power BI Desktop**. Essa medida é uma expressão de Inteligência de Dados Temporais e, portanto, requer um filtro na **tabela Data** para produzir um resultado.*

    ![Figura 14](Linked_image_Files/09-create-power-bi-dashboard_image25.png)

1. Especifique a pergunta com: **no ano FY2020**.

1. Observe que a resposta agora é **US$33 milhões**.

    ![Figura 13](Linked_image_Files/09-create-power-bi-dashboard_image27.png)

1. Para fixar a resposta no dashboard, no canto superior direito, clique em **Fixar Visual**.

    ![Figura 15](Linked_image_Files/09-create-power-bi-dashboard_image28.png)

1. Quando precisar fixar o bloco no dashboard, selecione **Fixar**.

1. Para voltar ao dashboard, no canto superior esquerdo, selecione Sair da P e R.

1. Para adicionar o logotipo da empresa, na barra de menus, selecione **Editar** e escolha **Adicionar um bloco**.
    
    O uso dessa técnica para adicionar um bloco do dashboard permite aprimorar o dashboard com uma mídia, incluindo conteúdo da Web, imagens, caixas de texto com formatação e vídeos (usando links do YouTube ou do Vimeo).

1. No painel Adicionar um Bloco (localizado à direita), selecione o bloco Imagem.

1. No painel Adicionar Bloco de Imagem, na caixa URL, insira a URL completa encontrada no arquivo D:\DA100\Resources\AdventureWorksLogo_DataURL.txt.
    
    Você pode inserir uma imagem usando a URL dela ou uma URL de dados, que insere o conteúdo embutido.

1. Para redimensionar o bloco do logotipo, arraste o canto inferior direito e redimensione o bloco até que ele tenha uma unidade de largura e duas de altura.
    
    *Os tamanhos dos azulejos são limitados a uma forma retangular.*

1. Organize os blocos para que o logotipo seja mostrado no canto superior esquerdo, com o bloco **Vendas acumuladas no ano** abaixo dele e o bloco **Vendas, Margem de Lucro** à direita.

    ![Figura 52](Linked_image_Files/09-create-power-bi-dashboard_image35.png)

## Editar detalhes do bloco

Nesta tarefa, você editará os detalhes de dois blocos.

1. Posicione o cursor sobre o bloco **Vendas acumuladas no ano** e, no canto superior direito do bloco, selecione as reticências e escolha **Editar Detalhes**.

    ![Figura 50](Linked_image_Files/09-create-power-bi-dashboard_image36.png)

1. No painel Detalhes do Bloco (localizado à direita), na caixa Subtítulo, insira FY2020.

1. Observe que o bloco **Vendas acumuladas no ano** exibe um subtítulo.

    ![Figura 21](Linked_image_Files/09-create-power-bi-dashboard_image39.png)

1. Edite os detalhes do bloco para o bloco **Vendas, Margem de Lucro**.

1. No painel Detalhes do Bloco, na seção Funcionalidade, marque Exibir a Hora da Última Atualização.

    ![Figura 22](Linked_image_Files/09-create-power-bi-dashboard_image40.png)

1. Observe que o bloco descreve a hora da última atualização (que foi realizada ao atualizar o modelo de dados no Power BI Desktop).

*Você atualizará o conjunto de dados no próximo exercício. Dependendo dos seus dados e relatório, você pode fazer uma atualização de dados adhoc a qualquer momento ou definir uma agenda. No entanto, as atualizações agendadas exigem gateways que não podemos configurar para este laboratório. Portanto, no Power BI Desktop, você executará uma atualização de dados manual e carregará o arquivo em seu espaço de trabalho.*

## Atualizar o conjunto de dados

Neste exercício, primeiro, você carregará os dados de pedidos de vendas de junho de 2020 no banco de dados **AdventureWorksDW2020**. Depois, você abrirá o arquivo do Power BI Desktop, executará uma atualização de dados e carregará o arquivo no seu workspace.

## Atualizar o banco de dados do laboratório

Nesta tarefa, você executará um script do PowerShell para atualizar os dados do banco de dados **AdventureWorksDW2020**.

1. No Explorador de Arquivos, na pasta **D:\DA100\Setup**, clique com o botão direito do mouse no arquivo **UpdateDatabase-2-AddSales.ps1** e selecione **Executar com o PowerShell**.

    ![Imagem 28](Linked_image_Files/09-create-power-bi-dashboard_image46.png)

1. Caso precise alterar a política de execução, clique em **A**.

1. Quando for solicitado a pressionar qualquer tecla para continuar, pressione **Enter** novamente.

*Agora o banco de dados **AdventureWorksDW2020** inclui pedidos de vendas de junho de 2020.*

## Atualizar o arquivo do Power BI Desktop

Nesta tarefa, você abrirá o arquivo de Análise de Vendas do Power BI Desktop, executará uma atualização de dados e carregará o arquivo no workspace Análise de Vendas.

1. No arquivo do Power BI Desktop, no painel **Campos**, clique com o botão direito do mouse na tabela **Sales** e selecione **Atualizar dados**.

    ![Figura 11](Linked_image_Files/09-create-power-bi-dashboard_image47.png)

1. Quando a atualização for concluída, salve o arquivo do Power BI Desktop.

1. Para publicar o arquivo no seu workspace, na guia de faixa de opções Página Inicial, no grupo Compartilhar, clique em Publicar.

    ![Figura 59](Linked_image_Files/09-create-power-bi-dashboard_image48.png)

1. Quando precisar substituir o conjunto de dados, selecione **Substituir**.

1. Feche o Power BI Desktop.

*Agora, a data de vendas do conjunto de dados no serviço do Power BI é junho de 2020.*

### Examinar o dashboard

Nesta tarefa, você examinará o dashboard para observar as vendas atualizadas e se o alerta foi disparado.

1. Na janela do navegador Microsoft Edge, no serviço do Power BI, examine o dashboard Monitoramento de Vendas.

2. No bloco **Vendas, Margem de Lucro**, no subtítulo, observe que os dados foram atualizados **AGORA**.

3. Observe também que agora há uma coluna para **junho de 2020**.
    
    Se os dados de junho de 2020 não forem exibidos, clique em F5 para recarregar o navegador da Web.

    ![Figura 11](Linked_image_Files/09-create-power-bi-dashboard_image50.png)

### Conclusão

Nesta tarefa, você concluirá o laboratório.

1. Salve o arquivo e atualize seu navegador.
