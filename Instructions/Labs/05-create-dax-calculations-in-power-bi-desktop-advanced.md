---
lab:
  course: PL-300
  title: Criar Cálculos DAX Avançados no Power BI Desktop
  module: Create Model Calculations using DAX in Power BI
---


# Criar Cálculos DAX Avançados no Power BI Desktop

## **História do laboratório**

Neste laboratório, você criará medidas com expressões DAX envolvendo manipulação de contexto de filtro.

Neste laboratório, você aprenderá a:

- Usar a função CALCULATE () para manipular o contexto do filtro
- Usar as funções de Inteligência de dados temporais

**Este laboratório levará aproximadamente 45 minutos.**

## **Trabalhar com Contexto de Filtro**

*Importante: se estiver dando continuidade ao laboratório anterior (e concluiu esse laboratório com sucesso), não conclua essa tarefa; em vez disso, continue na próxima tarefa.*

1. Abra o Power BI Desktop.

    ![Ícone do Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. Para abrir o arquivo inicial do Power BI Desktop, clique em **Abrir > Procurar neste dispositivo Relatório**.

1. Na janela **Abrir**, navegue até a pasta **D:\Allfiles\Labs\05-create-dax-calculations-in-power-bi-desktop-advanced\Starter** e abra o arquivo **Análise de Vendas**.

   *Observação: neste momento, o Power BI solicitará que você entre se ainda não tiver entrado. Você pode entrar ou clicar em **Cancelar** e continuar o laboratório.*

1. Feche todas as janelas informativas que possam ser abertas.

1. Observe a mensagem de aviso abaixo da faixa de opções. 

    *Essa mensagem alerta para o fato de que as consultas não foram aplicadas para carregar como tabelas de modelo. Você aplicará as consultas posteriormente neste laboratório.*
    
    *Para ignorar a mensagem de aviso, à direita da mensagem de aviso, selecione **X**.*

1. Para criar uma cópia do arquivo, vá para **Arquivo > Salvar como** e salve na pasta **D:\Allfiles\MySolution**.

1. Caso precise aplicar as alterações, selecione **Aplicar Mais Tarde**.

## **Criar um visual de matriz**

Nesta tarefa, você criará um visual de matriz para testar suas novas medidas.

1. No modo de relatório do Power BI Desktop, crie uma página de relatório.

1. Na **Página 3**, adicione um visual de matriz.

    ![Figura 13](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image10.png)

1. Redimensione o visual da matriz de modo a preencher a página inteira.

1. Para configurar os campos de visuais da matriz, no painel **Data**, arraste a hierarquia **Região \| Regiões** e solte-a dentro do visual.
    
    *Os laboratórios usam uma notação abreviada para fazer referência a um campo ou hierarquia. O resultado será semelhante a este: **Região \| Regiões**. Neste exemplo, **Região** é o nome da tabela e **Regiões** é o nome da hierarquia.*

1. Adicione também o campo **Vendas \| Vendas**.

1. Para expandir toda a hierarquia, no canto superior direito do visual de matriz, selecione o ícone de seta bifurcada duas vezes.
    
    *Lembre-se de que a hierarquia **Regiões** possui os níveis **Grupo**, **País** e **Região**.*

    ![Figura 47](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image11.png)

1. Para formatar o visual, no painel **Visualizações**, selecione o painel **Formatar**.

    ![Figura 14](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image12.png)

1. Na caixa de **Pesquisa**, digite **Nível**.

1. Defina a propriedade **Layout de nível** como **Desativada**.

    ![Figura 49](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image14.png)

1. Verifique se o visual da matriz agora tem quatro cabeçalhos de coluna.

    ![Figura 50](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image15.png)

    *No Adventure Works, as regiões de vendas são organizadas em grupos, países e regiões. Todos os países, exceto os Estados Unidos, têm apenas uma região, que leva o nome do país. Como os Estados Unidos são um território de vendas muito grande, ele é dividido em cinco regiões de vendas.*

    *Você criará várias medidas neste exercício, depois as testará adicionando-as ao visual da matriz.*

## **Manipular o contexto de filtro**

Nesta tarefa, você criará várias medidas com expressões DAX que usam a função CALCULATE() para manipular o contexto de filtro.

1. Adicione uma medida à tabela **Vendas**, com base na seguinte expressão:
    
     *Para sua conveniência, todas as definições DAX deste laboratório podem ser copiadas do arquivo **D:\Allfiles\Labs\05-create-dax-calculations-in-power-bi-desktop-advanced\Assets\Snippets.tx**.*


    **DAX**


    ```
    Sales All Region =

    CALCULATE(SUM(Sales[Sales]), REMOVEFILTERS(Region))
    ```


    *A função CALCULATE() é uma função poderosa usada para manipular o contexto do filtro. O primeiro argumento toma uma expressão ou uma medida (uma medida é apenas uma expressão nomeada). Os argumentos subsequentes permitem modificar o contexto do filtro.*

    *A função REMOVEFILTERS() remove os filtros ativos. Ela pode não remover nenhum argumento ou usar uma tabela, uma coluna ou várias colunas como seu argumento.*

    *Nesta fórmula, a medida avalia a soma da coluna **Vendas** em um contexto de filtro modificado, que remove todos os filtros aplicados à tabela **Região**.*

1. Adicione a medida **Vendas de Todas as Regiões** ao visual da matriz.

    ![Figura 52](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image16.png)

1. Observe que a medida **Vendas de todas as regiões** calcula o total de vendas de todas as regiões por região, país (subtotal) e grupo (subtotal).

    *A nova medida ainda não entregou um resultado útil. Quando as vendas de um grupo, país ou região são divididas por esse valor, é gerada uma taxa útil conhecida como "porcentagem do total geral".*

1. No painel **Data**, verifique se a medida **Vendas de Todas as Regiões** está selecionada (quando selecionada, ela tem uma tela de fundo cinza-escuro) e, na barra de fórmulas, substitua o nome da medida e a fórmula pela seguinte fórmula:

    *Dica: para substituir a fórmula existente, primeiro copie o trecho. Em seguida, selecione dentro da barra de fórmulas e pressione **Ctrl+A** para selecionar todo o texto. Em seguida, pressione **Ctrl+V** para colar o trecho para substituir o texto selecionado. Em seguida, pressione **Enter**.*


    **DAX**


    ```
    Sales % All Region =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region)  
     )  
    )
    ```

    *A medida foi renomeada para refletir de modo mais preciso a fórmula atualizada. A função DIVIDE() divide a medida **Vendas** (não modificada pelo contexto de filtro) pela medida **Vendas** em um contexto modificado que remove todos os filtros aplicados à tabela **Região**.*

1. No visual da matriz, observe que a medida foi renomeada e que um valor diferente agora aparece para cada grupo, país e região.

1. Formate a medida **% de vendas de todas as regiões** como uma porcentagem com duas casas decimais.

1. No visual da matriz, revise os valores da medida **% de vendas de todas as regiões**.

    ![Figura 53](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image17.png)

1. Adicione outra medida à tabela **Vendas**, com base na seguinte expressão, e formate-a como uma porcentagem:


    **DAX**

    ```
    Sales % Country =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region[Region])  
     )  
    )
    ```

1. Observe que a fórmula da medida **% de vendas por país** difere ligeiramente da fórmula da medida **% de vendas de todas as regiões**.

    *A diferença é que o denominador modifica o contexto do filtro removendo os filtros na coluna **Região** da tabela **Região**, não em todas as colunas da tabela **Região**. Isso significa que todos os filtros aplicados às colunas de grupo ou país são preservados. Ele alcançará um resultado que representa as vendas como uma porcentagem do país.*

1. Adicione a medida **% de vendas por país** ao visual da matriz.

1. Observe que apenas as regiões dos Estados Unidos produzem um valor que não é 100%.
    
    *Você deve se lembrar que apenas os Estados Unidos têm várias regiões. Todos os outros países compõem uma única região, o que explica por que todos eles são 100%.*

    ![Figura 54](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image18.png)

    

1. Para melhorar a legibilidade dessa medida no visual, substitua a medida **% de vendas por país** por esta fórmula aprimorada.


    **DAX**


    ```
    Sales % Country =  
    IF(  
     ISINSCOPE(Region[Region]),  
     DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region[Region])  
     )  
     )  
    )
    ```


    *A função IF() usa a função ISINSCOPE() para testar se a coluna de região é o nível em uma hierarquia de níveis. Quando verdadeiro, a função DIVIDE() é avaliada. Quando false, um valor em branco é retornado porque a coluna de região não está no escopo.*

1. Observe que a medida **% de vendas por país** agora retorna um valor apenas quando a região está no escopo.

    ![Imagem 55](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image19.png)

1. Adicione outra medida à tabela **Vendas**, com base na seguinte expressão, e formate-a como uma porcentagem:


    **DAX**


    ```
    Sales % Group =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(  
     Region[Region],  
     Region[Country]  
     )  
     )  
    )
    ```


    *Para alcançar vendas como uma porcentagem de grupo, dois filtros podem ser aplicados para remover de maneira eficiente os filtros em duas colunas.*

1. Adicione a medida **% de vendas por grupo** ao visual da matriz.

1. Para melhorar a legibilidade dessa medida no visual, substitua a medida **% de vendas por grupo** por esta fórmula aprimorada.


    **DAX**


    ```
    Sales % Group =  
    IF(  
     ISINSCOPE(Region[Region])  
     || ISINSCOPE(Region[Country]),  
     DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(  
     Region[Region],  
     Region[Country]  
     )  
     )  
     )  
    )
    ```


1. Observe que a medida **% de vendas por grupo** agora retorna um valor apenas quando a região ou o país estão no escopo.

1. Em uma exibição Modelo, coloque as três novas medidas em uma pasta de exibição nomeada **Índices**.

    ![Figura 56](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image20.png)

1. Salve o arquivo do Power BI Desktop.

*As medidas adicionadas à tabela **Vendas** modificaram o contexto de filtros para alcançar a navegação hierárquica. Observe que o padrão para alcançar o cálculo de um subtotal requer a remoção de algumas colunas do contexto de filtro e, para chegar no total geral, todas as colunas devem ser removidas.*

## **Usar Inteligência de Dados Temporais**

Neste exercício, você criará uma medida de vendas YTD (desde o início do ano) e uma medida de crescimento YoY (ano a ano).

## **Criar uma medida YTD**

Nesta tarefa, você criará uma medida de vendas YTD.

1. Na exibição Relatório, na **Página 2**, observe o visual da matriz que apresenta várias medidas com anos e meses agrupados nas linhas.

2. Adicione uma medida à tabela **Vendas**, com base na seguinte expressão, e formate-a para zero casas decimais:


    **DAX**


    ```
    Sales YTD =  
    TOTALYTD(SUM(Sales[Sales]), 'Date'[Date], "6-30")
    ```


    *A função TOTALYTD() avalia uma expressão — neste caso, a soma da coluna **Vendas** — sobre uma determinada coluna de data. A coluna de data deve pertencer a uma tabela de data marcada como uma tabela de data, como foi feito no laboratório **Criar Cálculos DAX no Power BI Desktop**.*

    *A função também pode ter um terceiro argumento opcional que representa a última data de um ano. A ausência dessa data significa que 31 de dezembro é a última data do ano. Para o Adventure Works, junho é o último mês do ano, e assim "6-30" é usado.*

3. Adicione o campo **Vendas** e a medida **Vendas YTD** ao visual da matriz.

4. Observe o acúmulo de valores de vendas durante o ano.

    ![Figura 59](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image21.png)

    *A função TOTALYTD() realiza manipulação de filtros, especificamente manipulação de filtros de tempo. Por exemplo, para computar vendas YTD para setembro de 2017 (terceiro mês do ano fiscal), todos os filtros na tabela **Data** são removidos e substituídos por um novo filtro de datas que começa no início do ano (1º de julho de 2017) e estende-se até a última data do período dentro do contexto (30 de setembro de 2017).*

    *Muitas funções de inteligência de dados temporais estão disponíveis em DAX para dar suporte a manipulações de filtros de tempo comuns.*

## **Criar uma medida de crescimento YoY**

Nesta tarefa, você criará uma medida de crescimento de vendas YoY.

1. Adicione outra medida à tabela **Vendas**, com base na seguinte expressão:


    **DAX**


    ```
    Sales YoY Growth =  
    VAR SalesPriorYear =  
     CALCULATE(  
     SUM(Sales[Sales]),  
     PARALLELPERIOD(  
     'Date'[Date],  
     -12,  
     MONTH  
     )  
     )  
    RETURN  
     SalesPriorYear
    ```


    *A medida **Crescimento de Vendas YoY** usa uma variável. As variáveis ajudam a simplificar a fórmula e são mais eficientes se usarem a lógica várias vezes dentro de uma fórmula.*

    *As variáveis são declaradas com um nome exclusivo e a expressão de medida deve ser saída após a palavra-chave **RETURN**. Ao contrário de algumas outras variáveis de linguagem de codificação, as variáveis DAX só podem ser usadas dentro da fórmula única.*

    *A variável **SalesPriorYear** recebe uma expressão que calcula a soma da coluna **Vendas** em um contexto modificado que usa a função PARALLELPERIOD() para deslocar 12 meses para trás de cada data no contexto de filtro.*

1. Adicione a medida **Crescimento de vendas YoY** ao visual da matriz.

1. Observe que a nova medida retorna BLANK para os primeiros 12 meses (não foram registradas vendas antes do ano fiscal de 2017).

1. Observe que o valor da medida de **Crescimento de Vendas YoY** para **julho de 2018** é o valor de **Vendas** para **julho de 2017**.

    ![Figura 61](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image22.png)

    *Agora que a parte “difícil” da fórmula foi testada, você pode substituir a medida pela fórmula final que calcula o resultado de crescimento.*

1. Para completar a medida, substitua a medida **Crescimento de vendas YoY** por esta fórmula, formatando-a como uma porcentagem com duas casas decimais:


    **DAX**


    ```
    Sales YoY Growth =  
    VAR SalesPriorYear =  
     CALCULATE(  
     SUM(Sales[Sales]),  
     PARALLELPERIOD(  
     'Date'[Date],  
     -12,  
     MONTH  
     )  
     )  
    RETURN  
     DIVIDE(  
     (SUM(Sales[Sales]) - SalesPriorYear),  
     SalesPriorYear  
     )
    ```


1. Na fórmula, na cláusula **RETURN**, observe que a variável é referenciada duas vezes.

1. Verifique que o crescimento YoY para **Julho de 2018** é de **392,83%**.

    ![Figura 62](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image23.png)

    *A medida de crescimento YoY identifica um aumento de quase 400% (ou 4x) das vendas durante o mesmo período do ano anterior.*

1. Em uma exibição Modelo, coloque as duas novas medidas em uma pasta de exibição chamada **Inteligência de dados temporais**.

    ![Figura 63](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image24.png)

### **Conclusão**

Nesta tarefa, você concluirá o laboratório.

1. Para limpar a solução pronta para o desenvolvimento de relatórios, no canto inferior esquerdo, clique com o botão direito do mouse na guia **Página 2** e selecione a página **Excluir**. Quando precisar excluir a página, selecione **Excluir**.

1. Exclua também a **Página 3**.

1. Na página restante, para desmarcá-la, selecione o visual de tabela e clique na tecla **Delete**.

1. Salve o arquivo do Power BI Desktop.

1. Se você pretende iniciar o próximo laboratório, mantenha o Power BI Desktop aberto.

*Você criará um relatório com base no modelo de dados do laboratório **Criar um Relatório no Power BI Desktop**.*
