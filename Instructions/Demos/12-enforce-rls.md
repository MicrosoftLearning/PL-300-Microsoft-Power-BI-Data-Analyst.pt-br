---
demo:
  title: Impor a segurança em nível de linha no Power BI
  module: Secure data access in Power BI
---

# Impor a segurança em nível de linha no Power BI

## Adicionar uma tabela de segurança ao modelo

1. No Power BI Desktop, abra a janela do Editor do Power Query.

1. Adicione uma nova consulta com base no arquivo `D:\Demo\Data\**ManagerCategory**.xlsx`.

1. Use a tabela **ManagerCategory** no arquivo.

1. Remova a coluna **Manager**.

1. Divida a coluna **Category** pelo delimitador de ponto-e-vírgula e divida em linhas (opções avançadas).

1. Na coluna **Email**, substitua o valor **<ty-johnston@tailspintoys.com>** pela conta do destinatário (do arquivo MySettings.txt).

1. Saliente que este usuário é capaz de ver três categorias de produtos: **Collective pitch, Trainer e Warbird**.

1. Feche e aplique as consultas.

1. Na exibição Modelo, crie uma relação entre as tabelas **ManagerCategory** e Product relacionadas à coluna **Category**.

1. Defina a direção do filtro cruzado como Único (**ManagerCategory** filtra Product).

1. Oculte a tabela **ManagerCategory**.

## Adicionar uma função

1. Na exibição Report, abra Manage Roles e crie uma função chamada **Manager**.

1. Na função, filtre a coluna Email address da tabela **ManagerCategory** da seguinte maneira:

  ```dax
   [Email] = USERPRINCIPALNAME()
   ```

1. **Salvar**.

## Valide a função

1. Abra Exibir como, e defina as seguintes configurações:

    - Outro Usuário: marque e insira a conta do destinatário.

    - Função de gerente: verificar

1. Saliente que o visual do filtro mostra apenas três categorias de produtos.

1. Pare de exibir o relatório usando as opções de Exibir como.

1. Salve o arquivo do Power BI Desktop.

1. Publique o arquivo do Power BI Desktop no workspace, substituindo o modelo semântico e o relatório no serviço.

1. Feche o Power BI Desktop.

## Configurar a segurança do modelo semântico

1. No serviço do Power BI para o instrutor, no painel de Navegação, abra a página de segurança do modelo semântico da **Análise de Vendas**.

1. Na seção Members, insira a conta do destinatário (representando **Ty Johnston**).

1. Adicione e salve.

## Testar a segurança em nível de linha no aplicativo

1. No serviço do Power BI para o destinatário, atualize o dashboard (deixado aberto na demonstração anterior).

1. No bloco do dashboard **Profit Margin**, verifique se apenas três categorias de produtos podem ser vistas.
