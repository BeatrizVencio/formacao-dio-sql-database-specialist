# Sistemas de Gerenciamento de Banco de Dados

### Aula 1 - Abordagem de SGBDs versus Abordagem Tradicional

Este resumo compara a abordagem de bancos de dados utilizando Sistemas de Gerenciamento de Bancos de Dados (SGBDs) com a abordagem tradicional, destacando as vantagens e desvantagens de cada uma.

**Abordagem Tradicional:**

Na abordagem tradicional, as aplicações gerenciam diretamente os dados, geralmente armazenados em arquivos.  Isso resulta em:

- **Redundância:** Dados podem ser repetidos em diferentes arquivos ou aplicações, levando à inconsistência.
- **Esforço repetido:** A manutenção e atualização dos dados exigem esforço repetitivo e são suscetíveis a erros.
- **Falta de Concorrência:** O acesso concorrente a dados pode ser difícil e levar a problemas de consistência.
- **Incosistência:** Alterações em um local podem não ser refletidas em outros.

**Abordagem com SGBDs:**

Utilizar um SGBD centraliza o gerenciamento de dados, oferecendo várias vantagens:

- **Abstração:** O SGBD abstrai a complexidade de armazenamento e acesso a dados, facilitando a interação do programador.
- **Auto-descrição:** O banco de dados descreve a sua própria estrutura, permitindo que o SGBD gerencie os dados de forma eficiente.
- **Isolamento:** Permite acesso independente dos dados por diferentes aplicações sem interferência entre elas.
- **Compartilhamento:** Facilita o compartilhamento de dados com controle de concorrência, garantindo a integridade dos dados.
- **Transação multiusuário:** Garantem que transações sejam executadas de forma atômica, consistente e segura, mesmo com acesso concorrente.
- **Múltiplas visões:** Permitem diferentes perspectivas sobre os mesmos dados, adaptando a apresentação conforme a necessidade do usuário.

**Exemplo Comparativo:**

Cadastro e verificação de pagamento de alunos em uma universidade exemplificam os problemas da abordagem tradicional e as soluções oferecidas por SGBDs.  Na abordagem tradicional, a redundância e o esforço repetitivo são evidentes, enquanto o SGBD permite centralizar os dados, garantindo consistência e acesso concorrente sem perda de integridade.

**Curiosidade:**  Embora a abordagem com SGBDs seja mais robusta e eficiente, a abordagem tradicional pode ser adequada para aplicações muito simples e com baixo volume de dados.  A escolha entre as abordagens depende da complexidade e das necessidades do projeto.

### Aula 2 - Natureza Auto-descritiva da Abordagem de Banco de Dados

Vamos explorar a natureza auto-descritiva dos Sistemas de Gerenciamento de Banco de Dados (SGBDs), contrastando com a abordagem tradicional de gerenciamento de dados.

**Auto-descrição:**

Um SGBD possui a capacidade de se descrever a si mesmo.  Essa auto-descrição é feita através do armazenamento de informações sobre sua própria estrutura e regras que governam os dados.  Essas informações são chamadas de **metadados** e **esquema**.

**Componentes:**

- **Metadados:** Informações que descrevem os dados. Incluem informações sobre a estrutura dos dados e restrições (constraints).
- **Esquema (DB schema):** A descrição da estrutura física e lógica do banco de dados. Define as tabelas, colunas, tipos de dados e relacionamentos entre as tabelas.
- **Catálogo:** Uma tabela (ou conjunto de tabelas) especial dentro do banco de dados que armazena os metadados e descreve o esquema. O catálogo fornece informações sobre outros objetos no banco de dados, incluindo as tabelas, colunas, índices, etc.

**Abordagem Tradicional vs. SGBD:**

Na abordagem tradicional (sem SGBD), a estrutura de dados é definida dentro do programa de aplicação (exemplo: definição de atributos e métodos de uma classe em Java).  A auto-descrição é ausente, tornando o gerenciamento de dados complexo em aplicações grandes.  Já em um SGBD, esquema e metadados são separados, facilitando a sua manipulação e compreensão.  O SGBD utiliza o catálogo para extrair as informações necessárias para realizar consultas.

**Exemplo:**  [Amazon.com.br](http://amazon.com.br/) utiliza um SGBD com múltiplos bancos de dados, todos gerenciados pelo mesmo sistema.  Cada banco de dados possui seu próprio esquema, permitindo o gerenciamento eficiente de diferentes informações.

### Aula 3 - Isolamento Program/data e Abstração

Exploraremos o conceito de isolamento entre programa e dados em um SGBD, enfatizando o papel da abstração e a independência de dados.

**Abordagem Tradicional vs. SGBD:**

| Característica | Abordagem Tradicional | Abordagem com SGBD |
| --- | --- | --- |
| **Estrutura de Dados** | Embutida na aplicação | Definida separadamente (esquema) |
| **Manutenção** | Difícil, requer modificação de código | Simples, alterações independentes |
| **Flexibilidade** | Baixa, alterações complexas | Alta, mudanças fáceis e isoladas |
| **Escalabilidade** | Limitada | Alta |

**Isolamento e Abstração:**

SGBDs promovem alto nível de abstração, separando a lógica da aplicação do gerenciamento de dados.  Isso simplifica a manutenção e melhora a escalabilidade.  Alterações na estrutura de dados não impactam diretamente o código da aplicação.

**Independência de Dados:**

A abstração leva à independência de dados, onde modificações no banco de dados não exigem alterações no código da aplicação. Isso garante maior flexibilidade e facilita atualizações e *upgrades* do sistema.

**Transparência:**

O SGBD garante que as operações de consulta e manipulação sejam independentes da implementação física dos dados, fornecendo transparência ao desenvolvedor.

**Exemplo:**

Imagine uma aplicação que consulta uma tabela de alunos. Ao adicionar um novo atributo (ex: curso preferido) à tabela de alunos, usando um SGBD, a aplicação não precisa ser alterada para acessar esse novo dado. O SGBD gerencia esse acesso de forma transparente.  Na abordagem tradicional, o programa precisa ser alterado para adicionar esse atributo e lidar com a nova estrutura de dados.

**Curiosidade:** A abstração e a independência de dados são pilares do design de bancos de dados modernos, promovendo flexibilidade, escalabilidade e manutenabilidade de sistemas.

### Aula 4 - Suporte à Múltiplas Visões dos Dados

Vamos ver o conceito de *Table Views* em SGBDs, mostrando como diferentes usuários podem ter perspectivas distintas sobre o mesmo conjunto de dados.

**Views:**

SGBDs permitem criar *views* (visões), que são consultas salvas que fornecem uma perspectiva específica sobre os dados.  As *views* são úteis quando diferentes usuários ou departamentos precisam acessar os mesmos dados, mas com diferentes níveis de detalhe ou filtros.  As *views* não armazenam dados diretamente, eles são gerados dinamicamente a partir da consulta.  As mudanças na tabela subjacente são refletidas automaticamente nas *views*.

**Vantagens:**

- **Flexibilidade:** Permite diferentes perspectivas sobre os mesmos dados, sem duplicar informações.
- **Simplicidade:** Facilita o acesso a dados para usuários com diferentes necessidades.
- **Segurança:** Pode ser usada para restringir o acesso a dados sensíveis, exibindo apenas a informação necessária.

**Comparação entre Visão e Tabela:**

| Característica | Visão (View) | Tabela |
| --- | --- | --- |
| **Armazenamento** | Não armazena dados, apenas a consulta | Armazena dados |
| **Atualização** | Atualiza-se automaticamente | Requer atualização direta |
| **Complexidade** | Mais simples de gerenciar | Mais complexo para grandes conjuntos de dados |
| **Segurança** | Pode restringir acesso aos dados | Acesso pode ser mais amplo |

**Exemplo:**

Imagine um banco de dados de uma universidade, com informações sobre alunos, cursos e notas.  A área de educação pode estar interessada em *views* que mostram o nome, matrícula, matéria, sala e cursos extras do aluno.  A área financeira, por sua vez, pode precisar de uma *view* com nome, matrícula, mensalidade e atrasos. Ambas as áreas podem acessar o mesmo banco de dados, mas cada uma recebe uma visão filtrada e otimizada para suas necessidades.  Uma consulta (`query`) é usada para gerar cada *view*.

**Curiosidade:**  As *views* em bancos de dados podem ser *read-only* (somente leitura),  impedindo que usuários ou aplicações modifiquem os dados.  Isso proporciona segurança e controle de acesso aos dados.

### Aula 5 - Compartilhamento de dados e Processamento de Trasações Multiusuários

**Cenários de Múltiplos Acessos:**

Sistemas de banco de dados são frequentemente acessados por múltiplos usuários e processos concorrentemente.  Esse compartilhamento exige mecanismos para garantir a integridade e a consistência dos dados.  A manutenção do banco de dados e a integração com outros sistemas também são aspectos importantes a serem considerados.

**Controle de Concorrência (*Concurrency Control*):**

Mecanismos de controle de concorrência são essenciais para garantir que acessos simultâneos a dados não resultem em inconsistências.  Isso é especialmente crítico em operações de escrita, onde múltiplos usuários podem tentar modificar os mesmos dados ao mesmo tempo.  Os mecanismos de bloqueio e liberação garantem que apenas um processo acesse e modifique os dados de cada vez.

**OLTP (Online Transaction Processing) e OLAP (Online Analytical Processing):**

Duas abordagens principais para processamento de dados:

| Característica | OLTP (Online Transaction Processing) | OLAP (Online Analytical Processing) |
| --- | --- | --- |
| **Objetivo** | Processamento de transações em tempo real | Análise de dados e tomada de decisão |
| **Tipo de Dado** | Dados operacionais, atualizados frequentemente | Dados históricos, agregados |
| **Performance** | Alta performance, resposta imediata | Performance menos crítica, podendo envolver processamento longo |
| **Transações** | Transações curtas, atômicas e simultâneas | Sem transações simultâneas, operações de leitura predominam |
| **Ambiente** | Ambiente operacional | Ambiente de Data Warehouse ou *Data Lake* |
| **Exemplo** | Transações bancárias, reservas de voos, compras online | Análise de vendas, previsões de demanda, relatórios gerenciais |

**ELT Process (Extract, Load, Transform):**

O processo ELT é fundamental para a construção de *data warehouses* OLAP, extraindo dados de diversas fontes, carregando-os para o *data warehouse* e transformando-os em um formato adequado para análise.

**Integração e Processos:**

Sistemas OLTP e OLAP muitas vezes coexistem, com o ELT atuando como um *pipeline* que alimenta o ambiente OLAP com dados do ambiente OLTP.  Isso permite que as empresas utilizem dados operacionais para análises estratégicas, utilizando *data mining* e ferramentas de BI.

**Curiosidade:**  O acrônimo OLTP, Online Transaction Processing, reflete a natureza em tempo real e transacional desse tipo de processamento de dados.  Já o acrônimo OLAP, Online Analytical Processing, destaca a sua função voltada para análise de grandes conjuntos de dados.

### Aula 6 - Abordagem de banco de dados - Quais são os Atores em Banco de Dados

**Atores Principais:**

Em um sistema de banco de dados, vários atores interagem com o sistema, cada um com diferentes níveis de acesso e responsabilidades. Os principais são:

- **Designer:** Responsável pela modelagem e design do banco de dados, interagindo diretamente com o cliente para entender as necessidades e traduzindo-as em um modelo de dados. É uma fase préliminar.
- **Administrador (DBA):** Gerencia os recursos do banco de dados, garante sua performance e integridade, e controla os acessos. Frequentemente lida com uma equipe (DBA Staff).
- **Usuários Finais:** Interagem com o banco de dados para consultar e atualizar informações. São categorizados de acordo com seu nível de acesso e conhecimento técnico.

**Usuários Finais - Categorização:**

Os usuários finais podem ser classificados em diferentes categorias:

| Categoria | Acesso | Conhecimento | Interação | Exemplo |
| --- | --- | --- | --- | --- |
| **Casuais** | Ocasional | Baixo | APIs, interfaces simples | Usuário de um caixa eletrônico |
| **Ingênuos** | Via GUI | Básico | *Canned Transactions* | Usuário de uma rede social |
| **Sofisticados** | Queries SQL | Intermediário/Alto | APIs, Queries diretas | Cientistas de dados, analistas de BI |
| **Standalone** | Acesso direto | Alto | Gerenciamento completo | Administrador do próprio banco de dados |

**Vantagens de usar um SGBD:**

- **Compartilhamento:** Permite o acesso simultâneo e controlado a dados.
- **Manutenção:** Facilita a modificação e a atualização da estrutura de dados, sem grandes impactos na aplicação.
- **Usabilidade:** Simplifica o acesso aos dados para os usuários.
- **Integração:** Facilita a integração com outras aplicações e sistemas.

**Quando não usar um SGBD:**

Sistemas muito simples com baixo volume de dados e poucos usuários podem não necessitar de um SGBD.  A complexidade de implementação pode superar os benefícios em alguns cenários.

**Curiosidade:**  A escolha do tipo de banco de dados, relacional ou NoSQL, e as ferramentas de acesso (ex: APIs) impactam diretamente a experiência do usuário e a eficiência do sistema.

### Aula 7 - Workers em background - Banco de Dados

**Workers em Background:**

Diversos atores trabalham nos bastidores de um SGBD, garantindo o seu funcionamento e disponibilidade para os usuários.  Esses atores não interagem diretamente com os usuários finais, mas são fundamentais para o desempenho do sistema.

**Tipos de Workers:**

- **Designer do Sistema SGBD:** Responsável pelo design e arquitetura do SGBD.
- **Pessoal de Operação e Manutenção:** Garante a disponibilidade e a performance do hardware e do software.
- **Desenvolvedores de Ferramentas:** Cria ferramentas para melhorar o desempenho, a modelagem e a análise.

**Tarefas e Responsabilidades:**

A equipe de background tem responsabilidades cruciais:

- **Implementação:** Instalar e configurar o SGBD, garantir compatibilidade entre pacotes de software e os recursos da máquina.
- **Manutenção:** Manter o hardware e software em perfeito estado, garantir que o ambiente computacional esteja otimizado para o melhor desempenho do SGBD. Gerenciar segurança e realizar backups periódicos.
- **Desenvolvimento de Ferramentas:** Construir novas funcionalidades, otimizar performance e melhorar recursos de modelagem e análise.

**Comparação entre os Workers:**

| Atores | Tarefas | Ligação com o SGBD |
| --- | --- | --- |
| Designer do sistema SGBD | Design da arquitetura do sistema | Indireta |
| Pessoal de operação e manutenção | Manutenção de hardware e software, garantindo o funcionamento do SGBD | Direta |
| Desenvolvedores de ferramentas | Desenvolvimento de novas ferramentas para otimização e análise dos dados | Indireta |

**Curiosidade:**  A equipe de background em um SGBD é essencial para que os usuários finais possam ter uma experiência eficiente e segura.  A complexidade e a infraestrutura do SGBD exigem constante atenção e manutenção.

### Aula 8 - Vantagens de Utilizar a Abordagem de SGBDs

**Vantagens Principais:**

Utilizar um SGBD oferece diversas vantagens significativas em comparação com métodos tradicionais de gerenciamento de dados, simplificando e otimizando o processo.

**Controle de Redundância:**

SGBDs centralizam os dados, eliminando redundância e inconsistência.  Isso garante consistência de informação, pois todas as aplicações acessam os mesmos dados.

**Restrição de Acesso:**

SGBDs oferecem mecanismos robustos de controle de acesso.  Isso permite definir permissões específicas para diferentes usuários e grupos, garantindo segurança e confidencialidade de dados.

**Persistência:**

SGBDs garantem a persistência dos dados.  A informação é mantida mesmo com falhas de sistema ou desligamento, ao contrário de métodos tradicionais onde a persistência depende de mecanismos externos à aplicação.

**Compartilhamento e Concorrência:**

SGBDs facilitam o compartilhamento de dados e tratam a concorrência entre acessos simultâneos. Isso garante integridade dos dados.

| Característica | Abordagem Tradicional | Abordagem com SGBD |
| --- | --- | --- |
| **Compartilhamento** | Complexo, propenso a erros | Simples, eficiente, controle de acesso |
| **Concorrência** | Dificuldade em lidar com acessos simultâneos | Gerenciamento eficiente de transações |
| **Integridade dos Dados** | Alta probabilidade de inconsistência | Integridade garantida |

**Impedance Mismatch Problem:**

Há uma diferença de estrutura entre o modelo relacional de dados (SGBD) e a orientação a objetos em linguagens de programação.  SGBDs NoSQL orientado a objetos (como o db4objects e o ZOPE) ajudam a reduzir essa diferença.

**Interface Multi-usuário:**

SGBDs fornecem interfaces para múltiplos usuários acessarem e manipularem dados concorrentemente.  Interfaces variam conforme a necessidade e o conhecimento técnico.

**Estruturas de Armazenamento e Técnicas de Busca:**

SGBDs otimizam o armazenamento com indexação, *caching* e *buffering*. A linguagem SQL simplifica consultas complexas.

**Integridade de Dados:**

SGBDs garantem integridade com *constraints*, regras de negócio e *triggers*.

**Curiosidade:**  A escolha do SGBD (relacional ou NoSQL) impacta no desempenho, escalabilidade e manutenabilidade do sistema.

### Aula 9 - Ganhos em utilizar SGBDs

**Padronização:**

O uso de um SGBD promove a padronização na estrutura de dados, facilitando a organização, acesso e manipulação das informações.  Isso elimina a necessidade de diferentes estruturas de dados para cada aplicação.  A padronização também facilita a consulta e a geração de relatórios.

**Redução de Tempo no Desenvolvimento da Aplicação:**

Utilizar um SGBD reduz o tempo de desenvolvimento, pois funcionalidades de gerenciamento de dados (persistência, segurança, concorrência) são fornecidas pelo próprio SGBD.  Isso permite que os desenvolvedores se concentrem na lógica específica da aplicação, economizando tempo e recursos.  Comparação:

| Característica | Desenvolvimento sem SGBD | Desenvolvimento com SGBD |
| --- | --- | --- |
| **Gerenciamento de Dados** | Responsabilidade da aplicação | Gerenciado pelo SGBD |
| **Persistência** | Requer implementação específica | Fornecida pelo SGBD |
| **Controle de Concorrência** | Implementação complexa | Mecanismos robustos fornecidos pelo SGBD |
| **Tempo de Desenvolvimento** | Maior | Menor |

**Flexibilidade:**

A padronização de dados em um SGBD permite maior flexibilidade na adição de novos requisitos ou mudanças na estrutura do banco de dados, sem exigir grandes alterações na aplicação.  Modificações são relativamente simples e de impacto minimizado.

**Disponibilidade de Informação Atualizada:**

As informações no banco de dados estão sempre atualizadas, garantindo que as aplicações acessem sempre os dados mais recentes.

**Economia com Escalabilidade:**

Utilizar um SGBD permite maior economia em longo prazo através da escalabilidade.  O gerenciamento centralizado facilita o crescimento do banco de dados, sem exigir grandes mudanças na arquitetura ou no código.

**Operacional e Gerenciamento:**

Usar um SGBD centraliza o gerenciamento e a operação, reduzindo custos com manutenção e simplificando o acesso aos dados.

**Curiosidade:**  A economia de escala proporcionada pelo SGBD é ainda mais evidente em grandes organizações, onde o custo de gerenciar múltiplos sistemas e arquivos de dados seria significativamente maior.

### Aula 10 - Quando não usar SGBDs

**Custo-Benefício:**

A decisão de utilizar ou não um SGBD envolve uma análise de custo-benefício, considerando o custo de implementação e manutenção em relação aos benefícios proporcionados.  Em cenários simples ou com restrições específicas, o custo de um SGBD pode superar os benefícios.  Exemplo:

| Cenário | Custo do SGBD | Benefício do SGBD | Custo-Benefício |
| --- | --- | --- | --- |
| Aplicação simples, poucos dados | Alto | Baixo | Desfavorável |
| Aplicação complexa, muitos dados | Baixo | Alto | Favorável |

**Situações onde NÃO usar um SGBD:**

Existem vários cenários onde a implementação de um SGBD não é vantajosa. Exemplos:

- **Aplicativos Simples:** Em aplicações de baixa complexidade, com poucos dados e sem necessidade de compartilhamento ou concorrência, o custo e a complexidade de um SGBD podem ser desnecessários.
- **Processamento em Tempo Real (*Real-time*) com Alta Performance:** Em sistemas que exigem resposta imediata e altíssima performance, a sobrecarga de um SGBD pode afetar o desempenho. Neste caso, a abordagem tradicional pode ser preferível.
- **Zero Mudanças:** Em casos de dados estáticos, onde não se espera nenhuma alteração, um SGBD pode ser desnecessário. Um simples arquivo CSV pode ser suficiente.
- **Sistemas Embarcados:** Em sistemas embarcados (como dispositivos IoT), limitações de recursos (memória, processamento) podem inviabilizar a utilização de um SGBD.

**Alternativas:**

Dependendo da situação, as seguintes alternativas são viáveis:

- **Arquivos CSV:** Para dados simples e estáticos, um arquivo CSV oferece uma solução simples e eficiente.
- **Bibliotecas:** Para aplicações com requisitos específicos de performance, bibliotecas podem ser uma alternativa mais leve a um SGBD.

**Real World Examples:**

Alguns exemplos práticos onde a implementação de um SGBD não é usual:

- **AutoCAD:** Software de desenho que trabalha com dados gráficos complexos.
- **Sistemas Embarcados:** Dispositivos com recursos limitados que não suportam um SGBD.
- **Roteadores e Switches:** Dispositivos de rede que geram e utilizam dados de forma simples.

**Curiosidade:**  Apesar das vantagens dos SGBDs, é fundamental avaliar o custo-benefício e as necessidades específicas do projeto antes de escolher uma solução.  A escolha inadequada pode resultar em sobrecarga e complexidade desnecessárias.