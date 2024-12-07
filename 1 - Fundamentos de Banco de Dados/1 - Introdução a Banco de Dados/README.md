# Introdução a Banco de Dados

### Aula 1 - Cenário de dados

Vamos descrever a evolução e o contexto dos dados, culminando na necessidade de Sistemas de Gerenciamento de Bancos de Dados (SGBDs).  A crescente geração de dados em diversas áreas, impulsionada pela digitalização e pela internet das coisas (IoT), exige soluções robustas e escaláveis para seu armazenamento e processamento.  A análise desses dados, por sua vez, gera insights valiosos para tomada de decisões em negócios e outras áreas.

**A Evolução do Armazenamento de Dados:**

A forma como os dados são armazenados e gerenciados evoluiu dramaticamente.  Comparando o passado com o presente:

| Data | Método de Armazenamento | Capacidade | Confiabilidade | Exemplos | Tipos de Dados Predominantes |
| --- | --- | --- | --- | --- | --- |
| Antigamente | Cadernos, agendas de papel | Baixa | Baixa | Notas manuscritas, endereços em papel | Textual |
| Presente | Computadores, celulares, nuvem | Alta | Alta (em geral) | Bancos de dados, plataformas online | Textual, Numérico, Multimídia |

**Dados x Informação:**

- Dados são fatos brutos, como números, textos ou imagens isolados, sem contexto.
- A informação, por outro lado, resulta da análise e interpretação desses dados, fornecendo significado e permitindo a tomada de decisões embasadas.

A transformação de dados em informação exige técnicas de mineração de dados, análise estatística e outras metodologias de processamento.  A qualidade da informação depende diretamente da qualidade e da organização dos dados brutos.

**A Necessidade de Bancos de Dados:**

Com a crescente quantidade e variedade de dados, surgiu a necessidade de um sistema para armazená-los de forma:

- **Persistente:** Os dados precisam ser mantidos de forma segura e acessíveis ao longo do tempo, mesmo em caso de falhas de hardware ou software. Sistemas redundantes e mecanismos de backup são essenciais para garantir a persistência.
- **Confiável:** Os dados devem estar protegidos contra corrupção ou perda acidental, garantindo sua integridade e precisão. Medidas de segurança como controle de acesso, criptografia e validação de dados contribuem para sua confiabilidade.
- **Organizada:** Os dados devem ser estruturados para facilitar a busca e análise, permitindo a recuperação eficiente de informações específicas. Modelos de dados bem definidos e a utilização de índices são fundamentais para a organização eficiente.

**Exemplos de uso de Bancos de Dados:**

- **Acesso a contas bancárias:** A verificação de saldos e transações utiliza banco de dados robustos e seguros, garantindo a confidencialidade das informações financeiras. A segurança e a conformidade com regulamentações são cruciais nesse contexto.
- **Consulta de títulos em bibliotecas:** Sistemas de busca em bibliotecas utilizam bancos de dados para gerenciar o acervo, incluindo informações bibliográficas detalhadas como autores, títulos, editores, ISBNs, etc. A busca por palavras-chave ou por outros critérios é facilitada por meio de índices e algoritmos de busca.
- **Redes sociais:** Plataformas online como Facebook e Instagram dependem de bancos de dados para armazenar e gerenciar grandes volumes de informações, incluindo dados de usuários, publicações, interações, etc. O tratamento eficiente desses dados é crucial para o funcionamento dessas plataformas em larga escala.
- **Aplicativos diversos:** A maioria dos aplicativos utilizam bancos de dados, seja para armazenamento de perfis de usuários, informações de produtos ou qualquer outra informação relevante. A escolha do tipo de banco de dados depende das necessidades específicas de cada aplicação, incluindo escalabilidade, performance e tipo de dado a ser armazenado.

**O Papel do SGBD:**

Um SGBD (Sistema de Gerenciamento de Bancos de Dados) garante a persistência, confiabilidade e organização dos dados.  Ele provê:

- Segurança e controle de acesso, impedindo acessos não autorizados por meio de mecanismos de autenticação e autorização. O controle de acesso granular permite definir diferentes níveis de permissão para diferentes usuários.
- Estruturas para armazenamento eficiente dos dados, otimizando o uso de recursos e garantindo a performance do sistema. A escolha da estrutura de dados (relacional, NoSQL, grafo, etc.) afeta diretamente a eficiência do armazenamento.
- Ferramentas para manipulação e análise dos dados, incluindo linguagens de consulta como SQL e interfaces para visualização de dados. A capacidade de extrair informações relevantes e gerar relatórios é fundamental para a tomada de decisões.

**A Era do Big Data:**

O aumento da capacidade de processamento e armazenamento levou à era do Big Data. Os três "Vs" que definem o Big Data são:

- **Volume:** Grande quantidade de dados, frequentemente medido em petabytes ou exabytes.
- **Velocidade:** Dados gerados e processados rapidamente, exigindo sistemas com alta performance. A capacidade de processar *data streams* em tempo real é um fator crucial.
- **Variedade:** Dados em diversos formatos (texto, números, imagens, vídeos, sensores IoT, etc.), exigindo flexibilidade e adaptabilidade dos sistemas de armazenamento.

A evolução da tecnologia, incluindo a computação em nuvem (Cloud Computing), permitiu lidar com o desafio do Big Data, oferecendo escalabilidade e flexibilidade necessárias para processar e analisar enormes quantidades de dados.  Diversas plataformas, incluindo AWS, Azure, MongoDB, Cassandra, Neo4j e Redis, oferecem diferentes tipos de banco de dados para atender às necessidades de diversos cenários.  A escolha da plataforma correta depende de fatores como o tipo de dado, o volume de dados, a necessidade de escalabilidade, e o orçamento disponível.

**Curiosidade:**  A linguagem SQL (Structured Query Language), utilizada para interagir com bancos de dados relacionais, foi criada na década de 1970 e continua sendo uma das linguagens mais importantes na área de gerenciamento de dados.

### Aula 2 - O que são banco de dados?

**Conceitos Essenciais:**

Este resumo explora os fundamentos de bancos de dados e SGBDs, considerando a crescente relevância do Big Data.

**Aplicações em Diversos Setores:**

Bancos de dados são essenciais em diversos setores, com complexidade variável:

- **Engenharia:** Gerenciam projetos complexos, incluindo desenhos, cálculos, simulações e especificações, assegurando a integridade e rastreabilidade das informações técnicas.
- **Negócios:** Suportam o funcionamento de empresas, gerenciando informações cruciais sobre clientes, fornecedores, finanças, operações, e muito mais. Permitem análises de mercado e otimização de processos.
- **E-commerce:** Essencial para a gestão de catálogos de produtos, inventário, controle de estoque, processamento de pedidos e gestão de clientes. A eficiência desses bancos de dados impacta diretamente a experiência do usuário.
- **Saúde:** Armazenam prontuários eletrônicos, resultados de exames, histórico médico e outros dados críticos, garantindo a segurança e confidencialidade da informação. A gestão eficiente desses dados é fundamental para o tratamento de pacientes.
- **Redes Sociais:** Tratam de enormes volumes de dados de usuários, publicações, interações e conteúdo gerado, exigindo alta escalabilidade e performance. A análise destes dados permite a personalização de conteúdo e segmentação de anúncios.

**Sistemas de Gerenciamento de Bancos de Dados (SGBDs):**

SGBDs são os sistemas que gerenciam bancos de dados, garantindo persistência, confiabilidade e acesso eficiente.  Utilizam APIs para facilitar a interação com os usuários, abstraindo a complexidade interna.  Podemos comparar essa interação à forma como um cliente faz um pedido em um restaurante, sem precisar saber como o prato é preparado na cozinha.

**Big Data e Escalabilidade:**

O crescimento exponencial de dados exige SGBDs escaláveis.  O tamanho pode variar de centenas a bilhões de registros, demandando soluções complexas, como os SGBDs distribuídos usados por grandes empresas como a Amazon.

**Manutenção e Integridade:**

A manutenção contínua garante a integridade do banco de dados.  Modificações devem ser confiáveis, acuradas e ter reflexo imediato, garantindo a consistência e a validade das informações.

**Curiosidade:**  SQL, ou Structured Query Language, é uma linguagem de programação crucial para manipular e consultar bancos de dados relacionais.

### Aula 3 - Sistemas de Gerenciamento de Banco de dados - SGBDs

**Conceitos Principais:**

Um SGBD (Sistema de Gerenciamento de Banco de Dados) é um software que gerencia bancos de dados, permitindo a definição da estrutura, a inserção, a manipulação e o compartilhamento de dados de forma eficiente e segura. As etapas envolvidas são:

- **Definição:** Estabelecer o tipo de dados, estrutura e restrições (constraints) do banco de dados. Define-se o que será armazenado e como.
- **Construção:** Criar o banco de dados fisicamente, armazenando os dados em arquivos. A estrutura definida na etapa anterior é implementada.
- **Manipulação:** Realizar operações como consultas (queries), inserções, atualizações e deleções. As queries são traduzidas para linguagem de máquina pelo SGBD. A manipulação de dados gera transações, ou seja, mudanças no estado do banco de dados, que devem ser consistentes e confiáveis.
- **Compartilhamento:** Permitir o acesso concorrente ao banco de dados por múltiplos usuários ou aplicações, com mecanismos de bloqueio e liberação para garantir a integridade dos dados. O controle de concorrência é fundamental para evitar problemas de consistência.

**Exemplo:  Contexto Universitário**

Para ilustrar, considera-se o contexto de uma universidade.  As entidades envolvidas (alunos, cursos, turmas e pré-requisitos) são modeladas como tabelas relacionadas.  A definição inclui o tipo de dado para cada atributo (nome completo como texto, matrícula como inteiro, etc.).  A construção cria as tabelas no banco de dados. A manipulação permite consultas que, por exemplo, recuperam o histórico acadêmico de um aluno ou a lista de alunos matriculados em determinado curso.  O compartilhamento permite que diferentes departamentos e usuários acessem e manipulem os dados, sempre sob controle para evitar conflitos.  A estrutura de metadados descreve o esquema do banco de dados.

**Metadados:**

Os metadados descrevem o esquema e a estrutura do banco de dados, fornecendo uma descrição concisa dos dados armazenados.  Esta informação é usada pelo SGBD para otimizar consultas e gerenciar o acesso aos dados.

**Curiosidade:**  Existem diferentes tipos de SGBDs, como os relacionais (baseados em tabelas), os NoSQL (mais flexíveis em relação à estrutura de dados) e os de grafo (para representar relacionamentos complexos). A escolha depende das necessidades específicas de cada aplicação.

### Aula 4 - Modelo de Banco de Dados Relacional

**Características do Modelo Relacional:**

O modelo relacional, criado na década de 1970, fundamenta-se na álgebra relacional e utiliza a linguagem SQL.  Suas principais características são:

- **Álgebra Relacional:** Opera com conjuntos de dados, permitindo operações como união, interseção e diferença entre conjuntos de registros.
- **Relações:** Os dados são organizados em relações (tabelas), com linhas representando registros e colunas representando atributos.
- **Transparência:** O modelo esconde a complexidade de armazenamento e acesso, permitindo ao usuário interagir com os dados de forma mais intuitiva.
- **TAD (Tipo Abstrato de Dado):** Permite a abstração de tipos de dados, facilitando a manipulação e a organização das informações.

**Usuários e suas Interações:**

Existem dois tipos principais de usuários em um ambiente de banco de dados relacional:

- **Usuário Convencional:** Interage com o banco de dados utilizando uma linguagem de manipulação de dados (LMD), geralmente uma interface gráfica ou comandos SQL, para recuperar informações.
- **Administrador de Banco de Dados (DBA):** Define a estrutura do banco de dados, as tabelas, os atributos, e as *constraints*, utilizando uma linguagem de definição de dados (LDD), muitas vezes baseada em SQL.

**Funcionamento Interno:**

As operações de manipulação de dados envolvem:

1. **Tradução:** Comandos da LMD (ex: SQL) são traduzidos para uma linguagem de máquina.
2. **Mecanismo de Execução:** O SGBD executa as instruções na linguagem de máquina.
3. **Gerenciador:** Um gerenciador coordena o processo de tradução, execução e o acesso aos metadados e ao esquema para extrair os dados solicitados.

**Cenários e Integração:**

Empresas podem utilizar múltiplos bancos de dados, cada um com função específica.  Integração entre eles pode ser necessária. Abordagens incluem repositórios centralizados (Data Warehouses) ou mediadores (middleware).  Um exemplo de integração seria a combinação de diversas fontes de dados heterogêneas (arquivos XLS, CSV, TXT etc.) usando ferramentas como IPT e Darwin Core Archive para alimentar um sistema, neste caso, um portal de espécies e ocorrências (SiBBr).

**Metadados e Esquema:**

Metadados fornecem uma descrição concisa dos dados contidos no banco de dados, incluindo a estrutura, tipos de dados e restrições.  O esquema define a organização lógica do banco de dados, incluindo as tabelas e seus relacionamentos.

### Aula 5 - SGBDs mais utilizados pelo mercado

Este resumo apresenta os principais Sistemas de Gerenciamento de Banco de Dados (SGBDs) utilizados no mercado, considerando fatores como popularidade, tempo de mercado, robustez, segurança e compatibilidade multiplataforma.

**Panorama Geral:**

A escolha do SGBD ideal depende do contexto e das necessidades específicas de cada projeto.  Existem diversos sistemas disponíveis, cada um com suas forças e fraquezas.  A popularidade de um SGBD não é necessariamente um indicativo de sua adequação a um determinado cenário, embora geralmente reflita maturidade, robustez e adoção por grandes empresas e organizações.

**Principais SGBDs:**

A apresentação lista os seis SGBDs mais populares em 2022, segundo o site [*db-engines.com/en/ranking*](http://db-engines.com/en/ranking):

1. **Oracle:** Um dos pioneiros e líderes de mercado, conhecido por sua robustez e escalabilidade. Amplamente utilizado em grandes corporações e governos.
2. **MySQL:** Um sistema de código aberto muito popular, especialmente em aplicações web, devido à sua facilidade de uso e grande comunidade.
3. **Microsoft SQL Server:** Uma plataforma robusta e abrangente, com forte integração com o ecossistema Microsoft e ampla gama de recursos para aplicações críticas.
4. **PostgreSQL:** Um SGBD de código aberto, conhecido pela sua solidez, conformidade com padrões SQL e extensa gama de recursos avançados. Uma alternativa robusta ao Oracle.
5. **MongoDB:** Um banco de dados NoSQL orientado a documentos, ideal para cenários com dados semiestruturados ou não estruturados, muito utilizado para aplicações com alta demanda e necessidade de escalabilidade.
6. **Redis:** Um banco de dados in-memory, muito veloz e indicado para *caching* e armazenamento de dados em memória RAM, aumentando a performance de aplicações.

**Fatores que Influenciam a Escolha:**

A escolha entre os diferentes SGBDs envolve considerar os seguintes fatores:

- **Popularidade:** A popularidade de um SGBD indica a sua maturidade, a disponibilidade de suporte, a comunidade ativa e a vasta documentação.
- **Tempo de Mercado:** Sistemas mais antigos tendem a ter maior maturidade, estabilidade e documentação.
- **Robustez:** A capacidade do SGBD de lidar com grandes volumes de dados, alta demanda e falhas.
- **Confiabilidade:** A garantia de persistência, integridade e segurança dos dados.
- **Segurança:** Mecanismos de segurança robustos para proteger os dados contra acessos não autorizados.
- **Multiplataforma:** Compatibilidade com diferentes sistemas operacionais.

**Exemplo de Comparação: MySQL e MariaDB:**

MySQL e MariaDB são exemplos de SGBDs que, apesar de suas similaridades, apresentam diferenças importantes.  MariaDB surgiu como um fork do MySQL, mantendo compatibilidade, mas oferecendo uma licença de código aberto mais permissiva.  Uma análise detalhada das características e necessidades do projeto é fundamental para determinar qual deles melhor se adequa.

### Aula 6 - A era dos dados e o futuro da modelagem - Parte 1

**Contexto e Paradigmas:**

O contexto atual de dados é dominado pelo modelo relacional, amplamente utilizado em sistemas corporativos.  Entretanto,  a crescente complexidade e o volume de dados gerados em diversos campos, como pesquisa científica e Big Data, impulsionam a necessidade de novas abordagens.  A apresentação compara quatro paradigmas na evolução da ciência de dados e modelagem:

1. **Primeiro paradigma (pré-1960):** Experimentos empíricos em pequena escala.
2. **Segundo paradigma (1960-1990):** Modelagem teórica e computacional, utilizando simulações.
3. **Terceiro paradigma (1990-2000):** Modelagem computacional, com foco em simulações complexas e análise de dados.
4. **Quarto paradigma (2000-presente):** Modelagem baseada na análise e exploração de grandes volumes de dados heterogêneos, com computação paralela e distribuída.

**O Quarto Paradigma e seus Requisitos:**

O quarto paradigma se caracteriza por lidar com dados de forma mais abrangente e complexa, necessitando de novas tecnologias e metodologias.  Os requisitos incluem:

- **Grande número de tarefas computacionais:** Necessidade de processamento paralelo e distribuído para lidar com grandes volumes de dados.
- **Grande quantidade de dados:** Lidar com conjuntos massivos de dados, muitas vezes gerados em tempo real.
- **Heterogeneidade dos dados:** Capacidade de integrar e processar dados de diversas fontes e formatos.
- **Computação paralela e distribuída:** Utilização de recursos computacionais distribuídos e processamento paralelo para otimizar a performance e a escalabilidade.

**Exemplos:**

Dois exemplos ilustram as características do quarto paradigma:

- **Análise climática:** Para um estudo com resolução espacial de 3km, são necessários 8 petabytes de dados; para uma resolução de 100km, são 8 terabytes. A diferença ilustra a crescente complexidade e volume de dados.
- **Mapeamento de galáxias:** O Dark Energy Survey, um projeto de mapeamento de galáxias, supernovas e padrões, gera 6,6 petabytes de dados *diariamente*, envolvendo 25 instituições e mais de 400 cientistas.

**Requisitos para Modelagem no Quarto Paradigma:**

Para construir modelos eficazes no quarto paradigma, são necessários:

- **Composição:** Capacidade de construir modelos a partir de componentes reutilizáveis.
- **Reutilização:** Facilidade de reaproveitar componentes de modelos existentes.
- **Execução:** Sistemas robustos que garantam a execução eficiente das tarefas computacionais.
- **Análise:** Ferramentas e técnicas para analisar grandes volumes de dados.
- **Reprodutibilidade:** Possibilidade de reproduzir a análise e os resultados em diferentes ambientes.
- **Escalabilidade:** Capacidade de lidar com volumes crescentes de dados e tarefas computacionais.
- **Abstração:** Conceitos e metodologias que permitam lidar com a complexidade dos dados.

**Curiosidade:**  O quarto paradigma em ciência de dados e modelagem é um marco importante na evolução científica, permitindo abordar problemas complexos que antes eram inabordáveis.  A combinação de dados em larga escala e computação avançada revolucionou diversas áreas do conhecimento.

### Aula 7 - A era dos dados e o futuro da modelagem - Parte 2

**Quarto Paradigma: Big Data e HPC**

O quarto paradigma na ciência de dados se caracteriza pela utilização de grandes volumes de dados heterogêneos, computação paralela e distribuída, e recursos em nuvem.  Este paradigma contrasta com os anteriores, que eram mais focados em experimentos empíricos, modelagem teórica e computação sequencial.

**Big Data:**

Big Data se refere a conjuntos de dados de grande volume, velocidade e variedade.  As principais características são:

- **Processamento e Armazenamento Distribuídos:** Processamento paralelo de dados, utilizando múltiplos nós de processamento (clusters), e sistemas de arquivos distribuídos e persistentes. Exemplos de tecnologias incluem Spark e Hadoop.
- **Modelos Paralelos:** Utilização de modelos como MapReduce, Spark, e SGBDs paralelos para processar dados em larga escala.

**High-Performance Computing (HPC):**

A HPC é uma abordagem computacional voltada para problemas complexos, que exigem alto poder de processamento.  Em HPC, as principais características são:

- **Nós de Processamento:** Sistemas de HPC empregam vários nós de processamento operando concorrentemente para otimizar a execução de tarefas computacionais. O Lustre é um exemplo de sistema de arquivos paralelo usado em HPC.
- **Sistema de Arquivos Paralelo sem Persistência:** Os dados são processados em paralelo, sem a necessidade de armazenamento persistente. Isso aumenta a performance, mas exige atenção ao gerenciamento dos dados.
- **Modelos de Programação Paralela:** Utiliza modelos de programação como MPI, OpenMP e OpenCL para otimizar a utilização dos recursos computacionais.
- **Acesso:** Utilizam sistemas de acesso a dados como HDF5 e NetCDF para trabalhar com dados científicos em larga escala.

**Comparação Big Data e HPC:**

Big Data e HPC são complementares, porém distintos.  Big Data enfatiza o armazenamento e processamento persistente de dados em larga escala, enquanto HPC se concentra no processamento paralelo de grandes volumes de dados, sem a necessidade de persistência. A escolha da abordagem depende das necessidades do projeto.

**Curiosidade:** O rápido avanço nas tecnologias de processamento e armazenamento, aliado à crescente disponibilidade de dados, impulsiona a inovação no quarto paradigma.  Novas metodologias e ferramentas estão em constante desenvolvimento, abrindo novas possibilidades para a ciência e a tecnologia.

### Aula 8 - Novo cenário e novas tecnologias - E agora?

**O Novo Cenário:**

A era do Big Data trouxe novos desafios e oportunidades.  O volume, velocidade e variedade de dados aumentaram exponencialmente.  As empresas utilizam cada vez mais dados para tomar decisões estratégicas, tanto em áreas de gerenciamento quanto de marketing.  Essa mudança de paradigma exige novos modelos de SGBDs e novos perfis profissionais.

**Perfis Profissionais:**

Novos papéis surgem no mercado de dados:

- **Engenheiro de Dados:** Focado no design e construção de soluções de dados, extraindo dados de fontes heterogêneas e preparando-os para consumo por cientistas e analistas de dados. Lida com a infraestrutura e o fluxo de dados.
- **Cientista de Dados:** Especializado em modelagem, reconhecimento de padrões e predição, respondendo perguntas sobre o negócio através de técnicas estatísticas e de *machine learning*.
- **Analista de Dados:** Concentra-se na criação de *dashboards*, na apresentação visual de dados e na identificação de *insights* para tomada de decisões.

**Novos Modelos de SGBDs: NoSQL:**

O modelo relacional de banco de dados, embora amplamente utilizado, apresenta limitações para lidar com grandes volumes de dados e diferentes estruturas.  Bancos de dados NoSQL surgiram para atender essas necessidades, oferecendo maior escalabilidade e flexibilidade.  Tipos comuns incluem:

- **Orientado a documentos:** Armazene dados em formato de documentos (JSON). Exemplo: MongoDB.
- **Wide-columns:** Ideal para dados de séries temporais e análise de grandes conjuntos de dados. Exemplo: Cassandra.
- **Key-Value:** Muito performático; utilizado para *caching* e armazenamento de dados em memória RAM. Exemplo: Redis.
- **Grafos:** Representa dados e relacionamentos entre eles através de grafos. Exemplo: Neo4j.
- **Orientado a objetos:** Armazena dados como objetos, facilitando a representação de entidades complexas. Exemplo: db4objects.

**Bancos de Dados na Nuvem:**

A computação em nuvem possibilita o acesso a recursos escaláveis e robustos de banco de dados.  Diversas plataformas, como AWS e Azure, oferecem soluções como serviço (SaaS), permitindo escalar a capacidade conforme a demanda.  Exemplo: Amazon RDS, DynamoDB, Amazon Redshift e Azure BD.

**Curiosidade:**  A escolha entre um modelo relacional e um modelo NoSQL depende de uma cuidadosa análise das necessidades do projeto, considerando o tipo, volume, estrutura e complexidade dos dados, e o contexto de uso.

### Materiais Complementares