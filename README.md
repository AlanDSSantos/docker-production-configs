# 🐳 Docker Production Configs

Configurações Docker Compose utilizadas em ambientes de produção para múltiplos clientes em infraestrutura cloud (AWS e DigitalOcean).

## 📁 Estrutura

```
docker-production-configs/
├── nginx/
│   └── docker-compose.yml      # Proxy reverso com SSL/TLS
├── tomcat/
│   └── docker-compose.yml      # Servidor de aplicação Java
├── spring-boot/
│   └── docker-compose.yml      # Microsserviços Java
├── rabbitmq/
│   └── docker-compose.yml      # Message broker
├── mysql/
│   └── docker-compose.yml      # Banco de dados MySQL 8
├── postgresql/
│   └── docker-compose.yml      # Banco de dados PostgreSQL 15
├── redis/
│   └── docker-compose.yml      # Cache em memória
├── watchtower/
│   └── docker-compose.yml      # Atualização automática de containers
└── README.md
```

## 🚀 Como usar

```bash
# Clone o repositório
git clone https://github.com/AlanDSSantos/docker-production-configs.git

# Entre na pasta do serviço desejado
cd docker-production-configs/nginx

# Suba o serviço
docker compose up -d

# Verifique o status
docker compose ps
```

## ⚙️ Serviços disponíveis

| Serviço | Descrição | Porta |
|---|---|---|
| **Nginx** | Proxy reverso com SSL termination e Let's Encrypt | 80, 443 |
| **Apache Tomcat** | Servidor de aplicação Java com healthcheck | 8080 |
| **Spring Boot** | Microsserviços Java em produção | 8080 |
| **RabbitMQ** | Message broker com painel de gestão | 5672, 15672 |
| **MySQL** | Banco de dados relacional MySQL 8 | 3306 |
| **PostgreSQL** | Banco de dados relacional PostgreSQL 15 | 5432 |
| **Redis** | Cache em memória e filas | 6379 |
| **Watchtower** | Atualização automática de imagens Docker | — |

## 📋 Boas práticas aplicadas

- `restart: unless-stopped` — containers sobem automaticamente após reboot
- `healthcheck` — monitoramento de saúde da aplicação dentro do container
- `mem_limit` e `cpus` — limites de recursos para evitar sobrecarga
- Redes Docker isoladas por serviço
- Volumes nomeados para persistência de dados
- Variáveis de ambiente via arquivo `.env`
- Imagens Alpine quando possível — mais leves e seguras

## 🔗 Projetos relacionados

- [prometheus-grafana-stack](https://github.com/AlanDSSantos/prometheus-grafana-stack) — Stack completa de observabilidade com Prometheus, Grafana e Loki

## 🛠️ Tecnologias

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat&logo=rabbitmq&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

---

Desenvolvido por [Alan Santos](https://linkedin.com/in/alansantos2701) — DevOps Support Specialist
