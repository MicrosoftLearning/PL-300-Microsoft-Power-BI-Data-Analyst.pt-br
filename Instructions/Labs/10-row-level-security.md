---
lab:
  title: Impor a Segurança em Nível de Linha
  module: Enforce Row-Level Security
---

# Impor a Segurança em Nível de Linha

## História do laboratório

Neste laboratório, você vai impor a segurança em nível de linha para garantir que cada vendedor só possa analisar dados de vendas para as regiões atribuídas a ele.

Neste laboratório, você aprenderá a:

- Impor a Segurança em Nível de Linha
- Escolher entre métodos dinâmicos e estáticos

**Este laboratório levará aproximadamente 20 minutos.**

## Introdução

Para concluir este exercício, primeiro abra um navegador da Web e insira a seguinte URL para baixar a pasta zip:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/10-row-level-security/10-row-level-security.zip`

Extraia a pasta para a pasta **C:\Users\Student\Downloads\10-row-level-security**.

Abra o arquivo **10-Starter-Sales Analysis.pbix**.

> ***Observação**: você pode ignorar a entrada clicando em **Cancelar**. Feche todas as janelas informativas. Caso precise aplicar as alterações, clique em **Aplicar depois**.*

## Impor a segurança em nível de linha

Nesta tarefa, você vai impor a segurança em nível de linha para garantir que um vendedor só possa ver as vendas feitas nas regiões atribuídas a ele.

1. Alternar para a exibição de Tabela.

   ![Imagem 5701](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image20.png)

1. No painel **Data**, selecione a tabela **Vendedor (Desempenho)**.

1. Examine os dados, observando que Michael Blythe (EmployeeKey 281) tem um valor UPN igual a: **`michael-blythe@adventureworks.com`**
    
    > *Você deve se lembrar que Michael Blythe foi atribuído a três regiões de vendas: Nordeste dos EUA, EUA Central e Sudeste dos EUA.*

1. Na guia de faixa de opções **Página inicial**, no grupo **Segurança**, selecione **Gerenciar Funções**.

    ![Imagem 5700](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image21.png)

1. Na janela **Gerenciar funções de segurança**, na seção **Funções**, clique em **Novo**.

1. Na caixa, substitua o texto selecionado pelo nome da função: **Vendedores** e pressione **Enter**.

   ![Imagem 5703](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image23.png)

1. Para atribuir um filtro, clique na tabela **Vendedor (Desempenho)** e, em seguida, selecione **Alternar para o editor DAX** na seção **Filtrar dados**.

   ![Captura de tela 18-04-2024 144345](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/1308d47f-2cca-4f88-9237-b02b66b4cf1e)

1. No editor do DAX, digite a expressão a seguir:

    ```DAX
    [UPN] = USERPRINCIPALNAME()
    ```

   ![Figura 11](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image25.png)

    > *USERPRINCIPALNAME() é uma função DAX (Data Analysis Expressions) que retorna o nome do usuário autenticado. Isso significa que a tabela **Vendedor (Desempenho)** será filtrada pelo UPN (Nome Principal do Usuário) do usuário que está consultando o modelo.*

1. Selecione **Salvar** e **Fechar**.

1. Para testar a função de segurança, na guia de faixa de opções **Página inicial**, no grupo **Segurança**, selecione **Exibir como**.

   ![Imagem 5708](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image27.png)

1. Na janela **Exibir como Funções**, marque o item **Outro Usuário** e, na caixa correspondente, insira: **`michael-blythe@adventureworks.com`**

1. Verifique a função **Vendedores** e, em seguida, **OK**.
    
    > *Essa configuração resulta no uso da função **Vendedores** e na representação do usuário com o nome de Michael Blythe.*

   ![imagem 5709](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image28.png)

1. Observe a faixa amarela acima da página do relatório, descrevendo o contexto de segurança do teste.

   ![Figura 13](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image30.png)

1. No visual de tabela, observe que só o vendedor **Michael Blythe** está listado.

   ![Imagem 5713](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image31.png)

1. Para interromper o teste, no lado direito da faixa amarela, selecione **Parar de Exibir**.

   ![Imagem 5712](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image32.png)

1. Para excluir a função **Vendedor**, na guia de faixa de opções **Página Inicial**, no grupo **Segurança**, selecione **Gerenciar Funções**.

   ![Figura 16](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image33.png)

1. Na janela **Gerenciar funções de segurança**, clique nas reticências (...) na função **Vendedor** e clique em **Excluir**. Quando precisar confirmar a exclusão, selecione **Sim, Excluir**.

   ![Captura de tela 18-04-2024 145556](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/deeb4eac-b639-433d-a9d4-29c8e127008e)

*Observação: quando o arquivo do Power BI Desktop for publicado no serviço do Power BI, você precisará concluir uma tarefa de pós-publicação para mapear entidades de segurança para a função **Vendedores**. Isso não será feito neste laboratório.*

## Laboratório concluído
