# Integration with pk.uchet.kz (Spring Boot)

Простой backend-сервис для поиска компаний по БИН через API https://pk.uchet.kz и сохранения результатов в базу PostgreSQL.

## 📚 Технологии

- Java 17
- Spring Boot (WebFlux, Data R2DBC)
- PostgreSQL
- WebClient (реактивный HTTP-клиент)
- Maven

## 🚀 Запуск

### 1. Настрой `.env` или `application.yml`

```yaml
spring:
  r2dbc:
    url: r2dbc:postgresql://localhost:5432/company_db
    username: postgres
    password: your_password

external:
  uchet:
    base-url: "https://pk.uchet.kz"
    api-token: "ваш API токен"
```
### 2. Запуск
```
./mvnw spring-boot:run
```

📡 API

GET /api/company/{bin}
🔍 Поиск компании по БИН.
Если компания найдена — сохраняется в базу, если уже есть — не дублируется.
