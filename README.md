# MovieFlix API

API em Node.js + Express + TypeScript para gerenciar filmes, gêneros e idiomas, com integração ao Prisma e documentação via Swagger.

## 🚀 Tecnologias

- Node.js
- TypeScript
- Express
- Prisma ORM
- PostgreSQL
- Swagger UI

## 📦 Estrutura do projeto

```text
src/
  server.ts          # ponto de entrada da API
prisma/
  schema.prisma      # modelo do banco e configuração do Prisma
swagger.json        # documentação OpenAPI/Swagger
```

## ✅ Requisitos

Antes de começar, certifique-se de ter instalado:

- Node.js 18 ou superior
- npm
- PostgreSQL rodando localmente

## 🔧 Instalação

1. Clone o repositório
2. Acesse a pasta do projeto
3. Instale as dependências:

```bash
npm install
```

## 🗄️ Configuração do banco de dados

Crie um arquivo `.env` na raiz do projeto com a seguinte variável:

```env
DATABASE_URL="postgresql://seu-usuario:senha@localhost:5432/movieflix?schema=public"
```

Substitua os valores conforme sua configuração local.

## 🧱 Gerar client do Prisma

```bash
npx prisma generate
```

## 🛠️ Rodar as migrações

Se o banco ainda não estiver preparado:

```bash
npx prisma migrate dev --name init
```

## ▶️ Executar o projeto

### Modo desenvolvimento

```bash
npm run dev
```

### Modo produção

```bash
npm run build
npm start
```

A API será iniciada em:

```text
http://localhost:3000
```

## 📚 Documentação Swagger

A documentação da API fica disponível em:

```text
http://localhost:3000/docs
```

## Endpoints

### GET /movies

Retorna todos os filmes cadastrados.

### POST /movies

Cria um novo filme.

Body exemplo:

```json
{
  "title": "O Poderoso Chefão",
  "genre_id": 1,
  "language_id": 1,
  "oscar_count": 6,
  "release_date": "1972-03-24"
}
```

### PUT /movies/:id

Atualiza um filme existente pelo ID.

### DELETE /movies/:id

Remove um filme pelo ID.

### GET /movies/:genreName

Filtra filmes por nome de gênero.

## 🧪 Scripts disponíveis

```bash
npm run dev
npm run build
npm start
npm run format
```

## 🧩 Modelo de dados

O projeto utiliza as seguintes entidades principais:

- Movie
- Genre
- language

O modelo está definido em [prisma/schema.prisma](prisma/schema.prisma).

## ⚠️ Observações

- Certifique-se de que o PostgreSQL esteja acessível antes de rodar as migrations.
- O projeto usa o Prisma Client gerado dentro de [src/generated/prisma](src/generated/prisma).
- Se houver problemas de execução, verifique se a pasta de saída da build contém os arquivos gerados do Prisma.
