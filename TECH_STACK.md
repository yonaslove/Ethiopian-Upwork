# TECH_STACK.md

# AI-Powered Integrated Employment, Freelancing & Local Service Marketplace

**Team:** 4 Remote Developers
**Architecture:** Modular Full-Stack + Dedicated AI Service
**Repository:** GitHub
**Development:** Agile + GitHub Flow
Operating System:  Windows 11
Version Control: Git + GitHub 
Containerization: Docker Desktop

# 1. Technology Stack Overview

```text
┌─────────────────────────────────────────────────────────────┐
│                         USERS                               │
│        Job Seekers | Freelancers | Clients | Providers      │
└────────────────────────────┬────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                    FRONTEND APPLICATION                      │
│                                                             │
│        Next.js + React + TypeScript                         │
│        Tailwind CSS + shadcn/ui                             │
│        React Hook Form + Zod                                │
└────────────────────────────┬────────────────────────────────┘
                             │
                    REST API / WebSocket
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                     BACKEND API                              │
│                                                             │
│        NestJS + TypeScript                                  │
│        Prisma ORM                                           │
│        JWT Authentication                                   │
│        REST + Swagger/OpenAPI                               │
└──────────────┬──────────────────────────────┬───────────────┘
               │                              │
               ▼                              ▼
┌─────────────────────────┐      ┌────────────────────────────┐
│      PostgreSQL         │      │       Redis                │
│                         │      │                            │
│ Users                   │      │ Cache                      │
│ Jobs                    │      │ Sessions                   │
│ Projects                │      │ Rate limiting              │
│ Services                │      │ Background jobs            │
│ Applications            │      │                            │
│ Reviews                 │      └────────────────────────────┘
│ + pgvector              │
└────────────┬────────────┘
             │
             │ AI Request
             ▼
┌─────────────────────────────────────────────────────────────┐
│                       AI SERVICE                             │
│                                                             │
│        Python + FastAPI                                    │
│                                                             │
│        Sentence Transformers                                │
│        Transformers                                         │
│        scikit-learn                                         │
│        NLP / Embeddings                                     │
│        Requirement Extraction                               │
│        Semantic Matching                                    │
│        Ranking                                              │
│        Explainable Recommendations                          │
└─────────────────────────────────────────────────────────────┘

             INFRASTRUCTURE
                     │
       ┌─────────────┼─────────────┐
       ▼             ▼             ▼
    Docker       GitHub        GitHub Actions
                 Git             CI/CD
```

---

# 2. Core Technology Stack

| Layer             | Technology            | Purpose                        |
| ----------------- | --------------------- | ------------------------------ |
| Frontend          | Next.js               | Web application framework      |
| Frontend          | React                 | Component-based UI             |
| Language          | TypeScript            | Type-safe development          |
| Styling           | Tailwind CSS          | Responsive styling             |
| UI Components     | shadcn/ui             | Reusable UI components         |
| Forms             | React Hook Form       | Form management                |
| Validation        | Zod                   | Schema validation              |
| Backend           | NestJS                | Backend architecture           |
| Backend Language  | TypeScript            | Type-safe backend              |
| API               | REST                  | Frontend/backend communication |
| API Documentation | Swagger/OpenAPI       | API documentation              |
| ORM               | Prisma                | Database access                |
| Database          | PostgreSQL            | Main relational database       |
| Vector Search     | pgvector              | AI embeddings/search           |
| Cache             | Redis                 | Cache and temporary data       |
| Real-time         | Socket.IO             | Messaging/notifications        |
| AI                | Python                | AI/ML development              |
| AI API            | FastAPI               | AI microservice                |
| Embeddings        | Sentence Transformers | Semantic representation        |
| ML                | scikit-learn          | Ranking/evaluation             |
| NLP               | Transformers          | NLP/AI processing              |
| CV Parsing        | PyMuPDF               | PDF processing                 |
| DOCX Parsing      | python-docx           | Word document processing       |
| Maps              | Leaflet               | Map interface                  |
| Map Data          | OpenStreetMap         | Location/map data              |
| Testing           | Jest                  | Backend/frontend tests         |
| API Testing       | Supertest             | Backend API testing            |
| E2E               | Playwright            | Browser testing                |
| Python Testing    | Pytest                | AI tests                       |
| Containers        | Docker                | Development/deployment         |
| CI/CD             | GitHub Actions        | Automated testing/deployment   |
| Version Control   | Git/GitHub            | Collaboration                  |
| Reverse Proxy     | Nginx                 | Production web routing         |


---

# 3. Frontend Stack

## 3.1 Next.js

Use **Next.js** as the main frontend framework.

Responsibilities:

* Page routing
* Server/client rendering
* API integration
* Authentication state
* SEO
* Application structure

Main application:

```text
frontend/
├── app/
├── components/
├── features/
├── hooks/
├── lib/
├── services/
├── types/
└── public/
```

---

# 4. React

React is used to create reusable interface components.

Example components:

```text
Button
Modal
Input
SearchBar
JobCard
ProjectCard
ServiceCard
ProviderCard
Rating
MatchScore
RecommendationCard
ChatWindow
Notification
```

---

# 5. TypeScript

TypeScript is required for frontend and backend development.

Benefits:

* Type safety
* Better IDE support
* Easier refactoring
* Fewer runtime errors
* Shared API types where appropriate

Example:

```typescript
interface Provider {
  id: string;
  name: string;
  skills: string[];
  rating: number;
  experienceYears: number;
}
```

---

# 6. Tailwind CSS

Use Tailwind CSS for responsive UI.

Required:

* Mobile responsive design
* Tablet support
* Desktop support
* Consistent spacing
* Consistent typography
* Dark/light support if required

---

# 7. shadcn/ui

Use shadcn/ui for common interface components.

Examples:

```text
Button
Dialog
Dropdown
Tabs
Table
Card
Form
Toast
Select
Pagination
```

The team should customize components to match the project's design.

---

# 8. Forms & Validation

## React Hook Form

Use for:

* Registration
* Login
* Job posting
* Project posting
* Service request
* Proposal
* Booking
* Profile editing

## Zod

Use for frontend validation.

Example:

```text
Job Title
Description
Skills
Budget
Location
Deadline
Employment Type
```

---

# 9. Backend Stack

## NestJS

NestJS is the main backend framework.

Responsibilities:

* Authentication
* Authorization
* Users
* Profiles
* Jobs
* Applications
* Projects
* Proposals
* Contracts
* Services
* Bookings
* Reviews
* Messaging
* Notifications
* AI integration
* Admin

Recommended structure:

```text
backend/
├── src/
│   ├── auth/
│   ├── users/
│   ├── profiles/
│   ├── jobs/
│   ├── applications/
│   ├── projects/
│   ├── proposals/
│   ├── contracts/
│   ├── milestones/
│   ├── services/
│   ├── bookings/
│   ├── reviews/
│   ├── messaging/
│   ├── notifications/
│   ├── recommendations/
│   ├── admin/
│   └── common/
│
├── prisma/
└── test/
```

---

# 10. API Architecture

Use REST APIs for the main application.

Example:

```text
/api/auth
/api/users
/api/profiles

/api/jobs
/api/jobs/:id/apply
/api/applications

/api/projects
/api/projects/:id/proposals
/api/proposals

/api/contracts
/api/milestones

/api/services
/api/service-requests
/api/bookings

/api/reviews

/api/messages
/api/notifications

/api/search
/api/recommendations

/api/admin
```

---

# 11. API Documentation

Use **Swagger/OpenAPI**.

Every API should document:

* Endpoint
* HTTP method
* Parameters
* Request body
* Response
* Authentication
* Error responses

Example:

```text
POST /api/recommendations

Request:
{
  "opportunityId": "123"
}

Response:
{
  "recommendations": [
    {
      "providerId": "456",
      "score": 0.94
    }
  ]
}
```

---

# 12. Database

## PostgreSQL

PostgreSQL is the primary database.

Reasons:

* Relational data support
* Strong consistency
* Transactions
* Mature ecosystem
* Excellent support for complex relationships
* pgvector support

---

# 13. Main Database Entities

```text
User
Role
Profile
Skill
Experience
Education
Certification
Portfolio

Organization

Job
Application

Project
Proposal
Contract
Milestone

ServiceCategory
Service
ServiceRequest
Booking

Review
Rating

Conversation
Message
Notification

Recommendation
AIRequest
AIResult
```

---

# 14. Database Relationship

```text
User
 │
 ├── Profile
 │    ├── Skills
 │    ├── Experience
 │    ├── Education
 │    ├── Certifications
 │    └── Portfolio
 │
 ├── Job Applications
 │
 ├── Proposals
 │
 ├── Bookings
 │
 ├── Reviews
 │
 └── Messages
```

Marketplace:

```text
Organization
      │
      ▼
     Job
      │
      ▼
Application
      │
      ▼
    Hiring
```

Freelancing:

```text
Client
  │
  ▼
Project
  │
  ▼
Proposal
  │
  ▼
Contract
  │
  ▼
Milestone
```

Local services:

```text
Customer
   │
   ▼
Service Request
   │
   ▼
Provider
   │
   ▼
Booking
```

---

# 15. Prisma ORM

Use Prisma for database access.

Responsibilities:

* Database schema
* Migrations
* Queries
* Relationships
* Type-safe database access

Example:

```text
backend/prisma/
├── schema.prisma
└── migrations/
```

---

# 16. pgvector

Use PostgreSQL + pgvector for semantic search.

Provider:

```text
Profile
   ↓
Skills + Experience + Portfolio
   ↓
Text Representation
   ↓
Embedding
   ↓
Vector
```

Opportunity:

```text
Job / Project / Service Request
   ↓
Requirement Text
   ↓
Embedding
   ↓
Vector
```

Then:

```text
Opportunity Vector
        ↓
Similarity Search
        ↓
Potential Providers
```

This avoids introducing another database just for vector search in the MVP.

---

# 17. Redis

Use Redis for:

* Caching
* Temporary data
* Rate limiting
* Session-related data if needed
* Background jobs
* Frequently accessed recommendations

Redis is **not** the primary database.

---

# 18. Real-Time Communication

Use **Socket.IO** for:

* Chat
* Online status
* Real-time notifications
* Message delivery
* Booking updates where required

Architecture:

```text
User A
  │
  ▼
Socket.IO
  │
  ▼
NestJS
  │
  ▼
Socket.IO
  │
  ▼
User B
```

Messages should still be persisted in PostgreSQL.

---

# 19. AI Technology Stack

The AI service is separate from NestJS.

## Python

Use Python because it has a strong NLP/ML ecosystem.

## FastAPI

FastAPI exposes AI functionality as APIs.

Example:

```text
POST /ai/extract-requirements

POST /ai/parse-cv

POST /ai/embed

POST /ai/match

POST /ai/recommend

POST /ai/explain
```

---

# 20. AI Architecture

```text
                     USER REQUIREMENT
                            │
                            ▼
                    Requirement Parser
                            │
              ┌─────────────┼─────────────┐
              ▼             ▼             ▼
           Skills       Experience     Location
              │             │             │
              └─────────────┼─────────────┘
                            ▼
                       Embedding
                            │
                            ▼
                    Semantic Search
                            │
                            ▼
                  Candidate Providers
                            │
                            ▼
                     Ranking Engine
                            │
                            ▼
                  Explainable Results
```

---

# 21. Sentence Transformers

Use Sentence Transformers for semantic embeddings.

Main purpose:

```text
Text
 ↓
Embedding Vector
 ↓
Similarity Comparison
```

Example:

```text
"Flutter mobile developer"

and

"Experienced Dart developer building
Android and iOS applications"

```

Keyword matching may see limited overlap.

Semantic embeddings can identify that the concepts are related.

---

# 22. Transformers

Use the Transformers ecosystem where appropriate for:

* NLP
* Text classification
* Information extraction
* Multilingual processing
* Future AI features

Do not introduce large models unnecessarily.

The MVP should prioritize:

```text
Reliable
Fast
Affordable
Explainable
```

over unnecessarily complicated models.

---

# 23. scikit-learn

Use scikit-learn for:

* Similarity calculations
* Ranking experiments
* Classification experiments
* Evaluation metrics
* Baseline algorithms

Especially important for the university research component.

---

# 24. AI Matching Algorithm

The initial algorithm should combine multiple factors.

Example:

```text
Final Match Score =

0.35 × Skill Match
+
0.20 × Experience Match
+
0.15 × Semantic Similarity
+
0.10 × Availability
+
0.08 × Location
+
0.07 × Reputation
+
0.05 × Budget
```

The exact weights must be experimentally evaluated rather than claimed to be optimal.

---

# 25. Explainable Recommendation

The system should return not only:

```text
Match = 94%
```

but also:

```text
Why recommended?

✓ 5 required skills matched
✓ Relevant experience
✓ Similar portfolio projects
✓ Available during requested period
✓ Within requested budget
✓ Strong reputation
```

This becomes an important differentiating feature of the project.

---

# 26. CV Processing

Use:

## PyMuPDF

For:

```text
PDF CV
 ↓
Text extraction
```

## python-docx

For:

```text
DOCX CV
 ↓
Text extraction
```

Then:

```text
CV
 ↓
Text
 ↓
AI extraction
 ↓
Skills
Experience
Education
Projects
Certificates
Languages
 ↓
Profile
```

---

# 27. Maps & Location

Use:

```text
OpenStreetMap
+
Leaflet
```

For:

* Provider location
* Service areas
* Nearby providers
* Map visualization
* Location-based search

The MVP should avoid unnecessary complexity such as building its own mapping infrastructure.

---

# 28. File Storage

User-uploaded files may include:

```text
CV
Portfolio documents
Certificates
Project files
Service images
Profile images
```

The application should use object/file storage rather than storing large files directly inside PostgreSQL.

Recommended architecture:

```text
Frontend
   │
   ▼
Backend
   │
   ▼
Object Storage
   │
   ├── CV
   ├── Images
   ├── Certificates
   └── Project Files
```

For the university prototype, storage can be local during development and switched to an S3-compatible service for deployment.

---

# 29. Authentication

Use:

```text
JWT
+
Refresh Token
+
Password Hashing
+
Role-Based Access Control
```

Example roles:

```text
ADMIN
USER
JOB_SEEKER
FREELANCER
CLIENT
SERVICE_PROVIDER
ORGANIZATION
```

A single account may eventually have multiple capabilities.

---

# 30. Authorization

NestJS guards should protect sensitive resources.

Example:

```text
POST /jobs
```

Only authorized organization/client accounts.

```text
POST /jobs/:id/apply
```

Only eligible job seekers.

```text
POST /services/:id/book
```

Only authenticated customers.

```text
/admin/users
```

Only administrators.

---

# 31. Testing Stack

## Frontend

```text
Jest
React Testing Library
Playwright
```

## Backend

```text
Jest
Supertest
```

## AI

```text
Pytest
scikit-learn evaluation
```

## End-to-End

```text
Playwright
```

---

# 32. Testing Pyramid

```text
                 E2E
                /   \
               /     \
          Integration
             /     \
            /       \
        Unit Tests
```

Most tests should be unit/integration tests.

E2E tests should cover critical workflows.

---

# 33. Docker

Use Docker for consistent development.

Containers:

```text
frontend
backend
ai-service
postgres
redis
```

Development:

```text
docker compose up
```

This allows all four remote developers to use approximately the same environment.

---

# 34. GitHub

Use GitHub for:

* Source control
* Pull requests
* Issues
* Project management
* Code review
* CI/CD
* Documentation

Branch structure:

```text
main
│
└── develop
     │
     ├── feature/frontend/*
     ├── feature/backend/*
     ├── feature/ai/*
     └── feature/devops/*
```

---

# 35. GitHub Actions

CI should automatically run:

```text
Push / Pull Request
        │
        ▼
Install Dependencies
        │
        ▼
Lint
        │
        ▼
Unit Tests
        │
        ▼
Integration Tests
        │
        ▼
Build
        │
        ▼
Docker Build
```

A PR should not be merged when required CI checks fail.

---

# 36. Nginx

For deployment:

```text
Internet
   │
   ▼
 Nginx
   │
   ├── Frontend
   │
   ├── Backend
   │
   └── AI Service
```

Nginx can provide:

* Reverse proxy
* HTTPS termination
* Request routing
* Basic security configuration

---

# 37. Deployment Architecture

```text
                         INTERNET
                            │
                            ▼
                         NGINX
                            │
             ┌──────────────┼──────────────┐
             ▼              ▼              ▼
          Frontend       Backend       AI Service
          Next.js        NestJS        FastAPI
                            │
                 ┌──────────┴──────────┐
                 ▼                     ▼
             PostgreSQL              Redis
             + pgvector
```

---

# 38. Environment Structure

## Development

```text
.env.local
```

## Staging

```text
.env.staging
```

## Production

```text
.env.production
```

Never commit secrets.

Use:

```text
.env.example
```

for required variable names.

---

# 39. Environment Variables

Example:

```text
DATABASE_URL=
JWT_SECRET=
JWT_REFRESH_SECRET=

REDIS_URL=

AI_SERVICE_URL=

STORAGE_ENDPOINT=
STORAGE_ACCESS_KEY=
STORAGE_SECRET_KEY=
STORAGE_BUCKET=

NEXT_PUBLIC_API_URL=
```

Never commit actual credentials to GitHub.

---

# 40. Recommended Project Structure

```text
project-root/
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── features/
│   ├── hooks/
│   ├── lib/
│   ├── services/
│   └── types/
│
├── backend/
│   ├── src/
│   │   ├── auth/
│   │   ├── users/
│   │   ├── profiles/
│   │   ├── jobs/
│   │   ├── applications/
│   │   ├── projects/
│   │   ├── proposals/
│   │   ├── contracts/
│   │   ├── milestones/
│   │   ├── services/
│   │   ├── bookings/
│   │   ├── reviews/
│   │   ├── messaging/
│   │   ├── notifications/
│   │   ├── recommendations/
│   │   └── admin/
│   ├── prisma/
│   └── test/
│
├── ai-service/
│   ├── app/
│   │   ├── api/
│   │   ├── models/
│   │   ├── services/
│   │   ├── embeddings/
│   │   ├── matching/
│   │   ├── extraction/
│   │   └── evaluation/
│   ├── tests/
│   └── requirements.txt
│
├── database/
│
├── docs/
│
├── tests/
│
├── docker/
│
├── .github/
│   └── workflows/
│
├── docker-compose.yml
├── README.md
├── Roadmap.md
├── Todo.md
├── TECH_STACK.md
└── .gitignore
```

---

# 41. Developer Technology Ownership

## Developer 1 — Frontend

Primary technologies:

```text
Next.js
React
TypeScript
Tailwind CSS
shadcn/ui
React Hook Form
Zod
Playwright
```

Primary responsibility:

```text
User Experience
Web Interface
Dashboards
Search
Recommendations
Messaging UI
```

---

# 42. Developer 2 — Backend

Primary technologies:

```text
NestJS
TypeScript
Prisma
PostgreSQL
REST
Swagger/OpenAPI
Socket.IO
JWT
```

Primary responsibility:

```text
Business Logic
API
Database
Authentication
Authorization
Marketplace
Transactions
```

---

# 43. Developer 3 — AI

Primary technologies:

```text
Python
FastAPI
Sentence Transformers
Transformers
scikit-learn
PyMuPDF
python-docx
pgvector
Pytest
```

Primary responsibility:

```text
NLP
CV Processing
Embeddings
Semantic Search
Matching
Ranking
Explainability
AI Evaluation
```

---

# 44. Developer 4 — DevOps / QA

Primary technologies:

```text
Docker
Docker Compose
GitHub Actions
Linux
Nginx
GitHub
Playwright
Jest
Supertest
Pytest
```

Primary responsibility:

```text
CI/CD
Testing
Security
Deployment
Monitoring
Integration
Code Quality
```

---

# 45. Technology Decision Rules

The team should follow these rules.

## Rule 1

Do not introduce a new technology unless there is a clear reason.

## Rule 2

Prefer technologies already used by another team member.

## Rule 3

Do not use multiple technologies for the same responsibility.

Bad:

```text
PostgreSQL
MongoDB
MySQL
```

Good:

```text
PostgreSQL
```

for the main database.

## Rule 4

Do not create a separate microservice unless it provides a clear benefit.

The AI service is separated because AI development has different requirements from the main application.

## Rule 5

Keep the MVP manageable.

---

# 46. MVP Technology Scope

The minimum stack required for the first working version is:

```text
Next.js
React
TypeScript
Tailwind CSS

NestJS
Prisma

PostgreSQL
pgvector

Python
FastAPI
Sentence Transformers
scikit-learn

Docker
GitHub
GitHub Actions

Jest
Pytest
Playwright
```

The following can be added later:

```text
Redis
Socket.IO
Maps
Object Storage
Advanced NLP
Multilingual AI
```

---

# 47. Technology Development Order

```text
                    PHASE 1
               Project Foundation
                      │
                      ▼
             Next.js + NestJS
                      │
                      ▼
               PostgreSQL
                      │
                      ▼
               Authentication
                      │
                      ▼
             Profiles + Marketplace
                      │
                      ▼
                  Search
                      │
                      ▼
                    AI
                      │
                      ▼
             Semantic Matching
                      │
                      ▼
             Recommendations
                      │
                      ▼
               Explainability
                      │
                      ▼
                 Messaging
                      │
                      ▼
                  Testing
                      │
                      ▼
                Deployment
```

---

# 48. Final Technology Stack

```text
FRONTEND
────────────────────────
Next.js
React
TypeScript
Tailwind CSS
shadcn/ui
React Hook Form
Zod

BACKEND
────────────────────────
NestJS
TypeScript
REST
Swagger/OpenAPI
Socket.IO
JWT

DATABASE
────────────────────────
PostgreSQL
Prisma
pgvector

AI
────────────────────────
Python
FastAPI
Sentence Transformers
Transformers
scikit-learn
PyMuPDF
python-docx

INFRASTRUCTURE
────────────────────────
Docker
Docker Compose
Nginx
Linux

DEVOPS
────────────────────────
Git
GitHub
GitHub Actions

TESTING
────────────────────────
Jest
React Testing Library
Supertest
Pytest
Playwright

LOCATION
────────────────────────
OpenStreetMap
Leaflet
```

---

# 49. Relationship With Roadmap.md

The technology stack maps directly to the project roadmap.

| Roadmap Area    | Main Technology                          |
| --------------- | ---------------------------------------- |
| Authentication  | NestJS + JWT + PostgreSQL                |
| Profiles        | Next.js + NestJS + Prisma                |
| Employment      | Next.js + NestJS + PostgreSQL            |
| Freelancing     | Next.js + NestJS + PostgreSQL            |
| Local Services  | Next.js + NestJS + PostgreSQL            |
| Search          | PostgreSQL + pgvector                    |
| AI Matching     | Python + FastAPI + Sentence Transformers |
| CV Intelligence | Python + PyMuPDF + Transformers          |
| Recommendations | AI Service + pgvector                    |
| Messaging       | NestJS + Socket.IO + Redis               |
| Reviews         | PostgreSQL + Prisma                      |
| Admin           | Next.js + NestJS                         |
| Testing         | Jest + Pytest + Playwright               |
| Deployment      | Docker + Nginx + Linux                   |
| CI/CD           | GitHub Actions                           |

---

# 50. Relationship With Todo.md

Every technology must have an owner.

```text
DEV 1
│
├── Next.js
├── React
├── TypeScript
├── Tailwind
├── shadcn/ui
├── Forms
└── Frontend Testing

DEV 2
│
├── NestJS
├── Prisma
├── PostgreSQL
├── REST API
├── Swagger
├── JWT
└── Socket.IO

DEV 3
│
├── Python
├── FastAPI
├── Sentence Transformers
├── Transformers
├── scikit-learn
├── pgvector
├── CV Processing
└── AI Evaluation

DEV 4
│
├── Docker
├── GitHub Actions
├── Linux
├── Nginx
├── Security
├── Integration Testing
└── Deployment
```

---

# 51. Final Architecture Principle

The project should remain:

```text
Simple enough to finish
+
Advanced enough to demonstrate innovation
+
Modular enough for 4 developers
+
Measurable enough for academic evaluation
```

The core academic contribution should be:

```text
Traditional Keyword Matching
             VS
AI Semantic + Multi-Factor Matching
             │
             ▼
     Experimental Evaluation
             │
             ▼
     Measurable Improvement
```

This allows the project to be evaluated not only as a software application, but also as an **AI-supported software engineering research project**.

# END OF TECH_STACK.md
