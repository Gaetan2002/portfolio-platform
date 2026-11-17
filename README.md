# Portfolio Platform

A personal platform that brings together my portfolio, one-click project demos,
a knowledge base and an AI assistant, hosted on my own domain.

It is also a learning project: as a 2nd-year computer science student at IFOSUP
(Belgium), I build it step by step to learn how to create a real, complete
application, from analysis to deployment on Kubernetes.

## Project status

Current phase: **Phase 0 – Analysis**.
See [PROJECT_STATUS.md](PROJECT_STATUS.md) for details.

## Documentation

- [Project overview](docs/project-overview.md): goals, scope, tech stack, key
  decisions, modules, roles and roadmap
- [Architecture Decision Records](docs/adr/): important decisions and the
  reasons behind them
- [Phase summaries](docs/progress/): one summary per completed phase
- [Analysis](docs/analysis/): requirements, use cases, database schema and
  mockups

## Architecture

The platform is built around a C# API that contains all the business logic,
security and data access. A Next.js front-end displays the pages, and a separate
Python service handles the AI features.

A detailed architecture diagram will be added during Phase 1.

## Tech stack

- **Back-end:** C#, ASP.NET Core, Entity Framework
- **Front-end:** React, Next.js, TypeScript, Tailwind CSS, shadcn/ui, Motion,
  React Three Fiber
- **AI service:** Python, FastAPI, Claude API (RAG)
- **Database:** PostgreSQL with pgvector
- **Cache and messaging:** Redis, RabbitMQ
- **File storage:** MinIO
- **Desktop application:** C# Avalonia
- **Containers:** Docker and Docker Compose, then Kubernetes (k3s)
- **Monitoring:** Prometheus, Grafana, Loki

## Getting started

> Available from Phase 1 (MVP), when the first version of the API is ready.

## Configuration

> Available from Phase 1. Secrets will never be stored in the repository: they
> will be provided through environment variables.

## Tests

> Available from Phase 1: unit tests (xUnit) and integration tests
> (Testcontainers).

## Deployment

> Available from Phase 2: deployment on a VPS with my own domain, automatic
> HTTPS (Traefik) and CI/CD (GitHub Actions).

## Folder structure

```
portfolio-platform/
├── docs/
│   ├── adr/                  # Architecture Decision Records
│   ├── analysis/             # Requirements, use cases, database schema
│   │   └── mockups/          # Mockups of the application's pages
│   ├── progress/             # One summary per completed phase
│   └── project-overview.md   # Detailed project overview
├── .gitignore
├── PROJECT_STATUS.md         # Global project status
└── README.md
```

## Author

[Gaetan2002](https://github.com/Gaetan2002)
