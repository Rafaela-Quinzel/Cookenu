# Projeto Cookenu


Como rodar o projeto

1- rode o comando abaixo
````
npm install
````
2- crie um arquivo .env na raíz do projeto com esses dados:

//dados do seu banco
````
DB_HOST
DB_USER
DB_PASSWORD
DB_DATABASE_NAME
````

//suas preferências para key e expire
````
JWT_KEY
JWT_EXPIRES_IN
````


//suas preferências de cost
````
BCRYPT_COST
````

**ENDPOINTS:**

**User Endpoints**

***Signup***
- Método: POST
- Path: `/user/signup`
- Body:

```json
{
	"name": "Alice",
	"email": "alice@email.com",
	"password": "123456"
}
````

- Saídas:
````
{
	"access_token": "token de acesso"
}
````

***Login***

- Método: POST
- Path: `/user/login`
- Body de Resposta:

```json
{
	"email": "alice@email.com",
	"password": "123456"
}
```
- Saídas:

````
{
	"access_token": "token de acesso"
}
````

***getProfileUser***

- Método: GET
- Path: `/user/profile`
- Entradas:
````
Headers

Authorization: "token de autenticação"
````

- Saídas:

```json
Body

{
	"id": "id do usuário",
	"name": "Alice",
	"email": "alice@email.com"
}
```


***getUserById***

- Método: GET
- Path: `/user/:id`
- Entradas:
````
Path Param

id: "id do usuário"

Headers

Authorization: "token de autenticação"
`````

- Saídas: 

`````
Body

{
	"id": "id do usuário",
	"name": "Alice",
	"email": "alice@lbn.com"
}
`````

**Recipe Endpoints**

***createRecipe***

- Método: POST
- Path: `/recipe/create`
- Entradas:

````
Headers

Authorization: "token de autenticação"

Body

{
	"title": "título da receita",
	"description": "descrição da receita"
}
`````

***getRecipeById***

- Método: GET
- Path: `/recipe/:id`
- Entradas:

````
Path Param

id: "id da receita"

Headers

Authorization: "token de autenticação"
`````

- Saídas: 

````
Body

{
	"id": "id da receita",
	"title": "bolo",
	"description": "Mistura tudo e coloca no forno"
	"cratedAt": "31/12/2020"
}
`````
