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

### Frontend

- React
- React Router para navegação
- Axios para requisições HTTP
- React Context ou Zustand para estado global
- CSS ou Tailwind CSS para estilos

### Pré-requisitos
- Chaves de API do Pagar.me (ambiente de teste)

### Instalação

## Execução

Backend:

```bash
cd backend
npm install / npm i
npm run dev
```

Frontend:

```bash
cd frontend
npm install / npm i
npm run dev
```
