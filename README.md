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
<p>Para instalar as dependências use npm install; <br /> Para inicializar o banco de dados, rode docker compose -d, utilizando este código para configurar o arquivo .env ```bash DATABASE_URL="postgresql://docker:docker@localhost:5432/polls?schema=public" ``` <br/> Pronto, agora basta rodar npm run dev para sua aplicação funcionar!</p>

<hr />

<h3>POST /polls</h3>
<p>Create a new poll</p>

Request body
{
  "title": "Qual a melhor linguagem de programação?",
  "options": [
    "JavaScript",
    "Java",
    "PHP",
    "C#"
  ]
}
Response body
{
  "pollId": "194cef63-2ccf-46a3-aad1-aa94b2bc89b0"
}

<h3>GET /polls/:pollId</h3>

Return data from a single poll.

Response body
{
	"poll": {
		"id": "e4365599-0205-4429-9808-ea1f94062a5f",
		"title": "Qual a melhor linguagem de programação?",
		"options": [
			{
				"id": "4af3fca1-91dc-4c2d-b6aa-897ad5042c84",
				"title": "JavaScript",
				"score": 1
			},
			{
				"id": "780b8e25-a40e-4301-ab32-77ebf8c79da8",
				"title": "Java",
				"score": 0
			},
			{
				"id": "539fa272-152b-478f-9f53-8472cddb7491",
				"title": "PHP",
				"score": 0
			},
			{
				"id": "ca1d4af3-347a-4d77-b08b-528b181fe80e",
				"title": "C#",
				"score": 0
			}
		]
	}
}
POST /polls/:pollId/votes
Add a vote to specific poll.

Request body
{
  "pollOptionId": "31cca9dc-15da-44d4-ad7f-12b86610fe98"
}
WebSockets
ws /polls/:pollId/results
Message
{
  "pollOptionId": "da9601cc-0b58-4395-8865-113cbdc42089",
  "votes": 2
}
