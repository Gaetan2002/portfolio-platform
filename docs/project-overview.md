# Overview

The project is a personal online platform hosted on my own domain name, bringing together my entire IT background:
portfolio, one-click project demos, knowledge base, and AI assistant.

## Goals

* **Dual objective**: to have a useful everyday tool (for reviewing, finding a concept, or a piece of code) and a
  showcase to find an internship or job.

* **Learning objective**: to build a complete, end-to-end project featuring front-end, back-end, API, database,
  security, AI, Docker, and Kubernetes.

* **Context**: 2nd-year IT bachelor's student at IFOSUP (Belgium). I am learning C# at school and have the basics of
  Python. I work on Fedora Linux.

* **Single-user version**: I am the sole owner of a profile. No open registration, but the database includes an
  `owner_id` on each data entity and a feature flag to enable registrations later.

* **Expected duration**: the entire duration of the bachelor's degree, with a first online-ready version starting from
  Phase 2.

## Tech stack

The back-end is in C#, the front-end in React with Next.js, and the AI in a separate Python service.

| Part                                 | Technology                                     | Why                                                                       | 
|--------------------------------------|------------------------------------------------|---------------------------------------------------------------------------| 
| Main API, workers, demo orchestrator | C# (ASP.NET Core, Entity Framework)            | Language learned at school, highly demanded in Belgium                    | 
| Web front-end                        | React + Next.js + TypeScript                   | Richest ecosystem for modern design and 3D, server-side rendering for SEO | 
| Styling and components               | Tailwind CSS, shadcn/ui                        | Modern and consistent design                                              | 
| Animations and 3D                    | Motion, GSAP, React Three Fiber + drei         | UI animations, scroll animations, 3D                                      | 
| AI service                           | Python (FastAPI), Claude API                   | Document ingestion, embeddings, RAG                                       | 
| Database                             | PostgreSQL + pgvector                          | Classical data and vectors for AI in the same database                    | 
| Cache and messaging                  | Redis, RabbitMQ                                | Performance and background tasks                                          | 
| Files                                | MinIO                                          | Storage for attachments and screenshots                                   | 
| Desktop application                  | C# Avalonia                                    | Cross-platform, runs on Fedora                                            | 
| Containers                           | Docker + Docker Compose, then Kubernetes (k3s) | Main learning objective                                                   | 
| Monitoring                           | Prometheus, Grafana, Loki                      | Metrics and logs                                                          | 

## Key decisions

- Next.js is only used for the web front-end. The business logic, data access, and security stay in the C# API.
- Front-end tools are added progressively, in this order: Next.js, TypeScript and Tailwind, then shadcn/ui, then Motion,
  and 3D last.
- Docker is the reference tool for the project instead of Podman, which is installed by default on Fedora.
    - Docker is the industry standard; it is far more requested in job offers.
    - Most of the courses and tutorials use Docker.

## Functional Modules

The platform has eight modules; the demo launcher and the AI assistant are the most educational.

1. **Public profile and portfolio**

* Presentation, timeline background, skills with proficiency levels, certifications, training

* Project cards: description, screenshots, technologies, what I learned, GitHub link

* Automated PDF resume generation

* Contact form for recruiters

* Multiple public profiles depending on the target audience (application developer, medical IT)

2. **GitHub integration**

* OAuth login, repository, language, and activity synchronization

* Webhooks: automatic updates on every push

* Automatic skill suggestions based on projects

3. **Demo launcher ("Try in one click")**

* A temporary Docker container per visitor, accessible at `demo-xyz.<my domain>`

* Automatic destruction after 15 minutes, queue system if too many requests

4. **Knowledge base**

* Markdown notes, organized by topic, IFOSUP courses, and tags, with links between notes

* Snippet library with syntax highlighting

* Attachments, version history, full-text search

5. **AI Assistant (RAG) with two modes**

* Private mode: knows everything (notes, code, projects, courses) and cites its sources. Examples: "Where did I use a
  stored procedure?", "In which file did I handle image uploads?"

* Public mode: chatbot for visitors, limited to public content

6. **Review and learning tracking**

* Quizzes and flashcards generated from notes, spaced repetition

* Progress tracking by course and skill

7. **Desktop application (C# Avalonia)**

* Offline note editing, synchronization upon reconnecting

* Small C# command-line tool to add a note or snippet directly from the terminal

8. **Administration and statistics**

* Invitation management, demo and AI quotas

* Statistics: visits, viewed projects, launched demos, received contacts

* Notifications: profile viewed by a recruiter, demo error, failed backup

## Roles and Users

No one else creates a profile, but five types of actors use the platform, each with their own permissions.

| Role                     | Access                                                   | Authentication                                     | 
|--------------------------|----------------------------------------------------------|----------------------------------------------------| 
| Owner (me)               | Everything                                               | Two-factor authentication with mandatory passkey   | 
| Anonymous visitor        | Public profile, demos with quotas, public chatbot        | None, limited by IP address                        | 
| Invited recruiter        | Plus: detailed resume, private projects, contact details | Expiring invitation link (e.g., 7 days), revocable | 
| Teacher or grading panel | Reading a specific project (capstone project)            | Invitation link limited to that project            | 
| Service accounts         | Microservices, desktop app, GitHub webhooks, CLI tool    | API keys or restricted-permission tokens           | 

## Phased Roadmap

The project progresses through ten phases; after Phase 2, a first version is online and improves with each phase.

0. **Analysis**: specifications, use cases, database model, mockups. I am learning analysis (in connection with my
   courses).

1. **MVP**: C# API, PostgreSQL, profile and projects, simple public page, Docker Compose. I am learning back-end basics.

2. **Online**: hosting on my domain, HTTPS, CI/CD. I am learning deployment, Linux, and networking.

3. **Access**: authentication, roles, invitation links. I am learning security.

4. **Knowledge**: notes, snippets, search, files. I am learning advanced databases and storage.

5. **GitHub**: OAuth, synchronization, webhooks, worker, and RabbitMQ. I am learning services and message queues.

6. **AI**: Python service, RAG, both modes. I am learning AI, Python, and AI security.

7. **Demos**: orchestrator and temporary containers. I am learning Docker in depth.

8. **Scaling**: Kubernetes (k3s), autoscaling, monitoring. I am learning Kubernetes and observability.

9. **Bonus**: desktop app, review, PDF resume, statistics, 3D on the homepage.
