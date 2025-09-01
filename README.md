# Transferência - Infraestrutura

Este repositório contém a infraestrutura do projeto **Transferência**, utilizando **Docker Compose** para orquestrar o frontend e backend da aplicação. Com este repositório, você pode subir toda a aplicação com um único comando, incluindo rede interna entre os containers e mapeamento de portas.

---

## Pré-requisitos

- [Docker](https://www.docker.com/get-started) instalado
- [Docker Compose](https://docs.docker.com/compose/install/) instalado
- Acesso à internet para baixar as imagens do Docker Hub

---

## Estrutura do projeto

- `docker-compose.yml` – Arquivo principal para subir toda a aplicação.
- `frontend/` – Container do frontend Vue.js, servido com Nginx.
- `backend/` – Container do backend Java Spring Boot.
- `nginx.conf` – Configuração do Nginx para SPA (frontend).

---

## Subindo o projeto

1. Clone este repositório:

```bash
git clone https://github.com/Desafio-Agendamento-Trasnferencia/transferencia-infra.git
cd transferencia-infra
```

2. Suba todos os containers usando Docker Compose:

```bash
docker-compose up -d
```

## Observações

- O frontend usa Vue.js e Nginx; o arquivo nginx.conf garante que todas as rotas do SPA funcionem corretamente mesmo após refresh.
- O backend é uma aplicação Java 11 (Spring Boot) e está configurado para aceitar conexões externas.
- Ambos os serviços estão na mesma rede Docker para que o frontend possa se comunicar com o backend usando http://localhost:8080.
