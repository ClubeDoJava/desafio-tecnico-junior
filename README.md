# Mini API de Blog

## Descrição do Problema

Projetar e implementar uma API RESTful simples para gerenciar posts de blog. 
A API deve permitir que os usuários realizem operações básicas como criar, ler, atualizar e deletar posts de blog.

## Funcionalidades Principais (Endpoints da API)

*   **POST /posts:** Criar um novo post de blog.
    *   Aceita dados JSON no corpo da requisição contendo o `título`, o `conteúdo` e o `autor` do post.
    *   Após a criação bem-sucedida, a API deve retornar o novo post de blog como um objeto JSON, incluindo um identificador exclusivo (ID) atribuído pelo sistema.

*   **GET /posts:** Recuperar uma lista de todos os posts de blog.
    *   Quando este endpoint é acessado por meio de uma requisição GET, a API deve retornar um array JSON onde cada elemento é um objeto JSON representando um post de blog.

*   **GET /posts/{id}:** Recuperar um post de blog específico por seu identificador exclusivo.
    *   O `{id}` no caminho representa um espaço reservado para o ID do post de blog desejado.
    *   A API deve retornar um objeto JSON representando o post de blog com o ID correspondente.
    *   Se nenhum post de blog com o ID fornecido existir, a API deve retornar uma resposta de erro apropriada, como um código de status HTTP 404 (Não Encontrado).

*   **PUT /posts/{id}:** Atualizar um post de blog existente identificado por seu ID.
    *   Este endpoint deve aceitar uma requisição PUT com um corpo JSON contendo o `título`, o `conteúdo` e/ou o `autor` atualizados.
    *   Após a atualização bem-sucedida, a API deve retornar o post de blog atualizado como um objeto JSON.
    *   Se um post de blog com o ID fornecido não existir, a API deve retornar um erro HTTP 404.

*   **DELETE /posts/{id}:** Deletar um post de blog específico identificado por seu ID.
    *   Este endpoint deve lidar com uma requisição DELETE.
    *   Após a exclusão bem-sucedida, a API deve retornar uma mensagem de sucesso (por exemplo, um código de status HTTP 204 No Content ou uma mensagem JSON simples).
    *   Se nenhum post de blog com o ID fornecido existir, a API deve retornar um erro HTTP 404.

## Requisitos e Restrições

*   **Stack:**
    *   **Linguagem:** Java 8 ou superior.
    *   **Framework (Opcional, mas Recomendado):** Spring Boot (com dependências mínimas) ou Spark Java.
    *   **Armazenamento de Dados:**
        *   Inicialmente, pode-se usar uma estrutura de dados na memória (como `HashMap` ou `ArrayList`).
        *   Opcionalmente, para uma implementação mais avançada, pode-se persistir os dados em um arquivo (JSON) ou em um banco de dados embutido (como H2).

    *   **Formato de Requisição/Resposta:** JSON.

*   **Estrutura e Organização do Código (Sugestão):**
    *   Classe `Post`: Modelo de dados para um post de blog (id, título, conteúdo, autor).
    *   Classe de Serviço (`PostService`): Lógica de negócios para operações CRUD em `Post`.
    *   Classe de Controller (`PostController`): Lida com os endpoints da API, recebe requisições, interage com o serviço e formata as respostas.

*   **Tratamento de Erros:**
    *   Implementar tratamento básico de erros, como retornar o código de status HTTP 404 quando um post com um ID específico não é encontrado.
    *   Utilizar códigos de status HTTP apropriados para indicar o resultado das requisições (200 OK, 201 Created, 204 No Content).

*   **Restrições:**
    *   Manter a implementação simples e focada nas funcionalidades principais.
    *   Não é necessário implementar autenticação ou autorização.
    *   Priorizar código limpo, legível e bem comentado.

## Métricas de Avaliação Potenciais

*   **Correção:** A API implementa corretamente todas as funcionalidades especificadas.
*   **Qualidade do Código:** O código é bem organizado, legível e de fácil manutenção.
*   **Tratamento de Erros:** A API lida com erros de forma adequada, retornando códigos de status HTTP apropriados.
*   **Uso dos Fundamentos de Java:** Demonstração de uma sólida compreensão dos conceitos principais de Java (POO, Collections Framework).

*   **Adesão aos Princípios RESTful:** Utilização correta dos métodos HTTP para as diferentes operações.

*   **Pontos Bônus (Opcional):**
    *   Implementação de persistência de dados.
    *   Validação básica de entrada.
    *   Implementação de testes unitários.
