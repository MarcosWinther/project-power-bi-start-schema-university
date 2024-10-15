# 🌟 Star Schema - Modelo de Dados para Universidade 🌟

Bem-vindo ao **Star Schema da Universidade**! Aqui, você encontrará uma visão simplificada e poderosa para organizar e analisar os dados de uma instituição de ensino, modelada em um diagrama Star Schema. 

Este diagrama foi implementado com base em um **Diagrama Entidade-Relacionamento (ER)** original, com algumas simplificações, como a remoção de relacionamentos muitos para muitos, para trazer mais simplicidade à gestão dos dados universitários.

Este desafio de projeto foi proposto no curso **Dashboard de Vendas com Power BI utilizando Star Schema** pela professora [Juliana Mascarenhas](https://www.linkedin.com/in/juliana-mascarenhas-ds/) no Bootcamp da [NTT DATA](https://www.linkedin.com/company/ntt-data-europe-latam/posts/?feedView=all) - Engenharia de Dados com Python, disponível na plataforma da [DIO](https://www.dio.me/).

> 🎨 **Nota**: O diagrama foi elaborado utilizando o [Lucidchart](https://www.lucidchart.com), uma ferramenta amigável para criação de diagramas.

<br>

## 📊 Visão Geral do Modelo

<p align="center">
   <img src="./diagramas/diagrama star schema/diagrama_star_schema_universidade.png"/>
</p>

Nosso **Star Schema** organiza as informações da universidade através de:
- **Uma tabela de fatos**: onde são registrados os principais eventos e transações;
- **Tabelas de dimensões**: que detalham as entidades chave da universidade, como alunos, professores, departamentos, cursos, entre outras.  
Essas dimensões se relacionam **somente com a tabela de fatos**, sem vínculos diretos entre si, respeitando a estrutura tradicional de um Star Schema.

<br>

## 🏫 Tabelas de Dimensão

### 1. **d_aluno** 👨‍🎓
**O que armazena**: Dados dos alunos.
- **idAluno**: Identificador único de cada aluno;
- **nome**;
- **sobrenome**.
  
### 2. **d_professor** 👩‍🏫
**O que armazena**: Informações sobre os professores.
- **id_professor**: Identificador único de cada professor.
- **nomeProfessor**;
- **sobrenomeProfessor**;
- **titulação**.

### 3. **d_departamento** 🏢
**O que armazena**: Dados dos departamentos.
- **idDepartamento**: Identificador único do departamento.
- **nomeDepartamento**;
- **localização**.

### 4. **d_curso** 🎓
**O que armazena**: Detalhes dos cursos oferecidos.
- **idCurso**: Identificador único do curso.
- **nomeCurso**.

### 5. **d_disciplina** 📘
**O que armazena**: Informações sobre as disciplinas.
- **idDisciplina**: Identificador da disciplina.
- **nomeDisciplina**;
- **cargaHorária**.

### 6. **d_matricula** 📝
**O que armazena**: Matrículas dos alunos nas disciplinas.
- **nr_matricula**;
- **data**.

### 7. **d_pre_requisitos** 📜
**O que armazena**: Pré-requisitos das disciplinas.
- **idPreRequisitos**: Identificador dos pré-requisitos;
- **requisitos**.

<br>

## 🔥 Tabela de Fatos: **f_universidade**

A tabela de fatos **f_universidade** centraliza as principais transações e eventos da universidade. Todas as dimensões se conectam **somente a esta tabela**, sem qualquer relacionamento direto entre as tabelas de dimensões:

- **idUniversidade**: Identificador único da universidade.
- **idAluno**: Relaciona-se com a dimensão `d_aluno`;
- **idProfessor**: Relaciona-se com a dimensão `d_professor`;
- **idDepartamento**: Relaciona-se com a dimensão `d_departamento`;
- **idCurso**: Relaciona-se com a dimensão `d_curso`;
- **idDisciplina**: Relaciona-se com a dimensão `d_disciplina`;
- **nrMatricula**: Relaciona-se com a dimensão `d_matricula`;
- **idPreRequisitos**: Relaciona-se com a dimensão `d_pre_requisitos`.

<br>

## 🔗 Relacionamentos

No modelo Star Schema, a tabela de fatos `f_universidade` é o **ponto central** que se conecta a todas as dimensões. Não há relacionamentos entre as dimensões, apenas com a tabela de fatos:

- `idAluno` → `d_aluno`
- `idProfessor` → `d_professor`
- `idDepartamento` → `d_departamento`
- `idCurso` → `d_curso`
- `idDisciplina` → `d_disciplina`
- `nrMatricula` → `d_matricula`
- `idPreRequsitos` → `d_pre_requisitos`

<br>

## 💡 Exemplos de Uso

O modelo de dados permite fazer várias consultas úteis e gerar insights poderosos:

- Quantos **alunos estão matriculados** em cada curso? 👨‍🎓
- Quantos **professores** existem por departamento? 👩‍🏫
- Qual a **carga horária** total por disciplina? 📘
- Quem são os **alunos matriculados** em cada disciplina? 📝
- Quais são os **pré-requisitos** de cada disciplina? 📜

<br>

## 🚀 Benefícios

- **Simplicidade**: A estrutura do Star Schema é de fácil entendimento e manutenção, ideal para consultas rápidas.
- **Eficiência**: Com as tabelas de fatos e dimensões bem organizadas, as consultas são rápidas e eficientes, mesmo em grandes volumes de dados.
- **Agregação**: Capacidade de sumarizar dados facilmente e gerar relatórios detalhados ou agregados.

<br>

## ⚠️ Limitações

- **Flexibilidade**: Embora fácil de consultar, adicionar novas dimensões ou modificar a estrutura pode ser um desafio.
- **Redundância**: Alguns dados podem ser duplicados entre as tabelas de dimensão, aumentando o espaço de armazenamento.

<br>

## 📌 Observações Finais

Este Star Schema foi projetado como um exemplo para modelar os dados de uma universidade, com base em um **Diagrama Entidade-Relacionamento (ER)** original. 

<p align="center">
   <img src="./diagramas/diagrama ER/diagrama_relacional_universidade.PNG" />
</p>

Dependendo das necessidades específicas da instituição, podem ser necessárias adaptações. Ao implementar este modelo, garanta que o sistema de gerenciamento de banco de dados (SGBD) escolhido seja otimizado para lidar com grandes volumes de dados e consultas agregadas.

<br>

## 👨‍💻 Expert

<p>
    <img 
      align=left 
      margin=10 
      width=80 
      src="https://avatars.githubusercontent.com/u/44624583?v=4"
    />
    <p>&nbsp&nbsp&nbspMarcos Winther<br>
    &nbsp&nbsp&nbsp
    <a href="https://github.com/MarcosWinther">
    GitHub</a>&nbsp;|&nbsp;
    <a href="https://www.linkedin.com/in/marcoswinthersilva/">LinkedIn</a>
    </p>
</p>
<br/><br/>

---

⌨️ com 💜 por [Marcos Winther](https://github.com/MarcosWinther)

