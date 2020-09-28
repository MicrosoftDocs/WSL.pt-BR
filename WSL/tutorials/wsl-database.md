---
title: Introdução ao uso do MySQL MongoDB, PostgreSQL, SQLite, Microsoft SQL Server ou Redis para configurar um banco de dados no subsistema do Windows para Linux
description: Saiba como configurar o MySQL MongoDB, PostgreSQL, SQLite, Microsoft SQL Server ou Redis no subsistema do Windows para Linux.
keywords: WSL, Windows, windowssubsystem, MySQL MongoDB, PostgreSQL, SQLite, Microsoft SQL Server, Redis, Windows 10
ms.date: 07/07/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: b7e4f7477741a931c4ee71e07736bac115443ac9
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413297"
---
# <a name="get-started-with-databases-on-windows-subsystem-for-linux"></a>Introdução aos bancos de dados no subsistema do Windows para Linux

Este guia passo a passo ajudará você a começar a conectar seu projeto no WSL a um banco de dados. Introdução ao MySQL, PostgreSQL, MongoDB, Redis, Microsoft SQL Server ou SQLite.

## <a name="prerequisites"></a>Pré-requisitos

- Executar o Windows 10, [atualizado para a versão 2004](ms-settings:windowsupdate), **Build 19041** ou superiores.
- [WSL habilitado e instalado e atualizado para o WSL 2](../install-win10.md).
- [Distribuição do Linux instalada](../install-win10.md#step-6---install-your-linux-distribution-of-choice) (Ubuntu 18, 4 para nossos exemplos).
- Verifique se a distribuição do Ubuntu 18, 4 está [em execução no modo WSL 2](../install-win10.md#set-your-distribution-version-to-wsl-1-or-wsl-2). (WSL pode executar distribuições no modo v1 ou v2.) Você pode verificar isso abrindo o PowerShell e inserindo: `wsl -l -v`

## <a name="differences-between-database-systems"></a>Diferenças entre sistemas de banco de dados

As [opções mais populares](https://insights.stackoverflow.com/survey/2019#technology-_-databases) para um sistema de banco de dados incluem:

- [MySQL](https://www.mysql.com/why-mysql/) (SQL)
- [PostgreSQL](https://www.postgresql.org/about/) (SQL)
- [Microsoft SQL Server](/sql) (SQL)
- [SQLite](https://www.sqlite.org/about.html) (SQL)
- [MongoDB](https://www.mongodb.com/what-is-mongodb) (NoSQL)
- [Redis](https://redis.io/topics/introduction) (NoSQL)

O **MySQL** é um banco de dados RELACIONAl SQL de código-fonte aberto, organizando-os em uma ou mais tabelas nas quais os tipos de dados podem estar relacionados. Ele é verticalmente escalonável, o que significa que uma máquina final fará o trabalho para você. Atualmente, é o mais amplamente usado nos quatro sistemas de banco de dados.

O **PostgreSQL** (às vezes chamado de Postgres) também é um banco de dados RELACIONAl SQL de código-fonte aberto com ênfase em extensibilidade e conformidade com os padrões. Agora ele também pode tratar JSON, mas geralmente é melhor para dados estruturados, dimensionamento vertical e necessidades em conformidade com ACID, como comércio eletrônico e transações financeiras.

O **Microsoft SQL Server** inclui SQL Server no Windows, SQL Server em Linux e SQL no Azure. Esses também são sistemas de gerenciamento de banco de dados relacionais configurados em servidores com a função primária de armazenamento e recuperação de dados, conforme solicitado por aplicativos de software.

O **SQLite** é um banco de dados independente de software livre, baseado em arquivo, "sem servidor", conhecido por sua portabilidade, confiabilidade e bom desempenho mesmo em ambientes de baixa memória.

O **MongoDB** é um banco de dados de documentos do NoSQL de software livre projetado para funcionar com JSON e armazenar informações sem esquema. Ele é horizontalmente escalonável, o que significa que vários computadores menores farão o trabalho para você. É bom para flexibilidade e dados não estruturados, além de armazenar em cache a análise em tempo real.

**Redis** é um armazenamento de estrutura de dados na memória do NoSQL de código aberto. Ele usa pares chave-valor para armazenamento em vez de documentos. O Redis é conhecido por sua flexibilidade, desempenho e suporte de linguagem ampla. É flexível o suficiente para ser usado como um agente de cache ou mensagem e pode usar estruturas de dados como listas, conjuntos e hashes.

O tipo de banco de dados escolhido deve depender do tipo de aplicativo com o qual você usará o banco de dados. Recomendamos que você pesquise as vantagens e as desvantagens de bancos de dados estruturados e não estruturados e faça uma escolha com base em seu caso de uso.

## <a name="install-mysql"></a>Instalar MySQL

Para instalar o MySQL no WSL (Ubuntu 18, 4):

1. Abra o terminal do WSL (ou seja, Ubuntu 18.04).
2. Atualize os pacotes do Ubuntu: `sudo apt update`
3. Depois que os pacotes forem atualizados, instale o MySQL com: `sudo apt install mysql-server`
4. Confirme a instalação e obtenha o número de versão: `mysql --version`

Talvez você também queira executar o script de segurança incluído. Isso altera algumas das opções padrão menos seguras para coisas como logons raiz remotos e usuários de exemplo. Para executar o script de segurança:

1. Iniciar um servidor MySQL: `sudo /etc/init.d/mysql start`
2. Inicie os prompts de script de segurança: `sudo mysql_secure_installation`
3. O primeiro prompt perguntará se você deseja configurar o plug-in validar senha, que pode ser usado para testar a força da senha do MySQL. Em seguida, você definirá uma senha para o usuário raiz do MySQL, decida se deseja ou não remover usuários anônimos, decidir se deseja permitir que o usuário raiz faça logon tanto localmente quanto remotamente, decida se deseja remover o banco de dados de teste e, por fim, decidir se recarregará as tabelas de privilégios imediatamente.

Para abrir o prompt do MySQL, digite: `sudo mysql`

Para ver quais bancos de dados estão disponíveis, no prompt do MySQL, digite: `SHOW DATABASES;`

Para criar um novo banco de dados, digite: `CREATE DATABASE database_name;`

Para excluir um banco de dados, digite: ` DROP DATABASE database_name;`

Para obter mais informações sobre como trabalhar com bancos de dados MySQL, consulte os [documentos do MySQL](https://dev.mysql.com/doc/mysql-getting-started/en/).

Para trabalhar com bancos de dados MySQL no VS Code, experimente a [extensão do MySQL](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-mysql-client2).

## <a name="install-postgresql"></a>Instalar o PostgreSQL

Para instalar o PostgreSQL em WSL (Ubuntu 18, 4):

1. Abra o terminal do WSL (ou seja, Ubuntu 18.04).
2. Atualize os pacotes do Ubuntu: `sudo apt update`
3. Depois que os pacotes forem atualizados, instale o PostgreSQL (e o pacote -contrib que tem alguns utilitários úteis) com: `sudo apt install postgresql postgresql-contrib`
4. Confirme a instalação e obtenha o número de versão: `psql --version`

Há três comandos que você precisará saber quando o PostgreSQL estiver instalado:

- `sudo service postgresql status` para verificar o status do banco de dados.
- `sudo service postgresql start` para iniciar a execução do banco de dados.
- `sudo service postgresql stop` para interromper a execução do banco de dados.

O usuário administrador padrão, `postgres`, precisa de uma senha atribuída para se conectar a um banco de dados. Para definir uma senha:

1. Insira o comando: `sudo passwd postgres`
2. Você deverá inserir sua nova senha.
3. Feche e abra novamente o terminal.

Para executar o PostgreSQL com o Shell do [psql](https://www.postgresql.org/docs/10/app-psql.html) :

1. Inicie o serviço Postgres: `sudo service postgresql start`
2. Conecte-se ao serviço Postgres e abra o shell do psql: `sudo -u postgres psql`

Depois de entrar no shell do psql com êxito, você verá a linha de comando ser alterada para ter a seguinte aparência: `postgres=#`

> [!NOTE]
> Como alternativa, você pode abrir o shell do psql alternando para o usuário do Postgres com `su - postgres` e, em seguida, inserindo o comando `psql`.

Para sair de postgres = # Enter: `\q` ou use a tecla de atalho: CTRL + D

Para ver quais contas de usuário foram criadas na instalação do PostgreSQL, use `psql -c "\du"` no terminal do WSL ou apenas `\du` se o shell do psql estiver aberto. Este comando exibirá colunas: nome de usuário da conta, lista de atributos de funções e membro de grupos de funções. Para voltar à linha de comando, insira `q`.

Para saber mais sobre como trabalhar com bancos de dados PostgreSQL, confira os [documentos PostgreSQL](https://www.postgresql.org/docs/13/tutorial-createdb.html).

Para trabalhar com bancos de dados PostgreSQL no VS Code, experimente a [extensão PostgreSQL](https://marketplace.visualstudio.com/items?itemName=ms-ossdata.vscode-postgresql).

## <a name="install-mongodb"></a>Instalar o MongoDB

Para instalar o MongoDB em WSL (Ubuntu 18, 4):

1. Abra o terminal do WSL (ou seja, Ubuntu 18.04).
2. Atualize os pacotes do Ubuntu: `sudo apt update`
3. Depois que os pacotes forem atualizados, instale o MongoDB com: `sudo apt-get install mongodb`
4. Confirme a instalação e obtenha o número de versão: `mongod --version`

Há três comandos que você precisará saber quando o MongoDB estiver instalado:

- `sudo service mongodb status` para verificar o status do banco de dados.
- `sudo service mongodb start` para iniciar a execução do banco de dados.
- `sudo service mongodb stop` para interromper a execução do banco de dados.

> [!NOTE]
> Você pode ver o comando `sudo systemctl status mongodb` usado em tutoriais ou artigos. Para permanecer leve, o WSL não inclui `systemd` (um sistema de gerenciamento de serviços no Linux). Em vez disso, ele usa o SysVinit para iniciar serviços no computador. Você não deverá notar uma diferença, mas se um tutorial recomendar o uso de `sudo systemctl`, use `sudo /etc/init.d/`. Por exemplo, `sudo systemctl status mongodb` para o WSL será `sudo /etc/inid.d/mongodb status`, ou você também pode usar `sudo service mongodb status`.

Para executar o banco de dados Mongo em um servidor local:

1. Verifique o status do seu banco de dados: `sudo service mongodb status` você deverá ver uma resposta [falha], a menos que você já tenha iniciado seu banco de dados.

2. Inicie seu banco de dados: `sudo service mongodb start` agora você deve ver uma resposta [OK].

3. Verifique se conectando ao servidor de banco de dados e executando um comando de diagnóstico: isso produzirá `mongo --eval 'db.runCommand({ connectionStatus: 1 })'` a versão atual do banco de dados, o endereço do servidor e a porta e a saída do comando status. Um valor igual a `1` para o campo "OK" na resposta indica que o servidor está funcionando.

4. Para interromper a execução do serviço do MongoDB, insira: `sudo service mongodb stop`

> [!NOTE]
> O MongoDB tem vários parâmetros padrão, incluindo o armazenamento de dados em /data/db e a execução na porta 27017. Além disso, `mongod` é o daemon (processo de host para o banco de dados) e `mongo` é o shell de linha de comando que se conecta a uma instância específica do `mongod`.

VS Code dá suporte ao trabalho com bancos de dados do MongoDB por meio da [extensão CosmosDB do Azure](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb), você pode criar, gerenciar e consultar bancos de dados do MongoDB de dentro vs Code. Para saber mais, visite o VS Code docs: [trabalhando com o MongoDB](https://code.visualstudio.com/docs/azure/mongodb).

Saiba mais nos documentos do MongoDB:

- [Introdução ao uso do MongoDB](https://docs.mongodb.com/manual/introduction/)
- [Criar usuários](https://docs.mongodb.com/manual/tutorial/create-users/)
- [Conectar-se a uma instância do MongoDB em um host remoto](https://docs.mongodb.com/manual/mongo/#mongodb-instance-on-a-remote-host)
- [CRUD: criar, ler, atualizar, excluir](https://docs.mongodb.com/manual/crud/)
- [Documentos de referência](https://docs.mongodb.com/manual/reference/)

## <a name="install-microsoft-sql-server"></a>Instalar o Microsoft SQL Server

Para instalar o SQL Server no WSL (Ubuntu 18, 4), siga este guia de início rápido: [instalar SQL Server e criar um banco de dados no Ubuntu](/sql/linux/quickstart-install-connect-ubuntu).

Para trabalhar com bancos de dados Microsoft SQL Server no VS Code, experimente a [extensão MSSQL](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql).

## <a name="install-sqlite"></a>Instalar o SQLite

Para instalar o SQLite em WSL (Ubuntu 18, 4):

1. Abra o terminal do WSL (ou seja, Ubuntu 18.04).
2. Atualize os pacotes do Ubuntu: `sudo apt update`
3. Depois que os pacotes forem atualizados, instale o SQLite3 com: `sudo apt install sqlite3`
4. Confirme a instalação e obtenha o número de versão: `sqlite3 --version`

Para criar um banco de dados de teste, chamado "example. DB", digite: `sqlite3 example.db`

Para ver uma lista de seus bancos de dados do SQLite, digite: `.databases`

Para ver o status do seu banco de dados, digite: `.dbinfo ?DB?`

Para sair do prompt do SQLite, digite: `.exit`

Para obter mais informações sobre como trabalhar com um banco de dados SQLite, consulte os [documentos do SQLite](https://www.sqlite.org/quickstart.html).

Para trabalhar com bancos de dados SQLite no VS Code, experimente a [extensão SQLite](https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools).

## <a name="install-redis"></a>Instalar o Redis

Para instalar o Redis no WSL (Ubuntu 18, 4):

1. Abra o terminal do WSL (ou seja, Ubuntu 18.04).
2. Atualize os pacotes do Ubuntu: `sudo apt update`
3. Depois que os pacotes forem atualizados, instale o Redis com: `sudo apt install redis-server`
4. Confirme a instalação e obtenha o número de versão: `redis-server --version`

Para iniciar a execução do servidor Redis: `sudo service redis-server start`

Verifique se Redis está funcionando (Redis-CLI é o utilitário de interface de linha de comando para se comunicar com Redis): `redis-cli ping` isso deve retornar uma resposta de "pongue".

Para interromper a execução do servidor Redis: `sudo service redis-server stop`

Para obter mais informações sobre como trabalhar com um banco de dados Redis, consulte o [documentos do Redis](https://redis.io/topics/quickstart).

Para trabalhar com bancos de dados do Redis no VS Code, tente a [extensão Redis](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-redis-client).

## <a name="see-services-running-and-set-up-profile-aliases"></a>Consulte serviços em execução e configurar aliases de perfil

Para ver os serviços que você está executando no momento em sua distribuição do WSL, digite: `service --status-all`

Digitar `sudo service mongodb start` ou `sudo service postgres start` e `sudo -u postgrest psql` pode ser entediante.  No entanto, você pode considerar a configuração de aliases no arquivo `.profile` no WSL para tornar esses comandos mais rápidos e fáceis de serem lembrados.

Para configurar seu próprio alias personalizado ou atalho para execução destes comandos:

1. Abra o terminal do WSL e insira `cd ~` para ter certeza de que você está no diretório raiz.
2. Abra o arquivo `.profile`, que controla as configurações do terminal, com o editor de texto do terminal, o Nano: `sudo nano .profile`
3. Na parte inferior do arquivo (não altere as configurações de `# set PATH`), adicione o seguinte:

    ```bash
    # My Aliases
    alias start-pg='sudo service postgresql start'
    alias run-pg='sudo -u postgres psql'
    ```

    Isso permitirá que você insira `start-pg` para iniciar a execução do serviço PostgreSQL e `run-pg` para abrir o shell do psql. Você pode alterar `start-pg` e `run-pg` para os nomes que desejar; apenas tenha cuidado para não substituir um comando que o Postgres já usa.

4. Depois de adicionar seus novos aliases, saia do editor de texto Nano usando **Ctrl+X** – selecione `Y` (Sim) quando precisar salvar o conteúdo e Enter (deixando o nome de arquivo como `.profile`).
5. Feche e abra novamente o terminal do WSL e, em seguida, experimente os novos comandos de alias.

## <a name="additional-resources"></a>Recursos adicionais

- [Configurando seu ambiente de desenvolvimento no Windows 10](/windows/dev-environment/)