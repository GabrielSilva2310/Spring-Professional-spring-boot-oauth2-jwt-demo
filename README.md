# Spring Boot OAuth2 JWT Demo (password grant type)


# Sobre o projeto
É um projeto de referência para ter o procedimento de incluir em uma aplicação Spring Boot a segurança,OAuth2 com JWT , para controlar o acesso , fazer login e controlar o acesso via rotas.
Foi clonado um projeto com uma estrutura básica e sem segurança implementada, e aplicado o passo a passo de incluir a segurança.
Desenvolvi esse projeto durante o capítulo Login e controle de acesso do Curso Java Spring Professional da [DevSuperior](https://devsuperior.com.br "Site da DevSuperior").

# Modelo de dados User-Role
![Modelo User-Role](https://github.com/GabrielSilva2310/Assets/blob/main/Images%20spring-boot-oauth2-jwt-demo/Modelo%20de%20Dados%20User-role.png)

# Checklist do Spring Security
![Checklist](https://github.com/GabrielSilva2310/Assets/blob/main/Images%20spring-boot-oauth2-jwt-demo/Checklist%20do%20Spring%20security.png)


# Tecnologias utilizadas
- Java 17
- Spring Boot 3
- Maven
- JPA/Hibernate
- H2 Database
- Spring Security
- OAuth2
- JWT
- Postman

## Postman Collection e Enviroment
Link para o Download (https://github.com/GabrielSilva2310/Assets/tree/main/Postman%20Collections%20and%20Enviroments/Spring-Professional-spring-boot-oauth2-jwt-demo)


# Como executar o projeto

Pré-requisitos: Java 17

-Importar Collection e Enviroment do Postman 

```bash
# clonar repositório
git clone https://github.com/GabrielSilva2310/Spring-Professional-spring-boot-oauth2-jwt-demo.git

# entrar na pasta do projeto
cd Spring-Professional-spring-boot-oauth2-jwt-demo

# executar o projeto
./mvnw spring-boot:run
```

- Testes no Postman:
  - Parte 1: Sem fazer Login
    - Request GET /products (deve retornar os produtos)
    - Request GET /products/1 (deve retornar 401 Unauthorized)
    - Request POST /products {"name":"Tablet"} (deve retornar 401 Unauthorized)
  - Parte 2: Login com Alex
    - Colocar alex@gmail.com no username do environment
    - Request login request (deve retornar 200 Ok com o token JWT. Esse token vai ser salvo na variável 'token' do enviroment)
    - Request GET /products (deve retornar os produtos)
    - Request GET /products/1 (deve retornar o produto 1)
    - Request POST /products {"name":"Tablet"} (deve retornar 403 Forbidden, pois esse usuário não possui o role_admin) 
  - Parte 3: Login com Maria
    - Colocar maria@gmail.com no username do environment
    - Request login request (deve retornar 200 Ok com o token JWT. Esse token vai ser salvo na variável 'token' do enviroment)
    - Request GET /products (deve retornar os produtos)
    - Request GET /products/1 (deve retornar o produto 1)
    - Request POST /products {"name":"Tablet"} (deve inserir o produto) 



# Autor

Gabriel Da Silva 

www.linkedin.com/in/gabriel-da-silva-457039193
