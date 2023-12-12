---
demo:
  title: Gerenciar arquivos e conjuntos de dados no Power BI
  module: Deploy and manage Power BI service items
---
# Gerenciar arquivos e conjuntos de dados no Power BI

## Preparar-se para a atualização de dados do gateway

> **Observe** que as etapas a seguir não são necessárias ao usar o gateway de dados no modo pessoal. Você pode prosseguir diretamente para o próximo objetivo (configurar o gateway).

1. No Power BI Desktop, abra a janela do Editor do Power Query e selecione a consulta **ProductCost**.

1. Edite a etapa Source e modifique o caminho do arquivo para usar o compartilhamento de arquivos, da seguinte maneira:

    `\\DATA-AI\Data\ProductCost.xlsx`

1. Feche e aplique a janela do Editor do Power Query.

1. Salve o arquivo do Power BI Desktop.

1. Publique o arquivo do Power BI Desktop no workspace, substituindo o conjunto de dados e o relatório no serviço.

## Configurar o gateway (modo pessoal)

1. No serviço Power BI para o instrutor, recarregue (F5) a página de configurações do conjunto de dados.

1. Expanda a seção Conexão de gateway e indique que nenhum gateway está instalado.

1. Use a lista suspensa de download (localizada no canto superior direito) e selecione Gateway de dados.

1. Na nova página da Web, baixe o gateway de modo pessoal.

1. Uma vez baixado, abra o arquivo baixado.

1. Conclua a configuração do gateway usando as credenciais da conta do instrutor.

1. Após a instalação, retorne e recarregue a página de configurações do conjunto de dados.

1. Atribua o gateway pessoal e edite as credenciais das duas fontes de dados.

1. Para ambas as fontes de dados, defina o método de autenticação como **WindowsWithoutImpersonation** e defina o nível de privacidade como **Organizacional**.

1. Opcionalmente, expanda a seção **Atualização Agendada** e mostre como configurar uma agenda recorrente.

## Atualizar o conjunto de dados

1. Antes de atualizar o conjunto de dados, abra o dashboard **Sales Monitoring**.

1. Edite os detalhes do bloco Sales, Profit Margin para exibir a última hora de atualização.

1. Clique com o botão direito do mouse no arquivo `D:\PL300\Demo\Resources\UpdateDatabase-LoadAdditionalSales.ps1` e execute com o PowerShell. *Esse script carregará os dados de vendas de dezembro de 2020 no banco de dados.*

1. No serviço do Power BI para o instrutor, no painel de Navegação, atualize o conjunto de dados da **Sales Analysis**.

1. Quando a atualização for concluída, indique como a coluna do bloco do dashboard de **December 2020** aparece e que o tempo de atualização é **AGORA**.
