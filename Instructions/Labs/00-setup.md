---
lab:
  title: Configurar seu próprio ambiente
  module: Set up your own environment
---

# Configurar ambiente de laboratório local

Idealmente, você deve concluir esses laboratórios em um ambiente de laboratório hospedado. Se você quiser completá-los em seu próprio computador, você pode fazê-lo instalando o seguinte software.

- Todos os arquivos de instalação e recursos podem ser [baixados do GitHub](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/AllfilesDownload.zip).
  - Extraia a pasta "AllFiles" para D:/ e renomeie-a como "D:\Allfiles\'".

***Você pode enfrentar diálogos e comportamento inesperados ao usar seu próprio ambiente. Devido à ampla gama de configurações locais possíveis, a equipe do curso não pode oferecer suporte a problemas que você possa encontrar em seu próprio ambiente.***

## Instruções sobre como usar o Windows 11

> &#128221; As instruções abaixo são para um computador com Windows 11. A conexão a partir de um sistema operacional diferente pode não resultar na mesma experiência.

### Power BI Desktop

1. Baixe e instale usando a Microsoft Store. Se você não tiver acesso à Microsoft Store, faça o download da [Web](https://www.microsoft.com/download/details.aspx?id=58494). O Power BI Desktop é o aplicativo principal para esses laboratórios.

    - Use as opções padrão no instalador.

### Conta de Desenvolvedor M365

Para alguns dos exercícios, você precisará fazer logon no Power BI com uma conta organizacional. Você pode usar uma conta própria, mas se não tiver acesso, crie uma [Conta de desenvolvedor M365 gratuita](https://developer.microsoft.com/en-us/microsoft-365/dev-program).

### Mecanismo de Banco de Dados do SQL Server

1. O laboratório se conecta a uma instância localhost do SQL Server. As instruções a seguir ajudarão você a instalar o SQL Server e configurar as opções padrão. Você só precisa instalar o recurso Mecanismo de Banco de Dados.

    - Baixe a [Cópia gratuita para desenvolvedores da mídia de instalação](https://www.microsoft.com/sql-server/sql-server-downloads?SilentAuth=1&f=255&MSPPError=-2147217396&rtc=1)
    - [Instalar o SQL Server por meio do Assistente de Instalação (Instalação)](https://learn.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)

> &#128221; Você pode usar uma instância existente do SQL Server se tiver acesso, em vez de instalar uma versão local. No entanto, você precisará modificar a cadeia de conexão de "localhost" para o nome da instância.

### Microsoft Edge

1. Instale a versão mais recente do [Microsoft Edge](https://microsoft.com/edge) para acessar o serviço do Power BI online.
