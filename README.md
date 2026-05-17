# MoradaSync - Sistema de Gestão Condominial

## 1. Sobre o Projeto

O Sistema de Gestão Condominial é uma aplicação web fullstack desenvolvida como projeto acadêmico da disciplina de Tópicos Especiais, do curso de Análise e Desenvolvimento de Sistemas.

O objetivo do sistema é auxiliar na organização de informações básicas de um condomínio, permitindo o gerenciamento de unidades, moradores, reservas de áreas comuns, ocorrências e funcionários.

O projeto será desenvolvido utilizando arquitetura MVC, banco de dados PostgreSQL, autenticação de usuários, rotas protegidas e interface web com EJS e Bootstrap.

---

## 2. Objetivo

Desenvolver uma aplicação web simples, funcional e organizada para centralizar informações administrativas de um condomínio, facilitando o cadastro, consulta, edição e acompanhamento de dados relacionados à gestão condominial.

---

## 3. Tecnologias Previstas

- Node.js
- Express
- EJS
- HTML
- CSS
- Bootstrap
- PostgreSQL
- Git e GitHub
- ClickUp
- Miro
- Canvas

---

## 4. Arquitetura

O projeto seguirá a arquitetura MVC, separando as responsabilidades em:

- Models: responsáveis pela comunicação com o banco de dados;
- Controllers: responsáveis pelas regras da aplicação;
- Routes: responsáveis pelo mapeamento das rotas;
- Views: responsáveis pelas telas renderizadas com EJS;
- Middlewares: responsáveis por autenticação e proteção de rotas.

---

## 5. Entidades Principais

As entidades previstas para o sistema são:

- Usuários
- Unidades
- Moradores
- Reservas
- Ocorrências
- Funcionários

---

## 6. Integrantes e Responsabilidades

| Integrante | Papel no Grupo | CRUD Principal |
|---|---|---|
| Lucca Felipe | Documentação | Funcionários |
| Matheus Albertini | Banco de Dados | Unidades |
| Abel Piassa | Autenticação | Moradores |
| Emanulle Silva | Front-End | Reservas |
| Adrian Felipe | Back-End | Ocorrências |

---

## 7. Metodologia de Organização

A equipe utilizará Scrum como metodologia de organização do projeto, com apoio das ferramentas ClickUp, Miro e Canvas.

O quadro de tarefas será organizado com as seguintes colunas:

- A Fazer
- Em Desenvolvimento
- Em Revisão
- Concluído

---

## 8. Entregas da N1

A etapa N1 contempla o planejamento do sistema, incluindo:

- Requisitos funcionais;
- Requisitos não funcionais;
- Entidades do sistema;
- Relacionamentos;
- MER/DER;
- Protótipos de telas;
- Matriz de papéis e responsabilidades;
- Backlog inicial.

---

## 9. Status do Projeto

Projeto em fase de planejamento inicial para entrega da N1.

---

# Requisitos Funcionais

Os requisitos funcionais descrevem as funcionalidades que o sistema MoradaSync deverá oferecer aos usuários.  
O sistema será dividido em módulos, contemplando autenticação, gestão de moradores, unidades, reservas, ocorrências, funcionários e funcionalidades gerais.

## Tabela de Requisitos Funcionais do MVP

| Código | Módulo | Requisito Funcional | Prioridade | Perfil/Permissão | Observações |
|---|---|---|---|---|---|
| RF01 | Autenticação e Segurança | O sistema deve permitir login com e-mail e senha. | Alta | Administrador e Funcionário | O usuário deverá informar credenciais válidas para acessar o sistema. |
| RF02 | Autenticação e Segurança | O sistema deve permitir logout do usuário autenticado. | Alta | Administrador e Funcionário | Deve existir um botão de sair para encerrar a sessão. |
| RF03 | Autenticação e Segurança | O sistema deve proteger rotas privadas por meio de autenticação. | Alta | Usuário autenticado | A proteção será feita por middleware, impedindo acesso sem login. |
| RF04 | Autenticação e Segurança | O sistema deve controlar permissões por tipo de usuário. | Alta | Administrador e Funcionário | O perfil Administrador terá acesso completo; o perfil Funcionário terá acesso limitado conforme regras definidas. |
| RF05 | Gestão de Moradores | O sistema deve permitir cadastrar moradores. | Alta | Administrador | O cadastro poderá conter nome, CPF, telefone, e-mail e unidade vinculada. |
| RF06 | Gestão de Moradores | O sistema deve permitir listar moradores cadastrados. | Alta | Administrador e Funcionário | A listagem deverá exibir os dados principais dos moradores. |
| RF07 | Gestão de Moradores | O sistema deve permitir editar dados de moradores. | Alta | Administrador | A edição deve permitir atualizar informações cadastrais. |
| RF08 | Gestão de Moradores | O sistema deve permitir buscar moradores por nome, unidade ou CPF. | Média | Administrador | A busca facilita a localização de registros. |
| RF09 | Gestão de Unidades | O sistema deve permitir cadastrar unidades do condomínio. | Alta | Administrador | O cadastro das unidades será realizado pela administração do condomínio. |
| RF10 | Gestão de Unidades | O sistema deve permitir listar unidades cadastradas. | Alta | Administrador e Funcionário | A listagem deverá exibir número, bloco, tipo e status da unidade. |
| RF11 | Gestão de Unidades | O sistema deve permitir editar unidades. | Alta | Administrador | A edição poderá alterar dados como bloco, número, tipo e status. |
| RF12 | Gestão de Unidades | O sistema deve permitir excluir ou inativar unidades. | Alta | Administrador | Recomenda-se inativação em vez de exclusão definitiva. |
| RF13 | Gestão de Unidades | O sistema deve permitir vincular moradores às unidades. | Alta | Administrador | Uma unidade poderá possuir um ou mais moradores vinculados. |
| RF14 | Reservas de Áreas Comuns | O sistema deve permitir cadastrar reservas de áreas comuns. | Alta | Morador ou Administrador | O morador poderá solicitar reserva de espaços como salão de festas ou churrasqueira. |
| RF15 | Reservas de Áreas Comuns | O sistema deve permitir listar reservas cadastradas. | Alta | Administrador e Funcionário | A administração poderá acompanhar as reservas realizadas. |
| RF16 | Reservas de Áreas Comuns | O sistema deve permitir cancelar reservas. | Alta | Morador ou Administrador | O cancelamento deverá atualizar o status da reserva. |
| RF17 | Reservas de Áreas Comuns | O sistema deve permitir cadastrar áreas comuns disponíveis para reserva. | Alta | Administrador | As áreas comuns podem ser pré-cadastradas na implantação do sistema. |
| RF18 | Reservas de Áreas Comuns | O sistema deve validar conflitos de data e horário ao criar reservas. | Média | Sistema | O sistema deve impedir duas reservas no mesmo espaço, data e horário. |
| RF19 | Gestão de Ocorrências | O sistema deve permitir registrar ocorrências. | Alta | Morador, Funcionário ou Administrador | Ocorrências podem representar manutenção, reclamações ou sugestões. |
| RF20 | Gestão de Ocorrências | O sistema deve permitir listar ocorrências cadastradas. | Alta | Funcionário e Administrador | A listagem ajudará no acompanhamento das solicitações. |
| RF21 | Gestão de Ocorrências | O sistema deve permitir atualizar ocorrências. | Alta | Administrador ou Funcionário | A atualização poderá alterar descrição, status, responsável ou observações. |
| RF22 | Gestão de Ocorrências | O sistema deve permitir finalizar ocorrências. | Alta | Administrador ou Funcionário | A finalização altera o status da ocorrência para resolvida/concluída. |
| RF23 | Gestão de Ocorrências | O sistema deve permitir cadastrar tipos de ocorrência. | Alta | Administrador | Exemplos: manutenção, reclamação, sugestão, limpeza e segurança. |
| RF24 | Gestão de Funcionários | O sistema deve permitir cadastrar funcionários. | Alta | Administrador | O cadastro pode conter nome, CPF, cargo, telefone, e-mail e status. |
| RF25 | Gestão de Funcionários | O sistema deve permitir listar funcionários cadastrados. | Alta | Administrador | A listagem deverá exibir os principais dados dos funcionários. |
| RF26 | Gestão de Funcionários | O sistema deve permitir editar dados de funcionários. | Alta | Administrador | A edição permite atualizar dados cadastrais e cargo. |
| RF27 | Gestão de Funcionários | O sistema deve permitir inativar funcionários. | Alta | Administrador | Recomenda-se inativar em vez de excluir definitivamente. |
| RF28 | Sistema Geral | O sistema deve controlar status de reservas, ocorrências, unidades e usuários. | Alta | Sistema | Os status ajudam no acompanhamento dos registros. |
| RF29 | Sistema Geral | O sistema deve validar campos obrigatórios nos formulários. | Alta | Sistema | Campos essenciais não devem ser enviados vazios. |
| RF30 | Sistema Geral | O sistema deve possuir menu de navegação entre os módulos. | Alta | Usuário autenticado | O menu deve permitir acesso às principais telas do sistema. |
| RF31 | Sistema Geral | O sistema deve permitir visualizar detalhes dos registros cadastrados. | Média | Usuário autenticado | Cada módulo poderá ter uma tela ou botão de detalhes. |
| RF32 | Sistema Geral | O sistema deve armazenar dados em banco de dados persistente. | Alta | Sistema | O banco definido para o projeto será PostgreSQL. |
| RF33 | Sistema Geral | O sistema deve permitir filtrar listagens por status, data ou categoria. | Média | Usuário autenticado | Filtros poderão ser aplicados em reservas, ocorrências e moradores. |

---

## 10. Uso de Inteligência Artificial

A Inteligência Artificial será utilizada como apoio técnico e acadêmico durante o projeto, auxiliando na organização da documentação, revisão de requisitos, explicação de conceitos, apoio na modelagem, revisão de código e preparação para a defesa técnica.

O uso da IA será documentado no arquivo `USO_IA.md`, conforme exigido no projeto.
