# Homelab / Self-Hosted Infrastructure

**Timeframe:** 2024 – Present  
**Environment:** Ubuntu Server, Docker, Docker Compose  
**Scope:** Personal production-style homelab for systems administration, networking, and security practice

---

## Objective

Design, deploy, and maintain a **production-like self-hosted infrastructure** to gain hands-on experience with Linux system administration, containerization, service orchestration, networking, and security hardening. This homelab serves as a continuous learning environment for testing real-world scenarios such as service outages, backups, updates, and incident recovery.

---

## Infrastructure Overview

- Dedicated Linux server running **Ubuntu Server**
- Acts as a centralized host for multiple self-hosted services
- Designed for **24/7 uptime** with minimal manual intervention
- Emphasizes reliability, maintainability, and security over experimentation-only setups

---

## Architecture & Design

- **Host OS:** Ubuntu Server (headless)
- **Container Runtime:** Docker
- **Service Orchestration:** Docker Compose
- **Networking:**
  - Docker bridge networks for service isolation
  - Internal-only networking for backend services
  - Explicit port mappings only where external access is required
- **Storage:**
  - Bind-mounted persistent volumes for application data
  - Separation of configuration and data directories
  - Designed to survive container rebuilds and host reboots
- **Scalability:**
  - Modular Docker Compose stacks
  - Easy addition or removal of services without impacting others

---

## Services Deployed

### Core Services
- **Nextcloud**
  - Self-hosted file storage and collaboration platform
  - Used for file uploads, synchronization, and user management
  - Persistent storage and configuration directories
- **Uptime Kuma**
  - Monitors internal and external services
  - Provides uptime tracking, response-time metrics, and alerts
  - Used to quickly identify service outages or performance degradation
- **Heimdall**
  - Web-based dashboard for centralized access to all internal services
  - Improves usability and service discovery within the homelab

### Supporting Services
- Databases (e.g., MySQL/MariaDB containers) for application backends
- DNS and networking utilities
- Backup and monitoring integrations
- Utility containers for maintenance and administration tasks

---

## Networking & Access Control

- Internal services are **not publicly exposed** unless explicitly required
- Port forwarding restricted to specific services and ports
- Separation between frontend and backend services
- Designed to reduce attack surface while maintaining usability
- Remote access handled securely rather than blanket exposure

---

## Security Considerations

- Followed **least-privilege principles** across containers and services
- Avoided unnecessary Docker capabilities and privileged containers
- Strong authentication enforced on all exposed services
- Regularly applied:
  - OS updates
  - Docker image updates
  - Dependency and application updates
- Firewall rules enforced at the host level
- Configuration files and credentials stored securely
- No hard-coded secrets committed to version-controlled files

---

## Maintenance & Operations

- Routine service restarts and updates using Docker Compose
- Log inspection for troubleshooting and performance monitoring
- Health checks via Uptime Kuma to verify service availability
- Documented service configurations and deployment steps
- Incremental improvements made over time as new requirements emerged

---

## Troubleshooting & Lessons Learned

- Diagnosed and resolved container networking issues
- Addressed volume permission and ownership problems
- Debugged service startup failures and port conflicts
- Learned to balance convenience with security in self-hosted setups
- Gained experience handling real downtime and recovery scenarios

---

## Outcomes & Skills Gained

- Stronger understanding of:
  - Linux server administration
  - Docker networking and storage
  - Multi-service orchestration with Docker Compose
- Real-world experience maintaining long-running services
- Improved documentation and reproducibility practices
- Increased confidence managing infrastructure similar to small production environments
- Practical foundation for cybersecurity, DevOps, and system administration roles

---

## Future Improvements

- Expanded monitoring and alerting integrations
- Enhanced backup and disaster recovery workflows
- Network segmentation and VLAN experimentation
- Increased automation using scripts and scheduled tasks
- Continued security hardening and performance optimization
