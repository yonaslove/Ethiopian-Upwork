# Ethiopian Upwork (AI-Powered Integrated Employment, Freelancing & Local Service Marketplace)

An intelligent, multi-sector platform connecting job seekers, freelancers, and local service providers with clients and employers using explainable AI semantic matching.

---

## ðŸ‘¥ Team Ownership & Responsibilities (4 Remote Developers)

| Developer | Role | Primary Tech Stack | Primary Branch |
| :--- | :--- | :--- | :--- |
| **DEV-1** | **Frontend & UX** | Next.js, React, TypeScript, Tailwind CSS, shadcn/ui | eature/frontend/* |
| **DEV-2** | **Backend & Database** | NestJS, TypeScript, Prisma ORM, PostgreSQL, Socket.IO | eature/backend/* |
| **DEV-3** | **AI / ML & Recommendations** | Python, FastAPI, Sentence Transformers, scikit-learn, pgvector | eature/ai/* |
| **DEV-4** | **DevOps, Security, QA & Integration** | Docker, Docker Compose, GitHub Actions, Nginx, Playwright, Jest, Pytest | eature/devops/* |

---

## ðŸ“ Project Architecture & Folder Structure

`	ext
Ethiopian-Upwork/
â”œâ”€â”€ frontend/                     # [DEV-1] Next.js 14+ Frontend Application
â”‚   â”œâ”€â”€ app/                      # Next.js App Router (Pages, layouts, routes)
â”‚   â”œâ”€â”€ components/               # Reusable UI components (shadcn/ui, buttons, modals, cards)
â”‚   â”œâ”€â”€ features/                 # Domain-driven features (jobs, services, auth, chat)
â”‚   â”œâ”€â”€ hooks/                    # Custom React hooks
â”‚   â”œâ”€â”€ lib/                      # Utility functions, clients, helpers
â”‚   â”œâ”€â”€ services/                 # API service clients and HTTP wrappers
â”‚   â”œâ”€â”€ types/                    # Shared TypeScript interfaces & types
â”‚   â””â”€â”€ public/                   # Static assets (images, icons, fonts)
â”‚
â”œâ”€â”€ backend/                      # [DEV-2] NestJS REST & WebSocket API
â”‚   â”œâ”€â”€ src/
â”‚   â”‚   â”œâ”€â”€ auth/                 # Authentication (JWT, guards, strategies, hashing)
â”‚   â”‚   â”œâ”€â”€ users/                # User management & account settings
â”‚   â”‚   â”œâ”€â”€ profiles/             # User & Provider profiles (skills, portfolio, education)
â”‚   â”‚   â”œâ”€â”€ jobs/                 # Employment module (job listings, requisitions)
â”‚   â”‚   â”œâ”€â”€ applications/         # Job applications & status pipeline
â”‚   â”‚   â”œâ”€â”€ projects/             # Freelancing module (projects, gigs)
â”‚   â”‚   â”œâ”€â”€ proposals/            # Freelance bidding & proposals
â”‚   â”‚   â”œâ”€â”€ contracts/            # Contracts, terms, and agreements
â”‚   â”‚   â”œâ”€â”€ milestones/           # Project milestones, deliverables, escrow status
â”‚   â”‚   â”œâ”€â”€ services/             # Local services catalog & offerings
â”‚   â”‚   â”œâ”€â”€ bookings/             # Local service booking & schedule management
â”‚   â”‚   â”œâ”€â”€ reviews/              # Rating & review system
â”‚   â”‚   â”œâ”€â”€ messaging/            # Real-time chat (Socket.IO) & message persistence
â”‚   â”‚   â”œâ”€â”€ notifications/        # In-app and push notification service
â”‚   â”‚   â”œâ”€â”€ recommendations/      # AI recommendation connector & caching
â”‚   â”‚   â”œâ”€â”€ admin/                # Platform moderation & administration
â”‚   â”‚   â””â”€â”€ common/               # Shared filters, interceptors, decorators, DTOs
â”‚   â”œâ”€â”€ prisma/                   # Prisma schema & migrations
â”‚   â”‚   â””â”€â”€ migrations/
â”‚   â””â”€â”€ test/                     # Backend unit & integration test suites
â”‚
â”œâ”€â”€ ai-service/                   # [DEV-3] Python FastAPI AI & Recommendation Microservice
â”‚   â”œâ”€â”€ app/
â”‚   â”‚   â”œâ”€â”€ api/                  # FastAPI router endpoints
â”‚   â”‚   â”œâ”€â”€ models/               # Pydantic data schemas & request/response models
â”‚   â”‚   â”œâ”€â”€ services/             # Core business logic services
â”‚   â”‚   â”œâ”€â”€ embeddings/           # Sentence Transformers & vector representation
â”‚   â”‚   â”œâ”€â”€ matching/             # Multi-factor matching algorithms
â”‚   â”‚   â”œâ”€â”€ extraction/           # CV parsing (PyMuPDF, docx) & skill extraction
â”‚   â”‚   â””â”€â”€ evaluation/           # Evaluation metrics (Precision@K, baseline comparisons)
â”‚   â””â”€â”€ tests/                    # Pytest test cases for NLP & matching engines
â”‚
â”œâ”€â”€ database/                     # [DEV-2 / DEV-4] Database Configurations
â”‚   â”œâ”€â”€ init/                     # SQL initialization scripts (pgvector extensions)
â”‚   â”œâ”€â”€ migrations/               # Raw migration backups & SQL patches
â”‚   â””â”€â”€ seeds/                    # Seed datasets for development & testing
â”‚
â”œâ”€â”€ docs/                         # Project Documentation
â”‚   â”œâ”€â”€ architecture/             # System diagrams, component flowcharts
â”‚   â”œâ”€â”€ api/                      # OpenAPI specs, postman collections
â”‚   â””â”€â”€ setup/                    # Local environment setup instructions
â”‚
â”œâ”€â”€ tests/                        # [DEV-4] End-to-End & Cross-service Integration Tests
â”‚   â”œâ”€â”€ e2e/                      # Playwright end-to-end user journey tests
â”‚   â”œâ”€â”€ integration/              # Multi-container integration tests
â”‚   â””â”€â”€ unit/                     # Platform-wide test suites
â”‚
â”œâ”€â”€ docker/                       # [DEV-4] Docker Configuration Files
â”‚   â”œâ”€â”€ frontend/                 # Dockerfile for Next.js
â”‚   â”œâ”€â”€ backend/                  # Dockerfile for NestJS
â”‚   â”œâ”€â”€ ai-service/               # Dockerfile for Python FastAPI
â”‚   â””â”€â”€ nginx/                    # Reverse proxy & routing configuration
â”‚
â”œâ”€â”€ .github/                      # GitHub Configuration & Automation
â”‚   â”œâ”€â”€ workflows/                # CI/CD GitHub Actions (Lint, Test, Build, Docker)
â”‚   â”œâ”€â”€ ISSUE_TEMPLATE/           # Standard issue templates for bug/feature reports
â”‚   â””â”€â”€ PULL_REQUEST_TEMPLATE.md  # Team PR review template
â”‚
â”œâ”€â”€ docker-compose.yml            # Multi-container orchestration (Dev environment)
â”œâ”€â”€ .env.example                  # Environment variable blueprint
â”œâ”€â”€ .editorconfig                 # Unified code formatting guidelines
â”œâ”€â”€ .gitignore                    # Git ignore configurations
â”œâ”€â”€ Roadmap.md                    # Project roadmap and strategic milestones
â”œâ”€â”€ TECH_STACK.md                 # Complete technology stack specifications
â””â”€â”€ Todo.md                       # Task distribution & delivery checklist
`

---

## ðŸš€ Branching & Collaboration Workflow (GitHub Flow)

1. **main**: Production-ready, stable codebase.
2. **develop**: Integration branch where all approved features are combined.
3. **Feature Branches**:
   - eature/frontend/* (DEV-1)
   - eature/backend/* (DEV-2)
   - eature/ai/* (DEV-3)
   - eature/devops/* (DEV-4)

### Development Process
- Create your feature branch from develop.
- Implement features with appropriate unit/integration tests.
- Push your feature branch and open a Pull Request targeting develop.
- Pull Requests require review and passing CI checks before merging.
