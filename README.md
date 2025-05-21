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
