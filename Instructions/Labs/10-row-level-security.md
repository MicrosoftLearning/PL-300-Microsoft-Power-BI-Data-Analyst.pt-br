---
lab:
  title: Impor a Segurança em Nível de Linha
  module: Enforce Row-Level Security
---


# Impor a Segurança em Nível de Linha

## **História do laboratório**

Neste exercício, você vai impor a segurança em nível de linha para garantir que cada vendedor só possa analisar dados de vendas para as regiões atribuídas a ele.

Neste laboratório, você aprenderá a:

- Impor a Segurança em Nível de Linha
- Escolher entre métodos dinâmicos e estáticos

**Este exercício levará aproximadamente 20 minutos.**

## **Introdução**

Nesta tarefa, você vai configurar o ambiente para o laboratório.

Se estiver dando continuidade ao laboratório anterior (e concluiu esse laboratório com sucesso), não conclua essa tarefa; em vez disso, continue na próxima tarefa.

1. Abra o Power BI Desktop.

    ![* Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Dica: por padrão, a caixa de diálogo Introdução é aberta na frente do Power BI Desktop. **Entre** e feche o pop-up.*

1. Para abrir o arquivo inicial do Power BI Desktop, na guia de faixa de opções Arquivo, selecione Abrir relatório e Procurar relatórios.

1. **Na janela Abrir**, navegue até a **pasta D:\PL300\Labs\10-row-level-security\Starter** e abra o **arquivo Sales Analysis**.

1. Feche todas as janelas informativas que possam ser abertas.

1. Observe a mensagem de aviso em amarelo abaixo da faixa de opções. *Essa mensagem alerta para o fato de que as consultas não foram aplicadas para carregar como tabelas de modelo. Você aplicará as consultas posteriormente neste laboratório.*
    
    Para ignorar a mensagem de aviso, à direita da mensagem de aviso em amarelo, selecione X.

1. Para criar uma cópia do arquivo, vá para **Arquivo > Salvar como** e salve na **pasta D:\PL300\MySolution** .

1. Caso precise aplicar as alterações, selecione **Aplicar Mais Tarde**.

## Impor a Segurança em Nível de Linha

Nesta tarefa, você vai impor a Segurança em Nível de Linha para garantir que um vendedor só possa ver as vendas feitas nas regiões atribuídas a ele.

1. Alterne para a exibição Dados.

   ![Figura 48](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image20.png)

1. No painel **Campos**, selecione a tabela **Salesperson (Performance)**.


1. Examine os dados, observando que Michael Blythe (EmployeeKey 281) tem um valor UPN igual a: **michael-blythe@adventureworks.com**
    
    Lembre-se de que Michael Blythe foi atribuído a três regiões de vendas: Nordeste dos EUA, EUA Central e Sudeste dos EUA.

1. Na guia de faixa de opções Modelagem, no grupo Segurança, selecione Gerenciar Funções.

    ![Figura 48](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image21.png)

1. Na janela **Gerenciar Funções**, selecione **Criar**.

1. Na caixa Funções, substitua o texto selecionado pelo nome da função, Vendedores, e clique em ENTER.

   ![Figura 48](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image23.png)

1. Para atribuir um filtro à tabela Salesperson (Performance), selecione o ícone de reticências (…) e escolha Adicionar filtro | [UPN].

   ![Figura 48](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image24.png)

1. Na caixa Expressão DAX de Filtro de Tabela, modifique a expressão substituindo Valor por USERPRINCIPALNAME().
    
    *USERPRINCIPALNAME() é uma função DAX (Data Analysis Expressions) que retorna o nome do usuário autenticado. Isso significa que a **tabela Vendedor (Desempenho) será filtrada pelo Nome Principal do Usuário (UPN)** do usuário que está consultando o modelo.*

   ![Figura 11](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image25.png)

1. Para testar a função de segurança, na guia de faixa de opções **Modelagem**, no grupo **Segurança**, selecione **Exibir como**.

   ![Figura 48](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image27.png)

1. Na janela **Exibir como funções**, selecione o item **Outro Usuário** e, na caixa correspondente, insira: **michael-blythe@adventureworks.com**

1. Verifique a **função Vendedores** e, em seguida **, OK.**
    
    Essa configuração resulta no uso da função Vendedores e na representação do usuário com o nome de Mateus Rodrigues.

   ![Figura 48](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image28.png)

1. Observe a faixa amarela acima da página do relatório, descrevendo o contexto de segurança do teste.

   ![Figura 13](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image30.png)

1. No visual de tabela, observe que só o vendedor **Michael Blythe** está listado.

   ![Figura 48](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image31.png)

1. Para interromper o teste, no lado direito da faixa amarela, selecione **Parar de Exibir**.

   ![Figura 48](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image32.png)

1. Para excluir a função, na guia de faixa de opções Modelagem, no grupo Segurança, selecione Gerenciar Funções.

   ![Figura 16](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image33.png)

1. Na janela **Gerenciar Funções**, selecione **Excluir**. Quando precisar confirmar a exclusão, selecione Sim e Excluir.

   ![Figura 17](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image34.png)

### Conclusão

Nesta tarefa, você concluirá o laboratório.

1. Selecione **Salvar** e salve o arquivo do Power BI Desktop para encerrar o laboratório.

Quando o arquivo do Power BI Desktop for publicado no serviço do Power BI, você precisará concluir uma tarefa de pós-publicação para mapear entidades de segurança para a função Vendedores.
