###NLW Expert - NodeJS

<h3>Tecnologia usadas no projeto: </h3>
<p>Docker</p>
<p>Typescript</p>
<p>Redis</p>
<p>PostgreSQL</p>
<p>Prisma</p>
<p>WebSocket</p>

<hr />

<h3>Setup</h3>
<p>Para instalar as dependências use npm install; <br /> Para inicializar o banco de dados, rode docker compose -d, utilizando este código para configurar o arquivo .env ```
DATABASE_URL="postgresql://docker:docker@localhost:5432/polls?schema=public" ``` <br/> Pronto, agora basta rodar npm run dev para sua aplicação funcionar!</p>

<hr />

<h3>POST /polls</h3>
<p>Create a new poll</p>
<br />

<p>Request body</p>

```json
{
  "title": "Qual o emlhor framework NodeJS",
  "options": ["Express", "Fastify", "NestJS", "HapiJS"]
}

Response body
{
  "pollId": "58da077e-390f-4b74-8605-208989a48312"
}
```

<h3>GET /polls/:pollId</h3>

Return data from a single poll.

<p>Response body</p>

```json
{
  "poll": {
    "id": "80b073c2-78bd-4ac0-a188-400280581659",
    "title": "Qual o emlhor framework NodeJS",
    "options": [
      {
        "id": "f9bc39a1-154a-4069-aaa1-d5154ac834ba",
        "title": "Express",
        "score": 0
      },
      {
        "id": "eacd9d7b-8af0-4401-9982-2ab7d9079727",
        "title": "Fastify",
        "score": 0
      },
      {
        "id": "b15d6a32-cd46-40aa-92f6-dbff2f906dc4",
        "title": "NestJS",
        "score": 0
      },
      {
        "id": "e52ebeaf-1bfc-459e-95a5-fd5d81c3aac8",
        "title": "HapiJS",
        "score": 1
      }
    ]
  }
}
```

<h3>POST /polls/:pollId/votes</h3>
Add a vote to specific poll.

<p>Request body</p>

```json
{
  "pollOptionId": "e52ebeaf-1bfc-459e-95a5-fd5d81c3aac8"
}
WebSockets
ws /polls/:pollId/results
Message
{
  "pollOptionId": "e52ebeaf-1bfc-459e-95a5-fd5d81c3aac8",
  "votes": 1
}
```