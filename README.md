# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

essa api tem quatro endpoints, sendo login, cadastro, produtos, e carrinho

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

### Products

A rota de produtos não pode ser editada por ninguém, no entanto, todos podem ter acesso a ela, ela armazena os produtos disponivéis na loja.

GET/Products

### Cart

O carrinho é uma rota que apenas o usuário logado pode usar, ele tem acesso somente a produtos que ele adicionar ao carrinho, não esqueça de informar o token na requisição!

### Buscando seu carrinho:

GET /cart/?userId=<seu id aqui>

### Adicionando ao carrinho:

POST /cart/

ATENÇÃO: O userId deve ser informado MANUALMENTE pelo USUÁRIO
{
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"quantity": 1
userId="<seu id aqui>"
},

### Removendo um produto do carrinho

DELETE /cart/<id do produto>/

### Editando o numero de unidades de um produto

ATENÇÃO: O numero e unidades é informado MANUALMENTE pelo USUÁRIO
PATCH /cart/<id do produto>/
{
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"userId": 2,
"id": 1,
"quantity":<altere aqui>
}
