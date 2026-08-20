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