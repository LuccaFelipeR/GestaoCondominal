# MoradaSync - Sistema de Gestão Condominial

## 1. Sobre o Projeto

O **MoradaSync** é uma aplicação web fullstack desenvolvida como projeto acadêmico da disciplina de **Tópicos Especiais**, do curso de **Análise e Desenvolvimento de Sistemas**.

O sistema tem como objetivo auxiliar na organização de informações básicas de um condomínio, permitindo o gerenciamento de unidades, moradores, reservas de áreas comuns, ocorrências e funcionários.

O projeto será desenvolvido utilizando **Node.js**, **Express**, **EJS**, **PostgreSQL** e arquitetura **MVC**, contemplando autenticação de usuários, rotas protegidas, banco de dados persistente e interface web com Bootstrap.

---

## 2. Objetivo

Desenvolver uma aplicação web simples, funcional e organizada para centralizar informações administrativas de um condomínio, facilitando o cadastro, consulta, edição e acompanhamento de dados relacionados à gestão condominial.

---

## 3. Problema que o Sistema Resolve

Em muitos condomínios, informações sobre moradores, unidades, reservas e ocorrências são controladas de forma manual, por planilhas ou mensagens informais. Isso pode causar perda de informações, dificuldade de acompanhamento, retrabalho e falta de organização.

O **MoradaSync** busca resolver esse problema oferecendo uma plataforma web para registrar, consultar e gerenciar as principais informações administrativas do condomínio de forma centralizada.

---

## 4. Público-Alvo

O sistema é destinado a administradores, síndicos, funcionários e moradores de condomínios residenciais, permitindo o controle básico das informações internas do condomínio.

---

## 5. Tecnologias Previstas

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

## 6. Arquitetura

O projeto seguirá a arquitetura **MVC**, separando as responsabilidades em camadas:

- **Models:** responsáveis pela comunicação com o banco de dados;
- **Controllers:** responsáveis pelas regras da aplicação;
- **Routes:** responsáveis pelo mapeamento das rotas;
- **Views:** responsáveis pelas telas renderizadas com EJS;
- **Middlewares:** responsáveis por autenticação e proteção de rotas;
- **Public:** responsável por arquivos estáticos como CSS, imagens e scripts.

Estrutura prevista do projeto:

```txt
/projeto
/src
  /models
  /controllers
  /routes
  /views
  /middlewares
  /public
/database
  schema.sql
  seed.sql
README.md
USO_IA.md
package.json
server.js
```

---

## 7. Entidades Principais

As entidades previstas para o sistema são:

- Usuários
- Unidades
- Moradores
- Reservas
- Ocorrências
- Funcionários
- Áreas Comuns
- Tipos de Ocorrência

As entidades principais do CRUD serão:

- Unidades
- Moradores
- Reservas
- Ocorrências
- Funcionários

A entidade **Usuários** será utilizada para autenticação e controle de acesso ao sistema.

---

## 8. Integrantes e Responsabilidades

| Integrante | Papel no Grupo | CRUD Principal |
|---|---|---|
| Lucca Felipe | Documentação | Funcionários |
| Matheus Albertini | Banco de Dados | Unidades |
| Abel Piassa | Autenticação | Moradores |
| Emanulle Silva | Front-End | Reservas |
| Adrian Felipe | Back-End | Ocorrências |

---

## 9. Metodologia de Organização

A equipe utilizará **Scrum** como metodologia de organização do projeto, com apoio das ferramentas **ClickUp**, **Miro** e **Canvas**.

O quadro de tarefas será organizado com as seguintes colunas:

- A Fazer
- Em Desenvolvimento
- Em Revisão
- Concluído

A equipe trabalhará com backlog inicial, divisão de responsabilidades e acompanhamento das atividades durante as etapas do projeto.

---

## 10. Entregas da N1

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

## 11. Status do Projeto

Projeto em fase de planejamento inicial para entrega da N1.

---

## 12. Requisitos Funcionais

Os requisitos funcionais descrevem as funcionalidades que o sistema **MoradaSync** deverá oferecer aos usuários.

O sistema será dividido em módulos, contemplando autenticação, gestão de moradores, unidades, reservas, ocorrências, funcionários e funcionalidades gerais.

### 12.1 Tabela de Requisitos Funcionais do MVP

| Código | Módulo | Requisito Funcional | Prioridade | Perfil/Permissão | Observações |
|---|---|---|---|---|---|
| RF01 | Autenticação e Segurança | O sistema deve permitir login com e-mail e senha. | Alta | Administrador, Funcionário e Morador | O usuário deverá informar credenciais válidas para acessar o sistema. |
| RF02 | Autenticação e Segurança | O sistema deve permitir logout do usuário autenticado. | Alta | Usuário autenticado | Deve existir um botão de sair para encerrar a sessão. |
| RF03 | Autenticação e Segurança | O sistema deve proteger rotas privadas por meio de autenticação. | Alta | Usuário autenticado | A proteção será feita por middleware, impedindo acesso sem login. |
| RF04 | Autenticação e Segurança | O sistema deve controlar permissões por tipo de usuário. | Alta | Administrador, Funcionário e Morador | O perfil Administrador terá acesso completo; os demais perfis terão acesso conforme suas permissões. |
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
| RF22 | Gestão de Ocorrências | O sistema deve permitir finalizar ocorrências. | Alta | Administrador ou Funcionário | A finalização altera o status da ocorrência para resolvida ou concluída. |
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

### 12.2 Requisitos Funcionais para Melhorias Futuras

Algumas funcionalidades foram analisadas pela equipe, mas não farão parte do MVP inicial, pois aumentariam o escopo do projeto e poderiam comprometer a entrega dentro do prazo.

| Código | Módulo | Funcionalidade | Prioridade | Justificativa |
|---|---|---|---|---|
| MF01 | Autenticação e Segurança | Recuperação de senha via e-mail, SMS ou WhatsApp. | Média | Exige integração externa e será considerada em versão futura. |
| MF02 | Gestão de Ocorrências | Anexar imagens às ocorrências. | Média | Pode exigir upload de arquivos e controle de armazenamento. |
| MF03 | Gestão de Ocorrências | Visualizar histórico completo de ocorrências por unidade. | Média | Pode ser implementado após o CRUD principal estar funcionando. |
| MF04 | Gestão de Ocorrências | Definir prioridade para ocorrências. | Média | Funcionalidade útil, mas não essencial para o MVP. |
| MF05 | Controle de Visitantes | Cadastrar visitantes com data e hora de entrada. | Média | Módulo fora do escopo principal da primeira versão. |
| MF06 | Controle de Visitantes | Registrar saída de visitantes. | Média | Depende do módulo de visitantes, que ficará para versão futura. |
| MF07 | Gestão de Veículos | Cadastrar veículos vinculados aos moradores. | Média | Pode ser incluído futuramente como expansão do cadastro de moradores. |
| MF08 | Gestão de Veículos | Listar veículos por unidade ou morador. | Média | Depende do cadastro de veículos. |
| MF09 | Comunicação | Cadastrar avisos e comunicados. | Média | Funcionalidade interessante, mas não essencial para a entrega inicial. |
| MF10 | Comunicação | Registrar entregas e encomendas para moradores. | Média | Módulo adicional, fora do escopo principal. |
| MF11 | Comunicação | Notificar moradores sobre entregas recebidas. | Baixa | Exige sistema de notificação. |
| MF12 | Fornecedores | Cadastrar fornecedores e prestadores de serviço. | Baixa | Pode ser implementado após a conclusão dos CRUDs principais. |
| MF13 | Relatórios | Gerar relatórios de reservas por período. | Baixa | Pode ser incluído se houver tempo após o MVP. |

---

## 13. Requisitos Não Funcionais

Os requisitos não funcionais descrevem características de qualidade, restrições técnicas e padrões esperados para o funcionamento do sistema.

| Código | Categoria | Requisito Não Funcional | Prioridade | Observações |
|---|---|---|---|---|
| RNF01 | Arquitetura | O sistema deve seguir a arquitetura MVC. | Alta | O projeto será organizado em Models, Views, Controllers, Routes e Middlewares. |
| RNF02 | Banco de Dados | O sistema deve utilizar banco de dados PostgreSQL. | Alta | Os dados deverão ser armazenados de forma persistente. |
| RNF03 | Segurança | O sistema deve proteger rotas privadas por autenticação. | Alta | Usuários não autenticados não poderão acessar telas internas. |
| RNF04 | Segurança | As senhas dos usuários devem ser armazenadas de forma segura. | Alta | Recomenda-se uso de criptografia/hash para senhas. |
| RNF05 | Usabilidade | O sistema deve possuir interface simples e navegável. | Alta | A navegação deve ser clara para usuários administradores, funcionários e moradores. |
| RNF06 | Interface | O sistema deve utilizar HTML, CSS, Bootstrap e EJS. | Alta | A interface será renderizada no servidor com EJS. |
| RNF07 | Responsividade | O sistema deve possuir responsividade básica. | Média | As telas devem se adaptar minimamente a diferentes tamanhos de tela. |
| RNF08 | Manutenibilidade | O código deve ser organizado em pastas e arquivos separados por responsabilidade. | Alta | Evita concentração de código em um único arquivo. |
| RNF09 | Versionamento | O projeto deve ser versionado no GitHub. | Alta | Os integrantes deverão realizar commits frequentes e com mensagens claras. |
| RNF10 | Documentação | O projeto deve possuir README.md e USO_IA.md atualizados. | Alta | A documentação deve explicar o sistema, execução, responsabilidades e uso de IA. |
| RNF11 | Execução Local | O sistema deve rodar em ambiente local no dia da apresentação. | Alta | A equipe deve evitar configurações longas durante o pitch. |
| RNF12 | Validação | O sistema deve validar campos obrigatórios nos formulários. | Alta | Campos essenciais não devem ser enviados vazios. |

---

## 14. Relacionamentos do Sistema

O sistema **MoradaSync** possuirá entidades relacionadas entre si, garantindo que o banco de dados represente corretamente o contexto de gestão condominial.

| Entidade Origem | Relacionamento | Entidade Destino | Tipo |
|---|---|---|---|
| Unidade | possui | Moradores | 1:N |
| Morador | pertence a | Unidade | N:1 |
| Morador | realiza | Reservas | 1:N |
| Reserva | pertence a | Morador | N:1 |
| Área Comum | possui | Reservas | 1:N |
| Reserva | pertence a | Área Comum | N:1 |
| Morador | registra | Ocorrências | 1:N |
| Ocorrência | pertence a | Morador | N:1 |
| Funcionário | atende | Ocorrências | 1:N |
| Ocorrência | pode ser atendida por | Funcionário | N:1 |
| Tipo de Ocorrência | classifica | Ocorrências | 1:N |
| Ocorrência | pertence a | Tipo de Ocorrência | N:1 |
| Usuário | acessa | Sistema | Autenticação |

### Descrição dos Relacionamentos

- Uma unidade pode possuir vários moradores.
- Um morador pertence a uma unidade.
- Um morador pode realizar várias reservas.
- Uma reserva pertence a um morador.
- Uma área comum pode possuir várias reservas ao longo do tempo.
- Uma reserva pertence a uma área comum.
- Um morador pode registrar várias ocorrências.
- Uma ocorrência pertence a um morador.
- Um funcionário pode atender várias ocorrências.
- Uma ocorrência pode ser atribuída a um funcionário.
- Um tipo de ocorrência pode classificar várias ocorrências.
- Uma ocorrência pertence a um tipo de ocorrência.
- Um usuário autenticado pode acessar as rotas privadas do sistema.

---

## 15. MER/DER

O Modelo Entidade-Relacionamento e o Diagrama Entidade-Relacionamento serão utilizados para representar as entidades principais do sistema, seus atributos e relacionamentos.

As principais entidades modeladas são:

- Usuários;
- Unidades;
- Moradores;
- Reservas;
- Áreas Comuns;
- Ocorrências;
- Tipos de Ocorrência;
- Funcionários.

O DER será utilizado como base para a criação das tabelas no PostgreSQL.

> Inserir aqui a imagem do MER/DER ou o link para o arquivo no repositório.

Exemplo de inserção da imagem no GitHub:

```md
![DER do Sistema](./docs/der-moradasync.png)
```

---

## 16. Protótipos de Tela

Os protótipos representam a estrutura inicial das principais telas do sistema. Eles serão utilizados como guia para o desenvolvimento das views em EJS.

Telas previstas no protótipo:

| Tela | Descrição |
|---|---|
| Login | Tela de acesso ao sistema com e-mail e senha. |
| Dashboard | Tela inicial após o login, com atalhos para os módulos principais. |
| Listagem de Moradores | Tela para visualizar moradores cadastrados. |
| Cadastro de Moradores | Formulário para cadastrar ou editar moradores. |
| Listagem de Unidades | Tela para visualizar unidades do condomínio. |
| Cadastro de Unidades | Formulário para cadastrar ou editar unidades. |
| Listagem de Reservas | Tela para acompanhar reservas de áreas comuns. |
| Cadastro de Reservas | Formulário para solicitar ou registrar reservas. |
| Listagem de Ocorrências | Tela para acompanhar ocorrências registradas. |
| Cadastro de Ocorrências | Formulário para registrar ocorrências. |
| Listagem de Funcionários | Tela para visualizar funcionários cadastrados. |
| Cadastro de Funcionários | Formulário para cadastrar ou editar funcionários. |

> Inserir aqui imagens dos protótipos ou links para os protótipos no Miro/Canvas.

---

## 17. Matriz de Papéis e Responsabilidades

| Integrante | Papel no Grupo | CRUD Principal | Entregáveis Principais | Apoio da IA |
|---|---|---|---|---|
| Lucca Felipe | Documentação | Funcionários | README.md, USO_IA.md, documentação da N1 e CRUD de Funcionários | Organização da documentação e revisão textual |
| Matheus Albertini | Banco de Dados | Unidades | DER, scripts SQL, modelagem e CRUD de Unidades | Apoio na modelagem e revisão dos relacionamentos |
| Abel Piassa | Autenticação | Moradores | Login, logout, middleware de autenticação e CRUD de Moradores | Explicação de autenticação e revisão de segurança |
| Emanulle Silva | Front-End | Reservas | Protótipos, telas EJS, Bootstrap e CRUD de Reservas | Sugestões de interface e organização das telas |
| Adrian Felipe | Back-End | Ocorrências | Rotas, controllers, models e CRUD de Ocorrências | Revisão de controllers, rotas e regras de negócio |

A responsabilidade individual não impede colaboração entre os integrantes. No entanto, cada aluno deverá compreender e defender tecnicamente o CRUD pelo qual ficou responsável.

---

## 18. Backlog Inicial

O backlog inicial foi organizado com base nas entregas da N1 e nas próximas etapas do projeto. A equipe utilizará Scrum com apoio do ClickUp, mantendo as tarefas organizadas nas colunas: **A Fazer**, **Em Desenvolvimento**, **Em Revisão** e **Concluído**.

| Código | Tarefa | Responsável | Prioridade | Status |
|---|---|---|---|---|
| BK01 | Definir nome do projeto | Equipe | Alta | Concluído |
| BK02 | Criar README.md inicial | Lucca Felipe | Alta | Concluído |
| BK03 | Criar arquivo USO_IA.md | Lucca Felipe | Alta | Em Desenvolvimento |
| BK04 | Definir requisitos funcionais | Equipe | Alta | Em Revisão |
| BK05 | Definir requisitos não funcionais | Equipe | Alta | A Fazer |
| BK06 | Revisar entidades do sistema | Matheus Albertini | Alta | Em Desenvolvimento |
| BK07 | Finalizar MER/DER | Matheus Albertini | Alta | Em Desenvolvimento |
| BK08 | Definir relacionamentos entre entidades | Matheus Albertini | Alta | Em Revisão |
| BK09 | Criar protótipos das telas principais | Emanulle Silva | Alta | A Fazer |
| BK10 | Planejar autenticação e perfis de usuário | Abel Piassa | Alta | A Fazer |
| BK11 | Planejar estrutura de rotas e controllers | Adrian Felipe | Alta | A Fazer |
| BK12 | Revisar matriz de papéis e responsabilidades | Lucca Felipe | Alta | Em Revisão |
| BK13 | Organizar quadro Scrum no ClickUp | Equipe | Alta | A Fazer |
| BK14 | Revisar documentação completa da N1 | Equipe | Alta | A Fazer |
| BK15 | Preparar entrega da N1 no Blackboard | Equipe | Alta | A Fazer |

---

## 19. Organização Scrum

A equipe utilizará Scrum para organizar o desenvolvimento do projeto em ciclos de trabalho.

### Sprint 1 - Planejamento N1

Objetivo: organizar documentação, requisitos, entidades, relacionamentos, DER, protótipos, matriz de papéis e backlog inicial.

### Sprint 2 - Estrutura Inicial

Objetivo: criar o projeto Node.js, configurar Express, EJS, estrutura MVC, conexão com PostgreSQL e repositório GitHub.

### Sprint 3 - Backend e Banco de Dados

Objetivo: criar models, controllers, rotas e integração com o banco de dados para os CRUDs principais.

### Sprint 4 - Interface, Testes e Defesa

Objetivo: finalizar views, testar funcionalidades, revisar documentação, preparar README, USO_IA.md, pitch e defesa técnica.

---

## 20. Uso de Inteligência Artificial

A Inteligência Artificial será utilizada como apoio técnico e acadêmico durante o projeto, auxiliando na organização da documentação, revisão de requisitos, explicação de conceitos, apoio na modelagem, revisão de código e preparação para a defesa técnica.

O uso da IA será documentado no arquivo `USO_IA.md`, conforme exigido no projeto.

A equipe utilizará a IA de forma responsável, mantendo a autoria, revisão e compreensão técnica dos integrantes.

---

## 21. Critérios de Escopo do MVP

Para garantir que o projeto seja viável dentro do prazo, a equipe optou por desenvolver um MVP com as funcionalidades essenciais.

O MVP contempla:

- Login e logout;
- Proteção de rotas;
- Controle básico de permissões;
- CRUD de unidades;
- CRUD de moradores;
- CRUD de reservas;
- CRUD de ocorrências;
- CRUD de funcionários;
- Relacionamentos reais no banco de dados;
- Interface com EJS e Bootstrap;
- Validação mínima de formulários;
- Documentação técnica no GitHub.

Funcionalidades mais complexas, como notificações, recuperação de senha, anexos, visitantes, veículos, encomendas e relatórios avançados, serão consideradas melhorias futuras.

---

## 22. Considerações Finais

O **MoradaSync** será desenvolvido como um sistema acadêmico de Gestão Condominial, com foco em organização, simplicidade, funcionamento local e clareza técnica.

A proposta busca atender aos critérios definidos para o projeto, incluindo arquitetura MVC, banco de dados persistente, autenticação, rotas protegidas, CRUDs completos proporcionais à quantidade de integrantes, documentação, uso responsável de IA e gestão ágil.

A equipe manterá o projeto versionado no GitHub, com commits frequentes e documentação atualizada ao longo do desenvolvimento.
