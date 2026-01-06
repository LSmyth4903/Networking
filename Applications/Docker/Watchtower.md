# Watchtower – Docker Installation Guide

## Overview

Watchtower automatically checks for new container images, pulls updates, gracefully restarts containers with the same configuration, and cleans up old images. This ensures your services are always up to date without manual intervention.

---

## Why This Service Belongs in Docker

Watchtower is best run as a Docker container because it communicates directly with the Docker daemon to manage other containers. Running it in a VM or Proxmox container adds unnecessary overhead and complexity without providing any benefit. Docker provides a lightweight, isolated, and native environment for Watchtower to operate efficiently.

---

## Prerequisites

* Linux host with Docker installed
* Docker Compose plugin available (`docker compose`)
* User has permission to access Docker (or run as root)

Verify:

```bash
docker --version
docker compose version
```

---

## Create Project Directory

```bash
mkdir -p ~/watchtower
cd ~/watchtower
```

---

## Docker Compose Configuration

Create the compose file:

```bash
nano docker-compose.yml
```

Paste:

```yaml
version: "3.8"

services:
  watchtower:
    image: containrrr/watchtower
    container_name: watchtower
    restart: unless-stopped
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    command: >
      --schedule "0 0 4 * * *"
      --cleanup
      --label-enable
    environment:
      - TZ=Europe/London
```

---

## Enable Updates on Containers

For any container you want Watchtower to update, add this label:

```yaml
labels:
  - "com.centurylinklabs.watchtower.enable=true"
```

Containers without this label will be ignored.

---

## Start Watchtower

```bash
docker compose up -d
```

Verify:

```bash
docker ps
docker logs watchtower
```

---

## Manual Update Run (Optional)

To force an immediate update check:

```bash
docker run --rm \
  -v /var/run/docker.sock:/var/run/docker.sock \
  containrrr/watchtower --run-once
```

---

## Common Issues

### Docker command not found

Docker is not installed or not in PATH.

Install Docker (Debian/Ubuntu):

```bash
apt update
apt install -y docker.io docker-compose-plugin
```

### Permission denied on Docker socket

Add user to docker group:

```bash
usermod -aG docker $USER
logout
```

---

