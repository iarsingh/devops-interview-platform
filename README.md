# DevOps Interview Platform

<!-- project-guide:start -->
## Project guide

[Project architecture](PROJECT_ARCHITECTURE.md) · [Interview questions and answers](INTERVIEW_QA.md)

Use the architecture document for the component diagram, implementation boundaries, and verification entry points. The interview guide includes source-backed answers and project walkthroughs.

### Implementation map

| Component | Responsibility |
| --- | --- |
| [`backend/requirements.txt`](backend/requirements.txt) | Implementation or supporting configuration |
| [`backend/app/__init__.py`](backend/app/__init__.py) | Implementation or supporting configuration |
| [`backend/app/main.py`](backend/app/main.py) | Implementation or supporting configuration |
| [`backend/app/api/__init__.py`](backend/app/api/__init__.py) | Implementation or supporting configuration |
| [`backend/app/api/dependencies.py`](backend/app/api/dependencies.py) | Implementation or supporting configuration |
| [`backend/app/core/config.py`](backend/app/core/config.py) | Implementation or supporting configuration |
| [`backend/app/core/exceptions.py`](backend/app/core/exceptions.py) | Implementation or supporting configuration |
| [`backend/app/core/logging.py`](backend/app/core/logging.py) | Implementation or supporting configuration |
| [`backend/app/core/security.py`](backend/app/core/security.py) | Implementation or supporting configuration |
| [`backend/Dockerfile`](backend/Dockerfile) | Container build/service configuration |
| [`backend/pyproject.toml`](backend/pyproject.toml) | Implementation or supporting configuration |
| [`docker-compose.yml`](docker-compose.yml) | Container build/service configuration |
| [`frontend/Dockerfile`](frontend/Dockerfile) | User interface code/assets |
| [`README.md`](README.md) | Project explanations or operating notes |
| [`backend/README.md`](backend/README.md) | Project explanations or operating notes |
| [`docs/architecture/HLD.md`](docs/architecture/HLD.md) | Project explanations or operating notes |

### Local setup and verification

From the repository root (the commands follow the checked-in manifests):

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r backend/requirements.txt
```

<!-- project-guide:end -->

<!-- repository-summary -->
A full-stack interview preparation platform covering DevOps, cloud, Kubernetes, backend engineering, DSA, and system design.
<!-- /repository-summary -->

DevOps Interview Platform

A production-style full-stack learning and interview preparation platform built primarily as a 15-day backend, DevOps, cloud, Kubernetes, DSA and system-design revision project.

Objectives

This project is designed to revise and demonstrate:

* Python
* FastAPI
* REST API development
* PostgreSQL
* Redis
* Authentication and authorization
* JavaScript/TypeScript
* Docker
* Kubernetes
* GKE
* Helm
* Terraform
* Google Cloud Platform
* CI/CD
* GitHub Actions
* GitOps
* Prometheus
* Grafana
* OpenTelemetry
* DevSecOps
* Linux
* Git
* DSA
* System Design

Application Features

Users can:

* Register and log in
* Browse interview questions
* Filter questions by technology and difficulty
* Submit answers
* Track interview attempts
* Receive scores
* View progress
* View leaderboard data

Administrators can:

* Create questions
* Update questions
* Delete questions
* Manage question categories

High-Level Architecture

User
 |
 v
Frontend
 |
 v
Load Balancer
 |
 v
Cloud Armor
 |
 v
GKE Ingress
 |
 +--------------------+
 |                    |
Frontend            Backend
Service             FastAPI
                      |
             +--------+--------+
             |                 |
         PostgreSQL           Redis
         Cloud SQL            Cache

Infrastructure

Infrastructure is provisioned using Terraform.

Resources include:

* VPC
* Subnets
* Cloud NAT
* GKE
* Cloud SQL
* Memorystore/Redis
* Artifact Registry
* IAM
* GCS
* Monitoring

CI/CD

Git Push
   |
   v
GitHub Actions
   |
   +--> Lint
   +--> Unit Tests
   +--> Security Scan
   +--> Docker Build
   +--> Image Scan
   +--> Artifact Registry
   |
   v
Helm / GitOps
   |
   v
GKE

Observability

The application uses:

* Prometheus
* Grafana
* OpenTelemetry
* Google Cloud Logging

Repository Structure

backend/
frontend/
infrastructure/
kubernetes/
helm/
monitoring/
scripts/
dsa/
docs/
.github/

15-Day Plan

Daily revision notes and implementation tasks are available under:

docs/daily/

Local Development

Backend:

cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload

Frontend:

cd frontend
npm install
npm run dev

Docker:

docker compose up --build

Tests

cd backend
pytest

Terraform

cd infrastructure/environments/dev
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply

Kubernetes

kubectl apply -f kubernetes/

Helm

helm upgrade --install interview-platform \
helm/interview-platform \
-f helm/interview-platform/values-dev.yaml

Project Goal

At the end of the project, the application should be deployable from source code to GKE using an automated CI/CD pipeline with infrastructure provisioned using Terraform and full application monitoring enabled.

## Documentation checks

Project guides and local source links are checked on pushes and pull requests. Run locally:

```bash
python3 .github/scripts/validate_project_docs.py
```
