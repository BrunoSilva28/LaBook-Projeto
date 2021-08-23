# LABOOK
- Este é um projeto básico de Backend, utilizando Typescript, MySQL, além das bibliotecas knexJs e expressJs, desenvolvido para atender aos modelos REST API.

---
## DESCRIÇÃO DO PROJETO

- O projeto consiste em simular a metodologia CRUD na estruturação de Sistema de Posts de Rede Social,criando e acessando informações de usuários e posts, sendo criado endpoints `GET` e `POST` para alimentar as demandas.

---
## DOCUMENTAÇÃO DE FUNCIONAMENTO

### LINK DA DOCUMENTAÇÃO NO POSTMAN: https://documenter.getpostman.com/view/15825773/Tzz8sHfv


## Endpoints

1. Cadastro
   * Exemplo de requisição:
      ```bash
      curl -i -X POST http://localhost:3003/users/signup -H "Content-Type: application/json" -d '{"name":"Alice","email":"alice@gmail.com","password":"pass123"}'
      ```
   * Exemplo de resposta (sucesso):
      ```bash
      HTTP/1.1 201 Created
      X-Powered-By: Express
      Access-Control-Allow-Origin: *
      Content-Type: application/json; charset=utf-8
      Content-Length: 220
      ETag: W/"dc-ec7r4rkKsMBe/V0SGyUkO6Vyto0"
      Date: Tue, 17 Nov 2020 14:33:15 GMT
      Connection: keep-alive

      {"message":"Success!", "token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6Ijg5OGJjNDVlLTExZjEtNGEyMy04OTZhLTdmMmUyOWNmZTAxMiIsImlhdCI6MTYwNTYyMzU5NSwiZXhwIjoxNjA1NzA5OTk1fQ.pWxV2vtLnp0hKm0CXXnLpnDu6PEPkZM27A71oTTCYfE"}%   
      ```
1. Login
   * Exemplo de requisição:
      ```bash
      curl -i -X POST http://localhost:3003/users/login -H "Content-Type: application/json" -d '{"email":"alice@gmail.com","password":"pass123"}'
      ```
   * Exemplo de resposta (sucesso):
      ```bash
      HTTP/1.1 200 OK
      X-Powered-By: Express
      Access-Control-Allow-Origin: *
      Content-Type: application/json; charset=utf-8
      Content-Length: 220
      ETag: W/"dc-IBDYVXSmDzdFsqHXhPCAutzNwn8"
      Date: Tue, 17 Nov 2020 14:39:23 GMT
      Connection: keep-alive

      {"message":"Success!","token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6Ijg5OGJjNDVlLTExZjEtNGEyMy04OTZhLTdmMmUyOWNmZTAxMiIsImlhdCI6MTYwNTYyMzk2MywiZXhwIjoxNjA1NzEwMzYzfQ.9JvXRQpazI5k6GAnc1lFcVcTbZ_ElASnwyybU_tRU48"}%   
      ```
1. Criar Post
   * Exemplo de requisição:
      ```bash
      curl -i -X POST http://localhost:3003/posts/create -H "Content-Type: application/json" -H "authorization:$token" -d '{"photo":"https://i.picsum.photos/id/238/200/200.jpg?hmac=O4Jc6lqHVfaKVzLf8bWssNTbWzQoaRUC0TDXod9xDdM","description":"My city is beautiful =D","type":"normal"}'
      ```
   * Exemplo de resposta (sucesso):
      ```bash
      HTTP/1.1 201 Created
      X-Powered-By: Express
      Access-Control-Allow-Origin: *
      Content-Type: application/json; charset=utf-8
      Content-Length: 22
      ETag: W/"16-ChcZhlw1slqtGuDwxLsUclql5gE"
      Date: Tue, 17 Nov 2020 14:47:15 GMT
      Connection: keep-alive

      {"message":"Success!"}%    
      ```
1. Buscar Post por id
   * Exemplo de requisição:
      ```bash
      curl -i http://localhost:3003/posts/$id -H "Content-Type: application/json" -H "authorization:$token" 
      ```
   * Exemplo de resposta (sucesso):
      ```bash
      HTTP/1.1 200 OK
      X-Powered-By: Express
      Access-Control-Allow-Origin: *
      Content-Type: application/json; charset=utf-8
      Content-Length: 322
      ETag: W/"142-IYRwCODXZBltXE3MydHuIDB8M3w"
      Date: Tue, 17 Nov 2020 14:52:19 GMT
      Connection: keep-alive

      {"message":"Success!","post":{"id":"e4eb1531-d814-4742-b614-be2a36602548","photo":"https://i.picsum.photos/id/238/200/200.jpg?hmac=O4Jc6lqHVfaKVzLf8bWssNTbWzQoaRUC0TDXod9xDdM","description":"My city is beautiful =D","type":"normal","createdAt":"2020-11-17T17:47:15.000Z","authorId":"898bc45e-11f1-4a23-896a-7f2e29cfe012"}}% 
      ```
