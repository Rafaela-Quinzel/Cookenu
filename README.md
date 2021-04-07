# 🍽 _Projeto Cookenu_ 🍽

Este projeto foi desenvolvido no curso da `Labenu` é uma API com funcionalidades básicas de uma rede social sobre receitas, onde os usuários podem dividir informações sobre comidas que tenham experimentado.

***
<br/>

**Para utilizar este projeto você precisa dos primeiros passos abaixo:**

- Clonar este repositório
- Executar o comando npm install no terminal
- Criar um arquivo .env na raiz do projeto e preencher com os valores corretos.

```
   #exemplo de endereço do host
   DB_HOST = 00.000.000.000
   PORT = 0000
   DB_USER = nome-usuario
   DB_PASSWORD = 1a2b3c4d5e
   DB_NAME = nome-banco
   JWT_KEY = chave
   JWT_EXPIRES_IN = 1d
   BCRYPT_COST = 12
```

***
<br/>

No arquivo `tables.sql` estão todas as tabelas que foram criadas para guardar as informações no banco de dados.
 
Para criar estas tabelas no seu banco de dados basta clicar em `Run SQL` e as tabelas serão criadas.

***
<br/>

**Para rodar este projeto:**
- npm run start
- npm run dev

*** 
<br/>

**Endpoints existentes neste projeto são divididos em duas partes:** endpoints relacionados aos usuários e receitas.

<br/>

## Endpoints de Usuários:
<br/>
 
**POST** SignUp

- Para criar um novo usuário
- O usuário pode ser cadastrado como "NORMAL" ou "ADMIN"
- Exemplo
```
   http://localhost:3003/user/signup
```

Body:

```json
   {
      "name":"usuario",
      "email":"usuario@email.com.br",
      "password":"123456",
      "role": "ADMIN"
   }
```
<br/>

**POST** Login

- Fazer Login
- Exemplo
```
   http://localhost:3003/user/login
```

Body:

```json
   {
      "email":"usuario@email.com.br",
      "password":"123456"
   }
```

<br/>

**GET** Profile User

- Para o usuário ver as suas informações não sensíveis que foram salvas no banco.
- Exemplo
```
   http://localhost:3003/user/profile
```

Authorization(token):

```json
Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImZiNTEzMTIxLTE0MTEtNDZiZC1hMjEwLTQ0OGQ2YjA0ODIzZSIsImlhdCI6MTYxNTA2NTU3MywiZXhwIjoxNjE1MTUxOTczfQ.IuXjGbKiAMZZmTKhzWKD3RsboN7qRwOO7z4xUqupgso
```

<br/>

**GET** Another Profile

- Para o usuário ver as suas informações não sensíveis de outro usuário que foram salvas no banco através do id.
- Exemplo
```
   http://localhost:3003/users/profile/:id
```

Authorization(token):

```json
Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImZiNTEzMTIxLTE0MTEtNDZiZC1hMjEwLTQ0OGQ2YjA0ODIzZSIsImlhdCI6MTYxNTA2NTU3MywiZXhwIjoxNjE1MTUxOTczfQ.IuXjGbKiAMZZmTKhzWKD3RsboN7qRwOO7z4xUqupgso
```

***
<br/>

## Endpoints de Receitas:
<br/>

**POST** Create Recipe

- Para adicionar uma nova receita
- Exemplo
```
   http://localhost:3003/recipe/create
```

Authorization(token):

```json
Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImZiNTEzMTIxLTE0MTEtNDZiZC1hMjEwLTQ0OGQ2YjA0ODIzZSIsImlhdCI6MTYxNTA2NTU3MywiZXhwIjoxNjE1MTUxOTczfQ.IuXjGbKiAMZZmTKhzWKD3RsboN7qRwOO7z4xUqupgso
```

Body:

```json
{
   "title": "título da receita",
   "description": "descrição da receita"
}
```
<br/>

**GET** Recipe By Id

- Buscar receita específica através do id
- Exemplo:
```
   http://localhost:3003/recipe/:id
```

Authorization(token):

```json
Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImZiNTEzMTIxLTE0MTEtNDZiZC1hMjEwLTQ0OGQ2YjA0ODIzZSIsImlhdCI6MTYxNTA2NTU3MywiZXhwIjoxNjE1MTUxOTczfQ.IuXjGbKiAMZZmTKhzWKD3RsboN7qRwOO7z4xUqupgso
```

***
<br/>

**Bibliotecas, Frameworks e recursos utilizados neste projeto:**

<ul style="font-size: 14px; margin-left: 25px;">
   <li>Express</li>  
   <li>Cors</li>
   <li>Dotenv</li>
   <li>Knex</li>
   <li>uuid</li>
   <li>bcryptjs</li>
   <li>jsonwebtoken</li>
   <li>typescript</li>
   <li>ts-node-dev</li>
</ul>





