# **ClientAddressAPI**

## Descrição

O **ClientAddressAPI** é uma API RESTful desenvolvida com **Spring Boot** que permite a persistência de dados de clientes e seus respectivos endereços. A API integra-se com o serviço de consulta de CEP do **ViaCEP** para fornecer dados completos de endereço com base no CEP fornecido. O projeto utiliza **Spring Data JPA**, **H2 Database** (para armazenamento em memória) e **OpenFeign** para comunicação com o ViaCEP.

## Funcionalidades

- **CRUD de Clientes**: Permite criar, ler, atualizar e deletar informações de clientes.
- **Integração com ViaCEP**: Consulta o ViaCEP para buscar dados completos de endereço com base no CEP fornecido.
- **Armazenamento em Banco de Dados H2**: Utiliza o banco de dados em memória H2 para persistir dados de clientes e endereços.
- **Documentação OpenAPI (Swagger)**: A API é documentada automaticamente com o Swagger/OpenAPI, permitindo interações visuais com a API.

## Tecnologias Utilizadas

- **Spring Boot**: Framework principal para a criação da aplicação.
- **Spring Data JPA**: Para persistência de dados no banco de dados.
- **H2 Database**: Banco de dados em memória para persistência local.
- **OpenFeign**: Para integração com a API ViaCEP.
- **Swagger/OpenAPI**: Documentação interativa da API.
- **JUnit**: Para testes unitários e de integração.

## Como Rodar o Projeto

### Requisitos

Antes de rodar o projeto, verifique se você tem as seguintes ferramentas instaladas:

- **Java 11** ou superior
- **Maven** (Para gerenciar dependências e rodar o projeto)
- **IDE** (Ex: IntelliJ IDEA, Eclipse)

### Passos

1. **Clone o repositório**:

   ```bash
   git clone https://github.com/SEU_USUARIO/ClientAddressAPI.git
   ```

2. **Entre na pasta do projeto**:

   ```bash
   cd ClientAddressAPI
   ```

3. **Compile e execute a aplicação com Maven**:

   ```bash
   ./mvnw spring-boot:run
   ```

   Ou, se você estiver usando o Maven diretamente:

   ```bash
   mvn spring-boot:run
   ```

   A aplicação será iniciada na porta `8080` por padrão.

### Endpoints

A API oferece os seguintes endpoints:

- **GET** `/clientes`: Retorna todos os clientes.
- **GET** `/clientes/{id}`: Retorna o cliente com o ID especificado.
- **POST** `/clientes`: Cria um novo cliente com as informações fornecidas.
- **PUT** `/clientes/{id}`: Atualiza o cliente com o ID especificado.
- **DELETE** `/clientes/{id}`: Deleta o cliente com o ID especificado.

### Exemplo de Requisição

#### Criar Cliente

**Endpoint**: `POST /clientes`

**Corpo da Requisição**:

```json
{
  "nome": "Rodrigo",
  "endereco": {
    "cep": "14801788"
  }
}
```

#### Consultar Cliente por ID

**Endpoint**: `GET /clientes/{id}`

Exemplo: `GET /clientes/1`

---

## Documentação Interativa

A documentação da API está disponível via Swagger. Após iniciar o projeto, você pode acessar a interface Swagger no seguinte endereço:

```
http://localhost:8080/swagger-ui.html
```

## Testes

Para rodar os testes unitários e de integração do projeto, execute o comando:

```bash
./mvnw test
```

Os testes garantem o correto funcionamento dos serviços e controladores da API.

## Contribuição

Se você deseja contribuir com este projeto, siga os seguintes passos:

1. Faça um **fork** deste repositório.
2. Crie uma **branch** para sua modificação (`git checkout -b feature/alguma-modificacao`).
3. Faça suas alterações e adicione testes, se necessário.
4. Faça o **commit** das suas alterações (`git commit -am 'Adiciona nova funcionalidade'`).
5. **Push** para o repositório remoto (`git push origin feature/alguma-modificacao`).
6. Abra um **pull request** para a branch principal.