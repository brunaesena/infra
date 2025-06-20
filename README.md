# Infraestrutura - Sistema de Gerenciamento de Tarefas e Usuários

Este repositório contém a infraestrutura Docker necessária para rodar localmente toda a aplicação de microserviços, incluindo:

- Frontend Angular
- Microsserviço de Usuários (Java Spring Boot)
- Microsserviço de Tarefas (Java Spring Boot)
- Banco de dados PostgreSQL

---

## 🚀 Como rodar o projeto completo

1. Certifique-se de ter clonado todos os repositórios necessários no mesmo nível de pastas:

```
git clone https://github.com/brunaesena/frontend-angular-desafio
git clone https://github.com/brunaesena/infra
git clone https://github.com/brunaesena/user-microservice
git clone https://github.com/brunaesena/task-microservice
```

2. Acesse a pasta `infra` e rode:

```bash
docker-compose up --build
```

3. Acesse a aplicação no navegador:

- Frontend: http://localhost:4200
- API de Usuários: http://localhost:8081/api/users
- API de Tarefas: http://localhost:8082/api/tasks

---

## 📄 Documentação

Consulte o guia completo de deploy em [`docs/deploy.md`](docs/deploy.md) para mais detalhes, incluindo pré-requisitos, testes e estrutura da aplicação.

---
