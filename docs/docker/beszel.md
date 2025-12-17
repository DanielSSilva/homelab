# Beszel 

## What is it?

_Simple, lightweight server monitoring with Docker stats, historical data, and alerts._

&emsp;&emsp;\- [Source](https://www.beszel.dev/)

This contains two components:

- **Beszel Server**: The backend server that collects and stores monitoring data.

- **Beszel Agent**: A lightweight agent that runs on each monitored host to collect system metrics.

## Docker Compose

```yaml
networks:
  proxy:
    external: true
    name: proxy
services:
  beszel:
    image: henrygd/beszel:latest
    container_name: beszel
    restart: unless-stopped
    networks:
      - proxy
    volumes:
      - ${APPDATA_DIR}/beszel/data:/beszel_data
      - ${APPDATA_DIR}/beszel/socket:/beszel_socket
    labels:
      - traefik.enable=true
      - traefik.http.routers.beszel.rule=Host(`monitoring.${DOMAIN_BASE_URL}`)
      - traefik.http.routers.beszel.entryPoints=https
  beszel-agent:
    image: henrygd/beszel-agent:latest
    container_name: beszel-agent
    restart: unless-stopped
    networks:
      - proxy
    volumes:
      - ${APPDATA_DIR}/beszel/socket:/beszel_socket
      - /mnt/disk2:/extra-filesystems/disk2:ro
      - /mnt/cache:/extra-filesystems/cache:ro
    environment:
      DOCKER_HOST: tcp://dockersocket:2375
      LISTEN: /beszel_socket/beszel.sock
      KEY: ${BESZEL_AGENT_KEY}
```

## .env
```env
BESZEL_AGENT_KEY=ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAICv...
```

## References
- [Official Website](https://www.beszel.dev/)
- [Documentation](https://www.beszel.dev/guide/getting-started)
- [GitHub Repository](https://github.com/henrygd/beszel)