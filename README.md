# CRUD_JWT


# API JWT com Spring Boot

API REST desenvolvida com autenticação e autorização via JWT, utilizando Spring Boot, Spring Security, H2, Swagger, Actuator e Docker.

---

## 🚀 Tecnologias Utilizadas

- Java 17  
- Spring Boot 3.5.3  
- Spring Security  
- Spring Data JPA  
- H2 Database  
- JWT (JSON Web Token)  
- Swagger/OpenAPI  
- Spring Boot Actuator  
- Docker  

---

## ⚙️ Requisitos

- Java 17 instalado  
- Maven ou Wrapper (`mvnw`)  
- Docker instalado

---

## 📦 Como compilar o projeto

```bash
./mvnw clean package
No Windows: mvnw.cmd clean package

Isso irá gerar um arquivo .jar dentro da pasta target/.

🐳 Como rodar com Docker
Certifique-se de ter um arquivo Dockerfile na raiz do projeto com o seguinte conteúdo:

Dockerfile
Copiar
Editar
FROM eclipse-temurin:17-jdk-alpine
VOLUME /tmp
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]
Build da imagem:

bash
Copiar
Editar
docker build -t apijwt .
Rode o container:

bash
Copiar
Editar
docker run -p 8080:8080 apijwt
A aplicação estará disponível em: http://localhost:8080

📑 Endpoints principais
Método	Endpoint	Descrição
POST	/auth/login	Autentica e gera um JWT
POST	/auth/register	Registra novo usuário
GET	/auth/users	Lista todos os usuários
DELETE	/auth/users/{id}	Remove um usuário
GET	/actuator/health	Verifica status da API
GET	/actuator/prometheus	Métricas para Prometheus

🛠️ Acesso ao H2
URL: http://localhost:8080/h2-console

JDBC URL: jdbc:h2:file:./src/main/resources/db/bancoDeDados

Usuário: sa

Senha: (vazia)

🔐 Exemplo de login no Swagger
Acesse: http://localhost:8080/swagger-ui.html

Faça um POST em /auth/login com:

json
Copiar
Editar
{
  "username": "admin",
  "password": "123"
}
Copie o token gerado e clique no botão "Authorize" no Swagger. Use:

php-template
Copiar
Editar
Bearer <seu-token>
📈 Monitoramento com Actuator + Prometheus
Health Check:
http://localhost:8080/actuator/health

Métricas Prometheus:
http://localhost:8080/actuator/prometheus

✅ Usuários padrão (DataInitializer)
Username	Senha	Papel
admin	123	ROLE_ADMIN
user	123	ROLE_USER

📝 Autor
Richard Luiz

Projeto acadêmico com Spring Boot, JWT, e Docker

yaml
Copiar
Editar

---

Se quiser, posso criar esse arquivo e te enviar diretamente ou formatar para Visual Studio Code. Deseja isso?
