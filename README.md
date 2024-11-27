Projeto Java SpringBoot que consiste em uma aplicação web para gerenciar listas de games. O projeto foi desenvolvido ao decorrer do intensivão JavaSpring, um evento organizado pelo professor Nélio Alves que ensinou noções básicas do framework SpringBoot.

## Tecnologias

* **Backend:** Spring Boot (Java)
* **Banco de Dados:** PostgreSQL
* **Postman:** Testes de requisições da API.
* **Intelij:** Ambiente de desenvolvimento de código.

## Como executar o projeto

**Pré-requisitos:**

* Ter o Java instalado na sua máquina.
* Ter o Maven ou Gradle instalado na sua máquina.
* Ter um banco de dados PostgreSQL instalado e configurado (ou altere a configuração de conexão no arquivo `application.properties`).

**Passos:**

1. **Clone o repositório:**
   ```bash
   git clone <link-do-seu-repositorio>
   ```

2. **Navegue até o diretório do projeto:**
   ```bash
   cd <nome-do-diretorio>
   ```

3. **Execute o comando abaixo para construir o projeto usando Maven (se o projeto usar Maven):**
   ```bash
   mvn clean install
   ```
   **ou** execute o comando abaixo para construir o projeto usando Gradle (se o projeto usar Gradle):
   ```bash
   ./gradlew build
   ```

4. **Execute a aplicação:**
   ```bash
   mvn spring-boot:run
   ```
   **ou**
   ```bash
   ./gradlew bootRun
   ```

5. **Acesse a aplicação:**  A aplicação estará disponível em `http://localhost:8080`.


## Rotas da API

* **`/games`**:  Endpoint para buscar informações sobre jogos.
    * **`GET /games`**: Retorna uma lista de jogos com informações mínimas (`GameMinDTO`).
    * **`GET /games/{id}`**: Retorna as informações completas de um jogo específico (`GameDTO`).

* **`/lists`**: Endpoint para gerenciar listas de jogos.
    * **`GET /lists`**: Retorna uma lista de todas as listas de jogos (`GameListDTO`).
    * **`GET /lists/{listId}/games`**: Retorna a lista de jogos de uma lista específica (`GameMinDTO`).
    * **`POST /lists/{listId}/replacement`**: Permite mover um jogo na lista, recebendo um corpo JSON com `sourceIndex` e `destinationIndex` (`ReplacementDTO`).

## Estrutura do Projeto
```
dslist/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── devsuperior/
│   │   │           └── dslist/
│   │   │               ├── controllers/  (Controllers REST)
│   │   │               ├── dto/          (DTOs)
│   │   │               ├── entities/     (Entidades JPA)
│   │   │               ├── projections/  (Projections JPA)
│   │   │               ├── repositories/ (Repositórios JPA)
│   │   │               └── services/     (Serviços)
│   │   └── resources/
│   │       └── application.properties  (Configurações)
│   └── test/
└── ...
```