# Apache Guacamole Docker Stack

A production-ready Docker Compose stack for deploying **Apache Guacamole** with **PostgreSQL** authentication and the **guacd** protocol proxy.

## Prerequisites

* [Docker](https://docs.docker.com/get-docker/)
* [Docker Compose](https://docs.docker.com/compose/install/) (v2.0+)
* Bash shell environment (Git Bash, WSL, or Linux/macOS terminal)

---

## Getting Started

### 1. Configure Environment Variables

Copy the example configuration file and set your secure database credentials:

```bash
cp .env.example .env

### 2. Initialize the Database Schema
Run init-db.sh to extract the default PostgreSQL schema from the Guacamole image into an initdb.sql file:

```bash
chmod +x init-db.sh
./init-db.sh

or if you're on Windows:

```PowerShell

docker run --rm guacamole/guacamole /opt/guacamole/bin/initdb.sh --postgres > initdb.sql

### 3. Start the Stack
Launch all services in detached mode:

```bash
docker compose up -d

### 4. Access Guacamole
Navigate to the web application in your browser:
URL: `http://localhost:8080/guacamole/`
Default Username: `guacadmin`
Default Password: `guacadmin`
