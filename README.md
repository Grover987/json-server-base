# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.


### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"


### Rotas com autenticação

### Animes

Cadastrar

POST /animes<br/>

Utilizada para cadastrar animes do usuario, necessario o "userId" para a requisição, os demais dados são opcionais

{
  "name": "Haikyuu",
  "seasons": 4,
  "category": "sports",
  "userId": 233
}

Caso dê tudo certo, a resposta será assim:

POST /animes - FORMATO DA RESPOSTA - STATUS 201

POST /mangas<br/>

Utilizada para cadastrar mangas do usuario, necessario o "userId" para a requisição, os demais dados são opcionais

{
  "name": "One Piece",
  "chapters": "infinito",
  "category": "shounen",
  "userId": 233
}

Caso dê tudo certo, a resposta será assim:

POST /mangas - FORMATO DA RESPOSTA - STATUS 201

### Possiveis erros

POST /mangas - FORMATO DA RESPOSTA - STATUS 401

"Missing authorization header"

Falta a autenticação do usuario



POST /mangas - FORMATO DA RESPOSTA - STATUS 403

"Private resource creation: request body must have a reference to the owner id"

Faltou colocar o userId no corpo da requisição