---
lab:
  title: Criar um relatório no Power BI Desktop
  module: Create Reports in Power BI Desktop
---


# Criar um relatório no Power BI Desktop

## **História do laboratório**

Neste laboratório, você criará um relatório de três páginas. Você então publicará o relatório no Power BI, onde será possível abri-lo e interagir com ele.

Neste laboratório, você aprenderá a:

- Projetar um relatório
- Configurar campos visuais e propriedades de formato

**Este exercício deve durar aproximadamente 45 minutos.**

## **Criar um relatório**

Nesta tarefa, você vai configurar o ambiente para o laboratório abrindo o relatório inicial.

1. No Power BI Desktop, navegue até **Procurar relatório > ****de abertura** de arquivo.** > **

1. Abra o ****arquivo Sales Analysis** na pasta D:\PL300\Labs\06-design-report-in-power-bi-desktop\Starter**.

1. Crie uma cópia do arquivo indo para **Arquivo**** > Salvar como** e salve a **cópia na pasta D:\PL300\MySolution.**

## Página de design 1

Nesta tarefa, você criará a primeira página de relatório. Quando você tiver concluído o design, a página terá a seguinte aparência:

![Imagem da página 1, composta por um logotipo, duas segmentações de dados e três elementos visuais.](Linked_image_Files/06-finished-report-page.png)

1. No Power BI Desktop, para renomear a página, no canto inferior esquerdo, clique com o botão direito do mouse em Página 1 e escolha Renomear página.

    Você também pode clicar duas vezes no nome da página.

1. Para adicionar uma imagem, na guia de faixa de opções **Inserir**, no grupo **Elementos**, selecione **Imagem**.

    ![Figura 1](Linked_image_Files/07-design-report-in-power-bi-desktop_image15.png)

1. Na janela **Abrir**, procure a pasta **D:\DA100\Resources**.

1. Selecione o arquivo **AdventureWorksLogo.jpg** e escolha **Abrir**.

1. Arraste a imagem para reposicioná-la no canto superior esquerdo e também arraste os marcadores de guia para redimensioná-la.

     ![Figura 12](Linked_image_Files/07-design-report-in-power-bi-desktop_image17.png)

1. Para adicionar uma segmentação, primeiro cancele a seleção da imagem clicando em uma área vazia da página do relatório.

     ![Figura 49](Linked_image_Files/07-design-report-in-power-bi-desktop_image18.png)

1. **No painel Dados**, arraste o campo Data \| Ano (não o **** **nível Ano** da hierarquia) para a segmentação de dados **Campo** no painel Visualizações.
    
    *Os laboratórios usam uma notação taquigráfica para fazer referência a um campo. Ficará assim: **Data \| Ano**. Neste exemplo, **Data** é o nome da tabela e **Ano** é o nome do campo.*

1. Para converter a segmentação de dados de uma lista em uma lista suspensa, navegue até **Visualizações > Formatar visual > Configurações > Estilo** da segmentação de dados do Visual > e selecione **Menu suspenso no menu suspenso** .

    ![Estilos de Segmentação de Dados](Linked_image_Files/06_slicer_style.png)

1. Redimensione e reposicione a segmentação de modo que ela fique abaixo da imagem e tenha a mesma largura dela.

     ![Figura 19](Linked_image_Files/07-design-report-in-power-bi-desktop_image20.png)

1. Na segmentação **Ano**, selecione **AF2020** e recolha a lista suspensa.
    1. Agora a página de relatório é filtrada pelo ano AF2020.

     ![Figura 20](Linked_image_Files/07-design-report-in-power-bi-desktop_image21.png)

1. Desmarque a segmentação clicando em uma área vazia da página do relatório.

1. Crie uma segunda segmentação com base no campo **Região | Região\| (não o nível **Região da hierarquia).

1. Deixe a segmentação como uma lista e redimensione e reposicione a segmentação abaixo da segmentação **Ano**.

     ![Figura 21](Linked_image_Files/07-design-report-in-power-bi-desktop_image22.png)

1. Desmarque a segmentação clicando em uma área vazia da página do relatório.

1. Para adicionar um gráfico à página, no painel **Visualizações**, selecione o tipo de visual **Gráfico de Linhas e Colunas Empilhadas**.

     ![Figura 51](Linked_image_Files/07-design-report-in-power-bi-desktop_image26.png)

1. Redimensione e reposicione o visual para que ele fique à direita do logotipo e, portanto, preencha a largura da página do relatório.

     ![Figura 26](Linked_image_Files/07-design-report-in-power-bi-desktop_image27.png)

1. Arraste os seguintes campos para o visual:

     - Data – Mês
     - Vendas | Vendas

1. No painel de campos visuais (localizado abaixo do painel Visualizações **), observe que os campos são atribuídos aos poços/áreas do **eixo X e **do **eixo**** y da coluna.
    
    *Ao arrastar campos para um visual, eles serão adicionados a poços/áreas padrão. Para precisão, você pode arrastar campos diretamente para os poços/áreas, como fará a seguir.*

     ![Figura 27](Linked_image_Files/07-design-report-in-power-bi-desktop_image28_N.png)

1. No painel **Campos**, arraste o campo **Vendas | Margem de Lucro\| para a caixa **Valores de Linha.

     ![Imagem 28](Linked_image_Files/07-design-report-in-power-bi-desktop_image29.png)

1. Observe que o visual tem apenas 11 meses.
    
    *O último mês do ano, junho de 2020, não tem vendas (ainda). Por padrão, o visual eliminou meses com vendas em BRANCO. Agora você configurará o visual para mostrar todos os meses.*

1. No painel Campos do visual, na caixa **Eixo Compartilhado**, para o campo **Month**, escolha a seta para baixo e selecione **Mostrar Itens Sem Dados**.
    
    Observe que o mês de junho de 2020 aparece agora.

     ![Figura 52](Linked_image_Files/07-design-report-in-power-bi-desktop_image30.png)

1. Desmarque o gráfico clicando em uma área vazia da página do relatório.

1. Para adicionar um gráfico à página, no painel **Visualizações**, selecione o tipo de visual **Gráfico de Linhas e Colunas Empilhadas**.

     ![Figura 53](Linked_image_Files/07-stacked-column-chart.png)

1. Redimensione e reposicione o visual para que ele fique abaixo do gráfico de colunas/linhas e, portanto, preencha a largura da página do relatório.

     ![Figura 11](Linked_image_Files/07-design-report-in-power-bi-desktop_image32.png)

1. Adicione os seguintes campos às caixas de visual:

     - Eixo X: **Região \| País**
     - Eixo Y: **Vendas \|**
     - D Product Category

1. Desmarque o gráfico clicando em uma área vazia da página do relatório.

1. Para adicionar um gráfico à página, no painel **Visualizações**, clique no tipo de visual **Gráfico de Barras Empilhadas**.

     ![Figura 54](Linked_image_Files/07-design-report-in-power-bi-desktop_image33.png)

1. Redimensione e reposicione o visual para que ele preencha o espaço restante da página do relatório.

     ![Figura 35](Linked_image_Files/07-design-report-in-power-bi-desktop_image34.png)

1. Adicione os seguintes campos às caixas de visual:

     - Eixo Y: **Categoria de Produto \|**
     - Eixo X: **Quantidade de Vendas \|**

1. Para formatar o visual, abra o painel **Formatar**.

     ![Figura 3](Linked_image_Files/07-design-report-in-power-bi-desktop_image35.png)

1. Expanda o grupo Cores de Dados e defina a propriedade Cor Padrão com uma cor adequada (em contraste com o gráfico de colunas/linhas).

1. Defina a propriedade **Rótulos de Dados** como **Ativado**.

     ![Figura 2](Linked_image_Files/07-design-report-in-power-bi-desktop_image36.png)

1. Salve o arquivo do Power BI Desktop.

O design da primeira página agora está concluído.

## Página de design 2

Nesta tarefa, você criará a segunda página de relatório. Quando você tiver concluído o design, a página terá a seguinte aparência:

 ![Imagem da página 2, composta por uma segmentação de dados e matriz.](Linked_image_Files/07-design-report-in-power-bi-desktop_image37.png)

*Importante: Quando instruções detalhadas já foram fornecidas nos laboratórios, as etapas do laboratório fornecerão instruções mais concisas. Se você precisar das instruções detalhadas, você pode consultar outras tarefas neste laboratório.*

1. Para criar uma página de relatório, no canto inferior esquerdo, selecione o ícone de adição.

1. Adicione uma segmentação com base no campo Região | Região.

1. Use o painel **Formatar** para habilitar a opção "Selecionar Tudo" (no grupo **Controles de Seleção**).

1. Redimensione e reposicione a segmentação de modo que ela fique no lado esquerdo da página do relatório e, portanto, tenha cerca de metade da altura da página.

     ![Figura 44](Linked_image_Files/07-design-report-in-power-bi-desktop_image40.png)

1. Adicionar um visual de matriz, redimensioná-lo e reposicioná-lo para que ele preencha o espaço restante da página de relatório

     ![Figura 45](Linked_image_Files/07-design-report-in-power-bi-desktop_image41.png)

1. Adicione a hierarquia **Data | Fiscal\| à caixa **Linhas da matriz.

     ![Figura 46](Linked_image_Files/07-design-report-in-power-bi-desktop_image42.png)

1. Adicione os cinco campos de tabela **Vendas** seguintes à caixa **Valores**:

     - Pedidos (da pasta **Contagens**)
     - Sales
     - Cost
     - Lucro
     - Margem de Lucro

     ![Figura 11](Linked_image_Files/07-design-report-in-power-bi-desktop_image43.png)

1. No painel **Filtros** (localizado à esquerda do painel **Visualizações**), observe a caixa **Filtrar Nesta Página** (talvez seja necessário rolar para baixo).

     ![Figura 57](Linked_image_Files/07-design-report-in-power-bi-desktop_image44.png)

1. No painel **Campos**, arraste o campo **Produto | Categoria\| para a caixa **Filtrar Nesta Página.
    
    *Os campos adicionados ao **painel Filtros** podem obter o mesmo resultado que uma segmentação de dados. Uma diferença é que eles não ocupam espaço na página do relatório. Outra diferença é que eles podem ser configurados para atender a requisitos de filtragem mais sofisticados.*

1. No cartão de filtro, no canto superior direito, selecione a seta para recolher o cartão.

1. Adicione cada um dos seguintes campos da tabela **Produto** à caixa **Filtrar Nesta Página**, recolhendo cada um, diretamente abaixo do cartão **Categoria**:

     - Subcategoria
     - Product
     - Color

     ![Figura 60](Linked_image_Files/07-design-report-in-power-bi-desktop_image46.png)

1. Salve o arquivo do Power BI Desktop.

 O design da segunda página agora está concluído.

## Página de design 3

Nesta tarefa, você criará a terceira e última página do relatório. Quando você tiver concluído o design, a página terá a seguinte aparência:

 ![Imagem da página 3, composta por uma segmentação de dados e três elementos visuais.](Linked_image_Files/07-design-report-in-power-bi-desktop_image47.png)

1. Crie uma página e renomeie-a como **Meu Desempenho**.

1. Para simular o desempenho dos filtros de segurança em nível de linha, arraste o **campo Vendedor** (Desempenho) \| para os filtros de nível de página no painel de filtros.

     ![Imagem do campo Vendedor no painel de filtro.](Linked_image_Files/07-design-report-in-power-bi-desktop_image999.png)

1. Selecione **Michael Blythe**. Os **dados na página Meu relatório de desempenho** agora serão filtrados para exibir dados somente para Michael Blythe.

1. Adicione uma segmentação suspensa com base no campo Data | Ano e redimensione e reposicione-o para que fique no canto superior esquerdo da página.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image49.png)

1. Na segmentação, defina a página para filtrar o conteúdo por **FY2019**.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image50.png)

1. Adicione um visual **Cartão de Várias Linhas** e redimensione-o e reposicione-o para que ele fique à direita da segmentação e preencha a largura restante da página.

     ![Figura 56](Linked_image_Files/07-design-report-in-power-bi-desktop_image51.png)

     ![Figura 16](Linked_image_Files/07-design-report-in-power-bi-desktop_image52.png)

1. Adicione os quatro seguintes campos ao visual:

     - Vendas | Vendas
     - Metas | Meta
     - Metas | Variância
     - Metas | Margem de Variância

1. Formatar o Visual:

     - No grupo **Rótulos de Dados**, aumente a propriedade **Tamanho do Texto** para **28pt**

     - **No grupo Efeitos > Gerais > Plano de Fundo**, defina a **Cor** como uma cor cinza claro (como "Branco, 20% mais escuro) para fornecer contraste

         ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image53.png)

1. Adicione um visual **Gráfico de Barras em Cluster**. Em seguida, redimensione e reposicione-o para que fique abaixo do visual de cartão de várias linhas e preencha a altura restante da página e metade da largura do visual do cartão de várias linhas.

     ![Figura 59](Linked_image_Files/07-design-report-in-power-bi-desktop_image54.png)

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image55.png)

1. Adicione os seguintes campos às caixas de visual:

     - Eixo Y: **Data \| Mês**
     - Vendas | Vendas e Metas | Meta

         ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image56.png)

1. Para criar uma cópia do visual, pressione **Ctrl+C** e **Ctrl+V**.

1. Posicione o visual copiado à direita do visual original.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image57.png)

1. Para modificar o tipo de visualização, no painel **Visualizações**, selecione **Gráfico de Colunas em Cluster**.

     ![Figura 61](Linked_image_Files/07-design-report-in-power-bi-desktop_image58.png)

 *Agora é possível ver os mesmos dados expressos por dois tipos de visualização diferentes. Esse não é um bom uso do layout de página, no entanto, você o aprimorará no laboratório Aprimorar um Relatório no **Power BI Desktop** sobrepondo os elementos visuais. Ao adicionar botões à página, você permitirá que o usuário do relatório determine qual dos dois elementos visuais está visível.*

 Agora, o design da terceira página (a final também) está completo.

## Publicar o relatório

Nesta tarefa, você vai explorar o relatório no serviço do Power BI.

1. Selecione a **página Visão geral** e salve o arquivo do Power BI Desktop.

1. Na guia de faixa de opções **Página Inicial**, no grupo **Compartilhar**, selecione **Publicar**.
    
    Se você já entrou no Power BI, não precisa entrar novamente.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image59.png)

1. Na janela **Publicar no Power BI**, observe que **Meu Workspace** está selecionado.
    
    *Não entraremos em detalhes sobre os diferentes itens dentro do serviço do Power BI neste laboratório.*

1. Para publicar o relatório, escolha **Selecionar**. Isso pode demorar alguns instantes. 
1. Quando a publicação for bem-sucedida, selecione **Entendi**.

## Explorar o relatório

Neste exercício, você vai explorar o relatório publicado no Power BI.

1. Abra um navegador Microsoft Edge e entre em **https://app.powerbi.com**.

1. Na janela do navegador Microsoft Edge, no serviço do Power BI, no painel **Navegação** (localizado à esquerda, possivelmente recolhido), expanda **Meu Workspace**.

    ![Figura 48](Linked_image_Files/06-my-workspace-new.png)

1. Revise o conteúdo do espaço de trabalho. Observe as opções de navegação de Todos, Conteúdo e Conjuntos de Dados + fluxos de dados.
    1. *Há quatro tipos de itens que podem existir em um espaço de trabalho, e falaremos sobre **relatórios** e **conjuntos** de dados.*
    1. *Talvez seja necessário atualizar o navegador Microsoft Edge se o conjunto de dados não estiver visível.*
    1. Quando você publicou o arquivo do Power BI Desktop, o modelo de dados foi publicado como um conjunto de dados.

1. Para abrir o relatório, selecione o relatório **Análise de Vendas**.

1. À esquerda, no painel **Páginas**, selecione a página **Lucro**.

1. Na segmentação **Regiões**, ao pressionar a tecla **Ctrl**, selecione várias regiões.

1. No gráfico de colunas/linhas, selecione qualquer coluna de mês para realizar a filtragem cruzada da página.

1. Enquanto pressiona a tecla **Ctrl**, selecione um mês adicional.

     Por padrão, a filtragem cruzada filtra os outros visuais da página.

1. Observe que o gráfico de barras é filtrado e realçado, com a parte em negrito das barras representando os meses filtrados.

1. Posicione o cursor sobre o visual e, no canto superior direito, posicione-o novamente sobre o ícone de filtro. 
    
    O ícone de filtro permite que você compreenda todos os filtros aplicados ao visual, incluindo segmentações e filtros cruzados de outro visual.

1. Passe o cursor sobre uma barra e observe as informações da dica de ferramentas.

1. Para desfazer o filtro cruzado, no gráfico de colunas/linhas, selecione uma área vazia do visual.

1. Posicione o cursor sobre o visual de mapa e, no canto superior direito, selecione o ícone **Modo de foco**.
    
    O modo de foco amplia o visual para o tamanho total da página.

     ![Ilustração 96](Linked_image_Files/07-published-report-visual-filter.png)

1. Focalize o cursor sobre segmentos diferentes dos gráficos de pizza para revelar dicas de ferramentas.

1. Para voltar à página do relatório, no canto superior esquerdo, selecione **Voltar ao Relatório**.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image66.png)

1. Posicione o cursor sobre o visual de mapa novamente, selecione as reticências (…) e observe as opções de menu. Experimente cada uma das opções, exceto **Conversar no Teams**.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image67.png)

1. À esquerda, no painel **Páginas**, selecione a página **Lucro**.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image68.png)

1. Observe que a segmentação Região tem uma seleção diferente para a segmentação Região na página Visão Geral.
    
    Você modificará o design do relatório para garantir que elas sejam sincronizadas entre as páginas no laboratório Criar um relatório no Power BI Desktop, parte 2.

1. No painel **Filtros** (localizado à direita), expanda um cartão de filtro e aplique alguns filtros.
    
    O painel Filtros permite que você defina mais filtros do que podem caber em uma página como segmentações.

1. No visual de matriz, use o botão de adição (+) para analisar a hierarquia **Fiscal**.

1. Selecione a página **Meu Desempenho**.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image69.png)

1. No canto superior direito da barra de menus, selecione **Exibição** e escolha **Tela Inteira**.

     ![Figura 19](Linked_image_Files/07-design-report-in-power-bi-desktop_image70.png)

1. Interaja com a página modificando a segmentação e realizando a filtragem cruzada da página.

1. No canto inferior da janela, observe os comandos para mudar de página, navegar para trás ou para frente entre as páginas ou para sair do modo de tela inteira.

1. Selecione o ícone direito para sair do modo de tela cheia.

     ![Figura 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image71.png)

### Conclusão

Nesta tarefa, você concluirá o laboratório.

Para retornar a "Meu Espaço de Trabalho", selecione **Meu Espaço de Trabalho** no banner na página da Web da janela.

 Você vai aprimorar o design do relatório com recursos avançados no laboratório Criar um relatório no Power BI Desktop, parte 2.
