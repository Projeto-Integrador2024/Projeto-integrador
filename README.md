# Documentação do Projeto: Sistema de Cadastro e Consulta de Pessoas na Universidade

## Índice
* [1. Integrantes](#integrantes)
* [2. Introdução](#introdução)
* [3. Descrição Geral do Projeto](#descrição-geral-do-projeto)
* [4. Objetivo do Projeto](#objetivo-do-projeto)
* [5. Diagramas de Modelagem e Classes](#diagramas-de-modelagem-e-classes)
* [6. Descrição das Classes](#descrição-das-classes)
* [7. Diagrama de Entidade-Relacionamento (DER)](#diagrama-de-entidade-relacionamento-der)
* [8. Modelo Entidade-Relacionamento (MER)](#modelo-entidade-relacionamento-mer)
* [9. Detalhamento do MER](#detalhamento-do-mer)
* [10. Protótipos](#protótipos)
* [11. Descrição das Telas](#descrição-das-telas)
* [12. Conclusão](#conclusão)

<br><br>

## Integrantes
| Nome | Github | Responsabilidade |
| ---| ---| ---|
|André Luiz|https://github.com/AndreLFernandesDev|Organização da Documentação|
|Felippe Dezzoti|https://github.com/FelippeDezzotti|Organização e gestão do repositório git|
|Luciano Antônio|https://github.com/Lucianosillva|Telas do sistema|
|Rodrigo Oliveira|https://github.com/rodrigo730|Organização da Documentação|
|José Gabriel|https://github.com/cl0uD-C1SC0|Organização da Documentação|
|Ronaldo Oliveira|:x:|Envio do trabalho|

## Introdução
<p>
Este documento descreve o projeto de desenvolvimento de um sistema para cadastro e
consulta de diferentes tipos de pessoas em uma grande universidade. O sistema abrange
Pessoa Física, Pessoa Jurídica, Professores, Fornecedores e Alunos. A documentação
inclui diagramas de modelagem, protótipos e uma descrição geral do projeto.
</p>

<br><br>

## Descrição Geral do Projeto
<p>
O projeto visa a criação de um sistema que permita o cadastro, consulta e gerenciamento
de diferentes tipos de pessoas relacionadas à universidade. O sistema será utilizado para
manter registros organizados e acessíveis, facilitando a administração e operação das
atividades da universidade.
</p>

<br><br>

## Objetivo do Projeto
<p>
O objetivo principal do projeto é desenvolver uma plataforma integrada que:
<li>Permita o cadastro de pessoas físicas e jurídicas</li>
<li>Mantenha registros detalhados de professores, fornecedores e alunos</li>
<li>Facilite a consulta e atualização dos dados cadastrados</li>
<li> Garanta a segurança e integridade das informações armazenadas.</li>
</p>

## Diagramas de Modelagem e Classes
<h3>
O diagrama de classes detalha a estrutura e os relacionamentos entre as entidades do
sistema.
</h3>

<br>

## Descrição das Classes 

* Pessoa
    * Atributos: id, nome, dataNascimento, endereço, telefone, email
    * Métodos: cadastrar(), consultar(), atualizar(), deletar()
* PessoaFisica (herda de Pessoa) <br>
    * Atributos: cpf
* PessoaJuridica (herda de Pessoa) <br>
    * Atributos: cnpj, razaoSocial
* Professor (herda de PessoaFisica) <br>
    * Atributos: matricula, departamento
    * Métodos: atribuirTurma(), consultarTurma()
* Aluno (herda de PessoaFisica) <br>
    * Atributos: matricula, curso
    * Métodos: matricular(), consultarNotas()
* Fornecedor (herda de PessoaJuridica) <br>
    * Atributos: produtos, servicos
    * Métodos: cadastrarProdutos(), consultarProduto()

<br><br><br>

## Diagrama de Entidade-Relacionamento (DER)
<p>O DER descreve a modelagem lógica do banco de dados, mostrando as entidades,
atributos e os relacionamentos entre eles.</p> <br>

<p>Descrição das Entidades e Relacionamentos</p> 

* Pessoa (id, nome, dataNascimento, endereco, telefone, email)
    * Relacionamentos:
        * PessoaFisica
        * PessoaJuridica 

* PessoaFisica (id, cpf) <br>
    * Relacionamento: 1:1 com Pessoa

* PessoaJuridica (id, cnpj, razaoSocial) <br>
    * Relacionamento: 1:1 com Pessoa 

* Professor (id, matricula, departamento) <br>
    * Relacionamento: 1:1 com PessoaFisica 

* Aluno (id, matricula, curso) <br>
    * Relacionamento: 1:1 com PessoaFisica 

* Fornecedor (id, produtos, servicos) <br>
    * Relacionamento: 1:1 com PessoaJuridica 


## Modelo Entidade-Relacionamento (MER) 
<p>O Modelo Entidade-Relacionamento (MER) é utilizado para representar a estrutura lógica
do banco de dados do sistema de cadastro e consulta de pessoas na universidade. Este
modelo descreve as entidades, seus atributos e os relacionamentos entre elas.</p> <br>

<p>Entidades e Atributos</p>

1. Pessoa
    * id (PK): Identificador único da pessoa.
    * nome: Nome da pessoa.
    * dataNascimento: Data de nascimento da pessoa.
    * endereco: Endereço da pessoa.
    * telefone: Telefone de contato da pessoa.
    * email: Email da pessoa.

<br>

2. PessoaFisica
    * id (PK, FK): Identificador único da pessoa física (herda de Pessoa).
    * cpf: CPF da pessoa física.

<br>

3. PessoaJuridica
    * id (PK, FK): Identificador único da pessoa jurídica (herda de Pessoa).
    * cnpj: CNPJ da pessoa jurídica.
    * razaoSocial: Razão social da pessoa jurídica.

<br>

4. Professor
    * id (PK, FK): Identificador único do professor (herda de PessoaFisica).
    * matricula: Matrícula do professor.
    * departamento: Departamento do professor.

<br>

5. Aluno
    * id (PK, FK): Identificador único do aluno (herda de PessoaFisica).
    * matricula: Matrícula do aluno.
    * curso: Curso do aluno.

<br>

6. Fornecedor
    * id (PK, FK): Identificador único do fornecedor (herda de PessoaJuridica).
    * produtos: Lista de produtos fornecidos.
    * servicos: Lista de serviços fornecidos.

<h2>Relacionamentos</h2>

    *Pessoa 1:1 PessoaFisica: Uma pessoa pode ser uma pessoa física.
    Pessoa 1:1 PessoaJuridica: Uma pessoa pode ser uma pessoa jurídica.
    PessoaFisica 1:1 Professor: Uma pessoa física pode ser um professor.
    PessoaFisica 1:1 Aluno: Uma pessoa física pode ser um aluno.
    PessoaJuridica 1:1 Fornecedor: Uma pessoa jurídica pode ser um fornecedor.

## Detalhamento do MER 

* Entidade: Pessoa
    * id: PK, INT, Auto Increment
    * nome: VARCHAR(255)
    * dataNascimento: DATE
    * endereco: VARCHAR(255)
    * telefone: VARCHAR(20)
    * email: VARCHAR(255)

* Entidade: PessoaFisica
    * id: PK, FK, INT (herda de Pessoa)
    * cpf: VARCHAR(14)

* Entidade: PessoaJuridica
    * id: PK, FK, INT (herda de Pessoa)
    * cnpj: VARCHAR(18)
    * razaoSocial: VARCHAR(255)

* Entidade: Professor
    * id: PK, FK, INT (herda de PessoaFisica)
    * matricula: VARCHAR(20)
    * departamento: VARCHAR(255)

* Entidade: Aluno
    * id: PK, FK, INT (herda de PessoaFisica)
    * matricula: VARCHAR(20)
    * curso: VARCHAR(255)

* Entidade: Fornecedor
    * id: PK, FK, INT (herda de PessoaJuridica)
    * produtos: TEXT
    * servicos: TEXT


## Protótipos

<p>Protótipo da Interface de Usuário</p>

* Tela de Login
    > Tela inicial onde os usuários inserem suas credenciais para acessar o sistema.

* Tela de Cadastro
    > Interface para cadastrar novas pessoas (físicas ou jurídicas) no sistema, incluindo campos para informações básicas e específicas conforme o tipo de pessoa.

* Tela de Consulta
    > Interface para busca e visualização dos registros cadastrados no sistema. Permite filtrar por tipo de pessoa e outros critérios.

## Descrição das Telas

* Tela de Login
    > Descrição: Tela inicial onde os usuários inserem suas credenciais para acessar o sistema.
    *  Campos:
        * Email
        * Senha
    * Botões:
        * Entrar
        * Esqueci minha senha

* Tela de Cadastro
    > Descrição: Interface para cadastrar novas pessoas (físicas ou jurídicas) no sistema, incluindo campos para informações básicas e específicas conforme o tipo de pessoa.
    * Campos Comuns:
        * Nome
        * Data de Nascimento
        * Endereço
        * Telefone
        * Email
    * Campos para Pessoa Física:
        * CPF
    * Campos para Pessoa Jurídica:
        * CNPJ
        * Razão Social
    * Campos Adicionais para Professor:
        * Matrícula
        * Departamento
    * Campos Adicionais para Aluno:
        * Matrícula
        * Curso
    * Campos Adicionais para Fornecedor:
        * Produtos
        * Serviços
    * Botões:
        * Salvar
        * Limpar
        * Cancelar

* Tela de Consulta
    > Descrição: Interface para busca e visualização dos registros cadastrados no sistema. Permite filtrar por tipo de pessoa e outros critérios.
    * Campos de Filtro:
        * Tipo de Pessoa (Pessoa Física, Pessoa Jurídica, Professor, Aluno,
        Fornecedor)
        * Nome
        * CPF/CNPJ
        * Curso (para Alunos)
        * Departamento (para Professores)
    * Resultados da Consulta:
        * Lista de registros correspondentes aos filtros aplicados, exibindo informações
        resumidas (Nome, Tipo de Pessoa, etc.)
    * Botões:
        * Buscar
        * Limpar Filtros
        * Detalhes (para cada registro)
        * Editar (para cada registro)
        * Deletar (para cada registro)

## Conclusão
<p>O sistema de cadastro e consulta de pessoas na universidade visa melhorar a gestão e
organização dos dados de alunos, professores, fornecedores e demais pessoas físicas e
jurídicas relacionadas à instituição. Com uma estrutura bem definida e interfaces intuitivas,
espera-se que o sistema facilite o trabalho administrativo e contribua para a eficiência das
operações universitárias.
Esta documentação deve servir como guia para todos os membros da equipe durante o
desenvolvimento do projeto, garantindo que todos os requisitos e especificações sejam
atendidos conforme planejado</p>