# 📮 Postman API Tests – JSONPlaceholder

Este projeto é uma mini suíte de testes de requisições HTTP utilizando a API pública [JSONPlaceholder](https://jsonplaceholder.typicode.com/). Foi desenvolvido como parte dos meus estudos de QA e testes de API com o Postman.

## 🎯 Objetivo

Praticar os principais tipos de requisições REST usando o Postman com uma API pública e gratuita, simulando interações reais com um serviço back-end. As ações testadas cobrem o básico de **GET, POST, PUT e DELETE**, além de explorar os **headers, corpo da requisição e validações de status HTTP**.

## 🛠️ Tecnologias e Ferramentas

- [Postman](https://www.postman.com/)
- API JSONPlaceholder
- Testes simples com `pm.test`

## 🔗 API Utilizada

📌 **Base URL:** `https://jsonplaceholder.typicode.com`

Endpoint principal utilizado: `/posts`

## 🚀 Requisições testadas

| Método | Endpoint   | Ação                                |
| ------ | ---------- | ----------------------------------- |
| GET    | `/posts`   | Retorna todos os posts              | 
| GET    | `/posts/1` | Retorna um post específico          |
| POST   | `/posts`   | Cria um novo post                   |
| PUT    | `/posts/1` | Atualiza um post existente          |
| DELETE | `/posts/1` | Deleta um post existente (simulado) |

## 🖼️ Prints dos testes no Postman

### 🔹 Requisição GET All Posts
![GET All Posts](./assets/get-all-posts.png)

### 🔹 Requisição GET Posts 1
![GET Posts 1 ](./assets/get-posts-1.png)

### 🔹 Requisição POST Criar Novo Post
![POST Novo Post](./assets/post-new-posts-1.png)

### 🔹 Requisição PUT Atualizar Post
![PUT Atualizar Post](./assets/put-update-posts-1.png)

### 🔹 Requisição DELETE Deletar Post
![DELETE Post](./assets/delete-posts-1.png)


### ✅ Teste adicionado

Na requisição `GET ALL POSTS`, foi adicionado um teste automatizado para verificar o status da resposta:

```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
pm.test("Response body is an array", function () {
    const jsonData = pm.response.json();
    pm.expect(Array.isArray(jsonData)).to.eql(true);
});
```

Na requisição `POST /posts`, foi adicionado um teste automatizado para verificar o status da resposta:

```
pm.test("Status code is 201", function () {
   pm.response.to.have.status(201);
});
```
