---
demo:
  title: Gerenciar arquivos e modelos semânticos no Power BI
  module: Deploy and manage Power BI service items
---
# Gerenciar arquivos e modelos semânticos no Power BI

## Configurar o gateway (modo pessoal)

1. No serviço do Power BI, recarregue (F5) a página de configurações do modelo semântico.

1. Expanda a seção Conexão de gateway e indique que nenhum gateway está instalado.

1. Use a lista suspensa de download (localizada no canto superior direito) e selecione Gateway de dados.

1. Na nova página da Web, baixe o gateway de modo pessoal.

1. Uma vez baixado, abra o arquivo baixado.

1. Conclua a configuração do gateway usando sua conta organizacional.

1. Após a instalação, retorne e recarregue a página de configurações do modelo semântico.

1. Atribua o gateway pessoal e edite as credenciais das duas fontes de dados.

1. Para ambas as fontes de dados, defina o método de autenticação como **WindowsWithoutImpersonation** e defina o nível de privacidade como **Organizacional**.

1. Opcionalmente, expanda a seção **Atualização Agendada** e mostre como configurar uma agenda recorrente.

## Atualizar o modelo semântico

1. Antes de atualizar o modelo semântico, abra o painel de **Monitoramento de Vendas**.

1. Edite os detalhes do bloco Sales, Profit Margin para exibir a última hora de atualização.

1. Clique com o botão direito do mouse no arquivo `D:\Allfiles\Demo\Resources\UpdateDatabase-LoadAdditionalSales.ps1` e execute com o PowerShell. *Esse script carregará os dados de vendas de dezembro de 2020 no banco de dados.*

1. No serviço do Power BI para o instrutor, no painel de Navegação, atualize o modelo semântico da **Análise de Vendas**.

1. Quando a atualização for concluída, indique como a coluna do bloco do dashboard de **December 2020** aparece e que o tempo de atualização é **AGORA**.
