
```yaml
networks:
   proxy:
     external: true
     
services:
  pocket-id:
    image: ghcr.io/pocket-id/pocket-id:v1
    restart: unless-stopped
    env_file: .env
    networks:
      - proxy
    ports:
      - 1411:1411
    volumes:
      - "${APPDATA_DIR}/pocket-id/data:/app/data"
      - "${APPDATA_DIR}/pocket-id/secrets:/secrets/"
    # Optional healthcheck
    healthcheck:
      test: [ "CMD", "/app/pocket-id", "healthcheck" ]
      interval: 1m30s
      timeout: 5s
      retries: 2
      start_period: 10s
    labels:
      traefik.enable: true
      traefik.http.routers.pocket-id.entrypoints: https
      traefik.http.routers.pocket-id.rule: Host(`id.${DOMAIN_BASE_URL}`)
```