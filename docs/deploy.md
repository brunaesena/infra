# 📦 Guia de Deploy - Sistema de Gerenciamento

Este guia descreve como subir toda a stack da aplicação localmente usando Docker Compose. O sistema é composto por:

- Frontend Angular
- Microsserviço de Usuários (Spring Boot)
- Microsserviço de Tarefas (Spring Boot)
- Banco de dados PostgreSQL

---

## 🚀 Passo a passo para rodar localmente

### 1. Estrutura esperada dos repositórios

Clone todos os repositórios no mesmo nível de diretório:

```bash
git clone https://github.com/brunaesena/frontend-angular-desafio
git clone https://github.com/brunaesena/infra
git clone https://github.com/brunaesena/user-microservice
git clone https://github.com/brunaesena/task-microservice
```

A estrutura resultante será:

```
root/
├── frontend-angular-desafio
├── infra
├── task-microservice
└── user-microservice
```

### 2. Subir os containers

Acesse a pasta `infra` e execute:

```bash
docker-compose up --build
```

Isso irá subir os seguintes serviços:
- **Frontend** acessível em: http://localhost:4200
- **User Service**: http://localhost:8081/api/users
- **Task Service**: http://localhost:8082/api/tasks
- **PostgreSQL** para cada serviço, nas portas 5432 e 5433

---

## ✅ Rodando os Testes dos Microsserviços

Cada backend (`user-microservice` e `task-microservice`) possui testes que podem ser executados com:

```bash
mvn clean install
```

Execute esse comando dentro da pasta de cada microsserviço para rodar os testes unitários e de integração.

---

## ⚙️ Variáveis de Ambiente

Cada microsserviço define suas variáveis de ambiente diretamente no `docker-compose.yml`, incluindo:

- `SPRING_DATASOURCE_URL`
- `POSTGRES_USER`
- `POSTGRES_PASSWORD`

A aplicação está configurada para se conectar automaticamente aos serviços corretos definidos nos containers.

---

## 🛠 Parar os containers

Para parar todos os serviços:

```bash
docker-compose down
```

---

## ✅ Requisitos

- Docker e Docker Compose instalados
- Node.js (para build do frontend)
- Angular CLI (`npm install -g @angular/cli`)
- Java 17 e Maven

---

## 📌 Observações

- Certifique-se de que as portas `4200`, `8081`, `8082`, `5432` e `5433` estejam livres.
- O frontend Angular é servido via Nginx dentro do container.
- Os microsserviços usam Spring Boot com PostgreSQL para persistência.

---
