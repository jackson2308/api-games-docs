# API de Games
Esta API é utilizada para ....

## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados
### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça, você irá receber a listagem de todos os games.

Exemplo de resposta:
```
[
	{
		"id": "73032a7d-9b19-4803-ae8d-9dcfcc4587db",
		"title": "Mario",
		"year": "2017",
		"price": "299"
	},
	{
		"id": "a8483354-0f51-40bc-be9d-19772d5842ff",
		"title": "GOW",
		"year": "2022",
		"price": "339"
	}
]
```

Exemplo
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição.
Motivos: Token inválido, Token expirado.

Exemplo de resposta:
```
{
	"errors": [
		"Token expirado ou inválido"
	]
}
```

### POST /
Esse endpoint é responsável por fazer o processo de login
### Parâmetros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.
#### Respostas
##### OK! 200
Caso essa resposta aconteça, você irá receber o token JWT para conseguir acessar endpoints protegidos na API

Exemplo de resposta:
```
{
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJqYWNrc29uYXVndXN0b0B5YWhvby5jb20uYnIiLCJpYXQiOjE2Njk3MjA2MDYsImV4cCI6MTY2OTg5MzQwNn0.PG171NnHojUvSQCmywtsN0V5iX1nqCtSSrwKAhqsu50"
}
```

Exemplo
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição.
Motivos: Senha ou e-mail incorretos

Exemplo de resposta:
```
{err: 'Credenciais inválidas!'}
```
