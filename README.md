# Teste Técnico - Desenvolvedor Fullstack Pleno

## Sobre o Teste

Este teste técnico foi desenvolvido para avaliar competências de um desenvolvedor fullstack pleno, com foco em uma arquitetura moderna utilizando tecnologias como Node.js, MongoDB, React e integração com gateway de pagamento.

O candidato deve demonstrar capacidade de trabalhar em um projeto integrado, desde a construção de APIs robustas até a implementação de fluxos de pagamento e agendamento de tarefas assíncronas.

## Objetivo

Implementar um sistema de e-commerce funcional em um único repositório monorepo que contemple:

- Backend com Node.js e Express
- Frontend com React
- Integração com gateway de pagamento (Pagar.me)
- Banco de dados MongoDB
- Sistema de cronjobs para tarefas agendadas
- Autenticação e autorização
- Tratamento de erros e validações

## Requisitos Técnicos

### Backend (Node.js)

O candidato deve criar uma API REST que atenda aos seguintes requisitos:

1. Autenticação JWT com refresh tokens
2. Gerenciamento de usuários e clientes
3. Gestão de produtos com categorias
4. Criação e processamento de pedidos
5. Integração com gateway de pagamento simulado
6. Tratamento de simulação de webhooks do gateway
7. Validações em todos os endpoints
8. Tratamento centralizado de erros
9. Logging estruturado
10. Testes unitários para funções críticas

### Frontend (React)

O candidato deve criar uma aplicação web que inclua:

1. Páginas de autenticação (login e registro)
2. Listagem de produtos com filtros
3. Carrinho de compras funcional
4. Fluxo de checkout com integração ao Pagar.me
5. Página de perfil do usuário
6. Histórico de pedidos
7. Interface responsiva
8. Tratamento de erros e feedback ao usuário
9. Estados de carregamento adequados

### Cronjobs

Implementar pelo menos dois trabalhos agendados:

1. Sincronização de status de pagamentos com gateway simulado
2. Limpeza de carrinhos abandonados (opcional: envio de email)

### Banco de Dados

Criar um esquema MongoDB que modele:

1. Coleções de usuários, produtos, pedidos e pagamentos
2. Relacionamentos apropriados entre coleções
3. Índices para otimização de consultas
4. Validadores de schema quando aplicável

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

O backend deve rodar na porta 5000 (ou configurada) e o frontend na porta 3000.

## Documentação Esperada

O candidato deve incluir:

1. README descrevendo como executar o projeto
2. Instruções de configuração do banco de dados
3. Documentação dos endpoints principais
4. Exemplos de requisições e respostas
5. Instruções para testar o gateway de pagamento simulado

## Observações Importantes

1. O projeto deve ser funcional e executável
2. Variáveis sensíveis não devem ser commitadas
3. O código deve ser limpo e bem organizado desde o início
4. Prefira qualidade a quantidade de features
5. Documente decisões arquiteturais importantes
6. O gateway de pagamento deve ser simulado, mas com lógica realista de aprovação e rejeição
7. Implemente sistema de simulação de webhooks (por exemplo, via agendador que muda status após alguns segundos)

## Tempo Estimado

Este teste foi desenvolvido para ser concluído em 7 a 10 dias de trabalho, considerando dedicação em tempo parcial.

## Envio da Solução

### Processo de Submissão

1. Faça um fork deste repositório para sua conta pessoal no GitHub
2. Clone o repositório do seu fork para sua máquina local
3. Crie uma branch com seu nome: `git checkout -b seu-nome-sobrenome`
4. Desenvolva a solução do teste nesta branch
5. Faça commits regulares e significativos ao longo do desenvolvimento
6. Envie o código para o seu fork: `git push origin seu-nome-sobrenome`
7. Abra um Pull Request (PR) do seu fork para o repositório original
8. Preencha a descrição do PR com:
   - Resumo das funcionalidades implementadas
   - Desafios encontrados e como foram resolvidos
   - Melhorias implementadas
   - Instruções adicionais para execução, se necessário
   - Links para documentação de referência utilizada

### Critérios de Avaliação do Envio

- Histórico de commits legível e com mensagens claras
- Código organizado e bem estruturado
- README completo com instruções de execução
- Pull Request bem documentado
- Aderência aos requisitos técnicos do teste

### Exemplo de Comando Para Fork

```bash
# 1. Fazer fork no GitHub (através da interface web)

# 2. Clonar seu fork
git clone https://github.com/seu-usuario/teste-dev-fullstack-mern.git
cd teste-dev-fullstack-mern

# 3. Criar branch com seu nome
git checkout -b fulano-silva

# 4. Após completar o desenvolvimento
git push origin fulano-silva

# 5. Abrir PR através da interface do GitHub
```

### Avaliação do Pull Request

Nosso time irá avaliar:

- Funcionalidade completa e testes
- Qualidade do código e padrões de projeto
- Documentação e clareza das mudanças
- Boas práticas de Git e organização de commits
- Capacidade de comunicação através do PR

Não é necessário mesclar o PR, apenas submeter para que seja avaliado.

## Suporte

Para dúvidas sobre requisitos técnicos ou esclarecimentos sobre o teste, entre em contato com o time de recrutamento.

---

Boa sorte no teste!
