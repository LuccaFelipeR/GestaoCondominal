# CondoSys — Sistema Web Fullstack de Gestão Condominial

Projeto acadêmico desenvolvido para a disciplina **Tópicos Especiais**, do curso de **Análise e Desenvolvimento de Sistemas — ADS 2026/1**.

> **Status atual:** Planejamento concluído — Entrega 1 (N1)  
> **Versão da documentação:** V1.0.1 — 20/05/2026  
> **Repositório:** https://github.com/LuccaFelipeR/GestaoCondominal

---

## 1. Visão Geral

O **CondoSys** é uma aplicação web fullstack voltada à gestão de condomínios residenciais.

O objetivo do sistema é centralizar o controle de:

- moradores;
- unidades;
- reservas de áreas comuns;
- ocorrências;
- funcionários;
- usuários autenticados.

A proposta busca substituir controles manuais feitos em planilhas, mensagens soltas ou cadernos administrativos, oferecendo uma solução simples, funcional e adequada ao escopo acadêmico da disciplina.

---

## 2. Objetivo do Sistema

Desenvolver uma plataforma web fullstack em arquitetura **MVC**, com autenticação, rotas protegidas e banco de dados persistente, para auxiliar a administração de condomínios no controle de moradores, unidades, reservas, ocorrências e funcionários.

### Objetivos específicos

- Permitir login, logout e acesso protegido às telas internas do sistema.
- Cadastrar, listar, editar e inativar moradores vinculados às unidades.
- Cadastrar, listar, editar e inativar unidades do condomínio.
- Registrar reservas de áreas comuns vinculadas ao morador responsável.
- Impedir reservas duplicadas para a mesma área, data e horário.
- Controlar ocorrências com prioridade, status e funcionário responsável.
- Cadastrar e manter funcionários do condomínio.
- Exibir um dashboard simples com indicadores administrativos.
- Validar campos obrigatórios nos formulários.
- Manter o projeto documentado no GitHub.

---

## 3. Tecnologias Utilizadas

| Área | Tecnologia |
|---|---|
| Back-end | Node.js, Express |
| Front-end | EJS, HTML, CSS, Bootstrap |
| Banco de dados | PostgreSQL |
| Autenticação | bcrypt, express-session |
| Arquitetura | MVC |
| Versionamento | Git e GitHub |
| Gestão ágil | Kanban |
| Testes manuais | Navegador, Postman ou Insomnia |
| Apoio técnico | Inteligência Artificial documentada em `USO_IA.md` |

---

## 4. Funcionalidades Planejadas

### Autenticação

- Login com e-mail e senha.
- Logout.
- Sessão de usuário.
- Proteção de rotas privadas por middleware.
- Visualização de perfil e permissões.

### Moradores

- Cadastro de moradores.
- Listagem de moradores.
- Edição de dados.
- Inativação lógica.
- Vínculo com unidade.

### Unidades

- Cadastro de unidades.
- Listagem de unidades.
- Edição de bloco, número, andar e status.
- Inativação de unidade.
- Relacionamento com moradores.

### Reservas

- Cadastro de reservas de áreas comuns.
- Listagem de reservas.
- Edição ou cancelamento.
- Vínculo com morador.
- Validação para impedir conflito de área, data e horário.

### Ocorrências

- Cadastro de ocorrências.
- Listagem de ocorrências.
- Edição e finalização.
- Definição de prioridade.
- Definição de status.
- Vínculo com morador e funcionário responsável.

### Funcionários

- Cadastro de funcionários.
- Listagem de funcionários.
- Edição de dados.
- Inativação.
- Vínculo opcional com usuário do sistema.

### Dashboard

- Total de moradores.
- Total de unidades.
- Reservas previstas.
- Ocorrências abertas.

---

## 5. Arquitetura MVC

O projeto será organizado seguindo o padrão **Model-View-Controller (MVC)**.

### Fluxo básico

1. O usuário acessa uma rota pelo navegador.
2. A rota direciona a requisição para um controller.
3. O controller executa a regra de aplicação.
4. O model realiza operações no banco de dados.
5. A view EJS renderiza a resposta para o usuário.

### Estrutura prevista

```text
condosys/
├── src/
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── dashboardController.js
│   │   ├── moradorController.js
│   │   ├── unidadeController.js
│   │   ├── reservaController.js
│   │   ├── ocorrenciaController.js
│   │   └── funcionarioController.js
│   ├── models/
│   │   ├── usuarioModel.js
│   │   ├── moradorModel.js
│   │   ├── unidadeModel.js
│   │   ├── reservaModel.js
│   │   ├── ocorrenciaModel.js
│   │   └── funcionarioModel.js
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── dashboardRoutes.js
│   │   ├── moradorRoutes.js
│   │   ├── unidadeRoutes.js
│   │   ├── reservaRoutes.js
│   │   ├── ocorrenciaRoutes.js
│   │   └── funcionarioRoutes.js
│   ├── views/
│   │   ├── layouts/
│   │   ├── partials/
│   │   ├── auth/
│   │   ├── dashboard/
│   │   ├── moradores/
│   │   ├── unidades/
│   │   ├── reservas/
│   │   ├── ocorrencias/
│   │   └── funcionarios/
│   ├── middlewares/
│   │   └── authMiddleware.js
│   └── public/
│       ├── css/
│       ├── js/
│       └── img/
├── database/
│   ├── schema.sql
│   └── seed.sql
├── app.js
├── package.json
├── README.md
└── USO_IA.md
```

---

## 6. Modelagem de Dados

### Entidades principais

| Entidade | Descrição |
|---|---|
| `usuario` | Login, autenticação e controle de acesso. |
| `unidade` | Apartamentos ou casas do condomínio. |
| `morador` | Pessoas vinculadas às unidades. |
| `reserva` | Solicitações de uso de áreas comuns. |
| `ocorrencia` | Reclamações, problemas ou solicitações. |
| `funcionario` | Colaboradores do condomínio. |

### Relacionamentos

| Relacionamento | Cardinalidade | Descrição |
|---|---:|---|
| Unidade — Morador | 1:N | Uma unidade pode possuir vários moradores; cada morador pertence a uma unidade. |
| Morador — Reserva | 1:N | Um morador pode realizar várias reservas. |
| Morador — Ocorrência | 1:N | Um morador pode abrir várias ocorrências. |
| Funcionário — Ocorrência | 1:N | Um funcionário pode acompanhar várias ocorrências. |
| Usuário — Registros do sistema | 1:N | Um usuário autenticado pode cadastrar ou atualizar registros. |

### Tabelas previstas

#### usuario

| Campo | Tipo | Restrição |
|---|---|---|
| id_usuario | INT | PK, AUTO_INCREMENT, NOT NULL |
| nome | VARCHAR(100) | NOT NULL |
| email | VARCHAR(120) | UNIQUE, NOT NULL |
| senha_hash | VARCHAR(255) | NOT NULL |
| tipo_usuario | VARCHAR(30) | NOT NULL |
| ativo | BOOLEAN | DEFAULT TRUE |

#### unidade

| Campo | Tipo | Restrição |
|---|---|---|
| id_unidade | INT | PK, AUTO_INCREMENT, NOT NULL |
| bloco | VARCHAR(10) | NOT NULL |
| numero | VARCHAR(10) | NOT NULL |
| andar | INT | NOT NULL |
| status | VARCHAR(20) | DEFAULT 'Ativa' |

#### morador

| Campo | Tipo | Restrição |
|---|---|---|
| id_morador | INT | PK, AUTO_INCREMENT, NOT NULL |
| id_unidade | INT | FK → unidade.id_unidade |
| nome | VARCHAR(100) | NOT NULL |
| cpf | VARCHAR(14) | UNIQUE, NOT NULL |
| telefone | VARCHAR(20) | NOT NULL |
| email | VARCHAR(120) | UNIQUE |
| data_nascimento | DATE | NULL |
| placa_carro | VARCHAR(20) | NULL |
| ativo | BOOLEAN | DEFAULT TRUE |

#### reserva

| Campo | Tipo | Restrição |
|---|---|---|
| id_reserva | INT | PK, AUTO_INCREMENT, NOT NULL |
| id_morador | INT | FK → morador.id_morador |
| area_comum | VARCHAR(100) | NOT NULL |
| data_reserva | DATE | NOT NULL |
| horario_inicio | TIME | NOT NULL |
| horario_fim | TIME | NOT NULL |
| status | VARCHAR(20) | DEFAULT 'Solicitada' |

#### ocorrencia

| Campo | Tipo | Restrição |
|---|---|---|
| id_ocorrencia | INT | PK, AUTO_INCREMENT, NOT NULL |
| id_morador | INT | FK → morador.id_morador |
| id_funcionario | INT | FK → funcionario.id_funcionario, NULL |
| titulo | VARCHAR(150) | NOT NULL |
| descricao | TEXT | NOT NULL |
| data_abertura | TIMESTAMP | NOT NULL |
| data_fechamento | TIMESTAMP | NULL |
| status | VARCHAR(20) | DEFAULT 'Aberta' |
| prioridade | VARCHAR(20) | NOT NULL |

#### funcionario

| Campo | Tipo | Restrição |
|---|---|---|
| id_funcionario | INT | PK, AUTO_INCREMENT, NOT NULL |
| nome | VARCHAR(100) | NOT NULL |
| cpf | VARCHAR(14) | UNIQUE, NOT NULL |
| cargo | VARCHAR(80) | NOT NULL |
| telefone | VARCHAR(20) | NOT NULL |
| data_admissao | DATE | NOT NULL |
| salario | DECIMAL(10,2) | NULL |
| status | VARCHAR(20) | DEFAULT 'Ativo' |
| id_usuario | INT | FK → usuario.id_usuario, NULL |

---

## 7. Protótipos de Tela

As telas planejadas para o CondoSys são:

- Login.
- Dashboard.
- Listagem de moradores.
- Cadastro e edição de morador.
- Listagem de unidades.
- Cadastro e edição de unidade.
- Listagem de ocorrências.
- Cadastro e edição de ocorrência.
- Listagem de funcionários.
- Cadastro e edição de funcionário.
- Listagem de reservas.
- Solicitação de reserva.
- Perfil de usuário e permissões.

---

## 8. Equipe e Responsabilidades

| Integrante | Papel no grupo | CRUD principal | Entregáveis |
|---|---|---|---|
| Lucca Felipe | Documentação | Funcionários | Documentação, README, evidências e CRUD de funcionários. |
| Matheus Albertini | Banco de Dados | Unidades | DER, relacionamentos, `schema.sql` e CRUD de unidades. |
| Abel Piassa | Autenticação | Moradores | Login, sessão, middleware de autenticação e CRUD de moradores. |
| Emanulle Silva | Front-End | Reservas | Telas EJS/Bootstrap, formulários e CRUD de reservas. |
| Adrian Felipe | Back-End | Ocorrências | Rotas, controllers, regras de negócio e CRUD de ocorrências. |
| IA | Apoio técnico | — | Revisão de documentação, explicações conceituais e sugestões de modelagem. |
| Todos | Colaboração | — | Commits, revisão geral, atualização do Kanban e validação do sistema. |

---

## 9. Backlog Inicial

| ID | História de Usuário | Prioridade | Estimativa | Responsável |
|---|---|---|---:|---|
| US01 | Como usuário, quero fazer login no sistema para acessar as funções administrativas. | Must | 3 pts | Abel Piassa |
| US02 | Como administrador, quero cadastrar moradores para manter os dados dos residentes atualizados. | Must | 5 pts | Abel Piassa |
| US03 | Como administrador, quero cadastrar unidades para organizar apartamentos/casas do condomínio. | Must | 5 pts | Matheus Albertini |
| US04 | Como morador/administrador, quero solicitar reserva de área comum para organizar o uso dos espaços. | Must | 5 pts | Emanulle Silva |
| US05 | Como sistema, devo impedir reservas conflitantes para a mesma área, data e horário. | Must | 5 pts | Emanulle Silva |
| US06 | Como administrador, quero registrar ocorrências para acompanhar problemas e solicitações. | Must | 5 pts | Adrian Felipe |
| US07 | Como administrador, quero cadastrar funcionários para controlar colaboradores do condomínio. | Must | 5 pts | Lucca Felipe |
| US08 | Como usuário autenticado, quero visualizar um dashboard com indicadores gerais do condomínio. | Should | 3 pts | Todos |
| US09 | Como usuário, quero acessar meu perfil para visualizar permissões disponíveis. | Should | 3 pts | Abel Piassa |
| US10 | Como equipe, queremos manter README.md e USO_IA.md atualizados para documentar o projeto. | Must | 3 pts | Todos |

---

## 10. Kanban Inicial

| Coluna | Tarefas |
|---|---|
| A Fazer | Backlog inicial |
| Em Desenvolvimento | Documentação; Matriz de Papéis |
| Em Revisão | Protótipos |
| Concluído | DER; Requisitos Funcionais; Requisitos Não Funcionais; Relacionamentos; MER; Entidades |

---

## 11. Como Executar o Projeto Localmente

> Esta seção deve ser ajustada conforme a implementação do projeto evoluir.

### Pré-requisitos

- Node.js instalado.
- PostgreSQL instalado.
- Git instalado.
- Editor de código, como VS Code.

### Passos

Clone o repositório:

```bash
git clone INSERIR_LINK_DO_REPOSITORIO
cd condosys
```

Instale as dependências:

```bash
npm install
```

Configure o arquivo `.env`:

```env
PORT=3000
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=sua_senha
DB_NAME=condosys
SESSION_SECRET=sua_chave_secreta
```

Crie o banco de dados no PostgreSQL e execute os scripts:

```bash
psql -U postgres -d condosys -f database/schema.sql
psql -U postgres -d condosys -f database/seed.sql
```

Inicie o servidor:

```bash
npm start
```

Acesse no navegador:

```text
http://localhost:3000
```

---

## 12. Testes Manuais Previstos

Os testes serão realizados pelas telas do sistema e/ou por ferramentas como Postman ou Insomnia.

Checklist básico:

- Login com usuário válido.
- Bloqueio de acesso sem autenticação.
- Cadastro de morador vinculado a uma unidade.
- Cadastro de unidade.
- Cadastro de reserva.
- Bloqueio de reserva duplicada para mesma área, data e horário.
- Cadastro de ocorrência com prioridade, status e responsável.
- Cadastro de funcionário.
- Logout da aplicação.

---

## 13. Documentação do Uso de IA

O projeto possui o arquivo [`USO_IA.md`](./USO_IA.md), que registra:

- ferramentas utilizadas;
- finalidades de uso;
- exemplos de prompts;
- decisões aceitas, adaptadas e recusadas;
- reflexão crítica da equipe;
- cuidados para evitar cópia sem compreensão técnica.

---

## 14. Observação Acadêmica

O CondoSys foi planejado como um **MVP acadêmico**, com escopo simples e funcional. O foco do projeto é demonstrar domínio técnico sobre:

- arquitetura MVC;
- CRUDs completos por integrante;
- banco de dados com relacionamentos;
- autenticação e rotas protegidas;
- uso de EJS e Bootstrap;
- documentação clara;
- versionamento com GitHub;
- uso responsável de Inteligência Artificial.
