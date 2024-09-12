# Books API

Esta é uma API simples de gerenciamento de livros, que permite adicionar, atualizar, listar, e remover livros de uma coleção. A API foi desenvolvida utilizando `Python` com `http.server`.

## Funcionalidades

- **GET /books**: Retorna todos os livros.
- **GET /books/{id}**: Retorna um livro específico pelo seu `id`.
- **POST /books**: Adiciona um novo livro.
- **PUT /books/{id}**: Atualiza as informações de um livro existente.
- **DELETE /books/{id}**: Remove um livro da coleção.

## Como Executar

1. Clone o repositório.
2. Certifique-se de ter o Python instalado.
3. Execute o servidor com o seguinte comando:

    ```bash
    python api_books.py
    ```

4. A API estará disponível em `http://localhost:8000`.

## Exemplos de Requisições

### 1. Listar todos os livros
- **Método**: GET
- **Endpoint**: `/books`
- **Resposta**:
    ```json
    [
        {
            "id": 1,
            "title": "Livro Exemplo",
            "author": "Autor Exemplo"
        }
    ]
    ```

### 2. Consultar um livro específico
- **Método**: GET
- **Endpoint**: `/books/{id}`
- **Resposta (sucesso)**:
    ```json
    {
        "id": 1,
        "title": "Livro Exemplo",
        "author": "Autor Exemplo"
    }
    ```
- **Resposta (erro)**:
    ```json
    {
        "message": "Livro não encontrado"
    }
    ```

### 3. Adicionar um novo livro
- **Método**: POST
- **Endpoint**: `/books`
- **Body**:
    ```json
    {
        "id": 2,
        "title": "Novo Livro",
        "author": "Novo Autor"
    }
    ```
- **Resposta (sucesso)**:
    ```json
    {
        "id": 2,
        "title": "Novo Livro",
        "author": "Novo Autor"
    }
    ```

### 4. Atualizar um livro existente
- **Método**: PUT
- **Endpoint**: `/books/{id}`
- **Body**:
    ```json
    {
        "title": "Livro Atualizado",
        "author": "Autor Atualizado"
    }
    ```
- **Resposta (sucesso)**:
    ```json
    {
        "id": 1,
        "title": "Livro Atualizado",
        "author": "Autor Atualizado"
    }
    ```

### 5. Deletar um livro
- **Método**: DELETE
- **Endpoint**: `/books/{id}`
- **Resposta**:
    ```json
    {
        "message": "Livro deletado"
    }
    ```

## Estrutura de Dados

Cada livro é representado por um JSON com os seguintes campos:
- `id`: Identificador único do livro (inteiro).
- `title`: Título do livro (string).
- `author`: Autor do livro (string).

## Erros Comuns

- **400 - JSON inválido**: O corpo da requisição não pôde ser processado.
- **404 - Livro não encontrado**: O livro com o `id` fornecido não existe.
- **400 - ID inválido**: O `id` fornecido na URL não é um número válido.

## Autor
Feito por [Seu Nome]
