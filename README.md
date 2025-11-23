# E-commerce Fullstack

### 🟦 Backend (Node.js + Express)

- Express: Framework principal da API
- Prisma ORM: ORM para MongoDB
- MongoDB: Banco de dados NoSQL
- TypeScript: Tipagem e segurança
- Zod: Validação de dados
- JWT (jsonwebtoken): Autenticação
- Bcrypt-ts: Criptografia de senhas
- Dotenv: Variáveis de ambiente
- Helmet: Segurança e proteção de headers
- CORS: Permitir consumo externo
- Node-Cron: Tarefas agendadas


### Frontend (React)

- React: Interface do usuário
- React Router: Gerenciamento de rotas e navegação SPA
- TypeScript: Tipagem segura

### Banco de Dados

- MongoDB: Banco NoSQL orientado a documentos
- Prisma ORM: Controle de modelos, migrations e acesso ao banco

## Estrutura do Projeto

```
projeto-raiz/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── middlewares/
│   │   ├── services/
│   │   ├── utils/
│   │   ├── cronjobs/
│   │   ├── webhooks/
│   │   └── app.js
│   ├── tests/
│   ├── .env.example
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   ├── context/
│   │   ├── styles/
│   │   └── App.jsx
│   ├── .env.example
│   └── package.json
└── README.md
```

## Requisitos Funcionais

### Fluxo de Pagamento com Gateway Simulado

1. O usuário adiciona produtos ao carrinho
2. No checkout, as informações de pagamento são coletadas
3. Uma requisição é feita ao backend para criar a transação
4. O backend comunica com o gateway simulado para processar o pagamento
5. O gateway simulado retorna uma resposta com resultado da transação
6. Uma simulação de webhook do gateway confirma o resultado da transação
7. O pedido é atualizado com o status do pagamento
8. Cronjob sincroniza periodicamente o status com o gateway simulado

### Autenticação e Autorização

1. Implementar registro e login de usuários
2. Gerar JWT com expiração curta e refresh token com expiração longa
3. Middleware de autenticação em rotas protegidas
4. Apenas usuários autenticados podem criar pedidos
5. Usuários apenas veem seus próprios dados e pedidos

## Critérios de Avaliação

### Código

- Organização e limpeza do código
- Separação de responsabilidades
- Reutilização de componentes e funções
- Nomenclatura consistente e clara
- Tratamento de erros apropriado

### Arquitetura

- Design da API RESTful
- Estrutura do banco de dados
- Escalabilidade da solução
- Segurança implementada

### Funcionalidades

- Todos os requisitos básicos funcionando
- Integração correta com Pagar.me
- Cronjobs executando conforme esperado
- Validações de entrada adequadas

### Boas Práticas

- Autenticação e autorização seguras
- Variáveis de ambiente para configuração
- Documentação do código
- Estrutura preparada para testes

### Frontend

- Interface clara e usável
- Responsividade em diferentes dispositivos
- Estados de carregamento e erro bem tratados
- Comunicação eficiente com o backend

## Stack Tecnológico

### Backend

- Node.js
- Express.js
- MongoDB com Mongoose
- JWT para autenticação
- node-cron para agendamento de tarefas
- axios ou node-fetch para requisições HTTP
- dotenv para variáveis de ambiente

### Frontend

- React
- React Router para navegação
- Axios para requisições HTTP
- React Context ou Zustand para estado global
- CSS ou Tailwind CSS para estilos

### Infraestrutura

- MongoDB (Atlas ou local)
- Conta de desenvolvimento no Pagar.me
- Node.js 16+

## Instruções de Execução

### Pré-requisitos

- Node.js 16 ou superior
- MongoDB rodando localmente ou em nuvem
- Chaves de API do Pagar.me (ambiente de teste)
- Git

### Instalação

1. Clonar o repositório
2. Navegar até a pasta backend e executar `npm install`
3. Navegar até a pasta frontend e executar `npm install`
4. Criar arquivos .env em ambas as pastas com base nos .env.example
5. Popular variáveis de ambiente com credenciais

### Execução

Backend:

```bash
cd backend
npm install
npm run dev
```

Frontend:

```bash
cd frontend
npm install
npm start
```
