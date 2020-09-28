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
# <a name="get-started-with-databases-on-windows-subsystem-for-linux"></a><span data-ttu-id="be8ba-104">Introdução aos bancos de dados no subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="be8ba-104">Get started with databases on Windows Subsystem for Linux</span></span>

<span data-ttu-id="be8ba-105">Este guia passo a passo ajudará você a começar a conectar seu projeto no WSL a um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-105">This step-by-step guide will help you get started connecting your project in WSL to a database.</span></span> <span data-ttu-id="be8ba-106">Introdução ao MySQL, PostgreSQL, MongoDB, Redis, Microsoft SQL Server ou SQLite.</span><span class="sxs-lookup"><span data-stu-id="be8ba-106">Get started with MySQL, PostgreSQL, MongoDB, Redis, Microsoft SQL Server, or SQLite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be8ba-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="be8ba-107">Prerequisites</span></span>

- <span data-ttu-id="be8ba-108">Executar o Windows 10, [atualizado para a versão 2004](ms-settings:windowsupdate), **Build 19041** ou superiores.</span><span class="sxs-lookup"><span data-stu-id="be8ba-108">Running Windows 10, [updated to version 2004](ms-settings:windowsupdate), **Build 19041** or higher.</span></span>
- <span data-ttu-id="be8ba-109">[WSL habilitado e instalado e atualizado para o WSL 2](../install-win10.md).</span><span class="sxs-lookup"><span data-stu-id="be8ba-109">[WSL enabled and installed, and updated to WSL 2](../install-win10.md).</span></span>
- <span data-ttu-id="be8ba-110">[Distribuição do Linux instalada](../install-win10.md#step-6---install-your-linux-distribution-of-choice) (Ubuntu 18, 4 para nossos exemplos).</span><span class="sxs-lookup"><span data-stu-id="be8ba-110">[Linux distribution installed](../install-win10.md#step-6---install-your-linux-distribution-of-choice) (Ubuntu 18.04 for our examples).</span></span>
- <span data-ttu-id="be8ba-111">Verifique se a distribuição do Ubuntu 18, 4 está [em execução no modo WSL 2](../install-win10.md#set-your-distribution-version-to-wsl-1-or-wsl-2).</span><span class="sxs-lookup"><span data-stu-id="be8ba-111">Ensure your Ubuntu 18.04 distribution is [running in WSL 2 mode](../install-win10.md#set-your-distribution-version-to-wsl-1-or-wsl-2).</span></span> <span data-ttu-id="be8ba-112">(WSL pode executar distribuições no modo v1 ou v2.) Você pode verificar isso abrindo o PowerShell e inserindo: `wsl -l -v`</span><span class="sxs-lookup"><span data-stu-id="be8ba-112">(WSL can run distributions in both v1 or v2 mode.) You can check this by opening PowerShell and entering: `wsl -l -v`</span></span>

## <a name="differences-between-database-systems"></a><span data-ttu-id="be8ba-113">Diferenças entre sistemas de banco de dados</span><span class="sxs-lookup"><span data-stu-id="be8ba-113">Differences between database systems</span></span>

<span data-ttu-id="be8ba-114">As [opções mais populares](https://insights.stackoverflow.com/survey/2019#technology-_-databases) para um sistema de banco de dados incluem:</span><span class="sxs-lookup"><span data-stu-id="be8ba-114">The most [popular choices](https://insights.stackoverflow.com/survey/2019#technology-_-databases) for a database system include:</span></span>

- <span data-ttu-id="be8ba-115">[MySQL](https://www.mysql.com/why-mysql/) (SQL)</span><span class="sxs-lookup"><span data-stu-id="be8ba-115">[MySQL](https://www.mysql.com/why-mysql/) (SQL)</span></span>
- <span data-ttu-id="be8ba-116">[PostgreSQL](https://www.postgresql.org/about/) (SQL)</span><span class="sxs-lookup"><span data-stu-id="be8ba-116">[PostgreSQL](https://www.postgresql.org/about/) (SQL)</span></span>
- <span data-ttu-id="be8ba-117">[Microsoft SQL Server](/sql) (SQL)</span><span class="sxs-lookup"><span data-stu-id="be8ba-117">[Microsoft SQL Server](/sql) (SQL)</span></span>
- <span data-ttu-id="be8ba-118">[SQLite](https://www.sqlite.org/about.html) (SQL)</span><span class="sxs-lookup"><span data-stu-id="be8ba-118">[SQLite](https://www.sqlite.org/about.html) (SQL)</span></span>
- <span data-ttu-id="be8ba-119">[MongoDB](https://www.mongodb.com/what-is-mongodb) (NoSQL)</span><span class="sxs-lookup"><span data-stu-id="be8ba-119">[MongoDB](https://www.mongodb.com/what-is-mongodb) (NoSQL)</span></span>
- <span data-ttu-id="be8ba-120">[Redis](https://redis.io/topics/introduction) (NoSQL)</span><span class="sxs-lookup"><span data-stu-id="be8ba-120">[Redis](https://redis.io/topics/introduction) (NoSQL)</span></span>

<span data-ttu-id="be8ba-121">O **MySQL** é um banco de dados RELACIONAl SQL de código-fonte aberto, organizando-os em uma ou mais tabelas nas quais os tipos de dados podem estar relacionados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-121">**MySQL** is an open-source SQL relational database, organizing data into one or more tables in which data types may be related to each other.</span></span> <span data-ttu-id="be8ba-122">Ele é verticalmente escalonável, o que significa que uma máquina final fará o trabalho para você.</span><span class="sxs-lookup"><span data-stu-id="be8ba-122">It is vertically scalable, which means one ultimate machine will do the work for you.</span></span> <span data-ttu-id="be8ba-123">Atualmente, é o mais amplamente usado nos quatro sistemas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-123">It is currently the most widely used of the four database systems.</span></span>

<span data-ttu-id="be8ba-124">O **PostgreSQL** (às vezes chamado de Postgres) também é um banco de dados RELACIONAl SQL de código-fonte aberto com ênfase em extensibilidade e conformidade com os padrões.</span><span class="sxs-lookup"><span data-stu-id="be8ba-124">**PostgreSQL** (sometimes referred to as Postgres) is also an open-source SQL relational database with an emphasis on extensibility and standards compliance.</span></span> <span data-ttu-id="be8ba-125">Agora ele também pode tratar JSON, mas geralmente é melhor para dados estruturados, dimensionamento vertical e necessidades em conformidade com ACID, como comércio eletrônico e transações financeiras.</span><span class="sxs-lookup"><span data-stu-id="be8ba-125">It can handle JSON now too, but it is generally better for structured data, vertical scaling, and ACID-compliant needs like eCommerce and financial transactions.</span></span>

<span data-ttu-id="be8ba-126">O **Microsoft SQL Server** inclui SQL Server no Windows, SQL Server em Linux e SQL no Azure.</span><span class="sxs-lookup"><span data-stu-id="be8ba-126">**Microsoft SQL Server** includes SQL Server on Windows, SQL Server on Linux, and SQL on Azure.</span></span> <span data-ttu-id="be8ba-127">Esses também são sistemas de gerenciamento de banco de dados relacionais configurados em servidores com a função primária de armazenamento e recuperação de dados, conforme solicitado por aplicativos de software.</span><span class="sxs-lookup"><span data-stu-id="be8ba-127">These are also relational database management systems set up on servers with primary function of storing and retrieving data as requested by software applications.</span></span>

<span data-ttu-id="be8ba-128">O **SQLite** é um banco de dados independente de software livre, baseado em arquivo, "sem servidor", conhecido por sua portabilidade, confiabilidade e bom desempenho mesmo em ambientes de baixa memória.</span><span class="sxs-lookup"><span data-stu-id="be8ba-128">**SQLite** is an open-source self-contained, file-based, “serverless” database, known for its portability, reliability, and good performance even in low-memory environments.</span></span>

<span data-ttu-id="be8ba-129">O **MongoDB** é um banco de dados de documentos do NoSQL de software livre projetado para funcionar com JSON e armazenar informações sem esquema.</span><span class="sxs-lookup"><span data-stu-id="be8ba-129">**MongoDB** is an open-source NoSQL document database designed to work with JSON and store schema-free data.</span></span> <span data-ttu-id="be8ba-130">Ele é horizontalmente escalonável, o que significa que vários computadores menores farão o trabalho para você.</span><span class="sxs-lookup"><span data-stu-id="be8ba-130">It is horizontally scalable, which means multiple smaller machines will do the work for you.</span></span> <span data-ttu-id="be8ba-131">É bom para flexibilidade e dados não estruturados, além de armazenar em cache a análise em tempo real.</span><span class="sxs-lookup"><span data-stu-id="be8ba-131">It's good for flexibility and unstructured data, and caching real-time analytics.</span></span>

<span data-ttu-id="be8ba-132">**Redis** é um armazenamento de estrutura de dados na memória do NoSQL de código aberto.</span><span class="sxs-lookup"><span data-stu-id="be8ba-132">**Redis** is is an open-source NoSQL in-memory data structure store.</span></span> <span data-ttu-id="be8ba-133">Ele usa pares chave-valor para armazenamento em vez de documentos.</span><span class="sxs-lookup"><span data-stu-id="be8ba-133">It uses key-value pairs for storage instead of documents.</span></span> <span data-ttu-id="be8ba-134">O Redis é conhecido por sua flexibilidade, desempenho e suporte de linguagem ampla.</span><span class="sxs-lookup"><span data-stu-id="be8ba-134">Redis is known for its flexibility, performance, and wide language support.</span></span> <span data-ttu-id="be8ba-135">É flexível o suficiente para ser usado como um agente de cache ou mensagem e pode usar estruturas de dados como listas, conjuntos e hashes.</span><span class="sxs-lookup"><span data-stu-id="be8ba-135">It’s flexible enough to be used as a cache or message broker and can use data structures like lists, sets, and hashes.</span></span>

<span data-ttu-id="be8ba-136">O tipo de banco de dados escolhido deve depender do tipo de aplicativo com o qual você usará o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-136">The sort of database you choose should depend on the type of application you will be using the database with.</span></span> <span data-ttu-id="be8ba-137">Recomendamos que você pesquise as vantagens e as desvantagens de bancos de dados estruturados e não estruturados e faça uma escolha com base em seu caso de uso.</span><span class="sxs-lookup"><span data-stu-id="be8ba-137">We recommend that you look up the advantages and disadvantages of structured and unstructured databases and choose based on your use case.</span></span>

## <a name="install-mysql"></a><span data-ttu-id="be8ba-138">Instalar MySQL</span><span class="sxs-lookup"><span data-stu-id="be8ba-138">Install MySQL</span></span>

<span data-ttu-id="be8ba-139">Para instalar o MySQL no WSL (Ubuntu 18, 4):</span><span class="sxs-lookup"><span data-stu-id="be8ba-139">To install MySQL on WSL (Ubuntu 18.04):</span></span>

1. <span data-ttu-id="be8ba-140">Abra o terminal do WSL (ou seja, Ubuntu 18.04).</span><span class="sxs-lookup"><span data-stu-id="be8ba-140">Open your WSL terminal (ie. Ubuntu 18.04).</span></span>
2. <span data-ttu-id="be8ba-141">Atualize os pacotes do Ubuntu: `sudo apt update`</span><span class="sxs-lookup"><span data-stu-id="be8ba-141">Update your Ubuntu packages: `sudo apt update`</span></span>
3. <span data-ttu-id="be8ba-142">Depois que os pacotes forem atualizados, instale o MySQL com: `sudo apt install mysql-server`</span><span class="sxs-lookup"><span data-stu-id="be8ba-142">Once the packages have updated, install MySQL with: `sudo apt install mysql-server`</span></span>
4. <span data-ttu-id="be8ba-143">Confirme a instalação e obtenha o número de versão: `mysql --version`</span><span class="sxs-lookup"><span data-stu-id="be8ba-143">Confirm installation and get the version number: `mysql --version`</span></span>

<span data-ttu-id="be8ba-144">Talvez você também queira executar o script de segurança incluído.</span><span class="sxs-lookup"><span data-stu-id="be8ba-144">You may also want to run the included security script.</span></span> <span data-ttu-id="be8ba-145">Isso altera algumas das opções padrão menos seguras para coisas como logons raiz remotos e usuários de exemplo.</span><span class="sxs-lookup"><span data-stu-id="be8ba-145">This changes some of the less secure default options for things like remote root logins and sample users.</span></span> <span data-ttu-id="be8ba-146">Para executar o script de segurança:</span><span class="sxs-lookup"><span data-stu-id="be8ba-146">To run the security script:</span></span>

1. <span data-ttu-id="be8ba-147">Iniciar um servidor MySQL: `sudo /etc/init.d/mysql start`</span><span class="sxs-lookup"><span data-stu-id="be8ba-147">Start a MySQL server: `sudo /etc/init.d/mysql start`</span></span>
2. <span data-ttu-id="be8ba-148">Inicie os prompts de script de segurança: `sudo mysql_secure_installation`</span><span class="sxs-lookup"><span data-stu-id="be8ba-148">Start the security script prompts: `sudo mysql_secure_installation`</span></span>
3. <span data-ttu-id="be8ba-149">O primeiro prompt perguntará se você deseja configurar o plug-in validar senha, que pode ser usado para testar a força da senha do MySQL.</span><span class="sxs-lookup"><span data-stu-id="be8ba-149">The first prompt will ask whether you’d like to set up the Validate Password Plugin, which can be used to test the strength of your MySQL password.</span></span> <span data-ttu-id="be8ba-150">Em seguida, você definirá uma senha para o usuário raiz do MySQL, decida se deseja ou não remover usuários anônimos, decidir se deseja permitir que o usuário raiz faça logon tanto localmente quanto remotamente, decida se deseja remover o banco de dados de teste e, por fim, decidir se recarregará as tabelas de privilégios imediatamente.</span><span class="sxs-lookup"><span data-stu-id="be8ba-150">You will then set a password for the MySQL root user, decide whether or not to remove anonymous users, decide whether to allow the root user to login both locally and remotely, decide whether to remove the test database, and, lastly, decide whether to reload the privilege tables immediately.</span></span>

<span data-ttu-id="be8ba-151">Para abrir o prompt do MySQL, digite: `sudo mysql`</span><span class="sxs-lookup"><span data-stu-id="be8ba-151">To open the MySQL prompt, enter: `sudo mysql`</span></span>

<span data-ttu-id="be8ba-152">Para ver quais bancos de dados estão disponíveis, no prompt do MySQL, digite: `SHOW DATABASES;`</span><span class="sxs-lookup"><span data-stu-id="be8ba-152">To see what databases you have available, in the MySQL prompt, enter: `SHOW DATABASES;`</span></span>

<span data-ttu-id="be8ba-153">Para criar um novo banco de dados, digite: `CREATE DATABASE database_name;`</span><span class="sxs-lookup"><span data-stu-id="be8ba-153">To create a new database, enter: `CREATE DATABASE database_name;`</span></span>

<span data-ttu-id="be8ba-154">Para excluir um banco de dados, digite: ` DROP DATABASE database_name;`</span><span class="sxs-lookup"><span data-stu-id="be8ba-154">To delete a database, enter: ` DROP DATABASE database_name;`</span></span>

<span data-ttu-id="be8ba-155">Para obter mais informações sobre como trabalhar com bancos de dados MySQL, consulte os [documentos do MySQL](https://dev.mysql.com/doc/mysql-getting-started/en/).</span><span class="sxs-lookup"><span data-stu-id="be8ba-155">For more about working with MySQL databases, see the [MySQL docs](https://dev.mysql.com/doc/mysql-getting-started/en/).</span></span>

<span data-ttu-id="be8ba-156">Para trabalhar com bancos de dados MySQL no VS Code, experimente a [extensão do MySQL](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-mysql-client2).</span><span class="sxs-lookup"><span data-stu-id="be8ba-156">To work with with MySQL databases in VS Code, try the [MySQL extension](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-mysql-client2).</span></span>

## <a name="install-postgresql"></a><span data-ttu-id="be8ba-157">Instalar o PostgreSQL</span><span class="sxs-lookup"><span data-stu-id="be8ba-157">Install PostgreSQL</span></span>

<span data-ttu-id="be8ba-158">Para instalar o PostgreSQL em WSL (Ubuntu 18, 4):</span><span class="sxs-lookup"><span data-stu-id="be8ba-158">To install PostgreSQL on WSL (Ubuntu 18.04):</span></span>

1. <span data-ttu-id="be8ba-159">Abra o terminal do WSL (ou seja, Ubuntu 18.04).</span><span class="sxs-lookup"><span data-stu-id="be8ba-159">Open your WSL terminal (ie. Ubuntu 18.04).</span></span>
2. <span data-ttu-id="be8ba-160">Atualize os pacotes do Ubuntu: `sudo apt update`</span><span class="sxs-lookup"><span data-stu-id="be8ba-160">Update your Ubuntu packages: `sudo apt update`</span></span>
3. <span data-ttu-id="be8ba-161">Depois que os pacotes forem atualizados, instale o PostgreSQL (e o pacote -contrib que tem alguns utilitários úteis) com: `sudo apt install postgresql postgresql-contrib`</span><span class="sxs-lookup"><span data-stu-id="be8ba-161">Once the packages have updated, install PostgreSQL (and the -contrib package which has some helpful utilities) with: `sudo apt install postgresql postgresql-contrib`</span></span>
4. <span data-ttu-id="be8ba-162">Confirme a instalação e obtenha o número de versão: `psql --version`</span><span class="sxs-lookup"><span data-stu-id="be8ba-162">Confirm installation and get the version number: `psql --version`</span></span>

<span data-ttu-id="be8ba-163">Há três comandos que você precisará saber quando o PostgreSQL estiver instalado:</span><span class="sxs-lookup"><span data-stu-id="be8ba-163">There are 3 commands you need to know once PostgreSQL is installed:</span></span>

- <span data-ttu-id="be8ba-164">`sudo service postgresql status` para verificar o status do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-164">`sudo service postgresql status` for checking the status of your database.</span></span>
- <span data-ttu-id="be8ba-165">`sudo service postgresql start` para iniciar a execução do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-165">`sudo service postgresql start`  to start running your database.</span></span>
- <span data-ttu-id="be8ba-166">`sudo service postgresql stop` para interromper a execução do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-166">`sudo service postgresql stop` to stop running your database.</span></span>

<span data-ttu-id="be8ba-167">O usuário administrador padrão, `postgres`, precisa de uma senha atribuída para se conectar a um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-167">The default admin user, `postgres`, needs a password assigned in order to connect to a database.</span></span> <span data-ttu-id="be8ba-168">Para definir uma senha:</span><span class="sxs-lookup"><span data-stu-id="be8ba-168">To set a password:</span></span>

1. <span data-ttu-id="be8ba-169">Insira o comando: `sudo passwd postgres`</span><span class="sxs-lookup"><span data-stu-id="be8ba-169">Enter the command: `sudo passwd postgres`</span></span>
2. <span data-ttu-id="be8ba-170">Você deverá inserir sua nova senha.</span><span class="sxs-lookup"><span data-stu-id="be8ba-170">You will get a prompt to enter your new password.</span></span>
3. <span data-ttu-id="be8ba-171">Feche e abra novamente o terminal.</span><span class="sxs-lookup"><span data-stu-id="be8ba-171">Close and reopen your terminal.</span></span>

<span data-ttu-id="be8ba-172">Para executar o PostgreSQL com o Shell do [psql](https://www.postgresql.org/docs/10/app-psql.html) :</span><span class="sxs-lookup"><span data-stu-id="be8ba-172">To run PostgreSQL with [psql](https://www.postgresql.org/docs/10/app-psql.html) shell:</span></span>

1. <span data-ttu-id="be8ba-173">Inicie o serviço Postgres: `sudo service postgresql start`</span><span class="sxs-lookup"><span data-stu-id="be8ba-173">Start your postgres service: `sudo service postgresql start`</span></span>
2. <span data-ttu-id="be8ba-174">Conecte-se ao serviço Postgres e abra o shell do psql: `sudo -u postgres psql`</span><span class="sxs-lookup"><span data-stu-id="be8ba-174">Connect to the postgres service and open the psql shell: `sudo -u postgres psql`</span></span>

<span data-ttu-id="be8ba-175">Depois de entrar no shell do psql com êxito, você verá a linha de comando ser alterada para ter a seguinte aparência: `postgres=#`</span><span class="sxs-lookup"><span data-stu-id="be8ba-175">Once you have successfully entered the psql shell, you will see your command line change to look like this: `postgres=#`</span></span>

> [!NOTE]
> <span data-ttu-id="be8ba-176">Como alternativa, você pode abrir o shell do psql alternando para o usuário do Postgres com `su - postgres` e, em seguida, inserindo o comando `psql`.</span><span class="sxs-lookup"><span data-stu-id="be8ba-176">Alternatively, you can open the psql shell by switching to the postgres user with: `su - postgres` and then entering the command: `psql`.</span></span>

<span data-ttu-id="be8ba-177">Para sair de postgres = # Enter: `\q` ou use a tecla de atalho: CTRL + D</span><span class="sxs-lookup"><span data-stu-id="be8ba-177">To exit postgres=# enter: `\q` or use the shortcut key: Ctrl+D</span></span>

<span data-ttu-id="be8ba-178">Para ver quais contas de usuário foram criadas na instalação do PostgreSQL, use `psql -c "\du"` no terminal do WSL ou apenas `\du` se o shell do psql estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="be8ba-178">To see what user accounts have been created on your PostgreSQL installation, use from your WSL terminal: `psql -c "\du"` ...or just `\du` if you have the psql shell open.</span></span> <span data-ttu-id="be8ba-179">Este comando exibirá colunas: nome de usuário da conta, lista de atributos de funções e membro de grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="be8ba-179">This command will display columns: Account User Name, List of Roles Attributes, and Member of role group(s).</span></span> <span data-ttu-id="be8ba-180">Para voltar à linha de comando, insira `q`.</span><span class="sxs-lookup"><span data-stu-id="be8ba-180">To exit back to the command line, enter: `q`.</span></span>

<span data-ttu-id="be8ba-181">Para saber mais sobre como trabalhar com bancos de dados PostgreSQL, confira os [documentos PostgreSQL](https://www.postgresql.org/docs/13/tutorial-createdb.html).</span><span class="sxs-lookup"><span data-stu-id="be8ba-181">For more about working with PostgreSQL databases, see the [PostgreSQL docs](https://www.postgresql.org/docs/13/tutorial-createdb.html).</span></span>

<span data-ttu-id="be8ba-182">Para trabalhar com bancos de dados PostgreSQL no VS Code, experimente a [extensão PostgreSQL](https://marketplace.visualstudio.com/items?itemName=ms-ossdata.vscode-postgresql).</span><span class="sxs-lookup"><span data-stu-id="be8ba-182">To work with with PostgreSQL databases in VS Code, try the [PostgreSQL extension](https://marketplace.visualstudio.com/items?itemName=ms-ossdata.vscode-postgresql).</span></span>

## <a name="install-mongodb"></a><span data-ttu-id="be8ba-183">Instalar o MongoDB</span><span class="sxs-lookup"><span data-stu-id="be8ba-183">Install MongoDB</span></span>

<span data-ttu-id="be8ba-184">Para instalar o MongoDB em WSL (Ubuntu 18, 4):</span><span class="sxs-lookup"><span data-stu-id="be8ba-184">To install MongoDB on WSL (Ubuntu 18.04):</span></span>

1. <span data-ttu-id="be8ba-185">Abra o terminal do WSL (ou seja, Ubuntu 18.04).</span><span class="sxs-lookup"><span data-stu-id="be8ba-185">Open your WSL terminal (ie. Ubuntu 18.04).</span></span>
2. <span data-ttu-id="be8ba-186">Atualize os pacotes do Ubuntu: `sudo apt update`</span><span class="sxs-lookup"><span data-stu-id="be8ba-186">Update your Ubuntu packages: `sudo apt update`</span></span>
3. <span data-ttu-id="be8ba-187">Depois que os pacotes forem atualizados, instale o MongoDB com: `sudo apt-get install mongodb`</span><span class="sxs-lookup"><span data-stu-id="be8ba-187">Once the packages have updated, install MongoDB with: `sudo apt-get install mongodb`</span></span>
4. <span data-ttu-id="be8ba-188">Confirme a instalação e obtenha o número de versão: `mongod --version`</span><span class="sxs-lookup"><span data-stu-id="be8ba-188">Confirm installation and get the version number: `mongod --version`</span></span>

<span data-ttu-id="be8ba-189">Há três comandos que você precisará saber quando o MongoDB estiver instalado:</span><span class="sxs-lookup"><span data-stu-id="be8ba-189">There are 3 commands you need to know once MongoDB is installed:</span></span>

- <span data-ttu-id="be8ba-190">`sudo service mongodb status` para verificar o status do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-190">`sudo service mongodb status` for checking the status of your database.</span></span>
- <span data-ttu-id="be8ba-191">`sudo service mongodb start` para iniciar a execução do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-191">`sudo service mongodb start`  to start running your database.</span></span>
- <span data-ttu-id="be8ba-192">`sudo service mongodb stop` para interromper a execução do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-192">`sudo service mongodb stop` to stop running your database.</span></span>

> [!NOTE]
> <span data-ttu-id="be8ba-193">Você pode ver o comando `sudo systemctl status mongodb` usado em tutoriais ou artigos.</span><span class="sxs-lookup"><span data-stu-id="be8ba-193">You might see the command `sudo systemctl status mongodb` used in tutorials or articles.</span></span> <span data-ttu-id="be8ba-194">Para permanecer leve, o WSL não inclui `systemd` (um sistema de gerenciamento de serviços no Linux).</span><span class="sxs-lookup"><span data-stu-id="be8ba-194">In order to remain lightweight, WSL does not include `systemd` (a service management system in Linux).</span></span> <span data-ttu-id="be8ba-195">Em vez disso, ele usa o SysVinit para iniciar serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="be8ba-195">Instead, it uses SysVinit to start services on your machine.</span></span> <span data-ttu-id="be8ba-196">Você não deverá notar uma diferença, mas se um tutorial recomendar o uso de `sudo systemctl`, use `sudo /etc/init.d/`.</span><span class="sxs-lookup"><span data-stu-id="be8ba-196">You shouldn't notice a difference, but if a tutorial recommends using `sudo systemctl`, instead use: `sudo /etc/init.d/`.</span></span> <span data-ttu-id="be8ba-197">Por exemplo, `sudo systemctl status mongodb` para o WSL será `sudo /etc/inid.d/mongodb status`, ou você também pode usar `sudo service mongodb status`.</span><span class="sxs-lookup"><span data-stu-id="be8ba-197">For example, `sudo systemctl status mongodb`, for WSL would be `sudo /etc/inid.d/mongodb status` ...or you can also use `sudo service mongodb status`.</span></span>

<span data-ttu-id="be8ba-198">Para executar o banco de dados Mongo em um servidor local:</span><span class="sxs-lookup"><span data-stu-id="be8ba-198">To run your Mongo database in a local server:</span></span>

1. <span data-ttu-id="be8ba-199">Verifique o status do seu banco de dados: `sudo service mongodb status` você deverá ver uma resposta [falha], a menos que você já tenha iniciado seu banco de dados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-199">Check the status of your database: `sudo service mongodb status` You should see a [Fail] response, unless you've already started your database.</span></span>

2. <span data-ttu-id="be8ba-200">Inicie seu banco de dados: `sudo service mongodb start` agora você deve ver uma resposta [OK].</span><span class="sxs-lookup"><span data-stu-id="be8ba-200">Start your database: `sudo service mongodb start` You should now see an [OK] response.</span></span>

3. <span data-ttu-id="be8ba-201">Verifique se conectando ao servidor de banco de dados e executando um comando de diagnóstico: isso produzirá `mongo --eval 'db.runCommand({ connectionStatus: 1 })'` a versão atual do banco de dados, o endereço do servidor e a porta e a saída do comando status.</span><span class="sxs-lookup"><span data-stu-id="be8ba-201">Verify by connecting to the database server and running a diagnostic command: `mongo --eval 'db.runCommand({ connectionStatus: 1 })'` This will output the current database version, the server address and port, and the output of the status command.</span></span> <span data-ttu-id="be8ba-202">Um valor igual a `1` para o campo "OK" na resposta indica que o servidor está funcionando.</span><span class="sxs-lookup"><span data-stu-id="be8ba-202">A value of `1` for the "ok" field in the response indicates that the server is working.</span></span>

4. <span data-ttu-id="be8ba-203">Para interromper a execução do serviço do MongoDB, insira: `sudo service mongodb stop`</span><span class="sxs-lookup"><span data-stu-id="be8ba-203">To stop your MongoDB service from running, enter: `sudo service mongodb stop`</span></span>

> [!NOTE]
> <span data-ttu-id="be8ba-204">O MongoDB tem vários parâmetros padrão, incluindo o armazenamento de dados em /data/db e a execução na porta 27017.</span><span class="sxs-lookup"><span data-stu-id="be8ba-204">MongoDB has several default parameters, including storing data in /data/db and running on port 27017.</span></span> <span data-ttu-id="be8ba-205">Além disso, `mongod` é o daemon (processo de host para o banco de dados) e `mongo` é o shell de linha de comando que se conecta a uma instância específica do `mongod`.</span><span class="sxs-lookup"><span data-stu-id="be8ba-205">Also, `mongod` is the daemon (host process for the database) and `mongo` is the command-line shell that connects to a specific instance of `mongod`.</span></span>

<span data-ttu-id="be8ba-206">VS Code dá suporte ao trabalho com bancos de dados do MongoDB por meio da [extensão CosmosDB do Azure](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb), você pode criar, gerenciar e consultar bancos de dados do MongoDB de dentro vs Code.</span><span class="sxs-lookup"><span data-stu-id="be8ba-206">VS Code supports working with MongoDB databases via the [Azure CosmosDB extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb), you can create, manage and query MongoDB databases from within VS Code.</span></span> <span data-ttu-id="be8ba-207">Para saber mais, visite o VS Code docs: [trabalhando com o MongoDB](https://code.visualstudio.com/docs/azure/mongodb).</span><span class="sxs-lookup"><span data-stu-id="be8ba-207">To learn more, visit the VS Code docs: [Working with MongoDB](https://code.visualstudio.com/docs/azure/mongodb).</span></span>

<span data-ttu-id="be8ba-208">Saiba mais nos documentos do MongoDB:</span><span class="sxs-lookup"><span data-stu-id="be8ba-208">Learn more in the MongoDB docs:</span></span>

- [<span data-ttu-id="be8ba-209">Introdução ao uso do MongoDB</span><span class="sxs-lookup"><span data-stu-id="be8ba-209">Introduction to using MongoDB</span></span>](https://docs.mongodb.com/manual/introduction/)
- [<span data-ttu-id="be8ba-210">Criar usuários</span><span class="sxs-lookup"><span data-stu-id="be8ba-210">Create users</span></span>](https://docs.mongodb.com/manual/tutorial/create-users/)
- [<span data-ttu-id="be8ba-211">Conectar-se a uma instância do MongoDB em um host remoto</span><span class="sxs-lookup"><span data-stu-id="be8ba-211">Connect to a MongoDB instance on a remote host</span></span>](https://docs.mongodb.com/manual/mongo/#mongodb-instance-on-a-remote-host)
- [<span data-ttu-id="be8ba-212">CRUD: criar, ler, atualizar, excluir</span><span class="sxs-lookup"><span data-stu-id="be8ba-212">CRUD: Create, Read, Update, Delete</span></span>](https://docs.mongodb.com/manual/crud/)
- [<span data-ttu-id="be8ba-213">Documentos de referência</span><span class="sxs-lookup"><span data-stu-id="be8ba-213">Reference Docs</span></span>](https://docs.mongodb.com/manual/reference/)

## <a name="install-microsoft-sql-server"></a><span data-ttu-id="be8ba-214">Instalar o Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="be8ba-214">Install Microsoft SQL Server</span></span>

<span data-ttu-id="be8ba-215">Para instalar o SQL Server no WSL (Ubuntu 18, 4), siga este guia de início rápido: [instalar SQL Server e criar um banco de dados no Ubuntu](/sql/linux/quickstart-install-connect-ubuntu).</span><span class="sxs-lookup"><span data-stu-id="be8ba-215">To install SQL Server on WSL (Ubuntu 18.04), follow this quickstart: [Install SQL Server and create a database on Ubuntu](/sql/linux/quickstart-install-connect-ubuntu).</span></span>

<span data-ttu-id="be8ba-216">Para trabalhar com bancos de dados Microsoft SQL Server no VS Code, experimente a [extensão MSSQL](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql).</span><span class="sxs-lookup"><span data-stu-id="be8ba-216">To work with Microsoft SQL Server databases in VS Code, try the [MSSQL extension](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql).</span></span>

## <a name="install-sqlite"></a><span data-ttu-id="be8ba-217">Instalar o SQLite</span><span class="sxs-lookup"><span data-stu-id="be8ba-217">Install SQLite</span></span>

<span data-ttu-id="be8ba-218">Para instalar o SQLite em WSL (Ubuntu 18, 4):</span><span class="sxs-lookup"><span data-stu-id="be8ba-218">To install SQLite on WSL (Ubuntu 18.04):</span></span>

1. <span data-ttu-id="be8ba-219">Abra o terminal do WSL (ou seja, Ubuntu 18.04).</span><span class="sxs-lookup"><span data-stu-id="be8ba-219">Open your WSL terminal (ie. Ubuntu 18.04).</span></span>
2. <span data-ttu-id="be8ba-220">Atualize os pacotes do Ubuntu: `sudo apt update`</span><span class="sxs-lookup"><span data-stu-id="be8ba-220">Update your Ubuntu packages: `sudo apt update`</span></span>
3. <span data-ttu-id="be8ba-221">Depois que os pacotes forem atualizados, instale o SQLite3 com: `sudo apt install sqlite3`</span><span class="sxs-lookup"><span data-stu-id="be8ba-221">Once the packages have updated, install SQLite3 with: `sudo apt install sqlite3`</span></span>
4. <span data-ttu-id="be8ba-222">Confirme a instalação e obtenha o número de versão: `sqlite3 --version`</span><span class="sxs-lookup"><span data-stu-id="be8ba-222">Confirm installation and get the version number: `sqlite3 --version`</span></span>

<span data-ttu-id="be8ba-223">Para criar um banco de dados de teste, chamado "example. DB", digite: `sqlite3 example.db`</span><span class="sxs-lookup"><span data-stu-id="be8ba-223">To create a test database, called "example.db", enter: `sqlite3 example.db`</span></span>

<span data-ttu-id="be8ba-224">Para ver uma lista de seus bancos de dados do SQLite, digite: `.databases`</span><span class="sxs-lookup"><span data-stu-id="be8ba-224">To see a list of your SQLite databases, enter: `.databases`</span></span>

<span data-ttu-id="be8ba-225">Para ver o status do seu banco de dados, digite: `.dbinfo ?DB?`</span><span class="sxs-lookup"><span data-stu-id="be8ba-225">To see the status of your database, enter: `.dbinfo ?DB?`</span></span>

<span data-ttu-id="be8ba-226">Para sair do prompt do SQLite, digite: `.exit`</span><span class="sxs-lookup"><span data-stu-id="be8ba-226">To exit the SQLite prompt, enter: `.exit`</span></span>

<span data-ttu-id="be8ba-227">Para obter mais informações sobre como trabalhar com um banco de dados SQLite, consulte os [documentos do SQLite](https://www.sqlite.org/quickstart.html).</span><span class="sxs-lookup"><span data-stu-id="be8ba-227">For more information about working with a SQLite database, see the [SQLite docs](https://www.sqlite.org/quickstart.html).</span></span>

<span data-ttu-id="be8ba-228">Para trabalhar com bancos de dados SQLite no VS Code, experimente a [extensão SQLite](https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools).</span><span class="sxs-lookup"><span data-stu-id="be8ba-228">To work with SQLite databases in VS Code, try the [SQLite extension](https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools).</span></span>

## <a name="install-redis"></a><span data-ttu-id="be8ba-229">Instalar o Redis</span><span class="sxs-lookup"><span data-stu-id="be8ba-229">Install Redis</span></span>

<span data-ttu-id="be8ba-230">Para instalar o Redis no WSL (Ubuntu 18, 4):</span><span class="sxs-lookup"><span data-stu-id="be8ba-230">To install Redis on WSL (Ubuntu 18.04):</span></span>

1. <span data-ttu-id="be8ba-231">Abra o terminal do WSL (ou seja, Ubuntu 18.04).</span><span class="sxs-lookup"><span data-stu-id="be8ba-231">Open your WSL terminal (ie. Ubuntu 18.04).</span></span>
2. <span data-ttu-id="be8ba-232">Atualize os pacotes do Ubuntu: `sudo apt update`</span><span class="sxs-lookup"><span data-stu-id="be8ba-232">Update your Ubuntu packages: `sudo apt update`</span></span>
3. <span data-ttu-id="be8ba-233">Depois que os pacotes forem atualizados, instale o Redis com: `sudo apt install redis-server`</span><span class="sxs-lookup"><span data-stu-id="be8ba-233">Once the packages have updated, install Redis with: `sudo apt install redis-server`</span></span>
4. <span data-ttu-id="be8ba-234">Confirme a instalação e obtenha o número de versão: `redis-server --version`</span><span class="sxs-lookup"><span data-stu-id="be8ba-234">Confirm installation and get the version number: `redis-server --version`</span></span>

<span data-ttu-id="be8ba-235">Para iniciar a execução do servidor Redis: `sudo service redis-server start`</span><span class="sxs-lookup"><span data-stu-id="be8ba-235">To start running your Redis server: `sudo service redis-server start`</span></span>

<span data-ttu-id="be8ba-236">Verifique se Redis está funcionando (Redis-CLI é o utilitário de interface de linha de comando para se comunicar com Redis): `redis-cli ping` isso deve retornar uma resposta de "pongue".</span><span class="sxs-lookup"><span data-stu-id="be8ba-236">Check to see if redis is working (redis-cli is the command line interface utility to talk with Redis): `redis-cli ping` this should return a reply of "PONG".</span></span>

<span data-ttu-id="be8ba-237">Para interromper a execução do servidor Redis: `sudo service redis-server stop`</span><span class="sxs-lookup"><span data-stu-id="be8ba-237">To stop running your Redis server: `sudo service redis-server stop`</span></span>

<span data-ttu-id="be8ba-238">Para obter mais informações sobre como trabalhar com um banco de dados Redis, consulte o [documentos do Redis](https://redis.io/topics/quickstart).</span><span class="sxs-lookup"><span data-stu-id="be8ba-238">For more information about working with a Redis database, see the [Redis docs](https://redis.io/topics/quickstart).</span></span>

<span data-ttu-id="be8ba-239">Para trabalhar com bancos de dados do Redis no VS Code, tente a [extensão Redis](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-redis-client).</span><span class="sxs-lookup"><span data-stu-id="be8ba-239">To work with Redis databases in VS Code, try the [Redis extension](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-redis-client).</span></span>

## <a name="see-services-running-and-set-up-profile-aliases"></a><span data-ttu-id="be8ba-240">Consulte serviços em execução e configurar aliases de perfil</span><span class="sxs-lookup"><span data-stu-id="be8ba-240">See services running and set up profile aliases</span></span>

<span data-ttu-id="be8ba-241">Para ver os serviços que você está executando no momento em sua distribuição do WSL, digite: `service --status-all`</span><span class="sxs-lookup"><span data-stu-id="be8ba-241">To see the services that you currently have running on your WSL distribution, enter: `service --status-all`</span></span>

<span data-ttu-id="be8ba-242">Digitar `sudo service mongodb start` ou `sudo service postgres start` e `sudo -u postgrest psql` pode ser entediante.</span><span class="sxs-lookup"><span data-stu-id="be8ba-242">Typing out `sudo service mongodb start` or `sudo service postgres start` and `sudo -u postgrest psql` can get tedious.</span></span>  <span data-ttu-id="be8ba-243">No entanto, você pode considerar a configuração de aliases no arquivo `.profile` no WSL para tornar esses comandos mais rápidos e fáceis de serem lembrados.</span><span class="sxs-lookup"><span data-stu-id="be8ba-243">However, you could consider setting up aliases in your `.profile` file on WSL to make these commands quicker to use and easier to remember.</span></span>

<span data-ttu-id="be8ba-244">Para configurar seu próprio alias personalizado ou atalho para execução destes comandos:</span><span class="sxs-lookup"><span data-stu-id="be8ba-244">To set up your own custom alias, or shortcut, for executing these commands:</span></span>

1. <span data-ttu-id="be8ba-245">Abra o terminal do WSL e insira `cd ~` para ter certeza de que você está no diretório raiz.</span><span class="sxs-lookup"><span data-stu-id="be8ba-245">Open your WSL terminal and enter `cd ~` to be sure you're in the root directory.</span></span>
2. <span data-ttu-id="be8ba-246">Abra o arquivo `.profile`, que controla as configurações do terminal, com o editor de texto do terminal, o Nano: `sudo nano .profile`</span><span class="sxs-lookup"><span data-stu-id="be8ba-246">Open the `.profile` file, which controls the settings for your terminal, with the terminal text editor, Nano: `sudo nano .profile`</span></span>
3. <span data-ttu-id="be8ba-247">Na parte inferior do arquivo (não altere as configurações de `# set PATH`), adicione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="be8ba-247">At the bottom of the file (don't change the `# set PATH` settings), add the following:</span></span>

    ```bash
    # My Aliases
    alias start-pg='sudo service postgresql start'
    alias run-pg='sudo -u postgres psql'
    ```

    <span data-ttu-id="be8ba-248">Isso permitirá que você insira `start-pg` para iniciar a execução do serviço PostgreSQL e `run-pg` para abrir o shell do psql.</span><span class="sxs-lookup"><span data-stu-id="be8ba-248">This will allow you to enter `start-pg` to start running the postgresql service and `run-pg` to open the psql shell.</span></span> <span data-ttu-id="be8ba-249">Você pode alterar `start-pg` e `run-pg` para os nomes que desejar; apenas tenha cuidado para não substituir um comando que o Postgres já usa.</span><span class="sxs-lookup"><span data-stu-id="be8ba-249">You can change `start-pg` and `run-pg` to whatever names you want, just be careful not to overwrite a command that postgres already uses!</span></span>

4. <span data-ttu-id="be8ba-250">Depois de adicionar seus novos aliases, saia do editor de texto Nano usando **Ctrl+X** – selecione `Y` (Sim) quando precisar salvar o conteúdo e Enter (deixando o nome de arquivo como `.profile`).</span><span class="sxs-lookup"><span data-stu-id="be8ba-250">Once you've added your new aliases, exit the Nano text editor using **Ctrl+X** -- select `Y` (Yes) when prompted to save and Enter (leaving the file name as `.profile`).</span></span>
5. <span data-ttu-id="be8ba-251">Feche e abra novamente o terminal do WSL e, em seguida, experimente os novos comandos de alias.</span><span class="sxs-lookup"><span data-stu-id="be8ba-251">Close and re-open your WSL terminal, then try your new alias commands.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be8ba-252">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="be8ba-252">Additional resources</span></span>

- [<span data-ttu-id="be8ba-253">Configurando seu ambiente de desenvolvimento no Windows 10</span><span class="sxs-lookup"><span data-stu-id="be8ba-253">Setting up your development environment on Windows 10</span></span>](/windows/dev-environment/)