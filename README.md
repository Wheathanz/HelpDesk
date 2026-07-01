# Enterprise Helpdesk Infrastructure Architecture

A secure, high-availability hybrid-cloud helpdesk deployment leveraging containerized orchestration and zero-trust network topology. 

## Architectural Overview
This system architecture separates compute and routing layers to optimize system overhead while enforcing strict network security:
* **Compute Layer:** Hosted on a scalable **Microsoft Azure Virtual Machine (Ubuntu)** running microservices orchestrated via **Docker Compose**.
* **Access Control & Routing:** Secured via a private **Tailscale Mesh VPN** overlay and a localized **Caddy Reverse Proxy**, preventing exposure of any public-facing inbound ports to the open internet.
* **Data Persistence:** Managed via decoupled Docker Volumes connected to an isolated **PostgreSQL** relational database.

## System Stack
* **Deployment:** Docker, Docker Compose
* **Cloud Infrastructure:** Microsoft Azure (IaaS Compute)
* **Networking:** Tailscale VPN, Caddy Proxy
* **Database & ORM:** PostgreSQL, Prisma ORM

## Deployment Configuration
1. Clone this repository.
2. Replicate the configuration matrix:
   ```bash
   cp .env.example .env
