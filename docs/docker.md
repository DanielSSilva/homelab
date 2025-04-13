---
title: Docker
---

# Docker

This page documents my Docker setup, which is used to run many of the services in my homelab.

## Overview

Docker is a platform for developing, shipping, and running applications in containers. This page details how Docker is configured and used in my homelab.

## Installation

- **Installation Method**: [How Docker was installed]
- **Version**: [Docker version in use]
- **Host System**: [Where Docker is running (Unraid, direct on host, etc.)]

## Docker Network Configuration

| Network Name | Purpose | IP Range | Connected Services |
|--------------|---------|----------|-------------------|
| bridge | Default Docker network | 172.17.0.0/16 | [Services] |
| [custom_network] | [Purpose] | [IP Range] | [Services] |

## Volume Management

| Volume Name | Purpose | Host Path | Backup Strategy |
|-------------|---------|-----------|----------------|
| [volume_name] | [Purpose] | [Host path] | [How it's backed up] |

## Container Organization

I organize my Docker containers using:
- [Docker Compose/Portainer/Other tools]
- Directory structure for compose files
- Image versioning strategy

## Key Containers

| Container | Image | Ports | Volumes | Purpose |
|-----------|-------|-------|---------|---------|
| [container_1] | [image:tag] | [port mappings] | [volumes] | [purpose] |
| [container_2] | [image:tag] | [port mappings] | [volumes] | [purpose] |

## Example Docker Compose

```yaml
# Example compose file structure
version: '3'
services:
  service-name:
    image: image:tag
    container_name: container-name
    ports:
      - "host:container"
    volumes:
      - /host/path:/container/path
    environment:
      - VARIABLE=value
    restart: unless-stopped
    networks:
      - network-name
```

## Resource Limits

How container resources are managed:
- CPU limits
- Memory constraints
- Restart policies

## Management Interfaces

| Tool | Purpose | Access URL | Notes |
|------|---------|------------|-------|
| Portainer | Container management | [URL] | [Notes] |
| [Other tools] | [Purpose] | [URL] | [Notes] |

## Maintenance Procedures

- Image update strategy
- Container health checks
- Log management
- Pruning unused images/volumes