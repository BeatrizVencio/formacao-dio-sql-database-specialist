# Modelagem de Dados para Banco de Dados

### Aula 1 - Introdução à Modelagem de dados - Parte 1

**O que é Modelagem?**

Modelagem de dados é o processo de descrever e representar as informações que serão utilizadas em uma aplicação.  Seu objetivo é fornecer uma representação visual e abstrata do sistema, permitindo compreensão do todo e de suas partes, e simplificando o desenvolvimento de programas e a construção de um banco de dados.  Existem diferentes tipos de modelagem, incluindo:

- Modelagem de Software
- Modelagem de Dados
    - Conceitual
    - Computacional
    - Matemática

**Instâncias:**

As instâncias representam os objetos ou elementos que fazem parte do modelo.  Uma instância é uma ocorrência específica de uma entidade.  Um exemplo de instância são os periódicos, que são representados pelo nome e o ISSN.

**Multiplicidade:**

A multiplicidade define a relação entre entidades.  Indica o número de ocorrências de uma entidade que podem estar relacionadas a uma ocorrência de outra entidade.  Em um diagrama de entidade-relacionamento, a multiplicidade é representada pela notação (1,N).  Exemplo: Um editor pode publicar vários periódicos, e um periódico é publicado por um único editor.

**Chaves e *Constraints*:**

Chaves e *constraints* garantem a integridade e consistência dos dados.

- **Chave Primária:** Identifica unicamente cada registro em uma tabela.
- **Chave Estrangeira (*Foreign Key*):** Cria o relacionamento entre tabelas, referenciando a chave primária de outra tabela.
- ***Constraints*:** Restrições que garantem a qualidade dos dados, como, por exemplo, restrições de tipo de dados, restrições de valores nulos e restrições de unicidade.

**Exemplo:**

Considere um banco de dados que armazena informações sobre autores e periódicos.  A tabela "Autores" tem uma coluna "ID_Autor" como chave primária.  A tabela "Periódicos" tem colunas "ID_Periódico", "Nome" e "ID_Autor".   "ID_Autor" é uma chave estrangeira em "Periódicos", referenciando a chave primária "ID_Autor" na tabela "Autores", garantindo que cada periódico esteja associado a um autor existente no banco de dados.

| Conceito | Descrição | Exemplo |
| --- | --- | --- |
| Instâncias | Ocorrências específicas de uma entidade | Um periódico específico (ex: "Nature") |
| Multiplicidade | Relação entre entidades (1:1, 1:N, N:M) | Um editor publica vários periódicos (1:N) |
| Chave Primária | Atributo único que identifica cada registro em uma tabela | ID_Autor na tabela "Autores" |
| Chave Estrangeira | Atributo que referencia a chave primária de outra tabela, criando relacionamentos | ID_Autor na tabela "Periódicos" |
| *Constraints* | Regras que garantem a integridade e consistência dos dados | Tipo de dados (ex: inteiro, texto), NOT NULL |

**Curiosidade:**  O modelo entidade-relacionamento (ER) é uma ferramenta visual muito utilizada para o design de bancos de dados relacionais, permitindo representar entidades, atributos e relacionamentos de forma clara e concisa.

### Aula 2 - Introdução à Modelagem de dados - Parte 2

**Níveis de Abstração:**

A modelagem de dados pode ser realizada em diferentes níveis de abstração:

- **Conceitual (Alto Nível):** Foca na descrição dos dados e seus relacionamentos, independente da implementação. É uma representação abstrata do mini-mundo. Utiliza diagramas como Entidade-Relacionamento e UML. Exemplo: Diagrama que mostra as entidades "Periódicos", "Autores" e "Editores" e os relacionamentos entre elas.
- **Físico (Baixo Nível):** Detalha a implementação física do modelo, definindo as tabelas, os atributos, os tipos de dados e as chaves. Especifica o esquema do banco de dados. Exemplo: Scripts SQL que criam as tabelas "Periódicos", "Autores" e "Editores" e os relacionamentos entre elas.

**Modelo Conceitual:**

O modelo conceitual é uma representação abstrata que serve para descrever o que será armazenado e como os dados estão relacionados, independente de como os dados serão implementados fisicamente.  Objetivo: Entendimento do contexto do mini-mundo. Exemplo: Entidade-Relacionamento (ER) mostra entidades e relacionamentos, mas não os detalhes da implementação.

**Modelo Físico:**

O modelo físico define a implementação física da estrutura do banco de dados.   Esse modelo é uma tradução do modelo conceitual, levando em consideração as especificidades do SGBD e as restrições do sistema.  Objetivo: Persistência dos dados. Exemplo: Criar tabelas, atributos e suas propriedades com comandos SQL.

**Do Conceitual para o Físico:**

A transição do modelo conceitual para o modelo físico é feita através da escolha de um SGBD e da definição do esquema do banco de dados.  Para o modelo relacional, este processo envolve definir as tabelas e seus relacionamentos (utilizando chaves estrangeiras).  É importante seguir boas práticas para garantir a eficiência, a escalabilidade e a integridade do banco de dados.

| Nível de Abstração | Descrição | Exemplo |
| --- | --- | --- |
| Conceitual | Alto nível, independente da implementação | Diagrama Entidade-Relacionamento (ER) |
| Físico | Baixo nível, detalha a implementação física no banco de dados | Scripts SQL para criação das tabelas e relacionamentos |

**Curiosidade:**  A modelagem conceitual é um processo iterativo e colaborativo que envolve especialistas em negócio, desenvolvedores e administradores de banco de dados para garantir que o modelo represente adequadamente as necessidades da organização.