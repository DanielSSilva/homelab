---
title: Traefik
tags:
  - service
  - reverse-proxy
  - custom-server
status: active
---

# Traefik

Traefik is a reverse proxy and load balancer running on the custom server. It is used to manage and route traffic to various services in the homelab.

## Docker Compose Configuration

```yaml
version: '3'
services:
  traefik:
    image: traefik
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./traefik-config:/etc/traefik
    restart: unless-stopped
```

## Notes

- Traefik is configured to handle SSL termination and route traffic based on domain names.
- The `traefik-config` directory contains the configuration files for Traefik.
