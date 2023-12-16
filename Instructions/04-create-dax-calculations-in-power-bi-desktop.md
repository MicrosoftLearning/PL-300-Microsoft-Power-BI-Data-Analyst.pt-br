---
lab:
  title: 'Criar cálculos DAX no Power BI Desktop, parte 2'
  module: Create Model Calculations using DAX in Power BI
---


# Criar cálculos DAX no Power BI Desktop, parte 2

## **História do laboratório**

Neste laboratório, você criará tabelas e colunas calculadas, além de medidas simples usando o DAX (Data Analysis Expressions).

Neste laboratório, você aprenderá a:

- Criar tabelas calculadas
- Criar colunas calculadas
- Criar medidas

**Este exercício deve durar aproximadamente 45 minutos.**

## criar tabelas calculadas

Neste exercício, você criará duas tabelas calculadas. A primeira será a tabela **Vendedor**, para permitir um relacionamento direto entre ela e a tabela **Vendas**. O segundo será a tabela **Data**.

Se estiver dando continuidade ao laboratório anterior (e concluiu esse laboratório com sucesso), não conclua essa tarefa; em vez disso, continue na próxima tarefa.

1. Abra o Power BI Desktop.

    ![* Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Dica: por padrão, a caixa de diálogo Introdução é aberta na frente do Power BI Desktop. Você pode optar por entrar e, em seguida, fechar o pop-up.*

1. Para abrir o arquivo inicial do Power BI Desktop, na guia de faixa de opções Arquivo, selecione Abrir relatório e Procurar relatórios.

1. Na janela Abrir, procure a pasta D:\DA100\Labs\create-dax-calculations-in-power-bi-desktop\Starter.

1. Feche todas as janelas informativas que possam ser abertas.

1. Observe a mensagem de aviso em amarelo abaixo da faixa de opções.

    *Essa mensagem alerta para o fato de que as consultas não foram aplicadas para carregar como tabelas de modelo. Você aplicará as consultas posteriormente neste laboratório.*

    Para ignorar a mensagem de aviso, à direita da mensagem de aviso em amarelo, selecione X.

1. Para criar uma cópia do arquivo, vá para **Arquivo > Salvar como** e salve na **pasta D:\PL300\MySolution** .

1. Caso precise aplicar as alterações, selecione **Aplicar Mais Tarde**.

## criar a tabela Vendedor

Nesta tarefa, você criará a tabela **Salesperson** (relação direta com **Sales**).

Uma tabela calculada é criada inserindo primeiro o nome da tabela, seguido pelo símbolo de igual (=), seguido por uma fórmula DAX que retorna uma tabela. O nome da tabela não pode existir no modelo de dados.

A barra de fórmulas dá suporte à inserção de uma fórmula DAX válida. Ela inclui recursos como preenchimento automático, IntelliSense e codificação por cores, permitindo que você insira a fórmula com rapidez e precisão.

1. No Power BI Desktop, na exibição de Relatório, na faixa de opções **Modelagem** no grupo **Cálculos**, selecione **Nova Tabela**.

     ![Figura 1](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image9.png)

2. Na barra de fórmulas (que é aberta diretamente abaixo da faixa de opções ao criar ou editar cálculos), digite **Vendedor =**, pressione **Shift+Enter**, digite **"Vendedor (Desempenho)"** e pressione **Enter**.

    Para sua conveniência, todas as definições DAX deste laboratório podem ser copiadas do arquivo D:\DA100\Labs\create-dax-calculations-in-power-bi-desktop\Assets\Snippets.txt.

     ![Imagem 4](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image10.png)

     *Essa definição de tabela cria uma cópia da **tabela Vendedor (Desempenho).** Ele copia apenas os dados, no entanto, as propriedades do modelo, como visibilidade, formatação, etc. não são copiadas.*

     *Dica: você é incentivado a inserir "espaço em branco" (ou seja, retornos de carro e guias) para escrever fórmulas em um formato intuitivo e fácil de ler, especialmente quando as fórmulas são longas e complexas. Para inserir um retorno de carro, pressione **Shift+Enter**. "Espaço em branco" é opcional.*

1. No painel **Campos**, observe que o ícone de tabela tem um tom de azul (indicando uma tabela calculada).

    ![Figura 10](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image11.png)

    *Nota: As tabelas calculadas são definidas usando uma fórmula DAX que retorna uma tabela. É importante entender que as tabelas calculadas aumentam o tamanho do modelo de dados porque materializam e armazenam valores. Eles são recalculados sempre que as dependências de fórmula são atualizadas, como será o caso desse modelo de dados quando novos valores de data (futuros) são carregados em tabelas.*

    *Ao contrário das tabelas originadas pelo Power Query, as tabelas calculadas não podem ser usadas para carregar dados de fontes de dados externas. Eles só podem transformar dados com base no que já foi carregado no modelo de dados.*

1. Alterne para o modo de exibição Modelo e observe que a tabela Vendedor** está disponível (talvez seja necessário redefinir o modo de exibição para localizar a **tabela).

1. Crie um relacionamento da coluna **Vendedor | ChaveFuncionário\| com a coluna **Vendas | ChaveFuncionário.

1. Clique com o botão direito do mouse no relacionamento inativo entre as tabelas **Vendedor (Desempenho)** e **Vendas** e selecione **Excluir**. Quando precisar confirmar a exclusão, selecione Sim e Excluir.

1. Na tabela Vendedor, faça a multisseleção das seguintes colunas e oculte-as:

    - EmployeeID
    - EmployeeKey
    - UPN

1. No diagrama do modelo, selecione a tabela **Salesperson**.

1. No painel **Propriedades**, na caixa **Descrição**, insira: **Vendedor relacionado a uma venda**.
    
    Lembre-se de que descrições aparecem como dicas de ferramentas no painel Campos quando o usuário passa o cursor sobre uma tabela ou um campo.

1. Para a tabela Vendedor (Desempenho), defina a descrição como:

A tabela Vendedor** permite analisar as vendas feitas por um vendedor, enquanto a tabela **Vendedor (Desempenho) permite analisar as vendas realizadas nas regiões de vendas atribuídas ao vendedor.

## criar a tabela Data

Nesta tarefa, você criará a tabela **Data**.

1. Alterne para a exibição Dados. Na guia de faixa de opções **Página Inicial**, no grupo **Cálculos**, selecione **Nova Tabela**.

    ![Figura 5](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image15.png)

1. Na barra de fórmulas, insira o seguinte código:

    **DAX**

    ```
    Date =  
    CALENDARAUTO(6)
    ```

    ![Figura 6](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image16.png)


    *A função CALENDARAUTO() retorna uma tabela de coluna única que consiste em valores de data. O comportamento "automático" verifica todas as colunas de data do modelo de dados para determinar os valores de data mais antigos e mais recentes armazenados no modelo de dados. Em seguida, ele cria uma linha para cada data dentro desse intervalo, estendendo o intervalo em qualquer direção para garantir que anos completos de dados sejam armazenados.*

    *Essa função pode usar um único argumento opcional que é o último número de mês de um ano. Quando omitido, o valor é 12, o que significa que dezembro é o último mês do ano. Neste caso, 6 é inserido, o que significa que junho é o último mês do ano.*

1. Observe a coluna de valores de data.

    ![Figura 7](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image17.png)

    As datas mostradas são formatadas com as configurações regionais dos EUA (ou seja, mm/dd/aaaa).

5. No canto inferior esquerdo, na barra de status, observe as estatísticas de tabela, confirmando que foram geradas 1.826 linhas de dados, o que representa cinco anos completos de dados.

    ![Figura 9](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image18.png)

## Criar colunas calculadas

Nesta tarefa, você adicionará mais colunas para habilitar a filtragem e o agrupamento por períodos diferentes. Você também criará uma coluna calculada para controlar a ordem de classificação de outras colunas.

Para sua conveniência, todas as definições DAX deste laboratório podem ser copiadas do arquivo D:\DA100\Labs\create-dax-calculations-in-power-bi-desktop\Assets\Snippets.txt.

1. Na faixa de opções contextual **Ferramentas de Tabela**, no grupo **Cálculos**, selecione **Nova Coluna**.

    ![Figura 11](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image19.png)

1. Na barra de fórmulas, digite o seguinte e pressione **Enter**:


    **DAX**


    ```
    Year =
    "FY" & YEAR('Date'[Date]) + IF(MONTH('Date'[Date]) > 6, 1)
    ```


    Uma coluna calculada é criada inserindo primeiro o nome da coluna, seguido pelo símbolo de igual (=), seguido por uma fórmula DAX que retorna um resultado de valor único.

    A fórmula usa o valor de ano da data, mas adiciona um ao valor de ano quando o mês é posterior a junho.

1. Verifique se a nova coluna foi adicionada.

    ![Figura 12](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image20.png)

1. Use as definições de arquivo de snippets para criar estas duas colunas calculadas para a tabela **Data**:

    - Trimestre
    - Mês

    ![Figura 14](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image21.png)

1. Para validar os cálculos, alterne para a exibição Relatório.

1. Para criar uma nova página de relatório, selecione o ícone de adição ao lado de Página 1.

    ![Figura 15](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image22.png)

1. Para adicionar um visual da matriz à nova página de relatório, no painel **Visualizações**, selecione o tipo de visual da matriz.

    Você pode passar o cursor sobre cada ícone para revelar uma dica de ferramenta que descreve o tipo de visual.

    ![Figura 51](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image23.png)

1. No painel **Campos**, dentro da tabela **Data**, arraste o campo **Ano** para a caixa **Linhas**.

    ![Figura 17](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image24.png)

1. Arraste o campo **Mês** até a caixa **Linhas**, diretamente abaixo do campo **Ano**.

    ![Figura 18](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image25.png)

1. No canto superior direito do visual da matriz (ou inferior, dependendo da localização do visual), selecione o ícone de seta dupla bifurcada (que expandirá todos os anos para baixo um nível).

    ![Figura 19](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image26.png)

1. Observe que os anos se expandem para meses e que os meses são classificados em ordem alfabética, em vez de cronologicamente.

    ![Figura 20](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image27.png)

    Por padrão, os valores de texto são classificados em ordem alfabética, os números são classificados do menor para o maior, e as datas são classificadas da mais antiga para a mais recente.

1. Para personalizar a ordem de classificação do campo **Mês**, alterne para a exibição Dados.

1. Adicione a coluna **ChaveMês** à tabela **Data**.


    **DAX**


    ```
    MonthKey =
    (YEAR('Date'[Date]) * 100) + MONTH('Date'[Date])
    ```


    Essa fórmula calcula um valor numérico para cada combinação de ano/mês.

1. Na exibição Dados, verifique se a nova coluna contém valores numéricos (por exemplo, 201707 para julho de 2017 etc.).

    ![Figura 21](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image28.png)

1. Alterne novamente para a exibição de Relatório. No painel **Campos**, verifique se o campo **Mês** está selecionado (quando selecionado, ele terá um plano de fundo cinza escuro).

1. Na faixa de opções contextual **Ferramentas de Coluna**, no grupo **Classificar**, selecione **Classificar por Coluna** e escolha **MonthKey**.

    ![Figura 22](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image29.png)

1. No visual da matriz, observe que os meses agora estão classificados cronologicamente.

    ![Figura 23](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image30.png)

## concluir a tabela Data

Nesta tarefa, você concluirá o design da tabela **Data** ocultando uma coluna e criando uma hierarquia. Em seguida, você criará relacionamentos para as tabelas **Vendas** e **Destinos**.

1. Alterne para a exibição de Modelo. **Na tabela Data**, oculte a **coluna MonthKey** (defina **Está oculto** como **Sim**).


1. No painel direito Campos, selecione a tabela Date, clique com o botão direito do mouse na coluna Year e selecione Criar hierarquia. 

1. Renomeie a hierarquia recém-criada para **Fiscal** clicando com o botão direito do mouse e em **Renomear**


1. Adicione os dois campos restantes a seguir à hierarquia Fiscal selecionando-os no painel Campos, clicando com o botão direito do mouse e selecionando **Adicionar à hierarquia**Fiscal

    - Trimestre
    - Mês

    ![Figura 24](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image31.png)

1. Crie estas duas relações de modelo:

    - **Data | Data\| para **Vendas | DataPedido
    - **Data | Data\| para **Destino | MêsDestino

1. Oculte estas duas colunas:

    - Vendas (OrderDate)
    - Destinos | MêsDestino

## marcar a tabela Data

Nesta tarefa, você marcará a tabela **Data** como uma tabela de data.

1. Alterne para a exibição Relatório. No painel **Campos**, selecione a tabela **Date** (não o campo **Date**).

1. Na faixa de opções contextual **Ferramentas de Tabela**, no grupo **Calendários**, selecione **Marcar como Tabela de Data** e escolha **Marcar como Tabela de Data**.

    ![Figura 8](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image32.png)

1. Na janela **Marcar como Tabela de Data**, na lista suspensa **Coluna de Data**, selecione **Data**. Selecione **OK**.

    ![Figura 37](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image33.png)

1. Salve o arquivo do Power BI Desktop.

    *O Power BI Desktop agora entende que essa tabela define data (hora). É importante quando se baseia em cálculos de inteligência de tempo. Você trabalhará com cálculos de inteligência de tempo no laboratório Criar cálculos DAX avançados no **Power BI Desktop** .*

    *Essa abordagem de design para uma tabela de data é adequada quando você não tem uma tabela de data em sua fonte de dados. Se você tiver um data warehouse, seria apropriado carregar dados de data de sua tabela de dimensão de data em vez de "redefinir" a lógica de data em seu modelo de dados.*

## Criar medidas simples

Nesta tarefa, você criará medidas simples. Medidas simples agregam valores em uma única coluna ou contam linhas de uma tabela.

1. Na exibição Relatório, na Página 2, no painel Campos, arraste o campo Vendas | Preço Unitário para a seção Valores no visual da matriz.

    *Os laboratórios usam uma notação taquigráfica para fazer referência a um campo. Ficará assim: **Preço** Unitário de Vendas\|. Neste exemplo, **Sales** é o nome da tabela e **Unit Price** é o nome do campo.*

    ![Figura 27](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image35.png)

    *Você deve se lembrar de que, no laboratório Dados de **Modelo no Power BI Desktop** , você define a **coluna Preço** Unitário para resumir por **Média**. O resultado que você vê no visual da matriz é o preço unitário médio mensal (soma dos valores de preço unitário dividida pela contagem de preços unitários).*

1. No painel de campos de visuais (localizado abaixo do painel **Visualizações**), na caixa **Valores**, observe que **Preço Unitário** está listado.

    ![Imagem 28](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image36.png)

1. Escolha a seta para baixo de **Unit Price** e observe as opções de menu disponíveis.

    ![Imagem 30](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image37.png)

    *As colunas numéricas visíveis permitem que os autores de relatório em tempo de design do relatório decidam como os valores de coluna serão resumidos (ou não). Isso pode resultar em relatórios inadequados. Alguns modeladores de dados não gostam de deixar as coisas ao acaso, no entanto, e optam por ocultar essas colunas e, em vez disso, expor a lógica de agregação definida em medidas. É a abordagem que você agora adotará neste laboratório.*

1. Para criar uma medida, no painel **Campos**, clique com o botão direito do mouse na tabela **Vendas** e selecione **Nova Medida**.

1. Na barra de fórmulas, adicione a seguinte definição de medida:


    **DAX**


    ```
    Avg Price =  
    AVERAGE(Sales[Unit Price])
    ```

1. Adicione a medida **Receita do ano anterior** ao visual da matriz.

1. Observe que ela produz o mesmo resultado que a coluna **Preço Unitário** (mas com formatação diferente).

1. Na caixa **Valores**, abra o menu de contexto do campo **Preço Médio** e observe que não é possível alterar a técnica de agregação.

    ![Figura 32](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image39.png)

    *Não é possível modificar o comportamento de agregação de uma medida.*

1. Use as definições de arquivo de snippets para criar as cinco medidas a seguir para a tabela **Vendas**:

    - Preço Mediano
    - Preço Mín.
    - Preço Máx.
    - Ordens
    - Linhas de Pedidos

    *A função DISTINCTCOUNT() usada na **medida Orders** contará pedidos apenas uma vez (ignorando duplicatas). A função COUNTROWS() usada na **medida Order Lines** opera sobre uma tabela.*

    Nesse caso, o número de pedidos é calculado contando os valores distintos da coluna NúmeroPedidosVendas, enquanto o número de linhas do pedido é simplesmente o número de linhas da tabela (cada linha é uma linha de um pedido).

10. Alterne para o modo de exibição Modelo e selecione várias vezes as quatro medidas de preço: **Preço médio, Preço máximo, ****Preço médio e **Preço******** mínimo.

11. Para a seleção de várias medidas, configure os seguintes requisitos:

    - Definir o formato para duas casas decimais

    - Atribuir uma pasta de exibição chamada **Preços**

    ![Figura 11](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image40.png)

12. Oculte a coluna **Preço Unitário**.

    *A **coluna Preço Unitário** agora não está disponível para autores de relatórios. Eles devem usar as medidas de preços que você adicionou ao modelo. Essa abordagem de design garante que os autores de relatórios não agreguem preços inadequadamente, por exemplo, somando-os.*

13. Faça a seleção múltipla de medidas de **Pedidos** e **Linhas de pedidos** e configure os seguintes requisitos:

    - Definir o formato para usar o separador de milhar

    - Atribuir a uma pasta de exibição chamada **Contagens**

    ![Figura 36](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image41.png)

14. Na exibição de Relatório, na caixa **Valores** do visual de matriz, no campo **Preço Unitário**, selecione **X** para removê-lo.

    ![Figura 38](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image42.png)

15. Aumente o tamanho do visual da matriz para preencher a largura e a altura da página.

16. Adicione estas cinco novas medidas ao visual da matriz:

    - Preço Mediano
    - Preço Mín.
    - Preço Máx.
    - Ordens
    - Linhas de Pedidos

17. Verifique se os resultados parecem razoáveis e se estão formatados corretamente.

    ![Figura 39](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image43.png)

## criar medidas adicionais

Nesta tarefa, você criará medidas adicionais que usam expressões mais complexas.

1. No modo de exibição Relatório, selecione **Página 1** e revise o visual da tabela, observando o total da **coluna Destino** .

    ![Figura 41](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image45.png)


1. Selecione o visual de tabela e, no painel **Visualizações**, remova o campo **Meta**.

1. Renomear a coluna **Destinos | Destino\| como **Destinos | ValorDestino.

    *Dica: há várias maneiras de renomear a coluna no modo de exibição Relatório: no **painel Dados** , você pode clicar com o botão direito do mouse na coluna e selecionar **Renomear** ou clicar duas vezes na coluna ou pressionar **F2**.*

    *Você está prestes a criar uma medida chamada **Target**. Não é possível ter uma coluna e uma medida na mesma tabela com o mesmo nome.*

1. Crie a seguinte medida na tabela **Destinos**:

    **DAX**


    ```
    Target =

    IF(

    HASONEVALUE('Salesperson (Performance)'[Salesperson]),

    SUM(Targets[TargetAmount])

    )
    ```

    *A função HASONEVALUE() testa **se um único valor na coluna Vendedor** é filtrado. Quando true, a expressão retorna a soma dos valores de destino (apenas para esse vendedor). Quando false, BLANK é retornado.*

1. Formate a medida de **Destino** para zero casas decimais.

    Você pode usar a faixa de opções contextual Ferramentas de Medida.

1. Oculte a coluna **ValorDestino**.

    Clique com o botão direito do mouse na coluna no painel Campos** e selecione **Ocultar.

1. Adicione a medida **Destino** ao visual da tabela.

1. Observe que o total da coluna **Destino** está EM BRANCO agora.

    ![Figura 43](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image47.png)

1. Use as definições de arquivo de snippets para criar as duas medidas a seguir para a tabela **s**:

    - Variance
    - Margem de variância

1. Formate a medida de **Variância** para zero casas decimais.

1. Formate a medida **Margem de variância** como uma porcentagem com duas casas decimais.

1. Adicione as medidas **Variância** e **Margem de variância** ao visual da tabela.

1. Redimensione o visual de tabela para que você possa ver todas as colunas e linhas.

    ![Figura 44](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image48.png)

    *Embora pareça que todos os vendedores não estão cumprindo a meta, lembre-se de que o visual da tabela ainda não foi filtrado por um período de tempo específico. Você produzirá relatórios de desempenho de vendas que filtram por um período de tempo selecionado pelo **usuário no laboratório Criar um Relatório no Power BI Desktop** .*

1. No canto superior direito do painel **Campos**, recolha e então expanda o painel.

    Recolher e reabrir o painel redefine o conteúdo.

1. Observe que a tabela **Destinos** agora aparece na parte superior da lista.

    ![Figura 46](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image50.png)

    As tabelas que compõem apenas as medidas visíveis são listadas automaticamente na parte superior da lista.

### Conclusão

Salve o arquivo do Power BI Desktop.

Você vai aprimorar o modelo de dados com cálculos mais avançados usando o DAX no laboratório Criar cálculos DAX no Power BI Desktop, parte 2.
