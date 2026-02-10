# Nexus Repository Manager – Docker Setup

## Project Overview
This project provides a simple and repeatable way to run **Nexus Repository Manager 3** using Docker.
It is intended for DevOps practice, local testing, and learning artifact repository management.

## Why This Project
Manual Nexus installation is error-prone and time-consuming.
Using Docker ensures:
- Fast setup
- Clean environment
- Easy restart and removal
- Persistent data using volumes

## What This Project Does
- Runs Nexus Repository Manager in a Docker container
- Exposes Nexus on port 8081
- Persists repository data using Docker volumes

## Prerequisites
- Docker installed
- Port 8081 available

## How to Run
```bash
docker volume create nexus-data

docker run -d \
--name nexus \
-p 8081:8081 \
-v nexus-data:/nexus-data \
--restart unless-stopped \
sonatype/nexus3

Access Nexus
http://localhost:8081

Admin Credentials
docker exec -it nexus cat /nexus-data/admin.password


Username: admin

Password: output of above command

