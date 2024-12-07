# Arquitetura de Banco de Dados

### Aula 1 - Arquitetura de BD: Modelos

**Modelos de Banco de Dados:**

Existem diversos modelos de banco de dados, cada um com características distintas.  A escolha do modelo depende das necessidades do projeto.

**Modelos:**

- **Modelo Relacional:** Organiza dados em tabelas, linhas e colunas. Utiliza SQL. É o modelo mais utilizado, embora não o mais apropriado para todos os contextos. Exemplo: Um banco de dados relacional armazena informações sobre alunos, cursos e notas em tabelas interligadas.
- **Modelo Hierárquico:** Organiza dados em uma estrutura hierárquica em forma de árvore. Menos comum. Exemplo: Sistema de arquivos.
- **Modelo de Rede:** Mais complexo. Usa links para relacionar dados. Pouco comum.
- **Modelo de Objetos:** Armazena dados como objetos, incluindo atributos e métodos. Exemplo: db4objects, ObjectDB.
- **Modelo NoSQL:** Abrange diversos tipos, como Key-Value, Document, Column-Family e Graph. Alta escalabilidade. Exemplo: MongoDB, Cassandra, Redis.

| Modelo de Banco de Dados | Descrição | Exemplo |
| --- | --- | --- |
| Relacional | Dados em tabelas com linhas e colunas, utilizando SQL. | MySQL, PostgreSQL, Oracle |
| Hierárquico | Estrutura em árvore. | Sistema de arquivos |
| Rede | Dados relacionados por meio de links. | Sistemas legados |
| Objetos | Dados como objetos com atributos e métodos. | db4objects, ObjectDB |
| NoSQL | Vários tipos: Key-Value, Document, Column-Family, Graph. | MongoDB, Cassandra, Redis |

**Esquemas:**

O esquema descreve a estrutura dos dados.

- **Esquema Conceitual (Alto Nível):** Uma representação abstrata dos dados, sem detalhes de implementação. Utilizado para entendimento do contexto. Exemplo: Diagrama Entidade-Relacionamento (ER).
- **Esquema Físico (Baixo Nível):** Detalha a implementação física dos dados. Exemplo: Tabelas e tipos de dados em SQL.
- **Esquema Representacional:** Representa a implementação em um determinado SGBD. Exemplo: Modelo relacional.

**Instâncias:**

Uma instância é uma ocorrência específica dentro de um modelo de dados.  Exemplo:  Um aluno específico em uma tabela de alunos.

**Curiosidade:**  A escolha do modelo de banco de dados depende fortemente das características e volume dos dados, das necessidades da aplicação e da expertise da equipe de desenvolvimento.  A escolha inadequada pode comprometer o desempenho e a manutenibilidade do sistema.

### Aula 2 - Arquitetura de BD: Esquema, Instâncias e Estados de um BDs

**Esquema:**

O esquema de um banco de dados é uma descrição formal da sua estrutura.  Ele define os objetos que serão armazenados no banco de dados, seus atributos, seus tipos de dados e os relacionamentos entre eles.  O esquema é independente dos dados reais que serão armazenados e define o que os dados representam.

**Componentes do Esquema:**

- **Diagramas:** Representações visuais da estrutura do banco de dados. Exemplo: Diagrama Entidade-Relacionamento.
- **Descrição:** Descrição textual da estrutura, geralmente em uma linguagem de definição de dados (LDD).
- **Tipos de Dados e Itens:** Especificação do tipo de dados de cada atributo e dos itens que podem ser armazenados.
- **Construtores:** Define os objetos que serão criados no banco de dados.
- **Constraints:** Regras que garantem a integridade dos dados.

**Instâncias:**

Uma instância representa uma ocorrência específica de um dado.  As instâncias são armazenadas no banco de dados e refletem o estado atual do mini-mundo que o banco de dados representa.

**Estados:**

O estado de um banco de dados é um conjunto de instâncias em um determinado momento. O esquema permanece constante, mas os dados (instâncias) mudam, representando a evolução do mini-mundo.  Um *snapshot* é uma representação do estado do banco de dados em um instante específico do tempo.

**Mudança de Estado:**

Mudanças de estado ocorrem por meio de operações de inserção (*insert*), deleção (*delete*) e atualização (*update*).  Essas operações modificam o estado atual do banco de dados, alterando ou adicionando instâncias.

| Conceito | Descrição | Exemplo |
| --- | --- | --- |
| Esquema | Descrição formal da estrutura do banco de dados | Tabelas, atributos e relacionamentos em um diagrama ER |
| Instância | Ocorrência específica de um dado | Um aluno específico em uma tabela de alunos |
| Estado | Conjunto de instâncias em um dado momento | Todos os alunos cadastrados em um instante T |
| Mudança de Estado | Operações de *insert*, *delete*, e *update* que modificam o estado do BD | Inserir um novo aluno em uma tabela de alunos |

### Aula 3 - Three-Schema Architecture

A arquitetura *Three-Schema* é uma abordagem de modelagem de dados que visa separar as diferentes perspectivas e necessidades no acesso e manipulação dos dados.  Sua estrutura consiste em três níveis:

- **Físico (*Physical*):** Descreve como os dados são fisicamente armazenados no banco de dados. Este nível é de baixo nível e geralmente utiliza estruturas como árvores B e hashes. Ele é o nível mais interno do sistema. A sua estrutura e a sua implementação são de responsabilidade do administrador de banco de dados (DBA).
- **Conceitual (*Conceptual*):** Descreve a estrutura lógica dos dados de forma abstrata e independente do sistema de armazenamento específico. Este nível é de alto nível e geralmente utiliza o modelo Entidade-Relacionamento (ER). Ele serve como base para os níveis externo e físico, e sua criação envolve o entendimento das necessidades do negócio e do contexto onde o banco de dados será utilizado.
- **Externo (*External*):** Descreve as diferentes visões (Views) dos dados para cada usuário ou aplicação. Este nível é o mais externo do sistema. A criação das *views* permite adaptar a apresentação e o acesso aos dados conforme as necessidades específicas de cada usuário ou aplicação, sem a necessidade de conhecer os detalhes da implementação física dos dados. As *views* promovem o isolamento entre os usuários finais e a estrutura física do banco de dados.

**Isolamento entre Camadas:**

A arquitetura *Three-Schema* garante o isolamento entre as três camadas, de forma que mudanças em um nível não afetam os outros.  Exemplo: Alterações na estrutura física (*Physical Schema*) não afetam o esquema conceitual (*Conceptual Schema*), nem a visualização dos dados para o usuário final.

**Independência de Dados:**

A separação das camadas promove a independência de dados, facilitando a manutenção e o desenvolvimento do sistema. Alterações no esquema físico podem ser feitas sem impactar a aplicação, e novas aplicações podem ser desenvolvidas sem afetar a estrutura existente.   Exemplo:  A adição de um índice para otimizar a performance de consultas não precisa afetar nem o modelo conceitual, nem a interface do usuário.

| Nível | Descrição | Exemplo |
| --- | --- | --- |
| Físico | Implementação física dos dados no SGBD | Estruturas de armazenamento (árvores B, hashes), arquivos |
| Conceitual | Estrutura lógica abstrata, independente do SGBD | Modelo Entidade-Relacionamento (ER), diagrama de classes UML |
| Externo | Visões (Views) dos dados, personalizadas para cada usuário ou aplicativo | Uma *view* que mostra apenas informações de vendas para um determinado departamento |
| Isolamento | Mudanças em um nível não afetam outros níveis | Mudança no armazenamento físico sem afetar a aplicação do usuário |
| Independência de Dados | Alterações na estrutura de dados podem ser feitas sem modificar o programa da aplicação | Adição de um índice sem afetar a lógica da aplicação ou a interface do usuário |

**Curiosidade:** A arquitetura *Three-Schema* foi proposta inicialmente como um modelo para bancos de dados relacionais, mas seus princípios de modularidade e isolamento podem ser aplicados a outros tipos de bancos de dados, como os NoSQL.

### Aula 4 - Linguagens para SGBD

Existem diferentes linguagens associadas aos SGBDs, cada uma com propósitos específicos.

- **Data Definition Language (DDL):** Linguagem de definição de dados. Utilizada pelo DBA e designer para definir a estrutura do banco de dados. Exemplo: `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`.
- **Data Manipulation Language (DML):** Linguagem de manipulação de dados. Utilizada pelos usuários finais para consultar, inserir, atualizar e deletar dados. Exemplo: `SELECT`, `INSERT`, `UPDATE`, `DELETE`.

**Linguagens e Interfaces:**

A interação com o banco de dados pode ser realizada por meio de diferentes interfaces e linguagens:

- **Interface Gráfica:** Facilita a interação para usuários com menor conhecimento técnico.
- **Terminal:** Permite executar comandos SQL diretamente, dando maior controle para usuários experientes.
- **Linguagem de Programação:** Utilizando APIs e bibliotecas, as linguagens de programação facilitam a interação com o banco de dados. Exemplos: Python, Java, C++.

**Ambientes de SGBDs:**

Os SGBDs podem ser classificados em diversos ambientes:

- **Ambiente Cliente-Servidor:** O SGBD (servidor) disponibiliza os dados para as aplicações clientes, garantindo centralização e controle.
- **Ambiente Embarcado:** SGBDs são implantados diretamente em dispositivos, sem a necessidade de um servidor separado.

| Linguagem | Descrição | Exemplo |
| --- | --- | --- |
| DDL | Linguagem de definição de dados (CREATE, ALTER, DROP) | `CREATE TABLE` |
| DML | Linguagem de manipulação de dados (SELECT, INSERT, UPDATE, DELETE) | `SELECT * FROM` |
| Interface gráfica | Interface visual para usuários com menor conhecimento técnico | pgAdmin |
| Interface Terminal | Acesso via linha de comando, comandos SQL | Terminal MySQL |
| Linguagem de Programação | Interação via API, bibliotecas | Python, Java |
| Ambiente Cliente-Servidor | SGBD em servidor, acesso por aplicações clientes | MySQL Server |
| Ambiente Embarcado | SGBD implantado diretamente nos dispositivos, sem servidor separado | Sistemas IoT |

**Curiosidade:**  Existem diversos *dialetos* de SQL, adaptando-se às características e necessidades de diferentes SGBDs.  Apesar disso, a maioria possui comandos básicos semelhantes para as operações de manipulação e definição de dados.

### Aula 5 - Interfaces de SGBDs

**Tipos de Interfaces:**

Diversas interfaces permitem a interação com um SGBD, cada uma com características específicas:

- **Web Clients:** Interfaces web, acessíveis através de navegadores. Exemplo: pgAdmin. Preenchimento total ou parcial de dados.
- **App Mobile:** Aplicativos mobile para acesso a dados. Exemplo: Aplicativos de banco. Menus limitados.
- **Forms:** Formulários para inserção de dados. Preenchimento parcial ou total, validando os dados.
- **GUI (Graphical User Interface):** Interface gráfica, geralmente com menus e formulários.
- **Natural Language Interface (NLI):** Interfaces que interpretam comandos em linguagem natural. Exemplo: Assistentes virtuais. Contexto limitado, requer palavras-chave.
- **Pesquisa por Palavra-chave:** Busca dados baseada em palavras-chave. Exemplo: Busca no Google.
- **Speech Input/Output:** Entrada e saída de voz. Exemplo: Assistentes virtuais.
- **DBA (Database Administrator) Interfaces:** Interface para administradores, com comandos de alto privilégio.

**Categorias de Usuário:**

Os usuários são classificados de acordo com o seu nível de conhecimento e acesso:

- **Naïve:** Usuários com baixo conhecimento técnico. Utilizam interfaces simples e com menus limitados. Transações de rotina.
- **DBA (Database Administrator):** Usuários com acesso total e conhecimento avançado. Possuem comandos com privilégio, podendo modificar a estrutura do banco de dados.

**SQL Forms:**

Uma combinação de SQL e formulários para criar interfaces customizadas e mais amigáveis, facilitando o acesso e manipulação de dados.

### Aula 6 - Ambientes e utilities de SGBD

**Ambientes de Banco de Dados:**

A arquitetura de um SGBD é modularizada, composta por diversos módulos interagindo para o gerenciamento de dados.

**Componentes:**

- **Módulo do Usuário:** Inclui diferentes tipos de usuários: DBA staff, usuários casuais, desenvolvedores de aplicação e usuários paramétricos (naïve).
- **Módulo Interno:** Composto pelo *Runtime Database Processor*, *Query and Transaction Manager*, *Storage Manager*, *Data Dictionary* e *System Catalog*.

**Módulos Internos:**

Uma visão detalhada dos módulos internos mostra como o SGBD funciona:

| Módulo | Função Principal |
| --- | --- |
| *Runtime Database Processor* | Processamento de comandos em tempo real. |
| *Query and Transaction Manager* | Gerenciamento de transações e otimização de queries. |
| *Storage Manager* | Gerenciamento do armazenamento físico dos dados. |
| *Data Dictionary* | Armazena informações sobre o esquema e metadados do banco de dados. |
| *System Catalog* | Catálogo do sistema, contendo informações sobre outros objetos no banco de dados, como tabelas e colunas. |

**Utilidades:**

O *Runtime Database Processor* executa tarefas de:

- **Loading:** Carregamento e reformatação de dados.
- **Backup:** Criação de backups do banco de dados, podendo ser incremental.
- **Monitoramento:** Monitora a performance e o estado do banco de dados. Gera estatísticas.
- **Reorganização do Storage:** Otimização do armazenamento dos dados, melhorando a performance de consultas.

**Exemplo:**

Um banco de dados de uma loja online usa o *Runtime Database Processor* para processar pedidos, atualizar o estoque e gerar relatórios de vendas. O *Storage Manager* gerencia o armazenamento dessas informações, o *Data Dictionary* descreve a estrutura do banco de dados, e o *System Catalog* contém informações sobre as tabelas usadas.

| Módulo Interno | Responsabilidade | Interação com outros módulos |
| --- | --- | --- |
| *Runtime Database Processor* | Processamento de comandos em tempo real | Recebe comandos de outros módulos |
| *Query and Transaction Manager* | Otimização e execução de queries e transações | Interage com o *Runtime Database Processor* |
| *Storage Manager* | Gerenciamento do armazenamento físico dos dados | Interage com o *Runtime Database Processor* |
| *Data Dictionary* | Armazena informações sobre o esquema e metadados | Utilizado por todos os módulos internos |
| *System Catalog* | Informações sobre tabelas, colunas, índices e outras estruturas | Utilizado por todos os módulos internos |

**Curiosidade:**  A modularização do SGBD permite que diferentes componentes sejam otimizados independentemente, melhorando a performance e a escalabilidade do sistema como um todo.

### Aula 7 - Arquitetura Modelo Cliente-Servidor

**Arquitetura Física Centralizada:**

Em arquiteturas centralizadas, todos os componentes (hardware e software) residem em uma única máquina.  Este modelo, baseado em *mainframes*, era comum em sistemas antigos.  Acesso aos dados é realizado via terminais conectados em rede.

**Arquitetura Lógica Cliente-Servidor:**

Em arquiteturas cliente-servidor, a responsabilidade é distribuída entre clientes e servidores.  Clientes realizam as requisições, e os servidores processam as informações. A comunicação entre clientes e servidores ocorre por meio de uma rede.  Exemplo:  JDBC (Java Database Connectivity) ou ODBC (Open Database Connectivity).   É um modelo mais moderno, em dois níveis (*Two-Tier*), comumente visto em sistemas de rede.

**Comparação entre modelos centralizado e cliente-servidor:**

| Característica | Arquitetura Física Centralizada | Arquitetura Lógica Cliente-Servidor |
| --- | --- | --- |
| **Localização dos componentes** | Única máquina | Múltiplas máquinas |
| **Compartilhamento de recursos** | Compartilhado | Distribuído |
| **Escalabilidade** | Limitada | Alta |
| **Complexidade** | Simples | Mais complexo |
| **Segurança** | Mais centralizada, potencialmente mais vulnerável | Distribuída, segurança mais granular |
| **Custo** | Potencialmente menor | Potencialmente maior |

**Arquitetura Lógica Cliente-Servidor (*Three-Tier*):**

Uma arquitetura mais complexa, com três camadas: cliente, aplicação e banco de dados (*Three-Tier*).  O servidor de aplicação (*Application Server*) atua como intermediário, recebendo requisições do cliente e enviando respostas.  Isso permite melhor organização, escalabilidade e segurança.

**Stateless:**

Em arquiteturas cliente-servidor, é comum que tanto o cliente quanto o servidor sejam *stateless*, ou seja, não armazenam o estado da comunicação.  Isso simplifica o design e a implementação, mas exige que as requisições incluam toda a informação necessária.

### Aula 8 - Classificação de SGBDs

**Critérios de Classificação:**

Diversos fatores influenciam na escolha e classificação de um SGBD.  A escolha ideal depende das necessidades específicas do projeto.

**Parâmetros:**

- **Modelo de Dados:** O tipo de modelo de dados usado (relacional, hierárquico, rede, objeto, NoSQL). Exemplo: SQL, NoSQL (MongoDB, Cassandra, etc.)
- **Número de Usuários:** A quantidade de usuários que irão acessar simultaneamente o banco de dados.
- **Número de Sites:** Se o banco de dados é centralizado ou distribuído em múltiplos sites (centralizado, distribuído, *Big Data*, replicação, *DB federated*).
- **Custo:** O custo da licença de uso e de manutenção do SGBD. Exemplo: Open source vs. sistemas comerciais.
- **Tipo de Caminho de Acesso:** A forma como os usuários irão acessar os dados (nome do arquivo, armazenamento de arquivos, etc).

**Classificação Relacional:**

SGBDs relacionais usam o modelo relacional de dados, organizado em tabelas, com acesso via SQL.  Exemplo: MySQL, PostgreSQL, Oracle.  Em um banco de dados relacional, as informações são organizadas em tabelas, que são acessíveis via comandos SQL.  O esquema define a estrutura, os metadados contém informações adicionais e *views* fornecem diferentes perspectivas sobre os dados.  As tabelas são armazenadas em arquivos.

**SGBDs de Propósito Geral:**

SGBDs de propósito geral são projetados para atender a uma ampla gama de necessidades e podem ser classificados por sua performance, se são sistemas *Online Transaction Processing* (OLTP), ou *Online Analytical Processing* (OLAP). OLTP sistemas exigem alta performance e alta disponibilidade, sendo mais indicados para transações em tempo real. OLAP é usado para análise e geração de relatórios.

**Tabela de Classificação:**

| Critério | Descrição | Exemplo |
| --- | --- | --- |
| **Modelo de dados** | Tipo de estrutura de dados (relacional, NoSQL, etc.) | SQL, NoSQL (MongoDB, Cassandra) |
| **Número de usuários** | Quantidade de acessos simultâneos | Poucos, muitos, centenas, milhares, milhões |
| **Número de sites** | Localização dos dados (centralizado, distribuído) | Centralizado, distribuído, replicação |
| **Custo** | Licenciamento, open-source, etc. | Gratuito, pago, assinatura |
| **Tipo de caminho de acesso** | Método de acesso aos dados | Nome do arquivo, armazenamento de arquivos |

### Materiais Complementares

Com certeza! Aqui estão os links transcritos para você:

1. [**https://www.ime.usp.br/~andrers/aulas/bd2005-1/aula3**](https://www.ime.usp.br/~andrers/aulas/bd2005-1/aula3)
2. [**https://www.devmedia.com.br/a-historia-dos-banco-de-dados/1678**](https://www.devmedia.com.br/a-historia-dos-banco-de-dados/1678)
3. [**https://db-engines.com/en/ranking**](https://db-engines.com/en/ranking)
4. [**https://www.opservices.com.br/banco-de-dados/**](https://www.opservices.com.br/banco-de-dados/)
5. [**https://www.quora.com/What-is-a-canned-transaction**](https://www.quora.com/What-is-a-canned-transaction)
6. https://www.geeksforgeeks.org/impedance-mismatch-in-dbms/
7. https://www.oreilly.com/library/view/mysql-reference-manual/0596002653/ch03s05.html