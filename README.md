# Docker Lab: Containerizing a Three-Tier Application
**INET 4031 - Introductions to Systems**

This lab introduces Docker and Docker Compose by having you containerize a
real, multi-service application. You will package three components: Apache,
Flask, and MariaDB. These will be packaged into separate containers and wired together so they function as a complete application.

The application code and scaffolding are provided. Your job is to complete the Dockerfiles, verify the stack runs correctly, and document your work below.

> **Directions and explanations for this lab are on the repository Wiki.**
> Refer to the Wiki pages for step-by-step instructions.

---


---

# Project Overview
This project demonstrates how to containerize a three-tier application using Docker and Docker Compose. The application consists of three services: Apache (web server), Flask (backend API), and MariaDB (database). Each service runs in its own container and communicates through Docker’s internal network.

# Prerequisites
To run this project, you need:
- Ubuntu Virtual Machine
- Docker installed
- Docker Compose installed
- Git installed
- VirtualBox or another VM platform

# Getting Started
1. Clone the repository:

2. Build and start the containers:
docker compose up --build

3. Verify containers are running:
docker compose ps

# Configuration
This application uses environment variables stored in the `.env` file, including the database name, user, and password. These values are used by both the Flask application and the MariaDB service to establish a connection between them.

All services are defined in the `docker-compose.yml` file. The `db` service runs MariaDB, the `app` service runs the Flask backend, and the `web` service runs Apache as the frontend. Docker Compose allows these services to communicate with each other through an internal network.

# Verification
To verify the application is working:

1. Open the web app:
http://localhost:8080

2. Check API health:
curl http://localhost:80/health

3. Expected output:
{"database": "connected", "status": "healthy"}

4. Run the check script:
./check-lab.sh

All checks should pass successfully.


